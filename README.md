## Executando em ambiente Linux
- Antes de executar o docker-compose up, crie a rede `observability` com o comando
~~~shell
docker network create observability 
~~~

- Também é necessário criar a pasta elasticsearch_data no fc2-observabilidade-elastic na máquina local manualmente para evitar erro de permissionamento
~~~shell
mkdir elasticsearch_data
~~~

- Execute também o seguinte comando:
~~~shell
sudo chown root beats/metric/metricbeat.yml
~~~

- Suba os containers com o comando:
~~~shell
docker compose up -d
~~~

- Após terminar de subir os containers, acesse http://localhost:5601/

- Caso ocorra o erro `bootstrap check failure [1] of [1]: max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]`, execute o comando: 
~~~shell
sysctl -w vm.max_map_count=262144
~~~
