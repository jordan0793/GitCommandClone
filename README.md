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

<span style="color:green">*…or create a new repository on the command line*</span>.

> echo "# Test-automation" >> README.md

> git init

> git add README.md

> git commit -m "first commit"

> git branch -M main

> git remote add origin https://github.com/TucoBenedicto/Test-automation.git

> git push -u origin main


<span style="color:green">*…or push an existing repository from the command line .*</span>

>git remote add origin https://github.com/TucoBenedicto/Test-automation.git

>git branch -M main

>git push -u origin main

### <span style="color:yellow">Cloner un repository</span>

<span style="color:green">*Recuper un nouveau repository*</span>.

>git clone https://github.com/OpenClassrooms-Student-Center/7162856-G-rez-Git-et-GitHub.git

<span style="color:green">*Le nom de ce repository est beaucoup trop long ! Je vous conseille de créer un raccourci pour gagner du temps.*</span>.

>git remote add OC https://github.com/OpenClassrooms-Student-Center/7162856-G-rez-Git-et-GitHub.git

<span style="color:green">*OC représente le nom court que vous utiliserez ensuite pour appeler votre dépôt. Appelez-le comme bon vous semble, mais un nom court et simple est toujours plus facile par exemple : git push OC *</span>.

### <span style="color:yellow">Travailler avec un remote repository tiers</span>

<span style="color:green">*lier notre depot local (origin) à depot distant (remote repository)*</span>.

>git remote add 
origin https://github.com/EtudiantOC/OpenclassroomsProject
.git


<span style="color:green">*envoyer nos fichier vers notre depot distant (remote repository)*</span>.

>git add .

>git commit -m "update"

<span style="color:green">*corriger une erreur dans le message du commit*</span>.

>git commit --amend -m "nouveaux message"

>git push -u origin main (une seul fois)

>git push origin (a chaque fois raccourcie)

<span style="color:green">*Attention il faudra changer le nom du local repository si on souhaite l'envoyer dans notre remote repository*</span>.

<span style="color:green">*Annuler un commit*</span>.

>git revert HEAD



### <span style="color:yellow">Creer des branches</span>

<span style="color:red">*Je vous conseille fortement de créer une branche si votre modification est lourde, compliquée, ou si elle risque d’avoir des impacts importants sur votre projet.*</span>.

<span style="color:green">*Pour connaître les branches présentes dans notre projet local et distant*</span>.

>git branch -a


<span style="color:green">*créer la branche Cagnotte en local. Cette dernière ne sera pas dupliquée sur le dépôt distant.*</span>.

>git branch cagnotte


<span style="color:green">*Pour basculer de branche, nous allons utiliser :*</span>.

>git checkout cagnotte


<span style="color:green">*pour fusioner les modifications de la branche "cagnottes" à la branche "main", il faut se mettre dans la branche principal (main)*</span>.

>git merge cagnotte


<span style="color:green">*supprimer branche, ne pas laisser des branches inutiles dans un repository*</span>.

>git branch -d cagnotte

<span style="color:green">*renommer une branche dans laquelle nous somme *</span>.

>git branch -m new-name

<span style="color:green">*Si vous êtes sur une branche différente:*</span>.

>git branch -m old-name new-name


### <span style="color:yellow">Get a remote repository (depot  distant)</span>

<span style="color:green">*Cloner un remote repository ,pour recuperer l'ensemble d'un projet ,j'obtiens alors un local repository qui s'appellera "origin")*</span>


> git clone https://github.com/TucoBenedicto/Test-automation.git


<span style="color:green">*je peux changer le nom de mon local repository "origin" pour l'appeler "clone" ou autre si je veux l'envoyer vers un autre depot distant*</span>

<span style="color:green">*recuper un depot distant d'une source externe, nous donnera un depot local pour nom "origin" si je veux travailler dessus et l'envoyer vers mon propre depot distant je dois le renommer, parceque le nom du local repository de openclassroom s'appel deja origin et le mien aussi, ce qui entraine un conflit*</span>

> git remote rename origin clone


<span style="color:green">*j'ajoute le repository de openclassroom par exemple*</span>


> git remote add origin https://github.com/OpenClassrooms-Student-Center/testez-vos-applications-front-end-avec-javascript.git

<span style="color:green">*changer l'url d'un remote repository*</span>

> git remote set-url origin https://github.com/OpenClassrooms-Student-Center/testez-vos-applications-front-end-avec-javascript.git)

et pour finir un "pull" pour recuperer toutes les branches et ses mises à jour pour les mettre dans son local repository ("clone" , si on a changer le nom de son local repository (origin)

> git pull clone

consulter les toutes les branches du depot distant (sans fusionner)

> git fetch --all


### <span style="color:yellow">Get a remote repository & push shift to my remote repository</span>

<span style="color:green">*Pour recuperer un remote repository (depot distant) appartenant a un tiers il faut changer le nom du depot local "origin" ("origin = local name of the remote repository" du depot openclassroom par exemple) par "clone" (ou un autre nom) pour etre envoyer sur mon propre repository "commande push" sur mon depot) soit sa:*</span>

> git remote add clone https://github.com/TucoBenedicto/Test-automation.git

<span style="color:green">*Par consequent cette commande est erronée :*</span>

> git remote add origin https://github.com/TucoBenedicto/Test-automation.git

<span style="color:green">*Pour finir on envoie dans son depot distant (remote repository)*</span>

<span style="color:green">*(-u = upstream)
comprendre l'upstream : https://code-garage.fr/blog/a-quoi-sert-le-parametre-u-lors-d-un-git-push/#:~:text=Lorsque%20l%27on%20pousse%20les,appelle%20"l%27upstream".*</span>

> git push -u clone main // (uniquemenent la 1ere fois !) 
 
> git push clone // (les fois suivantes !) 

<span style="color:red">*!! Procedure à répéter pour chaque nouvelle branche !!*</span>
