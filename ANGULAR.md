## Entretien Technique Angular

### 1. Questions Théoriques

#### 1.1 Angular de base
- **Qu’est-ce qu’Angular et en quoi diffère-t-il d’AngularJS ?**
- **Expliquez le cycle de vie des composants Angular.**
- **Qu’est-ce qu’un Service en Angular et à quoi sert-il ?**
- **Comment fonctionne le mécanisme de data binding en Angular ?**
- **Qu’est-ce que le lazy loading et comment l’implémenter dans Angular ?**
- **Quelle est la différence entre `ngIf` et `hidden` en Angular ?**

#### 1.2 Composants, Directives et Signaux
- **Expliquez la différence entre les composants, les directives et les signaux en Angular. Comment sont-ils utilisés dans une application Angular ?**
- **Qu’est-ce qu’un Pipe en Angular et pouvez-vous en citer quelques-uns de base ?**
- **Comment gérez-vous les états dans une application Angular ? (RxJS, NgRx, Signaux, etc.)**

### 2. Exercices de Codage

#### Exercice 1 : Créer un composant Angular
**Objectif :** Créez un composant `UserListComponent` qui affiche une liste d’utilisateurs.

**Contraintes :**
- Utilisez un service `UserService` pour récupérer les données des utilisateurs.
- Affichez le nom et l’email de chaque utilisateur dans un tableau.

**Données mockées :**
```typescript
[
  { id: 1, name: 'Alice', email: 'alice@example.com' },
  { id: 2, name: 'Bob', email: 'bob@example.com' },
  { id: 3, name: 'Charlie', email: 'charlie@example.com' }
]
```

**Indications :**
- Utilisez `HttpClient` pour simuler une requête HTTP.
- Gérez le chargement des données avec `ngOnInit`.

#### Exercice 2 : Gestion des formulaires
**Objectif :** Créez un formulaire réactif pour ajouter un nouvel utilisateur.

**Contraintes :**
- Le formulaire doit contenir les champs suivants : `name`, `email`, et `password`.
- Validez que l’email est au bon format et que le mot de passe contient au moins 6 caractères.
- Affichez un message d’erreur si les champs ne sont pas valides.

**Indications :**
- Utilisez `FormBuilder`, `FormGroup`, et `FormControl`.
- Ajoutez des validateurs personnalisés si nécessaire.

#### Exercice 3 : Utilisation de RxJS ou Signaux

##### Option 1 (RxJS) :
- Créez un observable qui émet une valeur toutes les secondes.
- Affichez cette valeur dans le template.
- Ajoutez un bouton pour arrêter l’émission de valeurs.

##### Option 2 (Signaux) :
- Créez un compteur réactif en utilisant les signaux.
- Affichez la valeur du compteur et un bouton pour l’incrémenter.

**Indications :**
- **Pour RxJS :** Utilisez `interval` et gérez la souscription avec `ngOnDestroy`.
- **Pour les signaux :** Utilisez `signal` et `computed` pour gérer l’état réactif.

### 3. Questions Pratiques

#### 3.1 Optimisation et Bonnes Pratiques

##### Comment optimiser les performances d’une application Angular ?
- Utiliser le **lazy loading** pour les modules.
- Utiliser `OnPush` pour la stratégie de détection de changement.
- Éviter les expressions complexes dans les templates.
- Utiliser `trackBy` avec `ngFor` pour optimiser les listes.

##### Comment gérez-vous les erreurs HTTP dans une application Angular ?
- Intercepter les erreurs avec `HttpInterceptor`.
- Afficher des messages d’erreur conviviaux à l’utilisateur.
- Journaliser les erreurs pour le débogage.

##### Avez-vous déjà utilisé Angular Universal ? Si oui, dans quel contexte ?
- Angular Universal est utilisé pour le rendu côté serveur (SSR), améliorant le **SEO** et les **performances de chargement initial**.

##### Comment testeriez-vous un composant Angular ? (Jasmine, Karma, etc.)
- Utiliser **Jasmine** pour écrire des tests unitaires.
- Utiliser **Karma** comme exécuteur de tests.
- Tester les composants avec `TestBed`.

#### 3.2 Gestion d’État

##### Quels sont les avantages et inconvénients de l’utilisation de NgRx pour la gestion d’état ?
- **Avantages :** Centralisation de l’état, prévisibilité, outils de débogage puissants.
- **Inconvénients :** Courbe d’apprentissage, boilerplate code.

##### Quand utiliseriez-vous les signaux plutôt que RxJS pour la gestion d’état ?
- Les **signaux** sont idéaux pour des états simples et locaux.
- **RxJS** est plus adapté pour des **flux de données complexes ou asynchrones**.

#### 3.3 Questions de Comportement

- Pouvez-vous décrire un projet Angular sur lequel vous avez travaillé et les défis que vous avez rencontrés ?
- Comment gérez-vous les conflits dans une équipe de développement ?
- Comment restez-vous à jour avec les nouvelles versions d’Angular et les bonnes pratiques ?

### Conseils pour l’entretien

- **Pratiquez :** Utilisez un environnement comme **StackBlitz** ou **CodeSandbox** pour vous entraîner.
- **Communiquez :** Expliquez votre raisonnement pendant que vous codez.
- **Demandez des clarifications :** Si une question ou un exercice n’est pas clair, n’hésitez pas à demander plus d’informations.

### Exemple de Réponse Structurée (Markdown)

#### Question : Expliquez la différence entre les composants, les directives et les signaux en Angular.

| Fonctionnalité  | Composants  | Directives  | Signaux  |
|----------------|------------|------------|---------|
| **Rôle** | Gère une partie de l’UI. | Modifie le comportement ou l’apparence des éléments DOM. | Gère l’état réactif de manière simple et performante. |
| **Utilisation** | Pour créer des blocs d’interface utilisateur réutilisables. | Pour ajouter des comportements dynamiques aux éléments existants. | Pour gérer des états réactifs sans RxJS. |
| **Exemple** | Afficher une liste d’utilisateurs. | Appliquer un style conditionnel. | Gérer un compteur réactif. |

---
