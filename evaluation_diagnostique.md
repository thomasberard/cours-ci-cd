# Évaluation diagnostique – Formation CDA CI/CD
**Durée : 1h | Aucun document, aucun internet autorisé**

---

## Partie 1 – QCM (20 min | 15 questions)

*Une seule bonne réponse sauf mention contraire.*

---

**Q1. Quelle commande crée une branche ET se positionne dessus en même temps ?**

a) `git branch ma-branche`\n
b) `git checkout ma-branche`\n
c) `git checkout -b ma-branche`\n
d) `git push origin ma-branche`\n

---

**Q2. Que fait `git stash` ?**

a) Supprime les fichiers non suivis
b) Crée une nouvelle branche avec les modifications en cours
c) Sauvegarde temporairement les modifications non commitées sans créer de commit
d) Annule le dernier commit

---

**Q3. Quelle est la différence entre `git merge` et `git rebase` ?**

a) `merge` supprime l'historique, `rebase` le conserve
b) `merge` crée un commit de fusion visible, `rebase` rejoue les commits sur une nouvelle base
c) `rebase` fusionne deux branches, `merge` les sépare
d) Il n'y a aucune différence fonctionnelle

---

**Q4. Que contient le fichier `.gitignore` ?**

a) La liste des fichiers à commiter en priorité
b) La liste des fichiers et dossiers que Git doit ignorer
c) La configuration du dépôt distant
d) Les règles de nommage des branches

---

**Q5. Que retourne ce code JavaScript ?**
```js
console.log(typeof null);
```

a) `"null"`
b) `"undefined"`
c) `"object"`
d) `"boolean"`

---

**Q6. Quelle est la bonne façon de gérer une erreur avec `async/await` ?**

a) `if (err) return`
b) `.catch(err => {})`
c) `try { await maFonction() } catch (err) { console.error(err) }`
d) `async.error(() => {})`

---

**Q7. Que fait `npm ci` par rapport à `npm install` ?**

a) C'est identique
b) `npm ci` installe exactement ce qui est dans `package-lock.json` sans le modifier
c) `npm ci` n'installe que les dépendances de production
d) `npm ci` supprime les devDependencies

---

**Q8. Dans le pattern AAA, que signifie le premier A ?**

a) Assert
b) Async
c) Arrange
d) Action

---

**Q9. Quelle commande Jest génère un rapport de couverture de code ?**

a) `jest --report`
b) `jest --coverage`
c) `jest --analyse`
d) `jest --inspect`

---

**Q10. Que teste ce code ?**
```js
expect(() => divide(10, 0)).toThrow('Division par zéro');
```

a) Que `divide(10, 0)` retourne `0`
b) Que `divide(10, 0)` retourne `undefined`
c) Que `divide(10, 0)` lève une erreur avec le message "Division par zéro"
d) Que `divide` est une fonction asynchrone

---

**Q11. Quelle est la différence entre `toBe` et `toEqual` dans Jest ?**

a) `toBe` compare les valeurs primitives avec `===`, `toEqual` compare la structure profonde des objets
b) `toBe` est pour les strings, `toEqual` pour les nombres
c) Il n'y a aucune différence
d) `toEqual` est plus rapide que `toBe`

---

**Q12. Qu'est-ce que l'intégration continue (CI) ?**

a) Déployer automatiquement en production à chaque commit
b) Automatiser la vérification du code (tests, lint, build) à chaque push
c) Intégrer une base de données dans l'application
d) Fusionner deux projets Git

---

**Q13. Dans quel fichier Jenkins décrit-on un pipeline as code ?**

a) `jenkins.yml`
b) `pipeline.json`
c) `Jenkinsfile`
d) `.ci/config.groovy`

---

**Q14. Que fait ce bloc dans un Jenkinsfile ?**
```groovy
when { branch 'main' }
```

a) Crée la branche main
b) Supprime la branche main après le build
c) Conditionne l'exécution du stage uniquement si on est sur la branche main
d) Empêche de merger dans main

---

**Q15. Quelle est la bonne pratique concernant les secrets dans Jenkins ?**

a) Les stocker en clair dans le Jenkinsfile
b) Les mettre dans une variable d'environnement dans le code source
c) Les stocker dans le Jenkins Credentials Store et les injecter via `withCredentials`
d) Les envoyer par email à l'équipe

---

## Partie 2 – Questions ouvertes (20 min | 4 questions)

*Réponses courtes attendues — 3 à 5 lignes maximum.*

---

**Q1. Expliquez avec vos mots la différence entre `git reset` et `git revert`. Dans quel cas utilisez-vous l'un plutôt que l'autre ?**

&nbsp;

&nbsp;

&nbsp;

---

**Q2. Qu'est-ce que le principe SRP (Single Responsibility Principle) ? Donnez un exemple concret d'une fonction qui le viole et comment la corriger.**

&nbsp;

&nbsp;

&nbsp;

---

**Q3. Expliquez la pyramide des tests. Pourquoi investit-on davantage dans les tests unitaires que dans les tests e2e ?**

&nbsp;

&nbsp;

&nbsp;

---

**Q4. Quelle est la différence entre Continuous Integration, Continuous Delivery et Continuous Deployment ?**

&nbsp;

&nbsp;

&nbsp;

---

## Partie 3 – Extraits de code à analyser (20 min | 3 exercices)

---

### Exercice 1 – Trouver les bugs (7 min)

Ce code contient **3 bugs**. Identifiez-les et expliquez pourquoi c'est un bug.
```js
const users = [];
let nextId = 1;

function createUser(name, email) {
  if (name == null || email == null) {
    return false;
  }

  const user = {
    id: nextId,
    name: name,
    email: email,
    createdAt: Date()
  };

  users.push(user);
  nextId++;
  return user;
}

function getUserById(id) {
  for (let i = 0; i <= users.length; i++) {
    if (users[i].id === id) {
      return users[i];
    }
  }
  return null;
}
```

**Bug 1 (ligne ___)** :

&nbsp;

**Bug 2 (ligne ___)** :

&nbsp;

**Bug 3 (ligne ___)** :

&nbsp;

---

### Exercice 2 – Lire un historique Git (7 min)

Voici un extrait de `git log --oneline` :
```
a3f9c12 fix
b7d2e45 modif login
c9f1a33 wip
d4e8b21 feature user done finally
e2c7d09 test
f1a3b56 add stuff
```

**1. Quel est le problème avec cet historique ?**

&nbsp;

&nbsp;

**2. Réécrivez les 6 messages en respectant la convention Conventional Commits.**
```
a3f9c12 →
b7d2e45 →
c9f1a33 →
d4e8b21 →
e2c7d09 →
f1a3b56 →
```

**3. Parmi ces commits, lequel correspond probablement à une nouvelle fonctionnalité ? Lequel à une correction de bug ?**

&nbsp;

&nbsp;

---

### Exercice 3 – Lire un Jenkinsfile (6 min)
```groovy
pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Install') {
            steps {
                sh 'npm ci'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp -r dist/ user@prod.example.com:/var/www'
            }
        }
    }
}
```

**1. Ce pipeline contient une erreur d'ordre logique évidente. Laquelle ?**

&nbsp;

&nbsp;

**2. Quel risque pose le stage `Deploy` tel qu'il est écrit ?**

&nbsp;

&nbsp;

**3. Corrigez le stage `Deploy` pour qu'il ne s'exécute que sur la branche `main`.**
```groovy
stage('Deploy') {




}
```