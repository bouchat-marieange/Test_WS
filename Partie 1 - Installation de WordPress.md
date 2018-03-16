# Partie 1 : Installation de WordPress

## Pré-requis

Dans le cadre de ce WorKshop nous développeront un site WordPress en local (sur votre ordinateur) afin d'en tester les différentes fonctionnalités.

Pour déployer votre site WordPress sur un serveur en ligne, vous pouvez vous référer a la partie "Annexes" de ce document qui vous explique la marche à suivre.

Pour installer WordPress vous avez besoin de :
* Le fichier zip télécharger sur le site wordpress.org reprenant tous les fichiers et dossiers composant la dernière version de WordPress

* Un serveur web ou logiciel permettant de créer un serveur web et DB sur votre ordinateur (mamp, xampp, lamp)

* Une base de données vide au départ (MySQL)

* Un logiciel FTP qui permet de transférer les fichiers de votre ordinateur vers votre serveur en ligne.

Le logiciel FTP est nécessaire uniquement lorsque vous mettrez votre site en ligne. Pour ce workshop nous développerons en local. Vous trouverez la procédure pour mettre votre site en ligne dans la partie contenant les annexes.

## Création de la DB avec phpMyAdmin

* Lancer votre serveur Apache (Lamp, Xampp, Wamp)

* Pour lamp taper dans la console : sudo /opt/lampp/lampp start

* Dans le navigateur aller à l'adresse : http://localhost/phpmyadmin/

* Passer la langue en Français

* Utilisateur: root

* Mot de passe: vide, root, user, autres ....

Veuillez à bien connaitre votre nom d'utilisateur et mot de passe pour PhpMyAdmin pour pouvoir créer une base de données et vous connecter à celle-ci.

Une fois dans phpMyAdmin, aller sur l'onglet "Bases de données", indiqué le nom de votre base de données. Pour l'exercice, nous l'appellerons "wp_workshop" puis cliquer sur le bouton "créer".


![creation db](images/install_wp_creation_db.jpg)


Une nouvelle base de données apparait dans la liste de gauche.
Lors de l'installation de WordPress, toutes les tables nécessaires au fonctionnement de WordPress viendront se placer dans cette base de données que nous avons préalablement crée.


**La base de données après l'installation de WordPress :**


![db apres install WP](images/install_wp_DB_apres_install_WP.jpg)


## Téléchargement WordPress et installation en local


Site: https://fr.wordpress.org/ (version de l'interface en français ou anglais)

Site: https://wordpress.org/ (site avec interface en anglais - attention format date)


**Site WordPress.org en français**


![fr.wordPress.org](images/install_wp_wordpress-org-fr.jpg)


**Site WordPress.org en anglais**


![wordPress.org](images/install_wp_wordpress-org.jpg)


Attention : Ne confondez pas wordpress.org avec les sites https://fr.wordpress.com ou https://wordpress.com qui proposent une formule d'hébergement intégrée et gratuite de votre site WordPress mais dont les fonctionnalités, la possibilité de personnalisation, l'espace des stockage sont nettement plus limitée que celles de la version complète de WordPress. Nous allons donc nous intéresser à WordPress.org car qui peut le plus peut le moins. Libre à vous ensuite de choisir une formule plutôt que l'autre selon vos besoins en étant bien informé.

Pour en savoir plus sur la différence entre WordPress.org et WordPress.com :

* https://wpformation.com/wordpress-com-vs-wordpress-org-quelle-difference/

* https://wpmarmite.com/wordpress-com-ou-wordpress-org/


Dans la barre de menu, cliquer sur le bouton "Download WordPress", puis sur la nouvelle page qui s'ouvre cliquer sur "Download WordPress 4.9.4" (ou la dernière version disponible). Un fichier zip est télécharger sur votre ordinateur. Il contient tous le CMS WordPress de base.


![Decompress wordpress](images/install_wp_decompresse_wordpress.jpg)


Décompresser ce fichier zip et placer le dossier wordpress dans le répertoire utiliser par votre serveur local (www, html, ... ).

![WordPress dans dossier local](images/install_wp_wordpress_dossier_html.jpg)

Nous allons à présent renommé ce dossier wordpress et nous allons l'appeller "wp_workshop".


![Renommer dossier wp_workshop](images/install_wp_renomme_wp_workshop.jpg)


A ce stade, nous avons donc un dossier wp_workshop (contenant tous les dossiers et fichiers de WordPress) dans le repertoire de notre serveur local et un base de donnée appellée wp_workshop vide crée dans phpmyAdmin. Nous pouvons passé à l'installation de WordPress.

Aller à l'adresse localhost (localhost:8888 pour Mac utilisant Mamp) sur votre navigateur et cliquer sur le votre dossier wp_workshop. L'installation de wordpress se lance.


![Lancement installation WP à partir localhost](images/install_wp_lancement_install_wp_localhost.jpg)



![Installation WP - etape 1](images/install_wp_1.jpg)


Dans l'écran suivant on vous demande d'indiquer différentes informations, remplisser le nom de votre DB soit wp_workshop, votre nom d'utilisateur et votre mot de passe sur phpmyadmin, laisser localhost dans le champ suivant et afin d'améliorer la sécurité nous allons changer le préfixe qui sera ajouté à toutes les tables wordpress dans la DB par work_ à la place du wp_ par défault.


![Installation WP - etape 2](images/install_wp_2.jpg)


A ce stade il peut arriver qu'une erreur survienne, pas de panique. Cela signifie juste que WordPress n'arrive pas à créer automatiquement le fichier wp-config.php. POur le créer manuellement, il vous suffit de copier le code se trouvant dans la fenêtre (Ctrl+A puis Ctrl+C), de créer un nouveau fichier appelé wp-config.php à la racine du repertoire wp_workshop, d'y coller le contenu du code et de l'enregister.


![WP erreur création auto de wp-config.php - etape 3](images/install_wp_3_erreur.jpgg)


![Creation wp-config](images/install_wp_creation_wp_config.jpg)


Puis de cliquer sur le bouton "Lancer l'installation"


Dans la fenêtre suivante on vous demande de renseigner les information concernant votre site et le nom d'utilisateur et le mot de passe que vous utiliserait pour vous connecter à sa partie backend.

Pour le titre de site indiqué par exemple: WordPress Workshop


Username : admin (pour l'exercice laisser admin mais pour un site réel, je vous conseille de le changer, ce sera encore possible par après).


WordPress génère un mot de passe sécurisé par défaut contenant des majuscules, minuscules et caractères spéciaux, vous pouvez garder celui qui a été générer aléatoirement pour votre site ou utiliser un site du type https://www.motdepasse.xyz/ pour en générer un sur mesure. Veillez à ce qu'il affiche un niveau de sécurité Strong.


**Attention:** A cette étape, faites bien en copier-coller de votre mot de passe dans un fichier ou noter le sur un morceau de papier car sans ces informations vous ne pourrez pas vous connecter à l'interface d'administration de votre site.


Indiquer votre adresse mail et ne cocher pas la mention "Discourage search engines from indexing this site", car nous voulons que les moteurs de recherche indexe notre site.


Cliquer sur le bouton "Install WordPress".


![WordPress Bienvenue](images/install_wp_wordpress-bienvenue.jpg)


Success ! Voilà votre site WordPress est installé en local sur votre ordinateur. Cliquez sur le bouton "Se connecter" pour vous connecter au backend de votre site.


![Installation succes](images/install_wp_success.jpg)


**Remarque:**

A ce stade, si on se rend dans phpmyAdmin (localhost/phpmyadmin) on peut constater que toutes les tables de WordPress (précédée du suffixe personnalisé work_ que nous avions indiqué )ont bien été placées lors de l'installation de WordPress dans la base de données vide que nous avions précédemment créée.


![DB après install WP](images/install_wp_DB_apres_install_WP.jpg)


![Login WP](images/install_wp_login.jpg)


Vous arriver sur la page de login de votre site. C'est à cet endroit que vous vous connecter avec le backend avec le nom d'utilisateur (admin) et le mot de passe que vous avez noter à l'étape de Bienvenue de WordPress (et que vous avez noté et conservé précieusement).

Vous pouvez voir que l'url de votre site actuellement sur votre ordinateur en local est :

http://localhost/wp_workshop/wp-login.php

c'est cette adresse que vous devrez taper pour vous connecter à votre site en local dorénavant.


(L'adresse sera différente lorsque votre site sera installé sur un serveur en ligne et non en local, elle dépendra du nom de domaine que vous avez choisi ex: http://www.monsupersite.be/)et pour accéder au login du backend http://www.monsupersite.be/wp-admin, mais nous verrons tout à l'heure qu'il est préférable de changer ce wp-admin commun à tous les sites wordpress par soucis de sécurité.

Nous allons à présent pouvoir passer à la seconde partie de ce workshop l'exploration des bases de WordPress.
