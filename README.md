Documentation :

Première étape :
On commence par créer un repo :
 
 
Ensuite on va ajouter les différents membres du groupe via nos nom d’utilisateurs :
 
Deuxième étape :
On vient récupérer le code d’un ancien projet contenant plusieurs pages :
D’abord on se positionne dans le bon fichier via : 

cd snaker/
$ git commit -m 'ajout du code source'
$ git config --global user.email hugo.debarre@free.fr
$ git push origin main

    Branches

créer les branches :
git branch page_documentation
git checkout page_documentation
git add .
git commit -m 'initialisation de la branche documentation'
git push -u origin branche_documentation


Récupérer les branches :

for remote in `git branch -r`; do git branch --track ${remote#origin/} $remote; done