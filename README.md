# Netdata && Prometheus
# 

> BOULOGNE Nathan
> M1 Infra Cloud Sécurité



**Installer et configurer Netdata**

- Installer le paquet netdata

`sudo apt install netdata`

- Configurer netdata pour pouvoir accéder au dashboard depuis l’ip du serveur

```
sudo nano /etc/netdata/netdata.conf
```
![](https://i.imgur.com/u0DhTg4.png)


- Redémarrer le service netdata

```
sudo systemctl restart netdata
```

- Accéder à l’interface web depuis l’ip du serveur http://<IP>:19999

![](https://i.imgur.com/2mPrujw.png)
    

**Analyser la portée fonctionnelle de l’outil**
    
- L’outil permet d’avoir une visualisation globale et/ou détaillée sur l’utilisation des ressources du serveur.

```
CPU
RAM
Disques
Réseaux
…
```
    
- Les métriques s’affichent en temps réel dans le dashboard et nous pouvons visualiser des métriques spécifiques en les sélectionnants

![](https://i.imgur.com/Z1LR2ne.png)
![](https://i.imgur.com/DNRYGwk.png)

- Nous avons également la possibilité de voir l’utilisation des ressources par :


```
Applications
User group
User
```

- Nous avons la possibilité d’ajouter d’autres dashboards.

- Nous avons la possibilité d’ajouter des alarmes.

- Nous pouvons faire des imports et/ou exports de snapshots des dashboards.

- Nous pouvons faire une impression du dashboard sous format PDF par exemple.

- Nous pouvons mettre en pause la collecte des métriques et la relancer.


**Installer l’agent Prometheus et d’exposer les indicateurs du système d’exploitation et de la récupérer dans Zabbix à l’aide du modèle “Linux by Prom”**


- Installer l’agent prometheus

```
sudo apt install prometheus-node-exporter
```

- Créer un nouvel équipement qui utilisera le template Linux by Prom

![](https://i.imgur.com/hnn2FLc.png)

DNS zbx correspond à l’IP 127.0.0.1, configuré dans /etc/hosts


- les informations remontent correctement dans le dashboard Zabbix

![](https://i.imgur.com/R7mJJtz.png)
    

