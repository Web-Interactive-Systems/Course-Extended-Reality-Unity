---
type: NoteCard
---

# lab - C# GameObjects Behaviors
Designing Extended Reality Applications Using Unity

**Objectifs**

*   Apprendre à travailler avec des assets
*   Comprendre les collisions.

**Leçons**

*   Manipuler des assets avec des scripts
*   User Input
*   Rigidbodies
*   Colliders
*   Box, Sphere, Capsule

## **1- Cube, Sphere, Capsule**

**Rappel** : Dans Unity, un GameObject est un objet fondamental qui

représente des personnages, des accessoires et des décors dans une

scène. Les GameObjects sont des conteneurs pour les components qui

définissent leur comportement et leur apparence.

Les GameObjects peuvent être créés directement dans Unity ou importés à

partir de logiciels de modélisation 3D tiers. Les objets primitifs tels

que le cube, la sphère et la capsule peuvent être créés directement dans

Unity via le menu GameObject > 3D Object.

Ces objets sont des formes de base qui peuvent être utilisées pour créer

des objets simples dans Unity. Ils sont souvent utilisés comme

placeholders pour les modèles plus complexes ou pour les tests de

fonctionnalités.

*   Le cube est une forme simple qui peut être utilisée pour créer des

murs, des boîtes, des marches et d'autres objets similaires.

*   La sphère est utile pour représenter des balles, des planètes et des

projectiles.

*   La capsule est souvent utilisée pour représenter des objets

cylindriques tels que des poteaux, des tuyaux et des roues.

**Démonstration**

Ajouter des sphères, capsules, et cubes dans un nouveau projet.

Composition des objets de base.

**C'est à vous :**

1\. créez un nouveau projet

2\. ajouter une sphère à votre scène

3\. ajouter un cube à votre scène

4\. ajoutez une capsule à votre scène

## **2- User Input**

La notion de user input dans Unity fait référence à la manière dont les

utilisateurs interagissent avec un jeu ou une application. Les entrées

utilisateur peuvent inclure des actions telles que cliquer sur un

bouton, appuyer sur une touche du clavier, toucher l'écran d'un

appareil mobile, etc.

Unity fournit une classe appelée \`Input\` qui permet de lire les axes

configurés dans les entrées de jeu conventionnelles et d'accéder aux

données multi-touch/accéléromètre sur les appareils mobiles. Pour lire

un axe, utilisez \`Input.GetAxis\` avec l'un des axes par défaut

suivants: "Horizontal" et "Vertical" sont mappés sur le joystick, A,

W, S, D et les touches fléchées.

Plus d'information sur la classe Input: [[Unity - Scripting API: Input

(unity3d.com)]{.underline}]\(<https://docs.unity3d.com/ScriptReference/Input.html>)

**Démonstration**

Utilisation de user input dans un script.

**C'est à vous :**

1\. Créez un nouveau Script MoveController.cs

2\. Dans le script ajouter la ligne ci-dessous

![]\(:u[media/image2.png]){width="4.958333333333333in"

height="0.9479166666666666in"}

3\. Ajoutez le script à un de vos objets

4\. Lancez le player Unity

5\. Appuyez sur les flèche gauche et droite de votre clavier.

Que remarquez-vous ?

.................................................................................................................................................................................................................................................................................................................................................................................

**# 3- Rigidbodies**

Dans Unity, un Rigidbody est un composant qui permet à un objet de se

comporter sous le contrôle de la physique. Il permet d'interagir avec

la physique de vos objets et de simuler la physique du monde réel.

Les Rigidbodies permettent de contrôler la position et la rotation d'un

objet en utilisant la simulation physique. Les objets avec un Rigidbody

appliquent des forces et des impulsions en réponse aux collisions et aux

interactions physiques avec d'autres objets.

Plus d'information sur rigidbody: [[Unity - Scripting API: Rigidbody

(unity3d.com)]{.underline}]\(<https://docs.unity3d.com/ScriptReference/Rigidbody.html>)

**Démonstration**

Ajout de Rigidbody aux trois objets. jouer avec les masses, la gravité

**C'est à vous :**

5\. Ajoutez des RigidBodies aux 3 objets préalablement créés

6\. Lancez le player Unity

Que remarquez-vous ? .................................................................................................................................................................................................................................................................................................................................................................................

7\. Pour chacun des objets, désactivez la notion de gravité dans le

component "RigidBody"

8\. Lancez le player Unity

Que remarquez-vous ?

.................................................................................................................................................................................................................................................................................................................................................................................

## **4- Colliders**

Dans Unity, un Collider est un composant qui permet de gérer les collisions entre les objets. Les colliders sont des formes invisibles qui sont attachées aux objets et qui définissent leur forme pour les collisions physiques. Il existe plusieurs types de colliders dans Unity, chacun adapté à des formes d'objets spécifiques. Les types de colliders les plus courants sont les suivants:

*   Box Collider: Un collider en forme de boîte qui gère les collisions pour les objets cubiques.
*   Sphere Collider: Un collider en forme de sphère qui gère les collisions pour les objets sphériques.
*   Capsule Collider: Un collider en forme de capsule qui gère les collisions pour les objets cylindriques

**Démonstration**

Désactivation du collider.

**C'est à vous :**

9\. Désactiver le collider de la sphere

10\. Lancer le player Unity

11\. Faites bouger le cube pour qu'il entre en collision avec la sphère

et la capsule

Que remarquez-vous ?

## **5- project racing car**

### **Création du projet**

1\. Dans le unity HUB, créez un nouveau projet qui se nommera

"project_car_racing" avec le template "3D core"

2\. Récupérez le zip Prototype1 - Starter Files.zip sur moodle

3\. importez les assets dans unity, depuis le menu principal ,

sélectionnez

Assets > Import Package > Custom Package

sélectionnez Prototype-1_Starter-Files.unitypackage file

4\. Dans la fenêtre d'explorateur de projet, ouvrez la scène Prototype1.

### **Ajout de véhicule**

1\. Dans la fenêtre d'explorateur de projet, ouvrez Assets > Course

Library > Vehicles

2\. sélectionnez un véhicule et faites un drag and drop du véhicule sur

la route dans la visualisation de la scène.

3\. Si votre véhicule est sélectionné dans la scène et que votre curseur

de souris et sur la prévisualisation de la scène, un appui sur la

touche "F" permet de faire un focus sur le véhicule.

4\. Vous pouvez ensuite utiliser la molette pour zoomer et dezoomer .

5\. La touche alt + clic gauche de la souris permet de tourner autour de

l'objet

6\. La touche alt + clic droit + molette permet de zoomer/dézoomer sur

l'objet

### **Ajout d'obstacle**

1\. Dans la fenêtre d'explorateur de projet, ouvrez Assets > Course

Library > Obstacle

2\. Faire un drag an drop de l'obstacle dans le visualiseur de la scène

ou dans la hiérarchie de la scène

3\. Dans l'inspector, en haut à gauche du component transform, cliquez

sur les 3 petits point pour afficher plus d'options

4\. Selectionnez Reset Property > position

5\. Puis dans l'inspector , modifiez directement les propriété de la

position avec les valeurs x=0, y=0, z=25

6\. Renommer les deux objets ajoutés "Vehicle" et "Obstacle". Pour cela,

clic droit sur l'objet>Rename

### **Camera**

1\. Sélectionnez la caméra dans la hiérarchie et appuyez sur "F" pour

mettre le focus dessus

2\. Appuyez sur le bouton play pour faire fonctionner le jeu, appuyez de

retour pour le stopper

3\. Utilisez les outils pour repositionner la caméra et la faire tourner

de telle sorte à ce qu'elle soit derrière le véhicule.

### **Script**

1\. Dans l'explorateur de projet, créer un nouveau dossier "Scripts"

2\. Dans le dossier que vous venez de créer, créez un nouveau Script que

vous appellerez "PlayerController"

3\. Faite un glisser déposer du script sur le véhicule

4\. Sélectionnez le véhicule pour vous assurez que le script y est bien

associé

5\. Faite un double clic sur le script dans l'explorateur de fichier

pour l'ouvrir dans votre IDE

6\. Dans le Update du script, ajouter un commentaire

```js
void Update()

{

//move the vehicle forward

}
```

7\. Sous votre commentaire, tapez transform.Translate(0,0,1);

à chaque frame, l'objet va avancé de 1 sur l'axe z.

```js
void Update()

{

//move the vehicle forward

transform.Translate(0, 0, 1);

}
```

8\. Sauvegardez le script et lancez le jeu dans Unity

Qu'observez-vous ?

9\. Dans le script, remplacez les coordonnées (0,0,1) par Vector3.forward sauvegardez le script et lancez le jeu dans Unity

Qu'observez-vous ?

10\. Le véhicule roule un peu vite, nous allons adapter la vitesse. Pour

cela nous allons utilisez la classe Time

```js
void Update()

{

//move the vehicule froward

transform.Translate(Vector3.forward * Time.deltaTime * 20);

}
```

11\. Sauvegardez le script et lancez le jeu dans Unity

Qu'observez-vous ?

### **Rigidbody**

1\. Sélectionnez le véhicule, puis dans l'inspecteur cliquez sur "add

component" et ajoutez un "RigidBody"

2\. Faites de même avec l'obstacle

3\. Modifiez la valeur "Mass" des deux components RigidBody comme si il

s'agissait de Kilogramme

4\. Lancez le jeu

Qu'observez-vous ?

## **Duplication d'obstacle**

1\. Dans la hiérarchie de la scene, sélectionnez l'obstacle, glisser le

en bas de la hiérarchie

2\. Faites ensuite un Ctrl + D pour dupliquer l'élément. et modifier la

valeur Z de la position de l'obstacle pour le déplacer.

3\. Répétez les manipulations plusieurs fois pour créer plusieurs

obstacles.

4\. Lancez le jeu

## **Ajout d'une variable pour la vitesse du véhicule**

1\. Dans le script PlayerController, ajouter une variable public de type

float et de nom speed et de valeur 20.

2\. Dans l'appel à la méthode Translate remplacez le nombre 20 par la

variable speed.

3\. Sauvegardez le script et lancez le jeu

## **Créez un nouveau Script pour la camera**

1\. Dans le dossier scripts, créer un nouveau script du nom de

"FollowPlayer" et associez le à la camera.

2\. Dans le script ajouter une variable public de type GameObject et de

nom player

3\. Dans le Update du script, associez la position du player à la

position de la camera.

```js
public class FollowPlayer : MonoBehaviour

{

public GameObject player;

// Start is called before the first frame update

void Start()

{

}

// Update is called once per frame

void Update()

{

transform.position = player.transform.position;

}

}
```

4\. Sauvegardez le script, puis dans Unity faites un drag an drop du

véhicule dans le script que vous venez de créer.

5\. Lancez le jeu

Qu'observez-vous ?

6\. Pour éviter que la camera soit placée trop près du sol, nous allons

la décaler légèrement. Il s'agit d'ajouter d'un Offset à la camera.

Dans le script FollowPlayer, modifiez la position de la manière

suivante.

```js
void Update()

{

transform.position = player.transform.position+new Vector3(0,5,-7);

}
```

7\. Sauvegardez le script et lancez le jeu

Qu'observez-vous ?

8\. Pour avoir un code "plus propre", ajouter un variable private Vector3 offset pour y mettre les valeurs du offset. private Vector3 offset = new Vector3(0, 5, -7);

```js
transform.position = player.transform.position+offset;
```

9\. La caméra suit le véhicule mais le suivi est un peu saccadé. Pour y

remédier nous allons faire le suivi dans le LateUpdate plutôt que

dans le update

**Information** :

La fonction Update est appelée une fois par image et est utilisée pour effectuer des mises à jour de logique de jeu générales telles que la gestion des entrées utilisateur, le mouvement d'objets, etc.

La fonction LateUpdate est appelée une fois par image après que toutes les fonctions Update ont été appelées. Elle est couramment utilisée pour les tâches liées à la caméra, telles que le suivi en douceur d'un objet cible ou l'exécution d'actions dépendantes d'autres mises à jour

```js
void LateUpdate()

{

transform.position = player.transform.position+offset;

}
```

10\. Sauvegardez le script et lancez le jeu

Qu'observez-vous ?

### **Ajout de contrôle du véhicule**

1\. Dans le script PlayerController, ajouter une variable public de type

float et de nom turnSpeed

2\. Dans le update de ce même script ajouter cette ligne

```js
void Update()

{

//move the vehicule forward

transform.Translate(Vector3.forward * Time.deltaTime * speed);

transform.Translate(Vector3.right * Time.deltaTime * turnSpeed);

}
```

3\. Sauvegardez le script et lancez le jeu.Utilisez le slider de la

variable turnSpeed pour aller vers la droite ou la gauche.

## **Input utilisateur**

1\. Dans le menu principal de unity. edit>Project Settings,

sélectionnez input Manager puis explorez les différents "axes".

2\. Dans le PlayerController.cs Script ajoutez une nouvelle variable

public de type float et de nom horizontalInput

3\. Puis dans le update, associez la valeur de Input

GetAxis("Horizontal") à la variable horizontalInput.

4\. Enfin, ajoutez la variable au paramètre passé dans la méthode

translate quoi permet la direction comme ci-dessous

```js
void Update()

{

horizontalInput = Input.GetAxis("Horizontal");

//move the vehicule forward

transform.Translate(Vector3.forward * Time.deltaTime * speed);

transform.Translate(Vector3.right * Time.deltaTime * turnSpeed *

horizontalInput);

}
```

5\. Sauvegardez le script et lancez le jeu

Qu'observez-vous ?

6\. De la même manière, nous allons gérer la vitesse du véhicule.

créez une variable public float forwardInput;

7\. Dans le update, associez lui la valeur de Input.GetAxis("Vertical")

et ajoutez la variable dans le calcul du paramètre passé à la

méthode Translate qui gère l'avancement du véhicule.

```js
void Update()

{

horizontalInput = Input.GetAxis("Horizontal");

verticalInput = Input.GetAxis("Vertical");

//move the vehicule forward

transform.Translate(Vector3.forward * Time.deltaTime * speed*

verticalInput);

transform.Translate(Vector3.right * Time.deltaTime * turnSpeed *

horizontalInput);

}
```

8\. Sauvegardez le script et lancez le jeu

Qu'observez-vous ?

### **Rotation**

la voiture avance , va à gauche et à droite. mais elle ne tourne pas ,

elle glisse.

Nous allons faire en sorte que la voiture tourne.

1\. Reprenez votre script PlayerController

2\. Supprimez la ligne permettant de tourner à gauche ou à droite et

remplacez là par un appel à la méthode transform.Rotate() avec les

paramètres ci-dessous.

```js
void Update()

{

horizontalInput = Input.GetAxis("Horizontal");

verticalInput = Input.GetAxis("Vertical");

//move the vehicule forward

transform.Translate(Vector3.forward * Time.deltaTime * speed*

verticalInput);

//transform.Translate(Vector3.right * Time.deltaTime * turnSpeed *

horizontalInput);

transform.Rotate(Vector3.up,

turnSpeedhorizontalInputTime.deltaTime);

}
```

3\. Sauvegardez le script et lancez le jeu

Qu'observez-vous ?

### **Nettoyage du projet**

Il s'agit ici d'avoir un projet lisible et un code propre.

1\. Dans la hiérarchie du projet, ajouter un objet vide GameObject>create empty

2\. Nommez cet objet Obstacles (au pluriel).

3\. Sélectionner tous vos objets "obstacle" et faites un drag and drop

vers l'objet vide que vous venez de créer.

4\. Dans votre code, initialisez vos variables avec des valeurs.

5\. Les variables qui ne nécessitent pas d'être public doivent passer en private.

6\. Si besoin, ajoutez des commentaires.

## **6- Pour aller plus loin**

Le projet que vous venez de réaliser est issu des cours en ligne de

Unity. Si vous en avez le temps, ajoutez les fonctionnalités décrite sur la

page : <https://learn.unity.com/tutorial/bonus-features-1-share-your-work?uv=2021.3&projectId=5caccdfbedbc2a3cef0efe63>