# Jquery-Cheat-Sheets

Ce Sheat-sheet est inspiré de ce [cours](https://openclassrooms.com/fr/courses/1631636-simplifiez-vos-developpements-javascript-avec-jquery)

Jquery est une librairie qui permet de manipuler des éléments mise en place par le HTML et mise en par le CSS grâce à JavaScript et AJAX

## Selection des éléments 
Voci le syntade de base 
```
$(sélection)
// "sélection" est un selecteur CSS
```
Exemple concret
```
$('ul.bleu)
// Sélection de la balise <ul> de la classe bleu

$('li[class]')
// Sélection de tous les balises <li> possédant une classe

$('*');
// Sélection de tous les balises

$('#hola')
// Selection de l'id "hola")

$('.rouge)
Sélection de la classe "rouge"
```
Tous élément retourner par un la fonction "$()" ressemble à un tableau.
A ce titre on peut le parcourir
```
$('li[class="impair"]').length;
// Retourne le nombre de balise <li> ayant la classe "impair"

$('ul.bleau')[3]
// Retourne la 4ème balise <ul> de la classe bleu
```


## Sélecteurs avancés
```
$('.fermier*="eleveur")
// Elémént qui contient partiellement ou totalement la valeur "éleveur"
```
```
$('['title~="animal"]')
// Sélection de l'attribut "title" contenant le mot "animal" délimité par un espace
```
```
$('[src$="e.jpg"]')
// Sélectin de l'attribut "src" dont la valeur se termine par "e.jpg"
```
```
$('[border!="15"]')
// Selection de l'attribut border don't la valeur n'est pas égal à 15
```
```
$('[src^="ch"]')
// Sélection de l'attribut "src" dont la valeur commence par "ch"
```


## Sélecteurs hiérarchiques
```
$('li > ul')
// Sélection des éléments <ul> directement situés en dessus d'éléments <li>
```
```
$('li + li')
// Sélection d'éléments <li> directement précédés d'éléments <li>
```
```
$('li:first-child')
// Sélection du premier enfant de <li>
```
```
$('li:first')
// Sélection du premier <li>
```
```
$('li:nth-child(2)')
// Sélection du 2ème enfant de <li>
```

## Pseudo-sélecteurs d'éléments sélectionnés
Exemple HTML d'illustration
```
  <p>Paragraphe 1</p>
    <p>Paragraphe 2</p>
    <p>Paragraphe 3</p>
    <p>Paragraphe 4</p>
    <p>Paragraphe 5</p>   
  </body>
```
```
$('p:even)')
// Sélection de <p> pairs
```
```
$('p:odd')
// Sélection de <p> impairs
```
```
$('p:gt(1)')
// Sélection de tous les <p> qui se trouvent après le 2ème  <p> 
```
```
$('p:eq(3)')
// Sélection du 4ème <p>
```
```
$('p:lt(3)')
// Sélection de tous les <p> qui se trouvent avant le 4ème <p>
```


## Sélecteur d'éléments particuliers
Exemple HTML d'illustration
```
  <body>
    <h1>Titre de niveau 1</h1>
    <h2>Titre de niveau 2</h2>
    <h3>Titre de niveau 3</h3>
    <p>Un paragraphe de texte</p>
    <div>Texte dans une balise div</div>

    <script src="jquery.js"></script>
    <script>
      $(function() {
        $('div').hide();
        //Le code jQuery sera inséré ici
      }); 
    </script>
  </body>
```
```
$(':header').css('color','red');
// Tous les titres sont affichés en rouge
```
```
$('div:hidden').show();
// La <div> cachée est affiché
```
```
$(':header:not(h1)').hide();
// Tous les titres excepté <h1> sont cachés
```

## Accéder aux attributs HTML et CSS
```
$('#plus').attr('src');
// Lis, crée ou modifie l'attribut "src" de l'id "#plus
```
```
$('div').attr('class', 'madiv');
// Modifie ou crée l'attribut class="madiv" pour la balise <div>
```
```
$('a').removeAttr('href')
// Supprime l'attribut 'href' de tous les <a>
```

```
$('#pierre').removeClass('vert').addClass('rouge').removeClass('grand').addClass('petit');
// removeclass : supprime la classe
// addclass : ajoute une classe
```
```
$('#paul').toggleClass('vert').toggleClass('rouge').toggleClass('grand').toggleClass('petit');
toggleClass : ajoute s'il la classe n'éxiste pas ou supprime la classe existe
```
Tester l'existence d'une classe
```
if ($('#jean').hasClass('rouge'))
  alert('le span #jean est de classe rouge');
else
  alert('le span #jean n\'est pas de classe rouge');
// La méthode hasClass : test si la classe existe
```
