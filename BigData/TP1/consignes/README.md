- ouvrir un terminal dans le contexte "BigData/TP1/dev" et lancer la commande :

../consignes/master.sh

- faire pareil à chaque fois dans un terminal différent pour slave1.sh, slave2.sh, et slave3.sh

A cette étape on a 4 conteneur qui sont démarrés. mais ils forment pas encore un cluster car il n y a aucune communication entre les conteneurs.

Les conteneurs sont lancés tous à partir de la même image donc ils ont tous le même contenu, il n y a pas encore concrétement une différence entre un master et un slave. 

- inspecter les fichiers suivants :
  - /hadoop/etc/hadoop/core-site.xml
  - /hadoop/etc/hadoop/hdfs-site.xml
  - /hadoop/etc/hadoop/slaves
  - /etc/environment
  - /etc/hosts

le système de fichiers distribué de hadoop est spécial c'est un format différent de stockage. pour qu'il fonctionne correctement sur votre système d'exploitation il faut mettre un espace de stockage au bon format pour acceullir les données au format hdfs. cette mise au bon format s'appelle formatage. 

dans le terminal du master, lorsque le conteneur est bien démarré, lancer la commande se trouvant dans le fichier format.sh : 

`hdfs namenode -format`

maintenant que le formatage est effectué, il est possible de démarrer un master et ensuite intégrer des esclaves au cluster du master.

- dans le terminal master lancer la commande start_master, puis lancer la commande jps pour s'assurer qu'il y a deux services master (namdenode et ressourcemanager) qui s'exécutent.
- dans le terminal de chaque esclave lancer la commande start_slave, puis lancer la commande jps pour s'assurer qu'il y a deux services slave (datanode et nodemanager) qui s'exécutent.
- dans le terminal master observez les messages informatifs qui s'affichent, notamment la détection des esclaves qui rejoignent le cluster. 

L'outil hadoop propose des interface graphique de monitoring accessible via le navigateur : 

- dans votre navigateur accéder à l'adresse localhost:8088 c'est l'adresse de monitoring de yarn
- dans votre navigateur accéder à l'adresse localhost:9780 c'est l'adresse de monitoring de hdfs
