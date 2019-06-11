# MINI GUIDE DE PROGRAMMATION DE RADIO AVEC CHIRP

*Ce guide est realise avec une radio Baofeng UV-5R pour exemple*


## 1. Verification

1.1 Verifier que votre radio est supportee par le logiciel: elle doit apparaitre dans la liste des radios sur la page https://chirp.danplanet.com/projects/chirp/wiki/Home

Si elle n'y est pas, vous devez attendre qu'elle y apparaisse, inutile d'aller plus loin avec CHIRP.


## 2. Installation & Demarrage

2.1 Telecharger et installer la derniere version du logiciel de CHIRP sur la page: https://trac.chirp.danplanet.com/chirp_daily/LATEST/
- Pour Windows, telecharger et executer le fichier installeur chirp-daily-XXXXXXXXX-installer.exe
- Pour MacOS, telecharger et executer le fichier chirp-daily-XXXXXXXX.app.zip
- Pour Linux Ubuntu, il existe un repo:
      sudo apt-add-repository ppa:dansmith/chirp-snapshots
      sudo apt-get update
      sudo apt-get install chirp-daily

2.2 Lancer le programme CHIRP, vous devez n'avoir qu'un menu.

2.3 Brancher votre cable USB dans un port, sans mettre de radio sur la fiche.

## 3. Sauvegarde de votre programmation actuelle

3.1 Dans menu 'Radio', cliquer sur 'Download from Radio'
Une fenetre s'ouvre et vous laisse renseigner le modele de votre radio, ainsi que le port USB a utiliser.

![usb-settings](http://)

Valider, la radio clignote, les diodes sur le cable de programmation aussi si votre cable en possede, et une barre de progression 'Cloning' s'affiche indiquant la bonne communication entre la radio et le logiciel.

Une erreur de communication peut s'ouvrir a la place, pour corriger le probleme:

- Verifier que la fiche du cable USB est bien enfoncee dans la radio, qui est allumee et sans activite (se mettre sur une frequence sans activite)
- Verifier que vous entrez le bon modele de radio dans la fenetre
- Re-essayer avec un port USB different dans la fenetre
- Verifier que vous utilisez le cable de programmation qui va avec la bonne radio si vous avez plusieurs cables de programmation

Une fois le telechargement termine, la configuration de la programmation de votre radio s'affiche.

3.2 Dans le menu 'File', cliquer sur 'save' et sauver votre fichier original.

*Note: ceci n'est pas obligatoire, car en general toutes les radios possedent un moyen de reseter les parametres d'usines en cas ou vous obtenez une configuration non fonctionnelle, mais mieux vaut etre prudent*


## 4. Chargement de la configuration airsoft-milsim

4.1 Fermer le fichier de l'etape precedente (menu 'File', cliquer 'Close')

4.2 Ouvrir le fichier *Baofeng_UV-5R_airsoft-milsim.img* (menu 'File', cliquer 'Open' et selectionner le fichier telecharge precedemment)

4.3 Personnaliser la configuration:

- Dans l'onglet 'Settings'\'Others Settings', modifier le texte sur les 2 lignes  
  Ce texte apparaitra rapidement a chaque allumage de la radio (pratique pour identifier son proprietaire par exemple)
  ![Personnalisation](http://)
- Dans l'onglet 'Memories', un tableur presente les 128 canaux programmables. Copier/coller une ligne est possible comme dans tout tableur, libre a vous de modifier la programmation, sont deja programmes:
    - de 001 a 069: les canaux LPD-443 sans filtrage CTCSS
    - de 081 a 096: les canaux PMR-446 avec filtrage CTCSS (frequence de filtrage Nº4 a 77.0Hz)
    - de 101 a 116: les canaux PMR-446 sans filtrage CTCSS
  ![Memoires](http://)

4.4 Dans le menu 'File', cliquer sur 'save' et sauver votre nouvelle configuration personnalisee.

4.5 Telecharger la configuration sur la radio: menu 'Radio', cliquer 'Upload To Radio'

Une barre de progression 'Cloning' doit apparaitre. Une fois termine, eteindre la radio, debrancher le cable de programmation de la radio, votre radio est prete a l'emploi.

*note: un message d'erreur peut arriver a la fin de la barre de progression, il se peut que ce soit juste une histoire de numero de firmware qui ne peut pas etre mis a jour depuis la configuration Baofeng_UV-5R_airsoft-milsim.img telechargee, ignorer le message, et verifier que la radio est bien programmee*
