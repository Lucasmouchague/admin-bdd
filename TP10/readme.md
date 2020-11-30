# TP10
## Installation
Il suffit de cloner le projet et de demarrer le projet docker
```
git clone 
cd admin-bdd/TP10
docker-compose up -d
```
## Configuration SMTP
Pour configurer le compte mail qui permettra d'envoyer les alertes par mail il faut configurer le fichier grafana.ini
```
#################################### SMTP / Emailing ##########################
[smtp]
enabled = true
host = smtp.gmail.com:587
user = {{Insert you gmail account here}}
# If the password contains # or ; you have to wrap it with triple quotes. Ex """#password;"""
password = {{Insert your password gmail account}}
;cert_file =
;key_file =
;skip_verify = false
from_address = admin@grafana.localhost
from_name = Grafana
# EHLO identity in SMTP dialog (defaults to instance_name)
;ehlo_identity = dashboard.example.com

[emails]
;welcome_email_on_sign_up = false
;templates_pattern = emails/*.html

```
## Configuration du canal d'alerte

![part1.png](/home/nawak/git/admin-bdd/TP10/screen/part1.png)
Ici je renseigne l'adresse mail a qui grafana va envoyer les alertes
## Configuration de l'alerte

![part2.png](/home/nawak/git/admin-bdd/TP10/screen/part2.png)
Ici je demande a grafana de m'envoyer une alerte si le nombre de connexion refusé après 5 minutes est supérieure a 10.
## Test de l'alerte

![part3.png](/home/nawak/git/admin-bdd/TP10/screen/part3.png)
On vois bien que grafana detecte l'alerte
![part4.png](/home/nawak/git/admin-bdd/TP10/screen/part4.png)
Et ici on vois le mail que j'ai reçu de grafana