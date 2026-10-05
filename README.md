# Architecture

il y a un dossier par module

dans chaque dossier de module il y a un dossier par TP ou projet

dans chaque dossier TP ou projet il y a

- un dossier "consignes" qui contient les consignes à suivre pour faire le TP (le contenu de ce dossier peut être consulté mais ne doit pas être modifié)
- un dossier "dev" dans lequel vous répondez aux consignes et vous faites vos développements et tests

il y a un script "*.sh" dans chaque dossier de module. ce script permet simplement de démarrer un container (ou plusieurs) basé sur l'image docker dont on a besoin.

# Dans la plateforme github :

**créer un compte github si ce n'est pas déjà fait.**

**créer un repo privé ILISI3 dans votre espace github.**

# Dans votre machine (phase d'initialisation) :

**Cloner votre dépôt privé vide (ne cocher pas l'ajout d'un readme ou d'un .gitignore):**

git clone https://github.com/"votrecomptegithub"/ILISI3.git

**accéder au repo que vous venez de cloner:**
cd ILISI3

**ajouter le dépot template:**

git remote add template https://github.com/klaghmari-github/ILISI3.git

**récupérer la branche main du remote git template:**

git pull template main

**envoyer le contenu récupéré vers votre dépôt privé:**

git push -u origin main

# Dans votre machine (phase de développement) :

**identifier les modification avant de les intégrer :**

git status

**tracer tous les fichiers qui ont été modifiés :**

git add .

**faire un commit qui évite de déclencher des pipelines avec un commentaire qui indique ce qu'il y a dans le commit :**
git commit -m "[ci skip] etape 1 de l'exercice 2 par exemple"

**avant de faire un push, s'assurer d'être à jour par rapport au repo template au cas où il y a eu des mises à jour d'ennoncé ou de nouvelles consignes (par défaut les anciens fichiers de consignes seront écrasés par les nouveaux en cas de conflit):**

git pull --no-rebase -X theirs template main

**faire un push vers le git distant privé labelisé origin sur la branch main**
git push origin main
