# Etape 1

- Qu'est-ce qu'une machine virtuelle:  
C'est une machine avec un OS précis pouvant être différent ou non de l'OS de la machine hôte (ici la machine physique) tournant sur la machine physique grace à un hyperviseur et permettant de mutualiser et virtualiser les ressources de la machine hôte. Elle permet de créer un espace isolé de la machine hôte avec son propre OS, environnement de travail, gestionnaire de fichier.

- 2 Avantage de la virtualisation dans un environnement professionnel:
	- Créer un environnement de travail isolé et précis afin de pouvoir tester du codes ou des applications.
	- Avoir un environnement de travail reproductive grâce à IaC.
	- La mise en place d'une plus grande sécurité par exemple dans le cas de l'utilisation d'une application en micro-service, ou dans le Cloud, chaque VM étant isolé des autres, si une vulnérabilité touche une machine virtuelle et un service sur l'une de celle-ci, les autres ne sont pas impacter par cette vulnérabilité.

- Différence entre travailler directement sur la machine physique et dans un environnement virtuelle:

