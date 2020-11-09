# TP8
## Première partie
Voici le docker-compose.yml que  j'ai fait pour le TP8 :
```
version: "3.8"

services:
  mariadb:
    image: mariadb:latest
    hostname: mariadb
    ports:
      - 3306
    environment:
      MYSQL_ROOT_PASSWORD: password
    volumes:
      - ./mariadb:/var/lib/mysql
      - ./scripts:/docker-entrypoint-initdb.d
  prometheus:
    image: prom/prometheus:latest
    hostname: prometheus
    depends_on:
      - mysql-exporter
    ports:
      - 9090:9090
    volumes:
      - ./config/prometheus.yml:/etc/prometheus/prometheus.yml:ro
  mysql-exporter:
    image: prom/mysqld-exporter:latest
    hostname: mysql-exporter
    depends_on:
      - mariadb
    ports:
      - 9104:9104
    environment:
      DATA_SOURCE_NAME: "root:password@(mariadb:3306)/"
```
## Deuxième partie
Pour avoir sur le même graphique les opérations de lecture et d'écriture j'ai afficher le nombre de requete 'select' et 'insert' grace a l'opérateur "or"
![screen1.png](/home/nawak/Documents/ynov/admin_bdd/supervision/screen1.png)
Pour la seconde requête je n'ai pas compris votre demande d'afficher "la variation du taux d'opérations de lectures et d'écritures" j'ai donc afficher le nombre de requete "select" et "insert" dans un interval de temps de 5 minutes.

![screen2.png](/home/nawak/Documents/ynov/admin_bdd/supervision/screen2.png)

