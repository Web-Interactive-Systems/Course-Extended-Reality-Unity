---
type: NoteCard
---

# lab - C# Basics
**Objectifs**

*   Comprendre les bases du langage C#, principalement pour Unity.
*   Être capable d'écrire un programme C# de base, principalement pour Unity.

**Lessons**

*   Hello world
*   Variables et data types
*   Classes et méthodes
*   Conditions
*   Boucles
*   Debug.log
*   Scripting

## **1- Hello world**

**Démonstration**

Un hello world dans le Start() d'un script. Affichage dans la console de Unity.

**C'est à vous :**

1.  Créez un nouveau projet
2.  Ajoutez un objet, par exemple un cube GameObject>3DObject>Cube
3.  Dans la partie explorateur de projet dans le bas de l'écran, dans le dossier Assets, créer un dossier Scripts
4.  Faites un clic droits dans le dossier pour créer un nouveau script qui se nommera "HelloWorld.cs"
5.  Sélectionner le cube dans la partie gauche de l'écran
6.  Le détail de l'objet apparaît sur la droite de l'écran dans l'inspector.
7.  Glisser/déposer le script "HelloWorld.cs" dans le détail de votre Cube.
8.  Faites un double clic sur votre fichier "HelloWorld.cs", votre IDE devrait s'ouvrir
9.  Dans l'IDE vous devriez voir:
10. Dans le Start(), ajouter la ligne suivante :
11. Sauvegarder et retourner sur Unity .
12. Cliquez sur le bouton Play situé au centre haut de l'écran.
13. Dans le bas de l'écran, cliquez sur l'onglet console. Que remarquez-

vous ?

## **2- Variables and data types**

### **2a- nommage des variables**

Les règles de nommage des variables en C# pour Unity sont importantes

pour maintenir un code lisible et cohérent. Voici quelques règles de

base pour le nommage des variables en C# pour Unity:

*   Ne commence pas par un nombre et ne comprend pas d'espace
*   Utilise la convention **camelCase**

### **2b- variable public et private**

Les deux principaux niveaux de visibilité des variables dans Unity sont

"**public**" et "**private**".

*   Les variables publiques sont visibles dans l'inspecteur Unity,

tandis que les variables privées ne le sont pas.

*   Les variables publiques peuvent être utilisées pour partager des

données entre des scripts différents, tandis que les variables

privées sont utilisées pour stocker des données internes à une

classe.

```js
private int health = 100;

public int speed = 10;
```

**Démonstration**

Initialisation d'une variable private et d'une variable public.

Visibilité des variables dans l'inspector.

**C'est à vous :**

1\. Reprenez votre script préalablement créé

2\. Ajouter deux variables après la déclaration de la classe et avant

l'appelle à la méthode Start().

3\. Sauvegardez votre fichier.

4\. Dans unity, sélectionnez l'objet auquel le script est associé.

qu'observez vous ?

En C# pour Unity, il existe deux autres niveaux de visibilité des

variables en plus de public et private: protected et internal.

*   Les variables **protected** sont similaires aux variables private,

mais elles peuvent être accédées à partir des classes dérivées de la

classe dans laquelle elles ont été déclarées.

*   Les variables **internal** peuvent être accédées à partir de

n'importe quelle classe dans le même assembly (ensemble de fichiers

.dll ou .exe).

### **2c- types de variables**

En C# pour Unity, il existe plusieurs types de variables que vous pouvez

utiliser pour stocker différentes sortes de données. Voici une liste des

types de variables les plus courants en C# pour Unity:

*   int: utilisé pour les nombres entiers (par exemple, 1, 10, -5).
*   float: utilisé pour les nombres décimaux (par exemple, 3,14, -0,5).
*   bool: utilisé pour stocker des valeurs vraies ou fausses.
*   string: utilisé pour stocker du texte (par exemple, "Bonjour,

Unity!").

*   Vector2/Vector3: utilisé pour représenter des positions ou des

directions 2D/3D.

*   Color: utilisé pour stocker des valeurs RGBA de couleur.
*   GameObject: utilisé pour faire référence aux objets de jeu Unity.

Il existe également d'autres types de variables, tels que double, long,

short, byte, char, decimal, object, etc. Vous pouvez trouver plus

d'informations sur ces types de variables dans la documentation Unity.

Plus d'informations sur ces types de variable: <https://docs.unity3d.com/2019.3/Documentation/Manual/bolt-types.html>

**Démonstration**

Ajout de variables public de chaque type et visualisation dans

l'inspecteur.

**C'est à vous :**

1\. Reprenez votre script précédent.

2\. Ajoutez-y une variable de chaque type : int, float, bool, string,

Vector3, Color et GameObject, pensez à déclarer les variables en

public.

3\. Retournez dans unity voir le détails de l'objet auquel est associé

le Script dans l'inspector.

### **2d- les tableaux et les List**

Un tableau est une structure de données qui permet de stocker plusieurs

éléments de même type dans une seule variable. Les tableaux sont utiles

pour stocker des collections d'objets, tels que des positions de points,

des couleurs de pixels, des coordonnées de texture, etc

```js
using UnityEngine;

public class Example : MonoBehaviour

{

void Start()

{

// Create an array of 3 int

int[] values = new int[3];

// Set the values

values [0] = 5;

values [1] = 10;

values [2] = 15;

// Print the values

foreach (int value in values)

{

Debug.Log(value);

}

}

}
```

**Démonstration**

Création d'un tableau. Utilisation d'une boucle foreach dans le start

pour afficher le contenu du tableau dans la console.

**C'est à vous**

1\. Reprenez votre script précédent

2\. [Déclarez un tableau de taille 3.]{.mark}

3\. [Initiez les valeurs du tableau pour chaque index.]{.mark}

4\. [Faites une boucle foreach sur le tableau pour afficher le contenu

du tableau dans la console.]{.mark}

[Les List sont des tableaux à taille variable. Ils sont plus adaptés à

des manipulations mais nécessitent plus de ressources]{.mark}

```js
using UnityEngine;

public class Example : MonoBehaviour
{
    public List<GameObject> GameObjects= new List<GameObject>();


    void Start()
    {
        // Print the values
        foreach (GameObject gameObject in GameObjects)
        {
            Debug.Log(gameObject.name);
        }
    }
}
```

**C'est à vous**

1\. Reprenez votre script précédent

2\. Déclarez une List de GameObject

3\. Dans l'éditeur, ajoutez des GameObjects à la List

4\. Dans le script parcourir la liste pour afficher les noms des GameObject

### **2e- Constante**

En C# les constantes sont déclarées de la manière suivante :

```js
public const int Monts = 12;
```

## **3- Classes et méthodes**

### **3a- classe**

En C# une classe est un ensemble de méthodes et de variables qui

définissent un modèle d'objet.

Dans Unity, les classes sont utilisées pour créer des scripts qui

peuvent être attachés à des objets de jeu. Les scripts contiennent du

code qui définit le comportement de l'objet auquel ils sont attachés.

Les **conventions de nommage** des classes en C# recommandent

d'utiliser **PascalCase** pour les noms de classe. Essayez d'utiliser

un nom ou une phrase nominale pour le nom de la classe. N'utilisez pas

de préfixes et n'utilisez pas de traits de soulignement.

Le nom de la classe et le nom du fichier script créer doivent être les

mêmes.

Par exemple, vous pouvez créer une classe Player qui contient des

propriétés telles que la santé et la vitesse du joueur, ainsi que des

méthodes telles que Move() et Shoot() qui définissent le comportement du

joueur.

```js
public class Player : MonoBehaviour

{

public int health = 100;

public float speed = 10.0f;

void Update()

{

Move();

Shoot();

}

void Move()

{

// Code to move the player

}

void Shoot()

{

// Code to shoot a projectile

}

}
```

Dans l'exemple ci-dessus, la classe Player étend la classe MonoBehaviour.

Nous parlerons de la classe monobehaviour plus tard dans ce TP.

**Démonstration**

création d'une classe player avec deux variables.

**C'est à vous :**

dans votre explorateur de projet, dans le dossier Scripts; créer un

nouveau script que vous nommerez "Player.cs"

### **3b- méthode**

En C# Unity, une méthode est une fonction qui est définie dans une

classe et qui peut être appelée pour effectuer une tâche spécifique. Les

méthodes sont utilisées pour encapsuler la logique de traitement et pour

rendre le code plus modulaire et facile à comprendre.

Les méthodes en C# ont un nom, un type de retour (le cas échéant) et une

liste de paramètres. Elles sont déclarées avec un niveau d'accès

(public ou private)

### **Nommage**

Les conventions de nommage des méthodes en C# recommandent d'utiliser

**PascalCase** pour les noms de méthode. Essayez d'utiliser un verbe ou

une phrase verbale pour le nom de la méthode. N'utilisez pas de

préfixes et n'utilisez pas de traits de soulignement.

Par exemple, si vous créez une méthode pour calculer la somme de deux

nombres, vous pouvez l'appeler "AddNumbers" ou "CalculateSum". Si

vous créez une méthode pour afficher un message à l'utilisateur, vous

pouvez l'appeler "DisplayMessage" ou "ShowAlert".

### **Paramètre**

Comme dans d'autres langages que vous connaissez, les paramètres sont

des valeurs qui sont passées à la méthode lorsqu'elle est appelée.

### **Type de retour**

Le type de retour est la valeur renvoyée par la méthode après son

exécution. Si la méthode ne renvoie rien alors elle est décrite avec le

mot "void". Si elle renvoie par exemple un entier, elle est décrite avec

le mot int.

```js
public int AddNumbers(int a, int b)

{

int sum = a + b;

return sum;

}
```

```js
public void DisplaySumInLog(int sum){

Debug.Log("la somme est : "+sum);

}
```

**Démonstration**

Création de différentes méthodes dans le Start d'un script.

**C'est à vous :**

1.  Créez un nouveau script que vous nommerez SumScript.cs

2.  Ouvrez le script dans votre IDE

3.  Déclarez deux variables int en public

4.  Ajoutez deux méthodes à la classe SumScript.cs

    1.  une première pour additionner deux entiers entrés en paramètres et retourner la somme
    2.  une seconde pour faire un display d'un entier en paramètre

5.  Faites un appel à chacune de ses méthodes dans le start de votre script.

6.  Dans unity, associez le script à un objet.

7.  Dans l'inspector vous devriez voir votre script et deux champs d'entier.

8.  Vous pouvez modifier ses entiers, puis appuyer sur play pour lancer le programme. qu'observez vous dans la console du navigateur ?

## **4- Les conditions**

Comme dans les autres langages que vous connaissez, les conditions

permettent de faire des tests dans notre programme. L'intérêt dans

Unity est de créer des événements dans notre jeu lorsque ces conditions

sont remplies.

```js
using UnityEngine;

public class LiveScript : MonoBehaviour

{

public int life = 0;

// Start is called before the first frame update

void Start()

{

if (life > 0)

{

Debug.Log("I'm alive");

}

else

{

Debug.Log("I'm dead");

}

}

// Update is called once per frame

void Update()

{

}

}
```

**Démonstration**

Création d'une condition simple et manipulation de la variable via

l'inspector.

**C'est à vous :**

1.  Créez un nouveau script que vous nommerez LiveScript.cs

2.  Dans le script, initiez une variable public int life

3.  Dans le start, faites des vérifications de condition pour afficher

    un log en fonction de la variable life.

    1.  si life est supérieur à 0 alors on affiche dans les log "I'm alive"
    2.  dans les autres cas on affiche dans les log "I'm dead"

4.  Lancez le programme par le bouton play et observez la console.

5.  Modifier la valeur de life dans l'inspector

6.  Lancez le programme par le bouton play et observez la console. Qu'observez-vous ?

## **5- Boucles**

En C# pour Unity, les boucles sont utilisées pour répéter des opérations

identiques plusieurs fois. Les boucles les plus couramment utilisées en

C# sont for, while et do-while.

La boucle for est utilisée pour exécuter une série d'instructions un

nombre déterminé de fois. Voici un exemple de boucle for en C# pour

Unity:

```js
for (int i = 0; i < 10; i++)

{

// Code to execute

}
```

Dans cet exemple, la boucle for exécute le code entre les accolades 10

fois.

La boucle while est utilisée pour exécuter une série d'instructions

tant qu'une condition est vraie. Voici un exemple de boucle while en C#

pour Unity:

```js
while (condition)

{

// Code to execute

}
```

Dans cet exemple, la boucle while exécute le code entre les accolades

tant que la condition est vraie.

La boucle do-while est similaire à la boucle while, mais elle exécute le

code entre les accolades au moins une fois, même si la condition est

fausse. Voici un exemple de boucle do-while en C# pour Unity:

```js
do

{

// Code to execute

} while (condition);
```

Dans cet exemple, la boucle do-while exécute le code entre les accolades

au moins une fois, puis continue à l'exécuter tant que la condition est

vraie.

**Démonstration**

Dans le script précédent ajouter une boucle for, while et do while

**C'est à vous :**

1\. Dans le start du script précédent, ajoutez différentes boucles

2\. Cliquez sur le bouton "play" pour voir le résultat dans la console.

## **6- Debug.log**

La classe Debug est une classe de base en C# pour Unity qui permet de

visualiser des informations dans l'éditeur Unity.

Les méthodes exposées par cette classe peuvent aider à comprendre ou à

enquêter sur ce qui se passe dans votre projet pendant son exécution.

Par exemple, vous pouvez utiliser cette classe pour afficher des

messages dans la fenêtre de la console Unity, dessiner des lignes

visuelles dans la vue de scène et la vue de jeu, et mettre en pause

l'exécution de votre script dans l'éditeur Unity.

Voici quelques exemples d'utilisation de la classe `Debug` en C# pour

Unity:

```js
// Afficher un message dans la console Unity

Debug.Log("Hello, Unity!");

// Dessiner une ligne visuelle dans la vue de scène

Debug.DrawLine(Vector3.zero, Vector3.one, Color.red, 60);

// Mettre en pause l'exécution du script dans l'éditeur Unity

Debug.Break();
```

La classe Debug contient également d'autres méthodes utiles pour le

débogage, telles que

\- Debug.Assert() pour vérifier une condition et afficher un message

d'erreur si elle est fausse,

\- Debug.LogWarning() pour afficher un avertissement dans la console

Unity, et

\- Debug.LogError() pour afficher une erreur dans la console Unity.

Plus d'information sur la classe Debug : <https://docs.unity3d.com/ScriptReference/Debug.html>

**Démonstration**

Démonstration des différentes fonctions de la classe Debug

**C'est à vous :**

1\. Dans un nouveau Script, testez la méthode Debug.Drawline

2\. Pour visualiser le résultat, lancez le player unity.

## **7- Scripting**

Nous avons vu que chaque GameObject de Unity est composé de Component

visible dans l'inspecteur. Unity permet de créer vos propres components

en utilisant le scripting.

La structure de base d'un script est la suivante:

```js
using System.Collections;

using System.Collections.Generic;

using UnityEngine;

public class MonNouveauScript : MonoBehaviour

{

// Start is called before the first frame update

void Start()

{

}

// Update is called once per frame

void Update()

{

}

}
```

### **7a- namespace**

Un namespace est un moyen de regrouper des classes et des fonctions

connexes sous un même nom. Cela permet d'éviter les conflits de noms et

de faciliter la gestion du code. Par exemple, vous pouvez créer un

namespace appelé "MyGame" pour contenir toutes les classes et fonctions

liées à votre jeu. Vous pouvez ensuite accéder à ces classes et

fonctions en utilisant le préfixe "MyGame."

"System.Collections" est un namespace dans le cadre .NET qui contient

des interfaces et des classes qui définissent diverses collections

d'objets, telles que des listes, des files d'attente, des tableaux de

bits, des tables de hachage et des dictionnaires . Il fournit un moyen

d'organiser les données de manière structurée et d'effectuer des

opérations dessus.

Par exemple, la classe "ArrayList" dans "System.Collections" est un

tableau dynamique qui peut stocker des objets de n'importe quel type .

```js
namespace MyGame {

public class Controller1 : MonoBehaviour {

...

}

}
```

### **7b- MonoBehaviour**

"MonoBehaviour" est une classe dans Unity qui sert de base pour la

plupart des scripts. Elle fournit un ensemble de méthodes intégrées qui

sont appelées automatiquement au cours du cycle de vie d'un GameObject.

### **7c- Start**

La fonction Start() est une fonction intégrée dans les scripts Unity qui

est appelée lorsqu'un script est activé. Elle est appelée exactement

une fois dans la durée de vie du script et est utilisée pour initialiser

des variables ou des états qui doivent être configurés avant que le

script puisse s'exécuter.

### **7d- Update**

La fonction Update() est une fonction intégrée dans Unity qui est

appelée à chaque image. Update() est la fonction la plus couramment

utilisée pour implémenter tout type de script de jeu. Tous les scripts

MonoBehaviour n'ont pas besoin de Update(), mais si vous voulez mettre

à jour quelque chose chaque image, c'est là que vous le ferez.

**Démonstration**

Démonstration de l'utilisation de classe update

**C'est à vous :**

1\. Sélectionnez un objet présent dans votre scène.

2\. Ajouter lui un nouveau script que vous nommerez "move"

3\. Dans un premier temps , ajoutez la ligne suivante dans le "Start" du

script this.transform.Translate(Vector3.up);

4\. Lancez le player Que remarquez-vous ?

5\. Dans un second temps , ajoutez la ligne suivante dans le "Update" du

script this.transform.Translate(Vector3.up); Que remarquez-vous ?