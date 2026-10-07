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
L'image c'est le modèle reproductible de l'environnement, celle-ci contient l'environnement d'excécution de base et les dépendance, mais ne contient pas l'application. Le conteneur quand à lui, est l'appplication en exécution dans cette environnement.

# Etape 4

- Pourquoi Docker Compose est préférable au lancement manuel de plusieurs conteneurs ?
Docker compose est préférable étant donnée que celui-ci permet d'automatiser le lancement de plusieurs conteneur, permet de faire en sorte de lancé des centaine de conteneur en 1 fois sans avoir à tapper des centaine de commande pour les lancé un par un (mannuellement). Il permet également de pouvoir lier tous les conteneur dans un seul et même réseau et de les retirer de la liste des conteneur.

- Quel est le rôle du fichier "docker-compose.yml" ?
Ce fichier sert à donnée comme information à docker composer quel sont les différent service composant l'application ainsi que leur localisation, permettant à celui-ci de les trouver et de pouvoir lire leur dockerfile afin de pouvoir créer les conteneur et les lancé. Il permet également de spécifier sur quel port d'entré lancé les conteneurs et les redirection à effectuer, afin par exemple de pouvoir intéragir avec ceux-ci depuis la machine.

- Dans quels cas Docker compose pourrait-il ses limites ?
Une limite de Docker compose est que celui-ci s'exécute sur une seul machine, ainsi si celui-ci tombe en panne ou que la machine qui le maintient tombe en panne, tous les conteneur de celui-ci seront affecter. L'application entière pourrait cessez de fonctionner. (Il est impossible de répartir les conteneur sur différent serveur et de tous les lancé avec le même docker compose.)

