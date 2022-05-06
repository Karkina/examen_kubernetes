# Rapport d'examen

#### Nom pods et services de la base dans le dossier base : redis-nico 
#### Nom pods serveur web  dans le dossier site_web : nicoredisweb

## La première étape a été de créer la base de donne redis dans mon conteneur :

#### Pour cela j'ai crée un fichier .yaml pour mon service qui sera relié au pod avec le port de base de redis (6379), le fichier est nico_soum_deployement. Cependant j'ai eu un problème tout le long de ma création de pod et de service car j'ai utilisé "kind: Deployment" qui je pense a buggé pour un seul réplicat.

## La Deuxième étape a été de créer les pods du site web :
#### J'ai crée mes pods du service web grâce au fichier nico_soum_pod.yaml. Pour pouvoir faire la connection avec la base de donnée redis, j'ai récupéré l'adresse ip de mon cluster grâce :

```
kubectl get services
```

#### Ce qui m'a permis de le mettre dans la valeur d'env '- name: REDIS_URL avec le port 6379 a la fin'

#### Le problème de la connection avec redis et mon pod du serveur m'as pas permis de test la partie front, mais pour cette partie j'aurais crée un nouveau service qui gère la partie front puis j'aurais fais la connection avec les pods du serveur node-Redis.
