# Etape 1

- Qu'est-ce qu'une machine virtuelle:  
C'est une machine avec un OS précis pouvant être différent ou non de l'OS de la machine hôte (ici la machine physique) tournant sur la machine physique grace à un hyperviseur et permettant de mutualiser et virtualiser les ressources de la machine hôte. Elle permet de créer un espace isolé de la machine hôte avec son propre OS, environnement de travail, gestionnaire de fichier.

- 2 Avantage de la virtualisation dans un environnement professionnel:
	- Créer un environnement de travail isolé et précis afin de pouvoir tester du codes ou des applications.
	- Avoir un environnement de travail reproductive grâce à IaC.
	- La mise en place d'une plus grande sécurité par exemple dans le cas de l'utilisation d'une application en micro-service, ou dans le Cloud, chaque VM étant isolé des autres, si une vulnérabilité touche une machine virtuelle et un service sur l'une de celle-ci, les autres ne sont pas impacter par cette vulnérabilité.

- Différence entre travailler directement sur la machine physique et dans un environnement virtuelle:
La machine physique est plus rapide que la machine virtuelle, étant donnée que la machine virtuelle, utilise les ressource de la machine physique unique quand celle-ci sont disponible et le chemin d'accès au ressource est plus long sur la machine virtuelle devant passer par son OS, l'hyperviseur puis l'OS de la machine hôte avant d'avoir accès au ressource. Si il y a une panne sur la machine virtuelle, il n'y aura aucune incidence sur la machine physique. La possibilité d'utiliser un environnement de travail précis même si celui-ci est incompatible avec la machine hôte.


# Etape 2

- Qu'est-ce qu'un conteneur Docker ?
Un conteneur Docker est une boîte contenant toutes les informations nécessaire au lancement d'une application: sont environnement d'exécution, ses dépendances, l'application en elle même, et est fortement dépendant de l'OS sur lequel celui-ci est créé et lancé. Il est également isolé de la machine hôte et à son propre réseau.

- Différence entre machine virtuelle et conteneur:
La machine virtuelle est une machine donc elle contient sont propre OS et peut-être exécuter sur n'importe quel machine physique alors que le conteneur lui est très dépendant de l'OS de la machine sur lequel il est créé, il est donc moins portable que la machine virtuelle. En terme de taille un conteneur est une application, de l'ordre de la centaine de mégo octets alors que la VM est une machine de l'ordre du Giga octets

- pourquoi les conteneur sont adapter au déploiement d'application dans le Cloud ?
Il sont adapter au déploiement d'application dans le Cloud étant donnée que si on déploie le conteneur dans une machine virtuelle avec le même OS que celui sur lequel le conteneur à été créé, on pourra lancé l'application/le conteneur sans avoir besoin d'avoir à d'installer sur cette machine l'environnement d'exécution et les dépendance nécessaire au lancement de l'application.

# Etape 3

- Pourquoi un Dockerfile est préférable à la configuration manuelle d'un conteneur ?
Il est bien plus simple et rapide de créé beaucooup de conteneur grace à un dockerfile, cela permet aussi de diminuer les erreur humaine. Cela permet de mettre en place une automatisation du déploiement et la possibilité de partager le conteneur très facilement en échangeant uniquement le dockerfile (possibilité de créer exactement le même coonteneur)

- Différence entre une image Docker et un conteneur Docker:

