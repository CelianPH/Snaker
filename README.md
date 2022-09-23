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

    Travail sur les V2

