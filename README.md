# API Avatar Habbo 

Les rétros Habbo restent globalement discrets par rapport aux avatars de leurs utilisateurs, rares sont ceux qui mettent en place des API pour pouvoir les récupérer de façon externe.

C'est pourquoi nous proposons cette solution.

## Pré-requis

- [PHP](http://php.net) >= 5.5
- [PDO](http://php.net/manual/fr/class.pdo.php)
- [GD](http://php.net/manual/fr/book.image.php)
- [MySQL](http://mysql.com)

Pour la première installation, vous nécessitez [Git](http://git-scm.com).

_Si vous ne disposez pas de git, installez-le de cette façon :_
```sh
$ sudo apt-get update
$ sudo apt-get install git
```

## Installation

L'installation est très simple et peut s'effectuer de plusieurs façons différentes.

### En utilisant git et le terminal

Vous avez juste à exécuter ces quelques commandes sur votre terminal.

```sh
$ git clone git@github.com:LeHabbo/avatar-api.git api
```

_Veuillez noter qu'ici, l'API sera installée dans le dossier `api`_.

**ATTENTION !** Asurrez-vous que le dossier dans lequel l'API est installée est accessible par le serveur web, afin de pouvoir y accéder via votre site.

### En téléchargeant le fichier

C'est une procédure un peu plus longue mais tout aussi simple.

1. **Téléchargez le fichier**
   
   ![Lien de téléchargement](https://puu.sh/s7i2z/368bac8c6b.png)

   Voici l'interface accessible en cliquant sur le bouton "Clone or download", sur laquelle est disponible le bouton "Download ZIP" qui vous permettra de le télécharger.
   
2. **Décompressez le fichier**
   
   **Windows :** Utilisez `WinZIP` ou `WinRAR` à cet effet.

   **Linux :** Utilisez `unzip` à cet effet.
   
    Pour l'installer, suivez cette commande :
    
    ```sh
    $ apt-get install unzip
    ```
    
    Pour décompresser un fichier, utilisez cette commande :
    
    ```sh
    $ unzip avatar-api-master.zip
    ```
    
    Le fichier doit être situé à sa destination finale.
    
    **ATTENTION !** Asurrez-vous que le dossier dans lequel l'API est installée est accessible par le serveur web, afin de pouvoir y accéder via votre site.

## Configuration

La configuration de l'API se fait de façon claire et simple.

### Vous utilisez déjà PDO

Dans ce cas, vous devrez inclure votre fichier d'initialisation dans le fichier de l'API.

1. Ouvrez le fichier `init.php`
2. Éditez le afin d'y ajouter cette ligne, en l'éditant en fonction de votre situation personnelle

   ```php
   require '../config.php';
   ```
3. Dans le fichier `avatar.php`, effectuez ces quelques modifications

   ```php
   $avatar = new Avatar($username, $action, $gesture, $format, $db);
   ```
   
   Dans cette ligne, remplacez `$db` par votre variable PDO, elle est nécessaire au bon fonctionnement de l'API.

### Vous n'utilisez pas encore PDO

Dans ce cas, suivez ces étapes :

1. Ouvrez le fichier `init.php`
2. Décommentez cette ligne et configurez-la

   ```php
    $db = new PDO('mysql:host=[IP de votre serveur];dbname=[base de données]', '[utilisateur]', '[mot de passe]');
    ```

## Utilisation

Son utilisation est également très simple puisque basée sur les générateurs officiels d'avatars.

1. Accédez à l'API via votre site

   ```
   http://votreretro.tld/api/avatar.php?username=[pseudo]
   ```
2. **OPTIONNEL :** Définissez le format désiré

   ```
   http://votreretro.tld/api/avatar.php?username=[pseudo]&format=[format]
   ```
   
   Les différents formats sont : `png, gif, json, xml`
3. Vous pouvez utiliser les arguments GET classiques

   ```
   http://votreretro.tld/api/avatar.php?username=[pseudo]&action=[action]&gesture=[gesture]
   ```
   
Vous pouvez désormais utiliser l'API en fonction de vos besoins et souhaits.

## Des problèmes ? Des questions ?

Vous pouvez nous demander de l'aide via les Issues GitHub, nous répondrons au plus vite à vos demandes.
Pour vos questions, vous pouvez nous contacter via notre email ou dans la section Issues également.

