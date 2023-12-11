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

### Installer Wine


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





## Configurer Prospéro
Vous pouvez suivre les indications disponibles [ici](#configuration_prospero), vu qu'elles sont exactement les mêmes pour n'importe quel système d'exploitation de base.

## Informations sur ce tutoriel
- Sources utilisées:
  - https://linuxize.com/post/how-to-install-wine-on-ubuntu-20-04/
  - https://wine.htmlvalidator.com/install-wine-on-ubuntu-20.04.html
  - https://wiki.playonlinux.com/index.php/Troubleshooting_Common_Problems#Xterm_missing
- Produit avec le soutien des associations Corpora et Prefigura.
- Création, révision et vérification: Waldir LISBOA ROCHA et Aymeric LUNEAU.
