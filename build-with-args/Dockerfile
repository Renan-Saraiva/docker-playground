FROM debian
LABEL maintainer 'Renan Saraiva <renan.m.saraiva@gmail.com>'

#DEFINE ARGUMENTO POR PADRÃO O VALOR SERÁ FILES
ARG S3_BUCKET=files
ENV S3_BUCKET=${S3_BUCKET}

#comando para build
#docker image build -t build-with-args .

#comando para build com args
#docker image build --build-arg S3_BUCKET=myapp -t build-with-args . 

#Comando para imprimir variavel
#docker container run build-with-args bash -c "echo $S3_BUCKET" 

#Podemos filtrar o inspect usando o parametro --format