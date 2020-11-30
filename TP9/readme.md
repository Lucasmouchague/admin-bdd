# TP9
## Installation
Il suffit de cloner le projet et de demarrer le projet docker
```
git clone 
cd admin-bdd/TP9
docker-compose up -d
```
## Partie 1

![part1.png](https://raw.githubusercontent.com/Lucasmouchague/admin-bdd/main/TP9/screen/part1.png)
scrape duration : ```mysql_exporter_collector_duration_seconds{collector="collect.global_variables"}```


refused connection : ```mysql_global_status_access_denied_errors```


READ : ```mysql_global_status_innodb_data_reads```
## Partie 2
![part2.png](https://raw.githubusercontent.com/Lucasmouchague/admin-bdd/main/TP9/screen/part2.png)
Nombre de compte créée : ```SELECT created_at AS "time", id AS "id" FROM sylius_customer ORDER BY created_at```


Nombres d'utilisateurs : ```SELECT count(id) AS "id" FROM sylius_customer```


Paiements de la semaine dernière : ```select id from sylius_payment where created_at > '2019-11-24' and created_at < '2019-11-31'```


Sommes total des commandes : ```select created_at as "time", sum(amount) as "amount" from sylius_payment group by date(time)```
