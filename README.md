# Lexpérience que j'ai acquise à travers la résolution des 3 nexercices du projet Git/Github.

### Exercice 1 : Premier Dépôt/Commit Simple (https://github.com/prphysquant/git-learning-1)
- J'ai appris en gros la création, le clonnage, un peu la gestion basique d'un repository directement via le terminal.
- Ensuite j'ai compris comment envoyer directemeent depuis mon terminal les traveaux que j'ai effectué localement avec les commandes add → commit → push.
### Commandes exécutées
# Création et configuration du dépôt
gh repo create git-learning-1 --public
git clone https://github.com/prphysquant/git-learning-1.git
cd git-learning-1
echo "Mon premier projet Git" > README.md
git add README.md
git commit -m "Premier commit avec README.md"
echo "Je suis MANOMI AGYAOU Abdoul Magid, le numéro de mon Mac est le 14" >> README.md
git add README.md
git commit -m "Ajout des mes infos personnelles"
git push origin main

### Exercice 2 : Branching/Merging (https://github.com/prphysquant/git-learning-2)
- Ici j'ai appris à créer et gérer des branches
- Puis le processus de Pull Request
- Et enfin la fusion de branches
### Ici je montre comment j'ai effectué l'exo 2.
### Création et travail sur une branche
j'ai cloné d'abord le repo que j'ai manuellement créé sur git. La création avec le terminal m'a trop fait fatiguée. 
git checkout -b myself
cat > about.txt << EOF
Nom: MANOMI AGYAOU 
Prénom: Abdoul Magid
Lieu de naissance: Niamey
EOF
git add about.txt
git commit -m "Ajout fichier about avec informations personnelles"
git push origin myself
# Création et merge de la Pull Request
gh pr create --title "Ajout infos personnelles" --body "Merge branch myself"
gh pr merge

### Exercice 3 : Gestion des Conflits (https://github.com/prphysquant/git-learning-3)
- Là j'ai appris à identifier des conflits de merge
- A résolution manuelle ces conflits
### Commandes exécutées
# Sur main
echo "Ligne écrite depuis la branche main" > notes.txt
git add notes.txt && git commit -m "Ajout notes depuis main" && git push
# Sur conflict-test ( ici j'ai dû prendre notes.txt pas note.txt donné par l'exo. Puisque avec cela, je ne trouve pas d'erreur comme annoncé dans l'exo).
git checkout -b conflict-test
echo "Ligne écrite depuis la branche conflict-test" > notes.txt
git add notes.txt && git commit -m "Modif notes depuis conflict-test" && git push
# Retour sur main + modification conflictuelle
git checkout main
echo "Ligne écrite depuis la branche main pour la seconde fois" > notes.txt
git add notes.txt && git commit -m "Seconde modif notes depuis main" && git push
# Tentative de merge → CONFLIT
git merge conflict-test
ERREUR
Je suis rentré depuis mon terminal pour vérifier avec la commande nano notes.txt.
<<<<<<< HEAD
Ligne écrite depuis la branche main pour la seconde fois
=======
Ligne écrite depuis la branche conflict-test
>>>>>>> conflict-test >>>>>>
### Text qui reste après la supression des deux autres lignes comme l'a été demandé.
Ligne écrite depuis la branche main pour la seconde fois
Ligne écrite depuis la branche conflict-test.
Puis je suis revenu sur mon terminal pour exécuter ces commandes :
git add notes.txt
git commit -m "Résolution conflit merge conflict-test"
git push

### Synthèse de mon apprentissage et conceptes clés
### Je tiens à notifier que le deuxième Exo m'a beaucoup fait fatiguer car je créais le repo depuis le terminal et le clone. La branche main bien qu'elle existe déja par défaut, si je faisais git branch cela ne l'affiche pas. 
## Repository : Dépôt contenant l'historique complet du projet
## Commit : Point de sauvegarde dans l'historique Git
## Branch : Ligne de développement indépendante
## Merge : Fusion du code d'une branche dans une autre
## Conflict : Modifications incompatibles sur les mêmes lignes de code
## Staging : Zone intermédiaire où on prépare les fichiers pour le commit
## Pull Request : Demande de fusion de code sur les plateformes comme GitHub
## Push/Pull : Synchronisation entre le repository local et distant
