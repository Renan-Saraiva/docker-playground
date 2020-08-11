* Podemos criar containers que não tem acesso a internet e nem a outros containers do host, usando o comando '--net none'
* docker network ls (Lista as redes atuais do docker)
* o docker criar uma subnet para subir os containers em um host (modo de rede bridge, no modo host ele usa a mesma interface de rede do host)
* podemos criar redes diferentes, e podemos bloquear que um container não acesse outro container de outra rede
* podemos configurar que um container pode ter acesso a N redes atraves do comando 'docker network connect nome-rede nome-container' (podemos disconetar tbm)
* dentro do compose podemos acessar os outros container usando o nome do serviço (http://app:9090)
* No docker compose podemos inicializar somente um serviço, caso esse serviço depende de outro, podemos indicar isso atraves do depends_on
* Podemos escalar um unico serviço de uma composição usando o comando 'docker-compose up -d --scale worker=3' (--scale nome_do_servico=número_de_instancias)
* Podemos definir as variaveis de ambiente em um arquivo isolado, e referenciar o mesmo dentro do nosso arquivo docker-compose.yml

#docker container run -d --name container1 alpine sleep 1000
#docker container exec -it container1 ifconfig
#docker container exec -it container2 ping 172.17.0.3
#docker-compose exec db psql -U postgres -d email_sender -c "select * from emails"