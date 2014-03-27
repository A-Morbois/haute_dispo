haute_dispo
===========

Rendu projet haute disponibilité
-------------------------------

BUT:

Le but de ce projet est de rendre "invisible" les mises à jours d'un wordpress.
Autrement dit il faut que le site soit accessible sans interruption.


MARCHE A SUIVRE:

Dans un terminal cloner le projet à l'endroit souhaiter:

 /*  on clone le projet sur son pc puis on va dans le dossier téléchargé */
 
	git clone https://github.com/A-Morbois/haute_dispo

	cd haute_dispo/
	
/* on créer la VM grâce au Vagrantfile puis on s'y connecte en ssh  */

	vagrant up 

	vagrant ssh

/* on construit ensuite les "docks" qui servirons de serveur pour le wordpress */

	cd haute_dispo_dockerfile/

	docker build -t  equilibre  nginx/
	

/* une fois build, on les démarre */

	docker run -d -p 80:80 equilibre 
	
