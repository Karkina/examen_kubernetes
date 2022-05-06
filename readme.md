# Rapport d'examen

#### Nom pods et services de la base : redis-nico
#### Nom pods serveur web : nicoredisweb

## La première étape a été de créer la base de donne redis dans mon conteneur :

#### Pour cela j'ai crée un fichier .yaml pour mon service qui sera relié au pod avec le port de base de redis (6379), le fichier est nico_soum_deployement. Cependant j'ai eu un problème tout le long de ma création de pod et de service car j'ai utilisé "kind: Deployment" qui je pense a buggé pour un seul réplicat.

#### Puis j'ai crée mes pods du service web grâce au fichier nico_soum_pod.yaml. Pour pouvoir faire la connection avec la base de donnée redis, j'ai récupéré l'adresse ip de mon cluster grâce :

```
kubectl get services
```

#### Ce qui m'a permis de le mettre dans la valeur d'env '- name: REDIS_URL'
