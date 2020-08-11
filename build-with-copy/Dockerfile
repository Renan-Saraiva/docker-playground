FROM nginx:latest

LABEL maintainer 'Renan Saraiva <renan.m.saraiva@gmail.com>'

RUN echo '<h1>Sem conteudo</h1>' > /usr/share/nginx/html/conteudo.html

COPY *.html /usr/share/nginx/html/

#docker image build -t build-with-copy .
#docker container run -p 90:80 build-with-copy