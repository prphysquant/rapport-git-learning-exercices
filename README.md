# Projet d'Apprentissage Git/GitHub

**Réalisé par:**MANOMI AGYAOU Abdoul Magid**  
- GitHub: [@prphysquant](https://github.com/prphysquant)  
- Formation:  Développement CODELOCCOL 
- Projet: Apprentissage des outils Devps  
**Documentation personnelle -  07 Octobre 2025**

## Description
Ce projet documente mon parcours d'apprentissage des concepts fondamentaux de Git et GitHub à travers la résolution de trois exercices pratiques qu'a donné le staff CodeLoccol. J'ai traité les Exercices à la limite de mes pratiques et recherches.

## Table des Matières
Dans ce README.md, j'ai inclu les liens vers les corrigés des 3 Exercices. Au besion, le pair ou le staff peut directement les consulter. Je n'ai pas utilusé la méthode de capture d'écran comme le fond les autres CS puisque cela n'a pas été demandé au niveau des spécifications dans la résolution des Exercices et la soumission.
- [Exercice 1: Premier Dépôt/Commit Simple](#exercice-1-premier-dépôtcommit-simple)
- [Exercice 2: Branching/Merging](#exercice-2-branchingmerging)
- [Exercice 3: Gestion des Conflits](#exercice-3-gestion-des-conflits)
- [Synthèse d'Apprentissage](#synthèse-de-mon-apprentissage)


## Exercice 1: Premier Dépôt/Commit Simple

### Compétences Acquises
- J'ai appris la création et clonage de repository via terminal;
- Puis la gestion basique d'un dépôt Git;
- Avce l'utilisation du workflow add → commit → push

### Commandes Exécutées (Résolution Exercice 1: Premier Dépôt/Commit Simple)
# Création et configuration du dépôt
gh repo create git-learning-1 --public
git clone https://github.com/prphysquant/git-learning-1.git
cd git-learning-1
echo "Mon premier projet Git" > README.md
git add README.md
git commit -m "Premier commit avec README.md"
echo "Je suis MANOMI AGYAOU Abdoul Magid, le numéro de mon Mac est le 14" >> README.md
git add README.md
git commit -m "Ajout de mes infos personnelles dans README.md"
git push origin main
Repository: [https://github.com/prphysquant/git-learning-1](https://github.com/prphysquant/git-learning-1)


---

## Exercice 2: Branching/Merging

### Compétences Acquises
- J'ai compris et appris la création et gestion de branches;
- Le processus de Pull Request;
- La fusion de branches (Merge);
- Démarche Suivie : j'ai plutôt opté pour une création manuelle du repository sur GitHub suite aux difficultés rencontrées avec la branche main via la création depuis le terminal.

### Commandes Exécutées (Résolution Exercice 2: Branching/Merging)bash
# Création et travail sur une branche
Après création depuis github du repo, je suis revenu sur le terminal pour le cloner et créer la branche myself
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
# Difficultés Rencontrées à cet Exercice comme je l'ai souligné dans ma démarche suivie
- La branche main n'était pas visible avec git branch malgré son existence à défaut lorsque je crée le repo depuis le terminal avec la commande gh repo create git-learning-2 --public et je clone.
- La création du repository via terminal plus complexe que prévu au début.
Repository:  [https://github.com/prphysquant/git-learning-2](https://github.com/prphysquant/git-learning-2)

---

### Exercice 3: Gestion des Conflits

# Compétences Acquises
- J'ai d'abord sur identifier des conflits de merge
- J'ai su les résoudre manuellement
- j'ai enfin appris à utiliser des outils de merge

# Commandes Exécutées
# Sur main d'abord
echo "Ligne écrite depuis la branche main" > notes.txt
git add notes.txt && git commit -m "Ajout notes depuis main" && git push
# Retour sur conflict-test (adaptation: notes.txt au lieu de note.txt, je ne sais pas si c''est une erreur mais cela ne marchais pas avec note.txt de l'énnoncé. j'ai dû prendre notes.txt comme tous les autres CS)
git checkout -b conflict-test
echo "Ligne écrite depuis la branche conflict-test" > notes.txt
git add notes.txt && git commit -m "Modif notes depuis conflict-test" && git push
# Retour sur main + modification conflictuelle
git checkout main
echo "Ligne écrite depuis la branche main pour la seconde fois" > notes.txt
git add notes.txt && git commit -m "Seconde modif notes depuis main" && git push
# Tentative de merge → CONFLIT
git merge conflict-test
# Résolution du Conflit
# Examen du fichier avec nano notes.txt :
text
<<<<<<< HEAD
Ligne écrite depuis la branche main pour la seconde fois
=======
Ligne écrite depuis la branche conflict-test
>>>>>>> conflict-test
>>>>>>> 
# Résolution manuelle :
text
Ligne écrite depuis la branche main pour la seconde fois
Ligne écrite depuis la branche conflict-test
# Finalisation :
git add notes.txt
git commit -m "Résolution conflit merge conflict-test"
git push
Repository: [https://github.com/prphysquant/git-learning-3](https://github.com/prphysquant/git-learning-3)


## Synthèse de mon apprentissage 
Durant la résolution pas croyable de ce projet GIT/GIT HUB avec ses trois Exercices.
# Concepts Clés Maîtrisés
- Repository : Dépôt contenant l'historique complet du projet
- Commit : Point de sauvegarde dans l'historique Git
- Branch : Ligne de développement indépendante
- Merge : Fusion du code d'une branche dans une autre
- Conflict : Modifications incompatibles sur les mêmes lignes de code
- Staging : Zone intermédiaire où on prépare les fichiers pour le commit
- Pull Request : Demande de fusion de code sur les plateformes comme GitHub
- Push/Pull : Synchronisation entre le repository local et distant
# Leçons Importantes
- Workflow Git : Maîtrise du cycle add-commit-push (processus organisé du début à la fin)
- Gestion des Branches : Compréhension de l'isolement des fonctionnalités
- Résolution de Conflits : Capacité à identifier et résoudre les problèmes de merge
- Collaboration : Utilisation des Pull Requests pour le travail d'équipe
# Bonnes Pratiques Identifiées
- Commits automatiques avec messages descriptifs
- Validation régulière avec git status
- Résolution immédiate des conflits

Je suis à la fin de ma présentation. Merci !
