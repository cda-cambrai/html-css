# Hébergement

Un site web doit être accessible 24h/24. Pour cela, on doit héberger le site sur un serveur.
La plupart du temps, on accède à un site web via un nom de domaine, par exemple https://boxydev.com

http:// ou https:// est un protocole permettant de communiquer avec le serveur, on appelle cela un serveur web.

Le nom de domaine est payant et dépend d'une autorité (AFNIC pour le .fr par exemple). C'est un abonnement annuel à renouveller tous les ans à vie. Le tarif est d'environ 10 euros pour une année sur un .fr mais le prix peut varier pour d'autres domaines de premier niveau (.com, .it, .de, .voyage, .paris).

Je vous conseille :
- matthieu-mota.fr
- mota-matthieu.fr
- matthieumota.fr
- motamatthieu.fr
- anass.fr

Pas de majuscule, pas de caractères spéciaux sauf le tiret, pas de point.

Le nom de domaine correspond à une adresse IP (d'un serveur). On peut trouver l'adresse IP d'un domaine avec la commande ping. Le ping est le temps de réponse entre la requête au serveur et la réponse qu'il donne.

Le temps de réponse d'un serveur (que ce soit un ping ou une page html) est très important pour notre site. Pour "augmenter" la rapidité de chargement, on peut optimiser les images, héberger ses vidéos sur Youtube (Plus performant qu'un mp4).

Le domaine seul ne suffit pas à héberger le site web, il doit être associé à un hébergement. Il existe plusieurs types d'hébergements :

### Hébergement mutualisé

Cet hébergement est le moins coûteux et le plus facile à mettre en oeuvre techniquement. C'est un fournisseur qui s'occupe du serveur et il vous donne juste un accès FTP (Pour envoyer les fichiers de votre site) et une ou plusieurs bases de données.

Je vous recommande cette solution pour démarrer.

### VPS

Le VPS (Virtual Private Server) est un serveur virtuel situé sur un serveur physique. Il y a plusieurs VPS sur un serveur. L'avantage de cette solution est que vous pouvez installer ce que vous voulez sur ce serveur (même un serveur de jeu) mais c'est à vous de le faire. C'est un métier différent de développeur mais fortement lié, administrateur système. Aujourd'hui, un développeur qui sait faire cela est appelé "DevOps". Il est nécessaire de bien connaitre la couche OSI de l'informatique ainsi que l'OS Linux. Il faut bien entendu être à l'aise avec la ligne de commande car il n'y a pas d'écran sur un serveur.

### Serveur dédié

C'est un serveur physique. Il présente les mêmes caractéristiques qu'un VPS mais c'est vous qui êtes maître du serveur.

### Cloud

Le cloud comme le propose Scaleway ou Digital Ocean, c'est le fait de pouvoir créer plusieurs VPS à la volée en quelques secondes pour faire des tests et les arrêter n'importe quand. On paye donc la consommation à l'heure et non au mois.

## Envoyer les fichiers

Pour envoyer vos fichiers HTML et CSS, vous devez vous munir de vos accès FTP :

Hôte: marko.m2i.boxydev.com
Login: marko
Mot de passe: Envoyé en MP sur Discord

Attention, vous devez remplacer matthieu par votre prénom. Il est nécessaire d'installer un logiciel comme Cyberduck ou Filezilla pour envoyer vos fichiers sur le serveur.

Sur Cyberduck, on peut cliquer sur "Ouvrir une connexion".

Quand on veut éditer un fichier et que VS Code n'apparait pas. On peut aller dans Edition > Préférences > Editeur et choisir VS code.

Pour trouver VS Code, on peut noter %APPDATA% dans l'explorateur de fichier pour le trouver (le dossier AppData) ou C:\Users\Administrateur\AppData\Local\Programs\Microsoft VS Code

Pour protéger certains dossiers sur notre serveur (comme le .git par exemple), on peut créer un fichier .htaccess à la racine du site avec ce contenu :

```
# On indique au serveur web que personne ne pourra accèder à une URL qui commence
# par /.git
RedirectMatch 404 /\.git
```

## Balises Open Graph

Les balises Open Graph permettent de gérer la mise en forme de notre site quand on le partage sur Facebook, Linkedin, Discord... Exemple de mise en place des balises Open Graph :

```html
<meta name="description" content="Freelance web. Expert PHP, Symfony, Angular. Conseil, intégration, développement web, architecture logicielle et système.">
<meta name="keywords" content="site internet, web, application web, développement, hébergement web, développement web, symfony, wordpress, magento, prestashop, intégration web">
<meta name="author" content="Matthieu Mota">
<meta property="og:site_name" content="Matthieu Mota">
<meta property="og:title" content="Matthieu Mota - Consultant &amp; Expert web - Lens, Lille">
<meta property="og:description" content="Freelance web. Expert PHP, Symfony, Angular. Conseil, intégration, développement web, architecture logicielle et système.">
<meta property="og:image" content="https://www.gravatar.com/avatar/5355a3882df0fdd7689f8b0b5dc50720?s=200&d=identicon">
<meta property="og:url" content="/">
```

## Certificat SSL et HTTPS

Gratuit avec lets encrypt. Il faut forcément le faire via l'hébergeur.

## Petit portfolio

Sur notre hébergement, nous allons envoyé notre portfolio (10-bootstrap). Il faudra ajouter tous les projets qu'on a fait jusque là :

- La liste de Fiorella
- Le jeu du taquin
- La maquette du réseau social

On doit bien avoir une modal pour chaque projet où on voit un screenshot du projet puis un lien pour voir le projet. Le lien sera donc sur http://matthieu.m2i.boxydev.com/jeu-du-taquin ou http://matthieu.m2i.boxydev.com/reseau-social par exemple.
