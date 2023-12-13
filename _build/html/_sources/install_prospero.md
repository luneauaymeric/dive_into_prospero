
<style type="text/css">

entite{
  background-color: yellow;
}

qualite{
  background-color: pink;
}

marqueur{
  background-color: #33FFF0;
}

epreuve{
  background-color: #4cff33;
}

motoutil{
  background-color:  #ec7063 ;
}

table {
    border-collapse: separate;
    border-spacing: 5px;
  }

td{
    font-size:12pt;
    vertical-align: top;
    padding-left: 1;
    padding-right: 1;
  }

tr:hover {background-color: coral;}

</style>


# Télécharger et installer Prospéro

Pour télécharger Prospéro, se rendre à cette [adresse](http://prosperologie.org/?sit=dl)

## Windows

L'installation de Prospéro sur Windows ne devrait pas présenter de difficulté particulière. Il suffit de lancer le programme d'installation téléchargé et de suivre les instructions. Vous trouverez également une vidéo explicative [ici](https://webdiffusion.ehess.fr/permalink/v12618e7533d8ulkhh4y/) une vidéo explicative.



## Linux

Sur Linux et Mac, il faut au préalable installer une machine virtuelle qui "émulera" l'environnement windows.


```{warning}
Les instructions ci-dessous ont été testées sur une machine équipée Xubuntu 22.04.3 LTS (Jammy Jellyfish). Elles devraient donc fonctionner avec d'autres versions d'Ubuntu, ainsi que sur Debian, mais rien n'est garanti.

La version de Wine est wine-6.0.3 (Ubuntu 6.0.3~repack-1)

```

### Installer Wine sur Linux


1. Vérifier que l'architecture 32 bit est activée

- La plupart des logiciels Windows sont conçus pour une architecture 32 bits, du coup il faut vérifier qu'elle est installée dans votre machine;
- Pour ce faire:
    - ouvrez le terminal (Ctrl + Alt + T);
    - exécutez :   

    ```
    dpkg --print-architecture

    ```


  - la réponse doit être : "amd64"
  - pour voir si l'architecture 32 bit est installée, exécutez ensuite :

    ```
    dpkg --print-foreign-architectures
    ```

  - si la réponse est "i386", allez à l'étape 2 : "Ajouter le dépôt WineHQ"
  - Sinon, il faut exécuter:

    ```
    sudo dpkg --add-architecture i386
    ```

   - puis
    ```
    sudo apt update
    ```

2. Ajouter le dépôt WineHQ
  - Recherchez et installé la clé du dépôt, en exécutant:

    ```
    wget -nc https://dl.winehq.org/wine-builds/winehq.key
    ```

    - puis:

    ```
    sudo -H gpg -o /etc/apt/trusted.gpg.d/winehq.key.gpg --dearmor winehq.key
    ```

  - Ajoutez le dépôt (changez "jammy" pour le nom de votre distro):

    ```
    sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ jammy main'
    ```

  - Mettez à jour la base de données des paquets:

    ```
    sudo apt update
    ```

3. Vérifier que xterm est bien installée
  - Wine nécessite la bibliothèque xterm pour être installé
  - Vérifiez que xterm est installée:

  ```
  xterm -version
  ```

  - Si xterm n'est pas installée, exécutez:

  ```
  sudo apt install xterm
  ```

4. Procéder à l'installation de Wine
  - Exécutez:

  ```
  sudo apt install wine64 wine32
  ```

  - Vérifiez l'installation, en exécutant:

  ```
  wine --version
  ```

### Installer Prospéro avec wine

[https://www.zdnet.com/article/how-to-run-a-windows-app-on-linux-with-wine/](https://www.zdnet.com/article/how-to-run-a-windows-app-on-linux-with-wine/)
[https://help.ubuntu.com/community/Wine](https://help.ubuntu.com/community/Wine)

- Télécharger Prospéro dans le dossier de votre choix (exemple: /home/download)
- Ouvrir un terminal et aller dans le dossier utilisé à l'étape précédente

```
cd ./download
```

- Utiliser la commande ci-après pour exécuter le fichier d'installation:

```
wine setup-prospero-I-freeware.exe
```

Si l'application demande de sélectionner un dossier de direction, choisir de le placer sour "C:\Program Files".

### Lancer Prospéro avec wine

1. Depuis un terminal:

  - Utiliser la commande suivante (en supposant que l'executable de Prospéro s'appelle "prospero-I.exe") :

```
wine "/home/aymeric/.wine/drive_c/Program Files (x86)/Doxa/Prospéro-I/prospero-I.exe"
```

2. Créer un 'lanceur' sur le bureau:

 - Clique droit sur le bureau
 - Cliquer sur Créer un lanceur
 - Remplir les informations (choisir l'icone de votre choix)
 - à la ligne "Commande", écrire :

```
wine "/home/aymeric/.wine/drive_c/Program Files (x86)/Doxa/Prospéro-I/prospero-I.exe"
```


## macOS

```{warning}
Les instructions ci-dessous ont été élaborées de manière générique et non pas été testées sur une version spécifique de macOS. N'hésitez pas à nous faire des retours si vous rencontrez des problèmes et/ou des nouvelles solutions.

```

### Installer Wine

Comme pour les environnement Ubuntu, Debian et Fedora, il faut d'abord installer Wine dont l'exécutable pour macOS se trouve [ici](https://wiki.winehq.org/Download)


## Télécharger et installer PlayOnMac
- PlayOnMac est une interface graphique pour Wine
- Allez sur https://www.playonmac.com/fr/download.html.
- Choisissez bien l'option indiquée pour votre version de macOS.
- Une fois que le fichier dmg est téléchargé, il suffit de double-cliquer sur le disque et de glisser-déposer PlayOnMac dans le dossier application.
- [Cette page](https://wiki.playonlinux.com/index.php/Troubleshooting_Common_Problems), néanmoins plutôt centrée sur Linux, récense les problèmes les plus communs avec le logiciel. Si vous rencontrez un souci, vous pouvez aussi vous dirigez vers le [forum dédié](https://www.playonmac.com/fr/forums.html). En tout cas, n'hésitez pas à demander de l'aide.

## Installer Prospéro sur PlayOnMac
- Vous devez tout d'abord, si ce n'est déjà fait, télécharger Prospéro sur: http://prosperologie.org/?sit=dl (Il faudra s'inscrire);
- Ouvrez ensuite PlayOnMac;
  - Si c'est la première fois que vous la démarrez, l’application devrait télécharger XQuartz et l’installer. N'empêchez pas ce processus.
- Cliquez sur "Installer un logiciel";
- Puis sur "Installer une application non supportée" (en bas, à gauche);
- Dans la fenêtre "Que souhaitez-vous faire?", sélectionnez "Modifier une application existante" puis "Suivant";
- Dans la fenêtre "Quel est le préfixe de votre programme?", sélectionnez "playonmac" puis "Suivant";
- Dans la fenêtre "Veuillez sélectionner le fichier d'installation à exécuter", cliquez sur "Parcourir";
- Une fenêtre Finder s'ouvre et il vous faut alors sélectionner le fichier d'installation Prospéro puis cliquer sur "ouvrir";
- Acceptez toutes les paramètres par défaut suggérés par l'installateur;
- À la fin de la procédure d'installation de Prospéro, vous serez revenu sur la fenêtre PlayOnMac. N'hésitez alors pas à cliquer sur "Suivant";
- Acceptez la création d'un raccourci vers l'application, en cliquant sur "Oui";
- Sélectionnez alors le fichier prospero-1.exe, qui doit se trouver à l'intérieur de "PlayOnMac/wineprefix/playonmac/drive_c/Program Files/Doxa", puis cliquez sur "Ouvrir";
- Donnez un nom au raccourci: Prospéro. Cliquez sur "Suivant";
- PlayOnMac vous demandera ensuite d'en choisir un deuxième, mais là vous pouvez cliquer sur "Non";
- C'est normalement fini et vous devez maintenant avoir un raccourci Prospéro sur votre bureau. Vous pouvez fermer PlayOnMac.


## Configurer Prospéro
Vous pouvez suivre les indications disponibles [ici](#configuration_prospero), vu qu'elles sont exactement les mêmes pour n'importe quel système d'exploitation de base.

## Informations sur ce tutoriel
- Sources utilisées:
  - https://linuxize.com/post/how-to-install-wine-on-ubuntu-20-04/
  - https://www.zdnet.com/article/how-to-run-a-windows-app-on-linux-with-wine/
  - https://wine.htmlvalidator.com/install-wine-on-ubuntu-20.04.html
  - https://help.ubuntu.com/community/Wine
  - https://wiki.playonlinux.com/index.php/Troubleshooting_Common_Problems
- Produit avec le soutien des associations Corpora et Prefigura.
- Création, révision et vérification: Waldir Lisboa Rocha et Aymeric Luneau
