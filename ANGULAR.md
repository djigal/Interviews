# Interviews

# Qu’est-ce qu’Angular et en quoi diffère-t-il d’AngularJS ?
## Definition
Angular est un framework front-end open-source basé sur TypeScript, développé par Google. Il permet de créer des applications web dynamiques et modulaires en utilisant des composants, des services et des modules.

## Différences avec AngularJS :

- **AngularJS (version 1.x)** utilise JavaScript et est basé sur le modèle MVC (Modèle-Vue-Contrôleur), tandis qu'**Angular (2+)** utilise TypeScript et est basé sur une architecture de composants.
- **AngularJS** utilise un système de data binding bidirectionnel avec `$scope`, tandis qu'**Angular** utilise un système de data binding plus performant et explicite.
- **Angular** est plus performant, modulaire et adapté aux applications modernes.

---

# Expliquez le cycle de vie des composants Angular.

Le cycle de vie d’un composant Angular est géré par des hooks (méthodes) qui sont appelés à différents stades de la vie du composant. Voici les principaux hooks :

- `ngOnChanges` : Appelé lorsqu’une propriété d’entrée (`@Input`) change.
- `ngOnInit` : Appelé une fois après la première initialisation des propriétés d’entrée.
- `ngDoCheck` : Appelé à chaque cycle de détection de changement.
- `ngAfterContentInit` : Appelé après que le contenu projeté (via `ng-content`) est initialisé.
- `ngAfterContentChecked` : Appelé après chaque vérification du contenu projeté.
- `ngAfterViewInit` : Appelé après l’initialisation de la vue du composant.
- `ngAfterViewChecked` : Appelé après chaque vérification de la vue du composant.
- `ngOnDestroy` : Appelé avant la destruction du composant (pour nettoyer les ressources).

---

# Qu’est-ce qu’un Service en Angular et à quoi sert-il ?

Un **Service** en Angular est une classe annotée avec `@Injectable` qui fournit des fonctionnalités réutilisables à travers l’application.

## Utilisation :

- **Centraliser la logique métier** (par exemple, les appels HTTP).
- **Partager des données entre composants**.
- **Isoler les responsabilités** pour une meilleure maintenabilité.

Les services sont injectés via le système de dépendance (**Dependency Injection**) d’Angular.

---

# Comment fonctionne le mécanisme de data binding en Angular ?

Le **data binding** est un mécanisme qui synchronise les données entre le composant et le template. Angular propose plusieurs types de data binding :

- **Interpolation** : `{{ valeur }}` → Affiche des données dans le template.
- **Property Binding** : `[property]="valeur"` → Lie une propriété d’un élément DOM à une variable.
- **Event Binding** : `(event)="méthode()"` → Lie un événement DOM à une méthode du composant.
- **Two-Way Binding** : `[(ngModel)]="valeur"` → Synchronise les données dans les deux sens (**composant ⇄ template**).

---

# Qu’est-ce que le lazy loading et comment l’implémenter dans Angular ?

**Lazy Loading** est une technique qui charge les modules Angular uniquement lorsqu’ils sont nécessaires, améliorant ainsi les performances de l’application.

## Implémentation :

Dans le fichier de routage (`app-routing.module.ts`), utilisez la syntaxe suivante :

```typescript
const routes: Routes = [
  { path: 'feature', loadChildren: () => import('./feature/feature.module').then(m => m.FeatureModule) }
];
```

Cela charge le module `FeatureModule` uniquement lorsque l’utilisateur navigue vers la route `/feature`.

---

# Quelle est la différence entre `ngIf` et `hidden` en Angular ?

### `ngIf` :

- **Supprime ou ajoute** un élément du DOM en fonction de la condition.
- **Optimise les performances** en évitant de rendre des éléments inutiles.

**Exemple :**
```html
<div *ngIf="condition">Contenu</div>
```

### `hidden` :

- **Masque ou affiche** un élément en utilisant **CSS (`display: none`)**.
- **L’élément reste dans le DOM**, mais n’est pas visible.

**Exemple :**
```html
<div [hidden]="!condition">Contenu</div>
```

---

# Comment gérez-vous les états dans une application Angular ?

### Gestion d’état :

- **Services** : Utiliser des services pour partager des données entre composants.
- **RxJS** : Utiliser des `BehaviorSubject` ou `ReplaySubject` pour gérer des états réactifs.
- **NgRx** : Utiliser une bibliothèque de gestion d’état basée sur Redux pour les applications complexes.

**NgRx** utilise des **actions, réducteurs et un store** pour gérer l’état de manière prévisible.

---

# Qu’est-ce qu’un Pipe en Angular et pouvez-vous en citer quelques-uns de base ?

Un **Pipe** est une fonction qui transforme les données avant de les afficher dans le template.

### Pipes intégrés :

- `{{ valeur | uppercase }}` → Convertit en majuscules.
- `{{ valeur | date:'dd/MM/yyyy' }}` → Formate une date.
- `{{ valeur | currency:'EUR' }}` → Formate une valeur en devise.
- `{{ valeur | json }}` → Affiche un objet sous forme de JSON.

### Pipes personnalisés :

Vous pouvez créer des pipes personnalisés en implémentant l’interface `PipeTransform`.


---

# Bonus : Questions Pratiques

## Optimisation des performances :

- Utiliser le **lazy loading** pour les modules.
- Utiliser **OnPush** pour la stratégie de détection de changement.
- Éviter les **expressions complexes** dans les templates.
- Utiliser **trackBy** avec `ngFor` pour optimiser les listes.

## Gestion des erreurs HTTP :

- Intercepter les erreurs avec **HttpInterceptor**.
- Afficher des **messages d’erreur conviviaux** à l’utilisateur.
- Journaliser les erreurs pour le débogage.

## Angular Universal :

- Utilisé pour le **rendu côté serveur (SSR)**, améliorant le **SEO** et les performances de chargement initial.

## Tests :

- Utiliser **Jasmine** pour écrire des tests unitaires.
- Utiliser **Karma** comme exécuteur de tests.
- Tester les composants avec **TestBed**.
