## Table des matières
1. [Info General](#infos)
2. [Répartition des tâches](#répartition-des-tâches)
3. [ESLint](#ESLint)
4. [Syntaxe de code](#syntaxes)
5. [Definition of Done](#definition-of-done)
6. [Documentation](#documentation)
7. [Liens utiles](#liens)


### Infos
Cette documentation sert de guide aux projets informatique de l'entreprise Loc’Fast et explique les bonnes pratiques de code à respecter pour garder un code maintenable.

### Répartition des tâches

### ESLint

Nous utilisons ESLint pour les raisons suivants :
- la détection des erreurs
- la détection de syntaxe et de style non valide afin de dépersonnalisé le code. Nos règles concernant la syntaxe et le style sont disponible [ici](#syntaxes)

### Syntaxes
##### Chaînes de caractères
- Utilisez les apostrophes (single quotes) `''` pour les chaînes de caractères.
```javascript
// pas bien
const nom = "Bob Parr";

// pas bien - un template littéral devrait contenir des interpolations ou de nouvelles lignes
const nom = `Bob Parr`;

// bien
const nom = 'Bob Parr';
```
##### Bloc 
- Entourez d'accolades tous vos blocs contenus sur plusieurs lignes.
```javascript
// pas bien
if (test)
  return false;

// bien
if (test) return false;

// bien
if (test) {
  return false;
}

// pas bien
function() { return false; }

// bien
function() {
  return false;
}
```
##### Commentaire
- Utilisez `/** ... */` pour des commentaires qui s'étendent sur plusieurs lignes. Insérez une description, spécifiez les types et valeurs par défaut pour tous les paramètres et les valeurs de retour.
```javascript
// pas bien
// make() returns a new element
// based on the passed in tag name
//
// @param <String> tag
// @return <Element> element
function make(tag) {

  // ...stuff...

  return element;
}

// bien
/**
 * make() returns a new element
 * based on the passed in tag name
 *
 * @param <String> tag
 * @return <Element> element
 */
function make(tag) {

  // ...stuff...

  return element;
}
```
- Utilisez `//` pour les commentaires d'une seule ligne. Placez-les sur une nouvelle ligne au-dessus du sujet du commentaire. Ajoutez une ligne vide au-dessus du commentaire.
```javascript
// pas bien
var active = true;  // is current tab

// bien
// is current tab
var active = true;

// pas bien
function getType() {
  console.log('fetching type...');
  // set the default type to 'no type'
  var type = this._type || 'no type';

  return type;
}

// bien
function getType() {
  console.log('fetching type...');

  // set the default type to 'no type'
  var type = this._type || 'no type';

  return type;
}
```
##### Convention de nommage
- Évitez les noms ne faisant qu'une seule lettre. Soyez descriptifs dans votre déclaration.
```javascript
// pas bien
function q() {
  // ...stuff...
}

// bien
function query() {
  // ..stuff..
}
```
- Utilisez la camelCase lorsque vous nommez vos objets, fonctions et instances.
```javascript
// pas bien
var OBJEcttsssss = {};
var this_is_my_object = {};
function c() {};
var u = new user({
  name: 'Bob Parr'
});

// bien
var thisIsMyObject = {};
function thisIsMyFunction() {};
var user = new User({
  name: 'Bob Parr'
});
```
- Utilisez la PascalCase lorsque vous nommez vos constructeurs ou vos classes.
```javascript
// pas bien
function user(options) {
  this.name = options.name;
}

var bad = new user({
  name: 'nope'
});

// bien
function User(options) {
  this.name = options.name;
}

var good = new User({
  name: 'yup'
});
```
- Ajoutez un underscore `_` au début du nom de vos propriétés privées.
```javascript
// pas bien
this.__firstName__ = 'Panda';
this.firstName_ = 'Panda';

// bien
this._firstName = 'Panda';
```
##### Accesseurs
- Si vous faites des fonctions d'accès, utilisez getVal() et setVal('salut').
```javascript
// pas bien
dragon.age();

// bien
dragon.getAge();

// pas bien
dragon.age(25);

// bien
dragon.setAge(25);
```
- Si la propriété est un booléen, utilisez isVal() ou hasVal().
```javascript
// pas bien
if (!dragon.age()) {
  return false;
}

// bien
if (!dragon.hasAge()) {
  return false;
}
```
### Definition of Done
La definition of done (dod) ici présente sert à garantir la qualité de la production en définissant dans quel cadre une user story peut être validé ou non. 
De manière globale, pour qu'une user story soit validée, il faut au minimum :
- que les tests définis dans la user story soit réalisé et passés avec succès. 
- le product owner a vu la démo et valide le fonctionnement.

### Documentation

### Liens
- https://nodejs.org/en/
- https://www.w3schools.com/nodejs/
- https://fr.reactjs.org/
- https://fr.reactjs.org/tutorial/tutorial.html
- https://flutter.dev/

https://github.com/airbnb/javascript/blob/master/README.md
