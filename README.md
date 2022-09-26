B2 ESGI Lyon groupe3 Celian ; Hugo ; Josserand ; Pierre-Henry

Ce depot permet la collaboration autour d'un site web statique de vente de paires de chaussures : Snaker

Documentation :

   Set de l'environnement
Creation du repo sur le compte github de Celian https://github.com/CelianPH/Snaker.git
Ensuite on va ajouter les différents membres du groupe via nos nom d’utilisateurs
Josserand667 ; HuguDB ; pho-rg
 
    Initialisation du projet sur le main
On vient récupérer le code d’un ancien projet contenant plusieurs pages :
D’abord on se positionne dans le bon fichier via : 

cd snaker/
$ git commit -m 'ajout du code source'
$ git config --global user.email hugo.debarre@free.fr
$ git push origin main

    Branches

créer les branches :
git branch dev_
git checkout dev_
git add .
git push -u origin dev_

Supprimer les branches :

Récupérer les branches :
for remote in `git branch -r`; do git branch --track ${remote#origin/} $remote; done
-> cette commande boucle sur toutes les branches pour les recuperer sur son environnement

Organisation de nos branches :
- PROD 'main'
- PREPROD 'recette'
- DEV 'dev_*' -> une par feature (5)

    Developpement des features

Josserand se charge de la traduction du site et le changement du CSS
Celian ajoute des modeles de chaussures sur la HomePage
Hugo ajoute les pages de description des chaussures
Pierre-Henry cree la page de documentation (plan du site)

    Fusion
Les features sont prête à être mise en PREPROD (branche 'recette')

git add .
git commit -m 'ajout de la feature *'
git checkout recette
git pull
git merge dev_*
git push -u origin recette

    Publication de la premiere version sur la PROD 'main'
    
git checkout main
git merge recette
git push -u origin main

    Travail sur les V2
La tache de modification du CSS est faite puis mise en prod pour officier de V2

Déploiement :
On va venir link les comptes Netlify et Github en utilisant le workflow HTML Static. En changeant les paramètres dans le workflow notamment en changeant la branch racine (on remplace master par main) on va le commit. Cela va donc créer un .yml.
Dans Netlify une fois que le site est déployé on lui assigne une nom de domaine et on tire le lien final : https://clinquant-beignet-64dee1.netlify.app/

Vous trouverez les notes de Josserand Di Nunzio parmis les fichiers : Notes_Git_JDinunzio
Vous trouverez les notes de Célian PHILIBERT parmis les fichiers : https://brawny-quarter-1f0.notion.site/Versioning-GIT-a4e9039c90784079b8568b4f54637331
