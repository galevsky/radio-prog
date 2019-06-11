# radio-prog

Ce depot contient un mini-guide de programmation avec le logiciel CHIRP et un exemple de fichier de programmation pret a utilisation pour radio Baofeng UV-5R ou UV-5R+.

# Mini-guide de programmation

il se trouve dans le sous-repertoire ./mini-guide

# Fichier de programmation

Ce fichier de programmation a ete fait dans un but de faciliter l'utilisation de radio pour la pratique de l'airsoft milsim:

## Amelioration de la discretion

- bip des touches du clavier desactive
- retro-eclairage de l'ecran sur appui de touches desactive (utilisation de lumiere naturelle ou de votre frontale rouge pour l'utilisation nocturne)
- retro-eclairage de l'ecran sur emission/reception desactive
- desactivation de la radio FM

## Amelioration de l'usage

- desactivation de l'emission en VHF
- canaux programmes:
  - 001->069 : canaux "LPD #XX" (sans filtrage CTCSS)
  - 081->096 : canaux "PMR**XX" (avec filtrage CTCSS, voir guide de progammation )
  - 101->116 : canaux "PMR #XX" (sans filtrage CTCSS)


**ATTENTION !!! L'utilisation d'un poste radio programmable est interdit en France sans licence ou ussage qui lui est reserve**

Ceci etant dit, si vous souhaitez quand meme utiliser de tels appareils, il vaut mieux se conformer a un usage "responsable" dans la mesure du possible, c'est-a-dire n'utiliser que des frequences libre d'usage
pour ne gener personne.

Il existe 2 bandes de frequences utilisables librement en UHF:

- LPD-433 dans la bande des 433->434MHz avec 69 canaux utilisables (avec une puissance d'emission tres faible: 10 mW)
- PMR-446 dans la bande des 446->447MHz avec 16 canaux utilisables (avec une puissance d'emission faible: 500 mW)

*Note: vous connaissez certainement les 8 premiers canaux PMR, de 01->08, presents sur tous les appareils radio PMR, depuis juin 2018 la norme a accueilli 8 nouveaux canaux de 09->16*


## Filtrage CTCSS ("sous-canaux")
certains appareils PMR sont equipes de "sous-canaux", il s'agit en fait d'une frequence de filtrage CTCSS sur l'un des 8 (ou 16 maintenant) canaux PMR.
Parler de "sous-canaux" est abusif: il s'agit en fait de definir -optionnellement- une frequence de filtrage.
Mais le systeme est tres imparfait, voici le principe: lorsque vous émettez en ayant configuré un code CTCSS, un signal en continu se superpose à votre communication sur une fréquence inaudible par l’homme. Le talkie-walkie qui a lui aussi sélectionné le même code CTCSS ne déclenchera la réception uniquement si il reçoit ce signal, sinon le haut-parleur reste muet. Mais le système est imparfait, exemple :

Groupe A : fréquence 446,00625 – CTCSS : 88,5 Hz
Groupe B : fréquence 446,00625 – CTCSS : désactivé

Lorsque il y a une émission du groupe A :
- le groupe A reçoit A
- le groupe B reçoit malheureusement A (car B ne filtre pas les receptions)

Lorsque il y a une émission du groupe B :
- le groupe A ne reçoit pas B (filtrage CTCSS)
- le groupe B reçoit B

Lorsque il y a une émission simultanée des groupes A et B :
- le groupe A reçoit malheureusement A+B (l’émission A active les hauts-parleurs)
- le groupe B reçoit malheureusement A+B

Comme vous le constatez, le filtrage CTCSS (ou "sous-canal") est tout sauf une solution ideale.
La programmation proposee possede les 16 canaux PMR programmees avec un code CTCSS pour permettre de soulager l'utilisation des 8 premiers canaux PMR (contrainte de l'orga bien souvent), en esperant que la frequence de filtrage soit la meme pour toutes la faction. (A vous de pre-programmer la bonne, c.f. le guide de programmation).

+infos: http://pmr446.free.fr/index_codage_ctcss.htm



## Utilisation de la radio (exemple Baofeng UV-5r)

1. Allumer la radio
2. Deverouiller le clavier (appui long sur le petit cadenas, touche '#') qui est verrouille par defaut
3. Selectionner le canal souhaite pour le canal A:
    - en utilisant les fleches haut/bas pour cycler
    - en tapant directement le numero de canal (ex: pour aller sur le canal 'PMR #08' sans filtrage CTCSS, taper '1-0-8')
4. Basculer sur le canal B (bouton A/B)
5. Selectionner le canal souhaite pour le canal B:
    - en utilisant les fleches haut/bas pour cycler
    - en tapant directement le numero de canal (ex: pour aller sur le canal 'LPD #34' sans filtrage CTCSS, taper '0-3-4')
6. Attendre quelques secondes que le clavier se re-verrouille ou le faire manuellement (appui long sur le petit cadenas, touche '#')

**Important**: *votre radio est programmee pour fonctionner sur les 2 canaux A et B en meme temps !!!
L'emission se fait sur le canal A, mais la radio declenche en reception sur les canaux A et B !!!
Ceci peut s'averer pratique (Chef de Groupe par exemple) ou non-souhaitable.
Pour n'ecouter qu'un seul canal, il suffit simplement de choisir le meme canal pour A et B.
Si vous etes le seul de votre equipe a entendre des choses dans la radio, verifiez que vous n'avez pas un canal B  different de A*
