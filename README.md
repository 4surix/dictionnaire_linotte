
# Explication

Petit module pour utiliser les dictionnaires (ou tableau associatif) en [Linotte](https://github.com/cpc6128/LangageLinotte).  
  
Il y a plusieurs dossiers suivant la version de Linotte pour s'adapter à la syntaxe de la version, prennez le dosier qui correspond à la version que vous utilisez.  
  
Pour utiliser le module, mettez le fichier `dictionnaire.liv` dans le même dossier que votre programme, et importez le avec : `NOM QUE VOUS VOULEZ référence dictionnaire.liv`.  

# Aperçu

```js
Bibliothèque
    dict référence dictionnaire.liv

Principale :
    légumes est un dictionnaire
    Début

        légumes.clef("haricot", "vert")
        légumes.clef("haricot", "blanc")
        légumes.clef("tomate", "rouge")
        légumes.clef("piovron", "jaune")

        Affiche légumes.valeur("tomate")

        légumes.suppr_clef("tomate")

        Pour chaque légumes.items()
            Affiche "La couleur de {clef@joker} est {valeur@joker}."
        §
```

# Documentation

## Attributs

### clefs

Contient toutes les clefs du dictionnaires.

```js
Pour chaque clefs de dict
    Affiche joker
§
```

### valeurs

Contient toutes les valeurs du dictionnaires.

```js
Pour chaque valeurs de dict
    Affiche joker
§
```

## Méthodes

### clefs

Renvoie un texte présentant toutes les clefs du dictionnaire.

```js
Affiche dict.clefs()
```

### valeurs

Renvoie un texte présentant toute les valeurs du dictionnaire.

```js
Affiche dict.valeurs()
```

### clefs_valeurs

Renvoie un texte présentant toute les clefs et valeurs du dictionnaire.

```js
Affiche dict.clefs_valeurs()
```

### clef(clef, valeur)

Ajoute une clef qui a pour valeur la valeur indiquée.  
Si la clef exitait déjà, sa valeur est remplacée par la nouvelle valeur.  
  
Renvoie `vrai`.  

```js
dict.clef("pomme", "verte")
```

#### Erreurs

- `110030`, La clef n'est pas un texte.
- `110035`, La valeur n'est pas un texte.

### valeur(clef)

Renvoie la valeur de clef.  

```js
valeur pomme vaut dict.valeur("pomme")
```

#### Erreur

- `110020`, la clef n'exite pas dans ce dictionnaire.

### suppr_clef(clef)

Supprime la clef du dictionnaire.  

```js
dict.suppr_clef("pomme")
```

#### Erreur

- `110020`, la clef n'exite pas dans ce dictionnaire.

### longueur

Renvoie la longueur du dictionnaire, dit autrement, le nombre de clef dans le dictionaire.  

```js
dict.longueur()
```

### items

A utiliser dans une boucle `pour`.  
Affecte à `joker` l'espèce `item` qui à pour attribut `clef` et `valeur`.   

```js
Pour chaque dict.items()
    clef de joker !
    valeur de joker !
§
```