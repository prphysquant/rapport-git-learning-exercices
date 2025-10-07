# Lexpérience que j'ai acquise à travers la résolution des 3 nexercices du projet Git/Github.

### Exercice 1 : Premier Dépôt/Commit Simple
- J'ai appris en gros la création, le clonnage, un peu la gestion basique d'un repository directement via le terminal.
- Ensuite j'ai compris comment envoyer directemeent depuis mon terminal les traveaux que j'ai effectué localement avec les commandes add → commit → push.

### voici, je montre comment j'ai effectué l'exo 1 en question
### je me ferai certainement un grand plaisir à expliquer chaque commande que j'ai écrite.

Commandes exécutées
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

### Exercice 2 : Branching/Merging
- Ici j'ai appris à créer et gérer des branches
- Puis le processus de Pull Request
- Et enfin la fusion de branches

### Ici je montre comment j'ai effectué l'exo 2.
# Création et travail sur une branche
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
gh pr merge --squash


### Exercice 3 : Gestion des Conflits
- Là j'ai appris à identifier des conflits de merge
- A résolution manuelle ces conflits
- Avec de bonnes pratiques de prévention

## Synthèse des Apprentissages

### Branching
- Isolation des fonctionnalités via les branches
- Commandes maîtrisées : `git branch`, `git checkout -b`
- Avantages pour le développement collaboratif

### Merging
- Processus d'intégration via Pull Requests
- Importance des revues de code
- Gestion de l'historique après fusion

### Gestion des Conflits
- Diagnostic et résolution manuelle
- Compréhension des marqueurs de conflit
- Stratégies de prévention efficaces

## 🚀 Commandes Essentielles Maîtrisées
```bash
# Branching
git checkout -b nouvelle-branche
git branch
git push origin nom-branche

# Merging
git merge branche-source
git push origin main

# Conflits
git status (identification)
# Résolution manuelle + git add + git commit
