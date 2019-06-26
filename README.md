# Jquery-Cheat-Sheets

Ce Sheat-sheet est inspiré de ce [cours](https://openclassrooms.com/fr/courses/1631636-simplifiez-vos-developpements-javascript-avec-jquery). 
Il a pour but de se familiariser avec certaines méthodes de la librairie JQuery.

Jquery est une librairie qui permet de manipuler des éléments mise en place par le HTML et mise en par le CSS grâce à JavaScript et AJAX

## Selection des éléments 
Voci le syntaxe de base 
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
Requête Jquery
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
### Tester l'existence d'une classe
```
if ($('#jean').hasClass('rouge'))
  alert('le span #jean est de classe rouge');
else
  alert('le span #jean n\'est pas de classe rouge');
// La méthode hasClass : test si la classe existe
```

### Les méthodes .html() et .text()
```
$('h1:first').html()
// retourne le code HTML de <h1> (balise + texte)

$('p:first').html('<a href="http://www.google.com">Moteur de recherche Google</a>');
// Modifie le code HTML du 1er <p> en <a>
```

```
$('h1:first').text()
// retourne le texte de <h1> (que le texte)

$('p:first').text('Hola quetal');
// Modifie le texte 1er <p>
```

### Travailler sur un formulaire
Exemple HTML d'illustration 
```
    <form>
      Nom d'utilisateur
      <input type="text" id="nom"><br />

      Mot de passe
      <input type="password" id="pass"><br />

      Sexe 
      H <input type="radio" id="H" name="sexe" value="H">
      F <input type="radio" id="F" name="sexe" value="F"><br />

      Fonction
      <select id="fonction">
        <option VALUE="etudiant">Etudiant</option>
        <option VALUE="ingenieur">Ingénieur</option>
        <option VALUE="enseignant">Enseignant</option>
        <option VALUE="retraite">Retraité</option>
        <option VALUE="autre">Autre</option>
      </select><br /><br />

      <input type="submit" id="envoyer" value="Envoyer">
      <input type="reset" id="annuler" value="Annuler">
    </form> 

```
Requête Jquery
```
$('#nom').val()
// Lit le nom
```
```
$(':radio#H:checked').val()
// Lit l'état du bouton radio "H"
```
```
$('#nom').val('Sonia')
// Ecrit "Sonia" dans la zone de texte
```
```
$('#fonction').val('retraite')
// Sélectionne "retraite" dans la liste déroulante
```

## Position et taille des éléments .offset(); et .position();
Exemple d'illustration
```
 <style type="text/css">
      #parent {
        width: 300px;
        height:300px;
        position: absolute;
        top: 100px;
        left: 200px;
        background-color: yellow;
      }
      
      #enfant {
        width: 100px;
        height:100px;
        position: absolute;
        top: 150px;
        left: 100px;
        background-color: red;
      }
    </style>
  </head>
  <body>
    <div id="parent">
      Texte dans le parent
      <div id="enfant">
        Texte dans l'enfant
      </div>
    </div>
    <span id="resultat"></span>    
    
    <script src="jquery.js"></script>
    <script>
      $(function() {
        // Entrer les instructions jQuery ici
      }); 
    </script>
  </body>
```

Requête Jquery 
```
var posparent=$('#parent').offset();
var posenfant=$('#enfant').offset();
$('span').text('Parent : x=' + posparent.left + ', y=' + posparent.top + ' Enfant : x=' + posenfant.left + ', y=' + posenfant.top);
// La méthode .offset() récupérer la position de l'élémet sur la page
```
```
var posparent=$('#parent').position();
var posenfant=$('#enfant').postition();
$('span').text('Parent : x=' + posparent.left + ', y=' + posparent.top + ' Enfant : x=' + posenfant.left + ', y=' + posenfant.top);
// La méthode .position() va récupérer la position de chaque élément par rapport à son parent
```

## Insérer et remplacer des éléments dans le DOM
Code d'illustration HTML
```
<body>
    <h2 id="un">Lorem ipsum</h2>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
      Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
    </p>
    <hr>

    <h2 id="deux">Lorem ipsum suite</h2>
    <p>
      Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
      Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </p>
    <hr>

    <h2 id="trois">Liste à puces</h2>
    <ul>
      <li>Premier élément</li>
      <li>Deuxième élément</li>
      <li>Troisième élément</li>
      <li>Quatrième élément</li>
    </ul>      
    
    <script src="jquery.js"></script>
    <script>
      $(function() {
        // Insérer le code jQuery ici
        }); 
    </script>
  </body>
```

### Insérer du contenu
```
$('h2').append(' ***'); // ajoute juste après
$('h2').prepend(' ***'); // ajoute juste avant
$('#trois').before(' <hr>'); // ajoute une ligne de séparation juste avant "#trois"
$('hr').after('<br><br>'); // ajoute 2 sauts de lignes après <hr>
```

### Remplacer des éléments
```
$('hr').replaceWith('<br>');
// Remplace la ligne horizontale par un saut de ligne 
```

### Insérer des éléments
```
$('<li>Deuxième élément bis</li>').insertAfter($('li:nth-child(2)'));
// insé=ère d'un élément après le 2ème <li>

$('<li>Deuxième élément bis</li>').insertBefore($('li:nth-child(2)'));
// insère un élément avant le 2ème élément
```
 Voici les 4 méthodes :
  - .appendTo(); insère un élément à la fin de la cible
  - .afterTO(); insère un élément au début de la cible
  - .insertBefore(); insère un élément avant la cible
  - .insertAfter(); insère un élément après la cible

### Déplacer le contenu
Schéma 
```
$('sel').after(depl);
// "sel" repésente l'élément après lequel doit se faire le déplacement et "depl" l'élément à déplacer
```
 Voici les 4 méthodes :
  - .append(); le déplacement va se faire avant la balise de fin de l'élément séléctionné
  - .after(); le déplacement va se faire après la balise de fin de l'élément séléctioné
  - .prepend(); le déplacement va se faire après la balise de début de l'élément séléctionné
  - before(); le déplacement va se faire avant la balise de début de l'élément séléctionné

### Dupliquer des éléments
```
$('ul').clone().insertBefore($('h2:first'));
// séléctionne la balise <ul> et ses anfants puis les duplique (.clonc())avant la 1er balise <h2>
```
### Entourer les éléments
```
$('li').wrap('<i></i>'); // résultat : <i><p>Le texte du paragraphe</p></i>
// L'élément <li> sera entouré d'éléments <i>  au début et </i> à la fin
```
```
$('p').wrapInner('<i></i>'); //  résultat : <p><i>Le texte du paragraphe</i></p>
Les les éléments <i></i> seront placés à l'intérieur des du sélecteur "p"
```
```
$('p').wrapAll('<div></div>');
// résultat : 
// <div>
//  <p>Paragraphe 1</p>
//  <p>Paragraphe 2</p>
//  <p>Paragraphe 3</p>
//  <p>Paragraphe 4</p>
// </div>
// Séléctionne tous les "p" et les entoure d'éléments <div></div>
```

### Supprimer
```
$('li:nth-child(2)').remove();
Supprime le 3ème <li>
```
