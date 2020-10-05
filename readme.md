# Table des matières
>1. [Introduction](#Introduction)
>2. [La notion de variable](#La-notion-de-variable)
>3. [Les types de variable](#Les-types-de-variable)
>3. [Les mots clefs](#Les-mots-clefs)
>4. [Les opérateurs](#Les-opérateurs)
>5. [L'évaluation](#Évaluation)
>6. [L'assignation](#Assignation)
>7. [L'instruction](#Instructions)
>8. [Le bloc d'instructions](#Le-bloc-dinstructions)
>9. [Le commentaire](#Le-commentaire)
>10. [La condition](#La-condition)
>11. [Les boucles](#Les-boucles)
>12. [La fonction (ou méthode de classe)](#La-fonction)
>13. [Les paramètres](#Les-paramètres)
>
------------------------

## Introduction

Le langage Java est un langage généraliste de programmation synthétisant les principaux lan-gages existants lors de sa création en 1995 parSun Microsystems. Il permet une programmation orientée objet, modulaire (langage ADA) et reprend une syntaxe très proche de celle du langage C.

Outre son orientation objet, le langage Java a l’avantage d’être modulaire(on peut écrire des portions de code génériques, c-à-d utilisables par plusieurs applications), rigoureux (la plupart des erreurs se produisent à la compilation et non à l’exécution) et portable (un même programme compilé peut s’exécuter sur différents environnements). En contre-partie, les applications Java ont le défaut d’être plus lentes à l’exécution que des applications programmées en C par exemple.

[↑ Retour en haut](#Table-des-matières)

------------------------

## La notion de variable

Une variable est une donnée (un objet ou un type primitif) repérée par son nom, et qui pourra être lu, ou modifiée lors de l'exécution du programme.
 Les variables en langage Java sont typées, c'est-à-dire que les données contenues dans celles-ci possèdent un type, ainsi elles sont donc stockées à une adresse mémoire et occupent un nombre d'octets dépendant du type de donnée stockée.

En Java, les noms de variables peuvent être aussi long que l'on désire, toutefois le compilateur(programme qui traite les instructions écrites dans un langage de programmation donné pour les traduire en langage machine, ou « code », utilisé par le processeur d'un ordinateur) ne tiendra compte "que" des 247 premiers caractères. De plus, elles doivent répondre à certains critères :

-   un nom de variable ne peut comporter que des lettres, des chiffres (les caractères _ et $ peuvent être utilisés mais ne devrait pas l'être pour des variables)
-   un nom de variable ne peut pas commencer par un chiffre et ne doit pas comporter d'espace

Les noms de variables sont sensibles à la casse (Java fait la différence entre les lettres minuscules et majuscules, avec ou sans accent), il faut donc veiller à respecter la casse des noms !  
Par convention, un nom de variable est écrit en minuscules, sans accent, ni _ ou $. En revanche lorsqu'il est composé de plusieurs mots, on peut utiliser une majuscule pour l'initiale de chaque nouveau mot.

**Exemples de variables correctes**:
      nomDeVariable ; nomDeVariables123


### La déclaration des variables:

Pour pouvoir utiliser une variable, il faut la définir, c'est-à-dire lui donner un nom, mais surtout un type de donnée à stocker afin qu'un espace mémoire conforme au type de donnée qu'elle contient lui soit réservé.
Une variable se déclare de la façon suivante :   type nomDeVariable ;

Ou bien s'il y a plusieurs variables du même type :  type nomDeVariables ; ou nom_De_Variables2 ;

-   Java impose que les variables soient impérativement déclarées avant d'être utilisée.
-   Java permet de définir une variable à n'importe quel endroit du code.                 

### Affectation d'une donnée à une variable:
La déclaration d'une variable réserve un emplacement mémoire où stocker la variable, et une valeur par défaut (généralement 0, null ou false), pour modifier cette valeur par défaut, il faut faire une affectation, c'est-à-dire préciser la donnée qui va être stockée à l'emplacement mémoire qui a été réservé.  

Pour cela on utilise l'opérateur d'affectation "_=_" :
nomDeVariable = valeur;
Il est aussi possible d'initialiser les valeurs lors de leurs déclarations.
type nomDeVariable = valeur;

Exemple : Pour stocker le caractère B dans une variable que l'on appellera  _caractere_, il faudrait écrire :  

char caractere = 'B';
Ce qui signifie _"stocker la valeur Unicode de la lettre B dans la variable nommée 'caractere'_.

### Portée (visibilité) des variables :

Selon l'endroit où on déclare une variable, celle-ci pourra être accessible (visible) de partout dans le code ou bien que dans une portion confinée de celui-ci (à l'intérieur d'une méthode par exemple), on parle de  _portée_  d'une variable.  

Lorsqu'une variable est déclarée directement dans la classe, c'est-à-dire à l'extérieur de toute méthode, elle sera accessible dans toute la classe. On parle alors de  _champ_  de la classe (fields, en anglais). Elle représente l'état de l'objet courant (ou avec le mot clé static, l'état de la classe elle même).  

Lorsque l'on déclare une variable à l'intérieur d'un bloc d'instructions (entre des accolades), sa portée se restreint à l'intérieur de ce bloc (dans les lignes qui suit sa déclaration), on parle alors de variable locale.  

Il est interdit d'avoir deux variables de même nom si elles ont une portée commune. Il serait alors impossible de les distinguer...

### Définitions de constantes:

Une constante est une donnée dont la valeur est inchangeable lors de l'exécution d'un programme. Le mot clé _final_ permet de faire cela. Toutefois on ne peut véritablement parler de constantes en Java que pour les types primitifs, car pour un objet le mot clé final impose seulement que la référence de l'objet n'est pas modifiable, mais les champs de l'objets peuvent être modifiés malgré tout.  
  
Par convention, et pour les distinguer des variables, les constantes sont écrites entièrement en majuscules, et le caractère _ peut être utilisé pour séparer deux mots.

``final int MA_CONSTANTE = 12``

aura pour effet de définir une variable de type _int_ possèdant la valeur 12 et ne pouvant pas être modifiée dans la suite du code, auquel cas le compilateur générera une erreur...
                                                                         

[↑ Retour en haut](#Table-des-matières)

------------------------

## Les types de variable

### C'est quoi?

C’est une sorte de boîte, étiquetée, où l’on peut stocker de l’information pour la consulter ou la modifier plus tard.

Les variables doivent avoir un type et un nom.

### Les deux sortes de variables


Il existe deux sortes de variables:

- *les types primitifs qui contiennent des valeurs élémentaires:*

- le type booléen : boolean

Les variables de type booléen ne peuvent prendre que deux valeurs : true ou false. Par défaut, un attribut de type boolean vaut false.

On ne peut utiliser que des opérateurs booléens comme ==, != et ! sur des variables de type booléen (pas d’opération arithmétique autorisée).</li>

- Le type caractère : char

Les variables de type char sont codées sur 2 octets non signés car la représentation interne des caractères est l’UTF-16. Cela signifie que la valeur va de 0 à 2^16 - 1. Par défaut, un attribut de type char vaut 0 (c’est-à-dire le caractère de terminaison).

Pour représenter un littéral, on utilise l’apostrophe (simple quote) :

```java
char c = 'a';
```

Même si les caractères ne sont pas des nombres, Java autorise les opérations arithmétiques sur les caractères en se basant sur le code caractère. Cela peut être pratique si l’on veut parcourir l’alphabet par exemple :

```java
for (char i = 'a'; i <= 'z'; ++i) {
  // ...
}
```

On peut également affecter un nombre à une variable caractère. Ce nombre représente alors le code caractère :

```java
char a = 97; // 97 est le code caractère de la lettre a en UTF-16
```


- Les types entiers : byte, short, int, long

Les types entiers différent entre-eux uniquement par l’espace de stockage mémoire qui leur est alloué. Ils sont tous des types signés. Par défaut, un attribut de type byte, short, int ou long vaut 0.

La règle de conversion implicite est simple : on peut affecter une variable d’un type à une variable d’un autre type que si la taille mémoire est au moins assez grande.

```java
byte b  = 1;
short s = 2;
int i   = 3;
long l  = 4;

// conversion implicite ok
// car la variable à droite de l'expression
// est d'une taille mémoire inférieure
s = b;
i = s;
i = b;
l = b;
l = s;
l = i;
```

Dans tous les autres cas, il faut réaliser un transtypage avec un risque de perte de valeur :

```java
b = (byte) s;
s = (short) i;
i = (int) l;
```

Lorsque vous affectez une valeur littérale à une variable, le compilateur contrôlera que la valeur est acceptable pour ce type :

```java
byte b = 0;
b = 127; // ok
b = 128; // ko car le type byte accepte des valeurs entre -128 et 127
```

- Les types à virgule flottante : float, double.

Les types float et double permettent de représenter les nombres à virgule selon le format IEEE 754. Ce format stocke le signe sur un bit puis le nombre sous une forme entière (la mantisse) et l’exposant en base 2 pour positionner la virgule. Par défaut, un attribut de type float ou double vaut 0.

float est dit en simple précision et est codé sur 4 octets (32 bits) tandis que double est dit en double précision et est codé sur 8 octets (64 bits).

Il est possible d’ajouter une valeur entière à un type à virgule flottante mais l’inverse nécessite une transtypage (cast) avec une perte éventuelle de valeur.

```java
int i = 2;
double d = 5.0;
d = d + i;
i = (int) (d + i);
```

Les valeurs littérales peuvent s’écrire avec un . pour signifier la virgule et/ou avec une notation scientifique en donnant l’exposant en base 10 :

```java
double d1 = .0; // le 0 peut être omis à gauche de la virgule
double d2 = -1.5;
double d3 = 1.5E1; // 1.5 * 10, c'est-à-dire 15.0
double d4 = 0.1234E-15;
```

Une valeur littérale est toujours considérée en double précision. Pour l’affecter à une variable de type float, il faut suffixer la valeur par F ou f :

``float f = 0.5f;``


- *et les références aux objets qui continnent des références aux objets.*

- Les strings.
 La classe String est une classes dont les objets sont immuables : ils ne peuvent pas changer de valeur.
 Exemple: 
 ``String prenom = new String("Pierre");``
Les classes StringBuffer et StringBuilder produisent des objets qui peuvent changer de valeur. 
Ces deux classes ont exactement les mêmes méthodes.
Les méthodes de la classe StringBuffer sont synchronisées, et peuvent être utilisées par plusieurs thread sur une même chaîne de caractères.
Exemple:

``public StringBuffer(int longueur)``
    
Les méthodes de la classe StringBuilder ne sont pas synchronisées, elles sont donc plus rapides que celle de la classe StringBuffer, mais ne sont pas «thread safe».

La classe *StringTokenizer* (séparation d'une chaîne en plusieurs entités)
Exemple:

``public StringTokenizer(String s, String delim, boolean tokens)``

- Array
Un array est une liste qui va regrouper un certain nombre d’objet ou type de variable. 
Exemple:

```java 
// declare an array
int[] age = new int[5];

// initialize array
age[0] = 12;
age[1] = 4;
age[2] = 5;
//..
```

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191105111644/Data-types-in-Java.jpg)

[↑ Retour en haut](#Table-des-matières)

------------------------

## Les mots clefs

Les mots-clés sont des termes spécifiques au langage de programmation, certains sont utilisables par plusieurs langages et d'autres spécifiques à un langage.
On trouve plus de 50 mots clés qui ont les usages propres en java.
On ne peut les utiliser que dans un contexte précis et il est impossible de les déclarer en comme noms de classes ou variables. 
On retrouve différents types de mots-clés; des mots-clés pour déclarer des objets, variables, des états, des branchements et encore des exceptions.

Les mots pour les objets; "class", "interface", "implements", "enum", "import", "this", "abstract", "extends", "package", "super" &"native".

Les mots pour les types; "boolean", "char", "int", "float", "long", "short", "double", "byte" & "void".

Pour les états; "const" , "false", "true", "static", "null", "volatile", "new", "transient", "strictfp".

pour les boucles: "do", "for", "goto", "while", "continue".

pours les branchements; "if", "else", "return", "break", "assert", "switch", "synchronized", "default", "case" & "instanceof".

Et voici les mots-clés pour gérer des exceptions; "throw", "throws", "try", "catch" & "finally"

[↑ Retour en haut](#Table-des-matières)

------------------------

## Les opérateurs

Les opérateurs sont des symboles permettant de manipuler et d’effectuer des operations mathématiques sur des variables, il en existe plusieurs types:


### Les opérateurs de calcul  

Permettent d'effectuer des opérations mathématiques simples sur/entre des variables

|Opérateur|Effet|
|----|------|
|**+**|addition 
|**-**|soustraction
|*|multiplication
|**/**|division
|**%**|modulo (rends le reste de la division)
|**=**|affectation  (à ne pas confondre avec **==**, l'opérateur de vérification)



### Les opérateurs d\`assignation 

Permet d'effectuer une opération de calcule à une variable et d'affecter son resultat à cette même variable.
Exemple: 

```java
x = x + 1
```
 
pourra s'écrire 

```java
x += 1
```

|Opérateur|Effet|
|----|------|
|**+=**|additionne deux valeurs et stocke le résultat dans la variable 
|**-=**|soustrait deux valeurs et stocke le résultat dans la variable 
|***=**|multiplie deux valeurs et stocke le résultat dans la variable 
|**/=**|divise deux valeurs et stocke le résultat dans la variable 
|**%=**|module deux valeurs et stocke le résultat dans la variable 


### Les opérateurs d'incrémentation

Permet d'augmenter ou diminuer d'une unité une variable (utile pour les boucles par exemple)

|Opérateur|Effet|
|----|------|
|**++**|augmente d'une unité la variable 
|**- -**|diminue d'une unité la variable

### Les opérateurs de comparaison

Permettent d'effectuer des opérations de comparaison entre des variables, retournent  TRUE or FALSE

|Opérateur|Effet|
|----|------|
|**==**|égalité 
|**<**|inferiorité stricte
|**<=**|inferiorité
|**>**|superiorité stricte
|**>=**|superiorité
|**!=**|différence

### Les opérateurs logiques

Permet de vérifier si des conditions sont vraies

|Opérateur|Dénomination|Effet|
|----|------|----|
|**ll**|OU logique|Retourne true si au moins une des deux conditions vaut true (ou false sinon)|
|**&&**|ET logique|Retourne true si les deux conditions valent true (ou false sinon)|
|**!**|NON logique|Retourne true si la variable vaut false, et false si elle vaut true)|

[↑ Retour en haut](#Table-des-matières)

------------------------
## Évaluation 

Comme vu précédemment, les variables de type *double* contiennent plus d'informations de type *int*.

Lors d'une opération, Java va donc retourner un résultat de l'opération qui sera **"casté"** selon les type de variable.

```java
int nbre1 = 3  
int nbre2 = 2  
double resultat = nbre1 / nbre2  
// le résultat sera 1  
```

Le résultat de cet exemple sera un entier. En effet la priorité opératoire est en faveur du type int. Si l'on veut obtenir 1,5, il nous faudra faire un *cast* sur le résultat, en apposant le type désiré entre parenthèse devant chaque membre de l'opération.

```java
int nbre1 = 3
int nbre2 = 2
double resultat = double(nbre1) / double(nbre2)  
// le résultat sera 1.5
```

Ainsi en Java, chaque membre d'une opération passe automatiquement et implicitement par une évaluation de son type et par un cast si besoin.

Lorsque l’opérande de gauche n’est pas un tableau, il s'éxecute dans cet ordre:

1. Vérifier que l’opérande est une variable déclarée
2. Sauvegarder la valeur de l’opérande gauche

3. Évaluer l’opérande de droite

4. Effectuer l’opération binaire indiquée par l’opérateur composé

5. Convertir le résultat de l’opération binaire en type de variable de gauche **(casting implicite)** . Affecter le résultat converti à la variable de gauche

[↑ Retour en haut](#Table-des-matières)

------------------------
## Assignation

En programmation informatique, une affectation, ou assignation, est une structure qui permet d'attribuer une valeur à une variable.


En JAVA, **il faut déclarer toute les variables en précisant leur type** . On peut éventuellement ajouter des modificateurs. Ainsi déclarer une variable « final » revient à créer une constante car le compilateur refusera toutes les instructions modifiant la valeur de cette variable.  
On peut effectuer une affectation ou assignation (donner une valeur) en déclarant une variable.  


**Le signe égal ( = ) est le symbole basique d'assignation.**


```
// déclaration de a comme entier
int a;
//affectation de a avec la valeur 3
a = 3;
```

Cette instruction déclare une nouvelle variable x , attribue à x la valeur de 3 et renvoie 3 .

Il existe d'autre opérateur d'assignation ( cf [Les opérateurs d'assignation](#Les-opérateurs-dassignation) )


[↑ Retour en haut](#Table-des-matières)

------------------------
## Instructions

C'est quoi?
<p><br>Une instruction informatique désigne une étape dans un programme informatique.</br>
<p>Une instruction dicte à l'ordinateur l'action nécessaire qu'il doit effectuer avant de passer à l'instruction suivante. </p>
<p>Un programme informatique est constitué d'une suite d'instructions.</p>

En Java, une instruction se termine par un point virgule `;`

```exemples

System.out.println("Hello World"); // ceci est une instruction

int resultat = 1 + 1; // ceci est une autre instruction

String resultat2 = "Je suis un texte"; // une troisième instruction

```

Les instructions se lisent de haut en bas.

```en java

int nombre1 = 1; // première instruction

int nombre2 = 1 + 1; //deuxième instruction

int nombre3 = nombre2 + nombre1; // troisième instruction

```

Dans le code précédent, les instructions sont soit indépendantes, soit dépendantes.

`nombre1` et `nombre2` se voient assignés une valeur par assignation directe ou via une opération mathématique `(1 + 1)`

`nombre3` se voit assigné une valeur via l'addition de `nombre1` et `nombre2`.

Il ne serait pas possible d'assigner de à `nombre3` si `nombre1` et `nombre2` avaient été déclarés après.

```en java

int nombre3 = nombre2 + nombre1; // Erreur, nombre1 et nombre2 n'existent pas encore

int nombre1 = 1; 

int nombre2 = 1 + 1; 

```




[↑ Retour en haut](#Table-des-matières)

------------------------

## Le bloc d\`instructions


Dans le code précédent, les instructions sont soit indépendantes, soit dépendantes.

`nombre1` et `nombre2` se voient assignés une valeur par assignation directe ou via une opération mathématique `(1 + 1)`

`nombre3` se voit assigné une valeur via l'addition de `nombre1` et `nombre2`.

Il ne serait pas possible d'assigner `nombre1` et `nombre2` à `nombre3` si `nombre1` et `nombre2` avaient été déclarés après.

```java
int nombre3 = nombre2 + nombre1; // Erreur, nombre1 et nombre2 n'existent pas encore

int nombre1 = 1; 

int nombre2 = 1 + 1; 

```

Un programme informatique est constitué d'une suite d'instructions qui s'exécutent dans un `bloc d'instructions`.

### Déclaration d'un bloc d'instructions

En java, un bloc d'instructions se déclare entre crochets `{}`

Les conditions `if/else/else if` sont des blocs d'instructions.

(Voir [les conditions](#La-condition))

Les boucles `for/while/do while` sont des blocs d'instructions.

(Voir [boucles](#Les-boucles))

Les méthodes de classe sont des blocs d'instruction.

(Voir [la fonction](#La-fonction))
```
Les classes sont des blocs d'instruction.

```java

public class MaClasse{
    
    public void method1(){}

    public void method2(){}

    //...
}
```

Chaque bloc d'instruction définit la durée de vie des instructions qui sont déclarées à l'intérieur.

Ainsi dans une fonction, les instructions à l'intérieur ne sont pas accessibles à l'extérieur. Les variables déclarées à l'intérieur n'existent plus une fois le bloc d'instruction terminé

```java

public function MaMethode(int nombre, int nombre2){
    int addition =  nombre1 + nombre2;

    return addition;
}

int resultat = MaMethode(10,10);

System.out.println(addition) // Erreur, addition n'existe pas en dehors de la méthode MaMethode

```

Si une variable est déclarée dans un bloc d'instruction, elle n'existe plus en dehors de ce bloc.

```java

if(true){
    int nombre = 10;
}else{
    nombre = 20; //Erreur, nombre n'existe que dans if, pas dans else
}
```

Par contre

```java

public void function maMethode(){
    int nombre = 0;

    if(true){
        nombre = 10; //ok
    }else{
        nombre = 20; //ok
    }
}


```

`nombre` est défini en amont des blocs d'instruction if et else dans la méthode `maMethode`, les blocs d'instruction enfants peuvent donc récupérer la variable `nombre`.

Un bloc d'instruction enfant peut lire les variables de son parent mais pas l'inverse, la fin d'une instruction signifiant la fin de vie de toutes les instructions à l'intérieur. 

Comme le bloc d'instruction parent n'est pas fini, ses variables sont encore accessibles.

[↑ Retour en haut](#Table-des-matières)

------------------------

## Le commentaire

Les commentaires permettent de rendre le code lisible et surtout d'en faciliter ultérieurement la maintenance.

En général, l'insertion de commentaire se fait soit en fin de ligne, soit sur une nouvelle ligne mais en aucun cas au sein d'une ligne de commande.

- Ils ne sont pas pris en compte par le compilateur donc ils ne sont pas inclus dans le pseudo code
- ils ne terminent pas par un ;

### Types de commentaires en Java :

#### Commentaire sur une seule ligne
La première consiste à placer un double slash (//) 

Syntaxe:

```java
public class Main {
  public static void main(String[] args) {
    //Afficher le message Hello World!
    System.out.println("Hello World!");
  }
}
```

Sortie: *Hello World!*

#### Commentaire sur plusieurs lignes
La seconde solution est d'encadrer le texte par un slash suivi d'une étoile (/\*) et la même séquence inversée (\*/)

Syntaxe:

```
/*
  Ceci est un commentaire 
  sur plusieurs 
  lignes
*/
```

Example:
```java
public class Main {
  public static void main(String[] args) {
    /*
        Déclarer et afficher
        le message Hello World!
    */
    String str = "Hello World!";
    System.out.println(str);
  }
}
```

Sortie: *Hello World!*

#### Commentaire de documentation
Ce type de commentaires est généralement utilisé lors de l’écriture du code pour un projet, car il permet de générer une page de documentation de référence, qui peut être utilisée pour obtenir des informations sur les méthodes, ses paramètres, etc.

Syntaxe:

```java
**
*
*-Ceci est un Commentaire 
*- de documentation
*
**/
```

Example:
```java
/**
 *
 *Programme Java pour déclarer et afficher
 *le message Hello World!
 *-
 *- @author  Thomas babtise
 *-@version 2.5 
 *-@since   2021-12-10
 *-@link    www.waytolearnx.com
 *-
 **/
public class Main {
  public static void main(String[] args) {
    String str = "Hello World!";
    System.out.println(str);
  }
}
```

Sortie: *Hello World!*

[↑ Retour en haut](#Table-des-matières)

------------------------

## La condition


Une condition va vous permettre d'exécuter une portion de code ou non en fonction du résultat de variables booléennes, c'est à dire que vous pourrez dire "si X est faux alors je fais ça, sinon ceci et si aucune des conditions précédentes n'est remplie, je ferais plutôt cela".

### Exemple d'une condition

```java
public boolean variable = true;

if(variable == true)
{
     //Si variable = a vrai(true) alors on execute ce code
     System.out.println("La variable est vrai");
}
```


### Autres exemples 

```java
public int variable = 5;

if(variable == 5)
{
     //Si variable == 5 on execute ce code
     System.out.println("La variable est a 5 donc le code s'execute");
}
```

```java
public int variable = 10;

if(variable <= 5)
{
     //Si variable est inférieure ou egale 5 on execute ce code
     System.out.println("Ce code ne s'execute pas");
}
```

### Sinon (else)
Il existe une autre facon d'écrire des conditions que seulement avec des si (if) on peut ecrire une condition avec un sinon(else) à la suite d'un if(si), else signifie que si une condition et pas vrai alors on execute un autre bout de code 


### Exemple avec Else

```java
public int variable = 10;

if(variable <= 5)
{
     //Si variable est inférieure ou egale 5 on execute ce code
     System.out.println("Ce code ne s'execute pas");
} else
{
    //Sinon on execute ce code
    System.out.println("Ce code s'execute");
}
```

On peut aussi combiné un else avec un if
### Exemple avec Else If
```java
public int variable = 10;

if(variable <= 5)
{
     //Si variable est inférieure ou egale 5 on execute ce code
     System.out.println("Ce code ne s'execute pas");
} else if (variable == 10)
{
    //Sinon si variable == 10 on execute ce code
    System.out.println("Ce code s'execute");
}
```

[↑ Retour en haut](#Table-des-matières)

------------------------

## Les boucles


Les boucles permettent de **répéter une ou plusieurs instructions**, selon les conditions désirées.

On en compte plusieurs types:
<br>

### La boucle FOR

Elle permet de contrôler exactement le nombre de répétitions (d'*itérations*) de la boucle.
C'est la plus compliquée à appréhender de toutes parce qu'elle demande plusieurs paramètres.
Sa structure est composée de telle manière:

```java
for( <initialisation> ; <condition> ;  <incrémentation>) {
    <actions>
}
```

Souvent, on utilise une variable temporaire qui garde le compte du nombre d'itérations. Elle est souvent appelée `i` comme *index*, et est un point de repère pour la boucle et le développeur ; mais elle peut s'appeler n'importe comment.

- Dans l'**initialisation** de la boucle, on définit quel est l'état de la boucle avant sa première répétition ; par exemple
`int i = 0`.
Dans cet exemple, on définit une variable i étant égale à 0.

- Dans la **condition** de la boucle, on définit quel est la condition d'arrêt de la boucle ; par exemple
`i <= 20`.
Dans cet exemple, la boucle se répétera tant que la valeur de notre *i* sera inférieure ou égale à 20.

- Dans le paramètre d'**incrémentation** de la boucle, on définit ce qui change à chaque répétition, et qui va permettre à la boucle de se finir à un moment donné. Par exemple:
`i++`.
Dans cet exemple, à chaque répétition de la boucle, la valeur de `i` s'augmente de 1.

#### Résultat

Voilà ce que donne nos exemples appliqués ensemble:

```java
for( int i=0 ; i <= 20 ; i++){
    System.out.println(i);
}
```

Cet exemple dans la console nous renverra à chaque répétition la valeur de `i`, jusqu'à 20.

#### FOR avec une array

On peut utiliser For pour faire une action pour chaque variable d'une array, par exemple :

```java
for (int i=0; i<myArray.length; i++) {
    System.out.println(myArray[i]);
}
```

Cet exemple enverra chaque objet de l'array dans la console tour à tour.
<br>

### La boucle WHILE

La boucle while permet de créer une boucle avec pour seule instruction sa condition de répétition (s'imaginer while comme "*tant que* \<condition>, faire \<actions>".
Elle s'écrit comme dans cet exemple:

```java
while(i<20){
    i++;
}
```

<br>

### La boucle DO... WHILE

Cette boucle ressemble beaucoup à la précédente, à l'exception que sa condition est écrite après son action, garantissant que la boucle s'éxécute au moins une fois.
Exemple:

```java
int i = 0;

do{
    System.out.println("coucou");
} while(i ==1);
```

Affichera une fois *"coucou"*, même si la condition n'est jamais respectée.

<br>

### Pour aller plus loin

#### L'instruction *continue*

Dans une boucle, on peut utiliser `continue` pour dire qu'une partie du code ne doit pas s’exécuter selon certaines conditions:

```java
while(i<20){
    i++;
        if(i ==5){
            continue;
        }
    System.out.println("coucou");
    }
```

La suite du code ne s'exécute pas lorsque `i` est égal à 5, et donc n'affichera pas *"coucou"* à ce moment là.

#### L'instruction *break*

On peut utiliser `break` pour arrêter une boucle à un moment voulu, même si la condition de la boucle n'est pas encore respectée:

```java
while(i<20){
    i++;
    if(i ==5){
        break;
    }
}
````

Au moment où `i` sera égal à 5, la boucle s'arrêtera complêtement, alors même que `i` n'est pas encore supérieur ou égal à 20.

[↑ Retour en haut](#Table-des-matières)

------------------------

## La fonction

La fonction ou méthode de classe est un bloc d'instruction réutilisable permettant de recevoir des arguments.

Plutôt que de répéter plusieurs opérations identiques, il suffit de créer une fonction et de mettre ces opérations à l'intérieur.

Aisin si l'on voulait effectuer une opération mathématiques sur deux valeurs on pourrait le faire de cette façon:

```java

int addition = 2+2;

int soustration = 5 - 3;

float division = 10 / 2;

int multiplication = 4 * 7;

```

Grâce aux fonctions, il est possible d'encapsuler ces opérations:

```java

public int function Addition(int nombre1, int nombre2){
    return nombre1 + nombre2;
}

public int function Soustraction(int nombre1, int nombre2){
    return nombre1 - nombre2;
}

public float function Division(float nombre1, float nombre2){
    return nombre1 / nombre2;
}

public int function Multiplication(int nombre1, int nombre2){
    return nombre1 * nombre2;
}

```

### Déclaration d'une méthode de classe

La déclarion d'une méthode de classe/fonction s'éffectue d'abord par la déclaration de sa portée.

- `public` : accès publique. La méthode est disponible depuis partout, par toutes les classes.
- `protected` : accès protégé. La méthode n'est disponible qu'à l'intérieur d'une classe. Elle peut être donc visible pour les classes héritantes. Elle est aussi visible pour des classes non héritantes mais étant du même package.
- `private` : accès privé. La méthode n'est disponible qu'à l'intérieur d'une classe. Héritée, elle n'est pas visible.
 
Puisqu'en java, tout est objet, une méthode appartient obligatoirement à une classe.

une méthode de classe peut être déclarée `static`. Quand une méthode est déclarée `static`, elle ne peut être appelée que par la classe elle-même et non par une instance de classe. 

```java

class MaClass{
    public static void MaMethodeStatique(){
        System.out.print.ln('Je suis appelée par une classe");
    }

    public void MaMethode(){
        System.out.print.ln('Je suis appelée par une instance de classe");
    }
}

```
`MaMethodeStatique` ne peut être appelée que par `MaClass` quand `MaMethode` ne pourra être appelée que par une instance de `MaClass`

Il faut ensuite définir le type de retour de la fonction.
Une fonction peut ou non retourner un résultat.

Sans retour de résultat, il faudra déclarer la méthode par le mot clé `void`.

Selon la valeur de retour, il faudra déclarer le retour comme étant un `int`,`float`,`char`,`String`...

La fonction se déclare avec le mot clé `function` puis par le nom qu'on veut lui donner. Ce sera ensuite son identifiant pour l'appeller (`Addition`, `Soustraction`...).

Les arguments qu'on veut injecter dans cette fonction se déclarent entre parenthèses `()`.

Le traitement des arguments et autres opérations propres à la fonction se déclarent entre crochets  `{ }`. 

Si la méthode renvoit un résultat, le bloc d'instruction se terminera par l'instruction `return` puis le résultat à retourner.

Une fois la fonction déclarée, il est ensuite possible de l'utiliser à l'infini en l'appelant dans notre code:



```java

int resultatAddition = Addition(5,10);
int resultatAddition2 = Addition(6,9);

int resultatSoustraction = Soustraction(100,50);
int resultatSoustraction2 = Soustraction(4,1);

float resultatDivision = Division(10.0,4.0);
float resultatDivision2 = Division(300.0,8.0);

int resultatMultiplication = Multiplication(2,2);
int resultatMultiplication2 = Multiplication(5,9);

```

[↑ Retour en haut](#Table-des-matières)

------------------------

## Les paramètres

Les paramètres sont utilisées **par les fonctions** pour leur **donner du matériel avec lequel travailler**.

### Théorie

Lors de la déclaration d'une fonction, on lui indique à l'avance les outils dont elle aura besoin, entre parenthèses, juste après le nom de la fonction.
On sépare plusieurs paramètres par des virgules.
Exemple:

```java

fonction maFonction(int monParametre){
    <actions>
}

```

### Utilisation

Lors de **l'appel** d'une fonction, on donne entre parenthèses les valeurs que la fonction utilisera comme paramètres.
Exemple:


```java

fonction monProfil(String monAge, String monPrenom){
    return monPrenom + " a " + monAge + "ans."
}

String prenom = "Jean-Bob";

monProfil("12", prenom);

```

Notre fonction renverra ainsi *"Jean-Bob a 12 ans"*

### Cas d'exemple: pour conditionner

On peut aussi utiliser des paramètres pour donner des **conditions** pour l’exécution du code au sein d'une fonction
Exemple: 

```java

bool buMonCafé = true;
bool prisMonPC = true;

bool jeSuisPrêt = (buMonCafé && prisMonPC);

fonction commencerJournee(bool ready){
    if(ready){
        aller_a_simplon();
    }
}

commencerJournee(jeSuisPrêt);

```
[↑ Retour en haut](#Table-des-matières)

------------------------