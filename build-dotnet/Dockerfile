FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build-env
WORKDIR /app

# Copy csproj and restore as distinct layers
# Esses comanados são dados aqui para criar layers isoladas, para utilizar do aproveitamento de cache do docker
# ja que caso esses arquivos não tenham sofridos atualizações, os mesmo não serão executados novamente
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
#Esta copiando o resultado do build da imagem de build para a pasta definida como workdir desta imagem
COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "sample-api.dll"]


#docker build -t sample-api .
#docker run -d -p 8080:80 --name sample-api sample-api
