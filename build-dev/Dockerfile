FROM python:3.6

RUN useradd www && \
    mkdir /app && \
    mkdir /log && \
    chown www /log

USER www
VOLUME /log 
WORKDIR  /app
EXPOSE 8000

ENTRYPOINT ["/usr/local/bin/python"]
CMD ["run.py"]


#Colocar oq não muda com frequencia no inicio do arquivo faz com que o docker consiga usar o cache de dessas layers
#docker container run -it -v C:\Working\docker-playground\build-dev:/app -p 90:8000 --name python-server ex-build-dev


#Conseguimos usar  o volume de outro container atraves do comando 'volumes-from=python-server'
#docker container run -it --volumes-from=python-server debian cat /log/http-server.log

#podemos criar uma tag de uma imagen usando o comando 'docker tag nome-da-imagem nome-da-tag'