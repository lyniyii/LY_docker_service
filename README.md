# Rappel

Minikube est une version de Docker

Kubernetes a trois fonctions : 
- déploiement d'applications encapsulée dans des images Docker dans un cluster de machines où est installé dans le kubernetes :
    (mécanique de virtualisation, seul logciel utile pour exécuter les images -> Cloud native) 
	déploiement des images dans les pods
- maintien des applications en fonctionnement -> redémarrage automatique des applications en échec
- scalling d'application -> augmation ou diminution du nombre d'instances de la même image Docker 
	L'intérêt de faire du scalling ? 
		- tolérance aux pannes
		- répartition des charges : load balancing

Tous les clouds utilisent Kubernetes. 

Code app < image docler < processus kubernetes pods (adresse IP éphémère) < logique : deployement 
Service est séparé du pods dont l'adresse IP est fixe -> suit les changements/évolution d'IP du pods

Il y a quatre types de service :
- load balancer
- défaut (Node Port)
- external name (pour avoir un nom de domaine)
- cluster IP (adresse interne au cluster)

# Cluster IP

Comment connaître l'adresse d'un service ? 
Dans tous les services il y a un Domain Name Service

[schéma]
app front < image front < pod front -> app back < image back < pod back
service front					service back
