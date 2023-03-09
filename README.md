    	# Git Cheat Sheet

    	Aide memoire GitHub

### <span style="color:yellow">Definitions</span>

working directory = dossier de travail (dans son depot local)

Une pull request = ou demande de pull, en français, est une fonctionnalité de GitHub qui permet de demander aux propriétaires d’un repository l’autorisation de fusionner nos changements sur la branche principale ou toute autre branche sur laquelle on souhaite apporter nos modifications.

Donc si vous créez une pull request, vous avez au préalable :

Créé une nouvelle branche.

Envoyé votre code sur cette même branche.

D’ailleurs, lorsque ces deux conditions sont remplies, un bandeau apparaît à l’écran pour vous suggérer de créer une pull request :

### <span style="color:yellow">Commande de base</span>

<span style="color:green">_…or create a new repository on the command line_</span>.

> echo "# Test-automation" >> README.md

> git init

> git add README.md

> git commit -m "first commit"

> git branch -M main

> git remote add origin https://github.com/TucoBenedicto/Test-automation.git

> git push -u origin main

<span style="color:green">_…or push an existing repository from the command line ._</span>

> git remote add origin https://github.com/TucoBenedicto/Test-automation.git

> git branch -M main

> git push -u origin main

### <span style="color:yellow">Cloner un repository</span>

<span style="color:green">_Recuper un nouveau repository_</span>.

> git clone https://github.com/OpenClassrooms-Student-Center/7162856-G-rez-Git-et-GitHub.git

<span style="color:green">_Le nom de ce repository est beaucoup trop long ! Je vous conseille de créer un raccourci pour gagner du temps._</span>.

> git remote add OC https://github.com/OpenClassrooms-Student-Center/7162856-G-rez-Git-et-GitHub.git

<span style="color:green">_OC représente le nom court que vous utiliserez ensuite pour appeler votre dépôt. Appelez-le comme bon vous semble, mais un nom court et simple est toujours plus facile par exemple : git push OC _</span>.

### <span style="color:yellow">Travailler avec un remote repository tiers</span>

<span style="color:green">_lier notre depot local (origin) à depot distant (remote repository)_</span>.

> git remote add
> origin https://github.com/EtudiantOC/OpenclassroomsProject
> .git

<span style="color:green">_envoyer nos fichier vers notre depot distant (remote repository)_</span>.

> git add .

> git commit -m "update"

<span style="color:green">_corriger une erreur dans le message du commit_</span>.

> git commit --amend -m "nouveaux message"

> git push -u origin main (une seul fois)

> git push origin (a chaque fois raccourcie)

<span style="color:green">_Attention il faudra changer le nom du local repository si on souhaite l'envoyer dans notre remote repository_</span>.

<span style="color:green">_Annuler un commit_</span>.

> git revert HEAD

### <span style="color:yellow">Creer des branches</span>

<span style="color:red">_Je vous conseille fortement de créer une branche si votre modification est lourde, compliquée, ou si elle risque d’avoir des impacts importants sur votre projet._</span>.

<span style="color:green">_Pour connaître les branches présentes dans notre projet local et distant_</span>.

> git branch -a

<span style="color:green">_créer la branche Cagnotte en local. Cette dernière ne sera pas dupliquée sur le dépôt distant._</span>.

> git branch cagnotte

<span style="color:green">_Pour basculer de branche, nous allons utiliser :_</span>.

> git checkout cagnotte

<span style="color:green">_pour fusioner les modifications de la branche "cagnottes" à la branche "main", il faut se mettre dans la branche principal (main)_</span>.

> git merge cagnotte

<span style="color:green">_supprimer branche, ne pas laisser des branches inutiles dans un repository_</span>.

> git branch -d cagnotte

<span style="color:green">_renommer une branche dans laquelle nous somme _</span>.

> git branch -m new-name

<span style="color:green">_Si vous êtes sur une branche différente:_</span>.

> git branch -m old-name new-name

### <span style="color:yellow">Get a remote repository (depot distant)</span>

<span style="color:green">_Cloner un remote repository ,pour recuperer l'ensemble d'un projet ,j'obtiens alors un local repository qui s'appellera "origin")_</span>

> git clone https://github.com/TucoBenedicto/Test-automation.git

<span style="color:green">_je peux changer le nom de mon local repository "origin" pour l'appeler "clone" ou autre si je veux l'envoyer vers un autre depot distant_</span>

<span style="color:green">_recuper un depot distant d'une source externe, nous donnera un depot local pour nom "origin" si je veux travailler dessus et l'envoyer vers mon propre depot distant je dois le renommer, parceque le nom du local repository de openclassroom s'appel deja origin et le mien aussi, ce qui entraine un conflit_</span>

> git remote rename origin clone

<span style="color:green">_j'ajoute le repository de openclassroom par exemple_</span>

> git remote add origin https://github.com/OpenClassrooms-Student-Center/testez-vos-applications-front-end-avec-javascript.git

<span style="color:green">_changer l'url d'un remote repository_</span>

> git remote set-url origin https://github.com/OpenClassrooms-Student-Center/testez-vos-applications-front-end-avec-javascript.git)

et pour finir un "pull" pour recuperer toutes les branches et ses mises à jour pour les mettre dans son local repository ("clone" , si on a changer le nom de son local repository (origin)

> git pull clone

consulter les toutes les branches du depot distant (sans fusionner)

> git fetch --all

### <span style="color:yellow">Get a remote repository & push shift to my remote repository</span>

<span style="color:green">_Pour recuperer un remote repository (depot distant) appartenant a un tiers il faut changer le nom du depot local "origin" ("origin = local name of the remote repository" du depot openclassroom par exemple) par "clone" (ou un autre nom) pour etre envoyer sur mon propre repository "commande push" sur mon depot) soit sa:_</span>

> git remote add clone https://github.com/TucoBenedicto/Test-automation.git

<span style="color:green">_Par consequent cette commande est erronée :_</span>

> git remote add origin https://github.com/TucoBenedicto/Test-automation.git

<span style="color:green">_Pour finir on envoie dans son depot distant (remote repository)_</span>

<span style="color:green">_(-u = upstream)
comprendre l'upstream : https://code-garage.fr/blog/a-quoi-sert-le-parametre-u-lors-d-un-git-push/#:~:text=Lorsque%20l%27on%20pousse%20les,appelle%20"l%27upstream"._</span>

> git push -u clone main // (uniquemenent la 1ere fois !)

> git push clone // (les fois suivantes !)

<span style="color:red">_!! Procedure à répéter pour chaque nouvelle branche !!_</span>

span style="color:red">_!! Vérification du statut !!_</span>

n'importe urtuiuftucutfuf
