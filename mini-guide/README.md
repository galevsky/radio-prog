# MINI GUIDE DE PROGRAMMATION DE RADIO AVEC CHIRP

*Ce guide est réalisé avec une radio Baofeng UV-5R pour exemple*


## 1. Vérification

1.1 Vérifier que votre radio est supportée par le logiciel: elle doit apparaître dans la liste des radios sur la page https://chirp.danplanet.com/projects/chirp/wiki/Home

Si elle n'y est pas, vous devez attendre qu'elle y apparaisse, inutile d'aller plus loin avec CHIRP.


## 2. Installation & Démarrage

2.1 Télécharger et installer la dernière version du logiciel de CHIRP sur la page: https://trac.chirp.danplanet.com/chirp_daily/LATEST/
- Pour Windows, télécharger et exécuter le fichier installeur chirp-daily-XXXXXXXXX-installer.exe
- Pour MacOS, télécharger et exécuter le fichier chirp-daily-XXXXXXXX.app.zip
- Pour Linux Ubuntu, il existe un repo:

      sudo apt-add-repository ppa:dansmith/chirp-snapshots  
      sudo apt-get update  
      sudo apt-get install chirp-daily  

2.2 Lancer le programme CHIRP, vous devez n'avoir qu'un menu.

2.3 Brancher votre câble USB dans un port, sans mettre de radio sur la fiche.

## 3. Sauvegarde de votre programmation actuelle

3.1 Dans menu 'Radio', cliquer sur 'Download from Radio'
Une fenêtre s'ouvre et vous laisse renseigner le modèle de votre radio, ainsi que le port USB à utiliser.

![usb-settings](https://raw.githubusercontent.com/galevsky/radio-prog/master/mini-guide/img/usb-settings.png)

Valider, une deuxième fenêtre demande de connecter la radio et l'allumer volume au maximum, re-valider, commence alors le téléchargement: la radio clignote, les diodes sur le câble de programmation aussi si votre câble en possède, et une barre de progression 'Cloning' s'affiche indiquant la bonne communication entre la radio et le logiciel.

Une erreur de communication peut s'ouvrir à la place, pour corriger le problème:

- Vérifier que la fiche du câble USB est bien enfoncée dans la radio, qui est allumée et sans activité (se mettre sur une fréquence sans activité pour les 2 canaux A et B)
- Vérifier que vous entrez le bon modèle de radio dans la fenêtre
- Re-essayer avec un port USB différent dans la fenêtre
- Vérifier que vous utilisez le câble de programmation qui va avec la bonne radio si vous avez plusieurs câbles de programmation

Une fois le téléchargement terminé, la configuration de la programmation de votre radio s'affiche.

3.2 Dans le menu 'File', cliquer sur 'save' et enregistrer votre fichier original.

*Note: ceci n'est pas obligatoire, car en général toutes les radios possèdent un moyen de re-seter les paramètres d'usine au cas ou vous obtiendrez une configuration non fonctionnelle, mais mieux vaut etre prudent*


## 4. Chargement de la configuration airsoft-milsim

4.1 Fermer le fichier de l'étape précédente (menu 'File', cliquer 'Close')

4.2 Ouvrir le fichier *Baofeng_UV-5R_airsoft-milsim.img* (menu 'File', cliquer 'Open' et sélectionner le fichier téléchargé précédemment [ici](https://github.com/galevsky/radio-prog/raw/master/Baofeng_UV-5R_airsoft-milsim.img))

4.3 Personnaliser la configuration:

- Dans l'onglet 'Settings'\'Others Settings', modifier le texte sur les 2 lignes  
  Ce texte apparaitra rapidement à chaque allumage de la radio (pratique pour identifier son propriétaire par exemple)
  ![Personnalisation](https://raw.githubusercontent.com/galevsky/radio-prog/master/mini-guide/img/customisation.png)
- Dans l'onglet 'Memories', un tableur présente les 128 canaux programmables. Copier/coller une ligne est possible comme dans tout tableur, libre à vous de modifier la programmation, sont déjà programmés:
    - de 001 a 069: les canaux LPD-443 sans filtrage CTCSS
    - de 081 a 096: les canaux PMR-446 avec filtrage CTCSS (fréquence de filtrage Nº4 à 77.0Hz)
    - de 101 a 116: les canaux PMR-446 sans filtrage CTCSS
  ![Memoires](https://raw.githubusercontent.com/galevsky/radio-prog/master/mini-guide/img/memories.png)

4.4 Dans le menu 'File', cliquer sur 'save' et sauver votre nouvelle configuration personnalisée.

4.5 Télécharger la configuration sur la radio: menu 'Radio', cliquer 'Upload To Radio'

Une barre de progression 'Cloning' doit apparaître. Une fois terminé, éteindre la radio, débrancher le câble de programmation de la radio, votre radio est prête à l'emploi.

*note: un message d'erreur peut arriver à la fin de la barre de progression, il se peut que ce soit juste une histoire de numéro de firmware qui ne peut pas être mis-à-jour depuis la configuration Baofeng_UV-5R_airsoft-milsim.img téléchargée qui contient un numéro de firmware différent, ignorer le message, et vérifier que la radio est bien programmée*
