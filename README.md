---------------------------------------------
SITE WEB DE NEWS COMPLET EN PHP ORIENTÉ OBJET
---------------------------------------------

A propos
--------

Ceci est un site web de news complet construit grace au cours "Programmez en orienté objet en PHP" de OpenClassrooms. On y trouve la structure MVC, les modules frontend et backend ...

J'ai pas mis le système de mise en cache mais vous pouvez vous inspirer du video tutoriel "Créer un système de Cache en PHP" de Grafikart.fr.


Configuration
-------------

Sur un serveur local, vous devez configurer Virtual Host :

Sous Linux (XAMPP) :
 - Éditez le fichier /etc/hosts
 - Ajouter "127.0.0.1 monsupersite" après la ligne "127.0.0.1 localhost"
 - Décommentez (enlevez le # avant) "Include etc/extra/httpd-vhosts.conf" dans le fichier /opt/lampp/etc/httpd.conf

Sous Windows (WAMP) :
 - Éditez le fichier C:\windows\system32\drivers\etc\hosts
 - Ajoutez "127.0.0.1 monsupersite"
 - Décommentez "Include conf/extra/httpd-vhosts.conf" dans le fichier C:\wamp\bin\apache\apacheX.X.X\conf\httpd.conf

Sous Mac OS (MAMP) :
 - Je ne sais pas le faire :P

Maintenant, il faut que vhosts pointe vers le dossier Web de l'application, pour celà :
 - Ajouter dans le fichier /opt/lampp/etc/extra/httpd-vhosts.conf(sous Linux) ou C:\wamp\bin\apache\apacheX.X.X\conf\extra\httpd-vhosts.conf(sous Windows) ce qui suit :
 <VirtualHost *:80>
 	ServerAdmin admin@localhost
 	ServerName monsupersite
 	DocumentRoot /opt/lampp/htdocs/monsupersite/Web #Sous Linux
 	DocumentRoot "c:/wamp/www/monsupersite/Web" #Sous Windows
 	<Directory /opt/lampp/htdocs/monsupersite/Web>
 		Options Indexes FollowSymLinks MultiViews
 		AllowOverride #Permet d'activer les .htaccess.
 		deny from all
 		allow from localhost
 	</Directory>
 </VirtualHost>

Si vous avez un problème pour accéder à l'url http://localhost par la suite : créez-en aussi un Virtual Host pour localhost qui pointe vers votre dossier /opt/lampp/htdocs ou C:\wamp\www

Maintenant il ne vous reste plus qu'à : 
 - Cloner monsupersite dans votre dossier htdocs ou www selon votre OS
 - Créer une base de données "news" et importer les deux fichiers sql dans le dossier /bdd
 - Tapez http://monsupersite

Dérnière chose :
 - Pour accéder à la page d'administration, allez dans l'url http://monsupersite/admin/
 - Entrez admin comme Pseudo et mdp comme Mot de passe ;)