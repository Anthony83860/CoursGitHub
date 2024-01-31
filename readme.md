Les commandes de base de Github

Première étape : initialiser un repo

Créez dans le Github, un nouveau repository
Nommez le comme vous le souhaitez
Vous pouvez choisir sa visibiilité :
Public : Si vous souhaitez que tout le monde puisse y avoir accès
Private : Si vous souhaitez être le seul à y accéder
La description est optionnelle : Remplissez-là si vous le souhaitez
Allez en bas de page, cliquez sur "create repository"
Votre repository est maintenant créé, vous allez pouvoir faire votre premier commit.

Faire son premier commit

Vous allez vous rendre compte qu'il y a un petit encadré nommé "Quick setup" qui vous propose deux possibilités : HTTPS et SSH

Si ce n'est pas fait par défaut, choisissez HTTPS

Initialisation de Github sur votre machine

Sur Visual Studio Code :

Ouvrez un terminal (3 possibilités)
Menu affichage > Terminal
CTRL + ù
En bas à gauche, vous avez une icone triangle et rond, cliquez dessus
Initialiser github sur le dossier qui est ouvert avec la commande git init

Une fois initialisé, vous allez devoir indiquer quel(s) fichier(s) vous souhaitez envoyer sur github. Pour cela :

git add * Pour ajouter tous les fichiers
git add nomDuFichier Pour ajouter un fichier en particulier
Pour info, vous ne devez PAS entrer le nom complet du dossier ou du fichier à ajouter. Ca augmente le risque d'erreur. Au lieu d'écrire le nom complet vous-même, vous devez écrire seulement la ou les premières lettres et appuyer sur la touche tab

Dans le cas ou il existe plusieurs fichiers qui commencent avec les mêmes lettres, il vous suffit de continuer à appuyer sur la touche tab

Si vous avez plusieurs fichiers à ajouter, MAIS que vous ne souhaitez pas ajouter tous les fichiers qui se trouvent dans votre dossier de travail, vous devez faire plusieurs fois git add nomDuFichier

En résumé

git init - Pour initaliser le repo github
git add NomDuFichier - Pour ajouter un fichier
git add * - Pour ajouter TOUS les fichiers
Si vous faites par mégarde CTRL + S dans votre terminal. Il vous suffit de faire CTRL + C pour annuler

Exercice

Initaliser un nouveau repo github sur VSCode
Ajouter un fichier readme.md
Faire la liaison avec le repo distant

Vous venez d'intialiser git sur votre machine, mais il ne sait pas encore qu'il doit être lié à votre repository distant. Pour cela, vous allez devoir connecter l'origine à votre repository distant.

Commençons d'abord par ajouter un petit message qui précise ce qu'on a fait comme modificationn/ajout/suppression

git commit -m "explication du commit"
git commit -m "Ajout du fichier readme"
Une fois que le message de commit est défini, on va choisir la branche sur laquelle on va travailler.

Lorsque vous souhaitez stocker vos fichiers sur github, si vous le souhaitez, vous pouvez stocker différentes versions de vos fichiers. Cela s'appelle des branches.

La branche principale sur laquelle vos fichiers sont enregistrés s'appelle "main".

git branch -m main
Cette commande indique qu'on sélectionne la branche "main".

Il est maintenant temps de connecter votre repo local (votre machine) à votre repo distant (github). Pour cela, utilisez cette commande :

git remote add origin LIEN_DE_VOTRE_REPO
Exemple :

git remote add origin https://github.com/JackAdamsJenkins/coursgithub.git
Maintenant que le repo local et distant sont connectés, il vous reste à envoyer vos fichiers sur github. Cela se fait avec la commande git push -u origin main

En résumé

Voici les commandes à lancer :

git init pour initialiser le repo github (a faire qu'une seule fois par projet)
git add NomDuFichier ou * Pour ajouter un fichier ou tous les fichiers
git commit -m "Nom du commit" Pour ajouter une description de la modification/ajout
git branch -m main pour choisir la branche principale
git remote add origin URL_REPO_GITHUB Pour connecter le repo local et distant
git push -u origin main Pour publier les modifications sur github
Informations

Pour pouvoir envoyer les fichiers sur github, la première fois que vous réalisez les commandes, le système va vous demander de vous authentifier. Il faudra renseigner le mail que vous avez utilisé pour créer votre compte Github.

Pour pouvoir configurer le compte github, il faut entrer la commande :

git config --global user.email votreAdresse@mail.com
Les commandes git init, git branch et git remote add origin sont à lancer UNE SEULE FOIS au moment de l'initalisation du repo.

Une fois que ces commandes ont été faites, pendant le reste du développement de votre projet, vous pouvez utiliser les commandes suivantes : git add NomDuFichierModifié, git commit -m "message de modification" et git push

C'est ces trois commandes que vous utiliserez à chaque fois :

git add NomDuFichierModifié
git commit -m "message de modification"
git push
Ecrire un bon message de commit

Ecrire un bon message de commit est essentiel pour la maintenance et la compréhension d'un projet. Cela aide à suivre l'évolution du projet et à comprendre les raisons derrière chaque modification.

Voici une norme généralement acceptée pour rédiger des messages de commit.

Structure d'un message de commit

Un message de commit se compose généralement de deux parties :

Un titre (ou en-tête) : C'est une brève description des modifications. Il doit être concis et ne pas dépasser les 50 caractères. Il doit commencer par une majuscule.
Un corps : Il donne des détails supplémentaires sur les modifications. Il est séparé du titre par une ligne blanche.
Titre court et description

Corps du message : ici, on explique en détail le pourquoi et le comment
des changements si nécessaire. Essayez de garder chaque ligne à moins
de 72 caractères pour la lisibilité
Conseils pour un bon message de commit

Utiliser l'impératif : Le titre doit idéalement être écrit à la voix impérative (ex. Ajout, Corrige, Refactorise au lieu de Ajouté, Corrigé, Refactorisé)
Titre clair et concis : Doit être court et descriptif
Séparer les sujets : Si vous avez plusieurs modifications qui n'ont pas de rapport entre elles, envisagez de les séparer en plusieurs commits
Expliquer le pourquoi, pas le comment : Le code lui-même montre comment une certaine chose a été faite. Ce qui n'est pas toujours clair, c'est pourquoi cette modification a été apportée. Assurez-vous d'expliquer les raisons dans le corps du message.
Evitez les messages vagues : "Corrections diverses" ou "Mises à jour" ne sont PAS des messages utiles. Soyez aussi descriptif que possibile.
Utilisez des références aux issues/tracker : Si votre commit fait référence à une issue ou à un ticket, ajoutez cette référence dans le corps du message
Respectez les conventions de l'équipe : Si votre équipe a des conventions spécifiques pour les messages de commit, suivez-les.
Exemple d'un bon message de commit

Ajoute une fonctionnalité de recherche

La page d'accueil avait besoin d'une fonctionnalité de recherche
pour aider les utilisateurs à trouver des contenus spécifiques.

Cette modification ajoute un moteur de recherche et utilise l'API
de recherche pour récupérer les résultats.

Relatif à l'issue #123
En savoir plus sur le langage markdown

Pour la rédaction de vos fichiers Readme, n'hésitez pas à vous pencher sur la documentation markdown. Voici un lien pour vous aider : Lien pour apprendre le markdown

Eviter d'envoyer des fichiers/dossiers sur Github

Vous avez la possibilité de dire a github qu'il y a certains fichiers et dossiers que vous ne souhaitez pas partager sur votre repository.

Pour cela vous allez devoir :

Créer un fichier .gitignore à la racine de votre dossier
Dans le fichier .gitignore, vous devez ajouter ligne par ligne les fichiers/dossiers que vous ne souhaitez pas ajouter à votre repository
Exemple

Fichier .gitignore :

.code.js
./css
Exercice

Dans un de vos repository, ajoutez un nouveau fichier (.js, .html, .autre, on s'en fiche)
Une fois le fichier ajouté, publier la modification sur github (votre repo doit avoir le fichier)
Débrouillez-vous ensuite pour supprimer le fichier que vous venez d'ajouter et récupercuter la suppression sur votre repo github
Récupérer votre travail

Pour récupérer votre travail sur une autre machine, ou simplement récupérer la dernière version en date, vous devez utiliser la commande git clone URL_DU_REPO_A_CLONER

Par exemple : git clone https://github.com/JackAdamsJenkins/coursgithub.git

Pull Request

C'est une fonctionnalité clé des systèmes de gestion de version basées sur git comme Github, Gitlab, BitBucket... Elle représente une demande de fusion des modifications (commits) d'une branche vers une autre, généralement de la branche d'une fonctionnalité vers la branche principale d'un projet.

Concept de la Pull Request (PR)

Collaboration et revue de code : La PR n'est pas seulement un mécanisme de fusion de code. C'est aussi un outil de collaboration. Lorsqu'un développeur soumet un PR, d'autres membres de l'équipe peuvent la consulter, laisser des commentaires, suggérer des modifications et même proposer des commits pour améliorer la PR avant qu'elle ne soit fusionnée.

Point de contrôle : Avant la fusion, la PR fournit un point de contrôle pour s'assurer que le code respecte les qualités, passe tous les tests et n'introduit pas de régressions.

Intégration avec CI/CD : Les PR sont souvent intégrées avec des outils d'Intégration Continue et de Livraison Continue (CI/CD). Lorsqu'une PR est soumise, des tests automatisés peuvent être déclenchés, et le résultat de ces tests est souvent signalé directement dans l'interface de la PR.

Faire une Pull Request (PR)

Fork du repository

Avant de pouvoir soumettre une PR, vous devez avoir une copie du repository sur votre compte. Si ce n'est pas déjà fait :

Rendez-vous sur la page Github du projet auquel vous voulez contribuer
Cliquez sur le bouton "Fork" en haut à droite de la page. Cela créera une copie du projet sur votre compte Github personnel.
Cloner le fork

Après avoir fait un fork, vous allez pouvoir travailler dessus. Pour cela, vous allez devoir le cloner sur votre propre machine :

git clone URL_DU_REPO_A_CLONE (attention, c'est VOTRE repo)
git clone https://github.com/JackAdamsJenkins/Test-repos-Hugo.git
Créer une nouvelle branche

Il est conseillé de créer une nouvelle branche pour chaque nouvelle fonctionnalité ou correction. Cela vous permet de garder le travail organisé et séparé.

Pour créer une nouvelle branche, vous devez utiliser la commande git checkout -b NomDeLaNouvelleBranche

git checkout -b nom_de_la_branche
git checkout -b interfaceGUI
Apporter les modifications

Modifier le/les fichiers nécessaires et ajoutez-les à l'index :

git add nom_du_fichier
Ou pour ajouter tous les fichiers modifiés :

git add *
Ensuite, faites un commit de vos modifications :

git commit -m "Description des modifications"
Pousser la branche vers le fork

git push origin nom_de_la_branche
Créer la Pull Request

Aller sur la page Github de votre fork
Cliquer sur le bouton "New pull request"
Sélectionner votre nouvelle branche dans le menu déroulant "compare"
Assurez-vous que la branche de base (main) est celle du projet original et non celle de votre fork
Vérifier les modifications et cliquer sur "Create pull request"
Donner un titre à votre PR et décrire les modifications ou les raisons de votre PR
Cliquer sur "Create pull request" pour soumettre votre PR