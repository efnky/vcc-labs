# Etape 1

- Qu'est-ce qu'une machine virtuelle:  
C'est une machine avec un OS précis pouvant être différent ou non de l'OS de la machine hôte (ici la machine physique) tournant sur la machine physique grace à un hyperviseur et permettant de mutualiser et virtualiser les ressources de la machine hôte. Elle permet de créer un espace isolé de la machine hôte avec son propre OS, environnement de travail, gestionnaire de fichier.

- 2 Avantage de la virtualisation dans un environnement professionnel:
	- Créer un environnement de travail isolé et précis afin de pouvoir tester du codes ou des applications.
	- Avoir un environnement de travail reproductive grâce à IaC.
	- La mise en place d'une plus grande sécurité par exemple dans le cas de l'utilisation d'une application en micro-service, ou dans le Cloud, chaque VM étant isolé des autres, si une vulnérabilité touche une machine virtuelle et un service sur l'une de celle-ci, les autres ne sont pas impacter par cette vulnérabilité.

- Différence entre travailler directement sur la machine physique et dans un environnement virtuelle:
La machine physique est plus rapide que la machine virtuelle, étant donnée que la machine virtuelle, utilise les ressource de la machine physique unique quand celle-ci sont disponible et le chemin d'accès au ressource est plus long sur la machine virtuelle devant passer par son OS, l'hyperviseur puis l'OS de la machine hôte avant d'avoir accès au ressource. Si il y a une panne sur la machine virtuelle, il n'y aura aucune incidence sur la machine physique. La possibilité d'utiliser un environnement de travail précis même si celui-ci est incompatible avec la machine hôte.


