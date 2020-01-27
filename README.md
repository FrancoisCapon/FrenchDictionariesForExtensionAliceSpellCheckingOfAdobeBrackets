#  :fr: Dictionnaires français pour Adobe Brackets :desktop_computer: :book: 

**Il est possible d'ajouter des dictionnaires Hunspell à l'extension Alice - Spell Checking pour Brackets.**

Après un premier essai avec les dictionnaires français Grammalecte, je me suis rendu compte que l'extension ne fonctionne correctement que si les dictionnaires n'ont pas de champs optionnels d'où le dépôt [Dictionnaires Grammalecte sans champs optionnels](https://github.com/FrancoisCapon/GrammalecteDictionariesWithoutOptionalDataFields).

## :one: Installation de l'extension Alice - Spell Checking (si nécessaire)

Ces dictionnaires sont utilisés par cette extension qui doit donc être installée en premier : 
1. `Fichier > Gestionnaire d'extensions`
1. `Rechercher : Alice Spell`
1. `[Installer]`
1. `[Download Dictionnaries]`

Après redémarrage de Brackets, les extensions du correcteur et ses dictionnaires (anglais) sont installés.

Les réglages (`Proofing Options ▼`) :
* Activation / Désactivation
* Fixer le dictionnaire par défaut
* Choix du dictionnaire

sont disponibles dans la barre d'état (en bas) juste après le choix de l'encodage (`UTF-8 ▼`). 

###  Le dossier des extensions de Brackets et l'extension Alice - Spell Checking

Le chemin du dossier dépendant de nombreux facteurs (OS, version portable), le plus simple pour y accéder est de passer par les menus : 
* `Aide > Afficher le dossier d'extensions`

```
disabled
user
    auteur.extension
    ...
    stillat.linguistics ◀ le correcteur
    stillat.linguistics-dictionary
        natural-languages ◀ les dictionnaires
            ...
            en_US
                en_US.aff ◀ les règles d'affixe
                en_US.dic ◀ la liste des mots
                language.json ◀ les informations du dictionnaire
            ...
            en_ZA
    ...
    
```

```
stillat.linguistics-dictionary/natural-languages/en_US/language.json
{
    "locale": "en_US", ◀ obligatoire = le nom dossier, .aff et .dic
    "name": "English (United States)", ◀ obligatoire = affiché dans le menu de sélection
    "description": "",
    "version": "1.0.0",
    "author": "",
    "url": "",
    "releaseDate": ""
}
```


## :two: Installation des dictionnaires français
### Les 4 versions du dictionnaire français
* **Dictionnaire "Moderne"** : ce dictionnaire propose une sélection des graphies classiques et réformées, suivant la lente évolution de l'orthographe actuelle. Ce dictionnaire contient les graphies les moins polémiques de la réforme.

* **Dictionnaire "Classique" [recommandé]** : ce dictionnaire est une extension du dictionnaire « Moderne » et propose en sus des graphies alternatives, parfois encore très usitées, parfois tombées en désuétude.

* **Dictionnaire "Réforme 1990"** : ce dictionnaire ne connaît que les graphies nouvelles des mots concernés par la réforme de 1990.

* **Dictionnaire "Toutes variantes"** : ce dictionnaire contient les nouvelles et les anciennes graphies des mots concernés par la réforme de 1990.

### Installer la/les version(s) retenue(s)

Le ou les dictionnaires français doivent être ajoutés manuellement au dossier contenant les dictionnaires de l'extension. 

1. Télécharger le dépôt
1. Copier les dossiers des dictionnaires français sélectionnés dans le dossier des dictionnaires
1. Redémarrer Brackets `F5`
1. Choisir le dictionnaire et le sélectionner par défaut `Proofing Options ▼`

```
disabled
user
    auteur.extension
    ...
    stillat.linguistics
    stillat.linguistics-dictionary
        natural-languages
            ...
            en_US
            ...
            fr-classique ◀ la version classique
            fr-reforme1990 ◀ la version réforme 1990
            ...
    ...
    
```

### :warning: Limite des vérificateurs orthographiques

Cette extension est uniquement un vérificateur orthographique, il a pour seul but de vérifier l'existence d'un mot dans un dictionnaire et suggérer une correction. 

Donc la phrase ci-dessous, qui est en fait juste une suite de mots pour le vérificateur, est parfaitement correcte pour l'extension.

> ### :ok_hand:  La chats verte mange du souris gris. :roll_eyes:


## :three: Désactivation des dictionnaires non utilisés

Pour "désactiver" un dictionnaire, il suffit de :
1. Créer un dossier `disabled`
1. Y déplacer le dossier du dictionnaire
1. Redémarrer Brackets `F5`

```
user
    auteur.extension
    ...
    stillat.linguistics
    stillat.linguistics-dictionary
        natural-languages
            ...
            en_US
            ...
        disabled ◀ dossier des dictionnaires désactivés
            en_ZA ◀ dictionnaire désactivé (English South African)
    ...
    
```
## Références
* [Alice - Spell Checking: Super alpha as-you-type spell checker for Adobe Brackets](https://github.com/JohnathonKoster/brackets-spellcheck)
> Linguistics adds a very powerful spell checking system to the Brackets editor. It offers the following features right out of the box:
> * Off-line spell checking :white_check_mark:
> * Support for multiple dictionaries :white_check_mark: 
> * Custom user dictionary profiles
> * Integrated user interface
> *Intelligent built in support for common file extensions
> * Intelligent support for uppercased words
> * Spell check within camelCasedWords
> * Spell check available within your code files
* [Grammalecte.dic(fr)](https://grammalecte.net/home.php?prj=fr)
> :book: :fr: Le projet vise à améliorer les dictionnaires orthographiques françaispour les logiciels libres, comme LibreOffice, OpenOffice, Firefox, Thunderbird, Evolution, Pidgin, Notepad++, Eclipse, etc., ainsi que tous les logiciels utilisant le correcteur orthographique Hunspell.
* [Forum Grammalecte](https://grammalecte.net/thread.php?prj=fr&t=827)
> Hunspell prévoit la possibilité d'adjoindre à chaque entrée des champs optionnels concernant la nature grammaticale, les flexions et autres informations potentiellement utiles.
Le dictionnaire français est l'un des rares à utiliser cette possibilité. Il y a aussi le dictionnaire hongrois et peut-être quelques autres (le russe ? le portugais ? je ne suis pas très sûr...)
* [ :male_detective: Typo.js: A client-side JavaScript spellchecker that uses Hunspell-style dictionaries](https://github.com/cfinke/Typo.js/)
* [ :male_detective: Hunspell > Manual pages](https://github.com/hunspell/hunspell/releases)

