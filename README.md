# Java Interview Questions

## 1) What are static blocks and static initializers in Java?

Les blocs statiques (ou initialisateurs statiques) sont utilisés pour initialiser des variables statiques dans une classe. Ils sont exécutés une seule fois, lorsque la classe est chargée en mémoire, avant tout autre code.

### Exemple de code :
```java
class Example {
    static int value;

    static {
        value = 10;
        System.out.println("Static block executed");
    }

    public static void main(String[] args) {
        System.out.println("Value: " + value);
    }
}
```

## 2) How to call one constructor from the other constructor?

En Java, on peut appeler un constructeur depuis un autre à l'aide de `this()`. Cela permet de réutiliser un autre constructeur de la même classe.

### Exemple de code :
```java
class Example {
    int value;

    // Premier constructeur
    Example() {
        this(10);  // Appel du second constructeur
        System.out.println("Default Constructor");
    }

    // Second constructeur
    Example(int value) {
        this.value = value;
        System.out.println("Constructor with value: " + value);
    }

    public static void main(String[] args) {
        new Example();
    }
}
```

## 3) What is method overriding in Java?

Le "method overriding" en Java consiste à redéfinir une méthode d'une classe par une méthode dans une sous-classe avec la même signature. Cela permet de modifier le comportement d'une méthode héritée.

### Exemple de code :
```java
class Parent {
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    @Override
    void display() {
        System.out.println("Child display");
    }

    public static void main(String[] args) {
        Parent p = new Child();
        p.display();
    }
}
```

## 4) What is the `super` keyword in Java?

Le mot-clé `super` en Java est utilisé pour faire référence à la classe parente d'une classe enfant. Il permet d'accéder aux membres (méthodes, variables) de la classe parent.

### Exemple de code :
```java
class Parent {
    void show() {
        System.out.println("Parent show");
    }
}

class Child extends Parent {
    void show() {
        super.show();  // Appel de la méthode de la classe parente
        System.out.println("Child show");
    }

    public static void main(String[] args) {
        Child c = new Child();
        c.show();
    }
}
```

## 5) Difference between method overloading and method overriding in Java?

- **Surcharge de méthode (Method Overloading)** : La méthode porte le même nom mais avec des paramètres différents.
- **Redéfinition de méthode (Method Overriding)** : La méthode d'une classe parente est redéfinie dans une sous-classe avec le même nom et la même signature.

### Exemple de surcharge :
```java
class Example {
    void display(int x) {
        System.out.println("Display with int: " + x);
    }

    void display(String s) {
        System.out.println("Display with String: " + s);
    }

    public static void main(String[] args) {
        Example obj = new Example();
        obj.display(10);
        obj.display("Hello");
    }
}
```

### Exemple de redéfinition :
```java
class Parent {
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    @Override
    void display() {
        System.out.println("Child display");
    }

    public static void main(String[] args) {
        Parent p = new Child();
        p.display();
    }
}
```

## 6) Difference between abstract class and interface?

- **Classe abstraite** : Peut contenir des méthodes avec ou sans implémentation. Elle permet d'hériter des comportements partagés.
- **Interface** : Contient uniquement des méthodes sans implémentation. Une classe peut implémenter plusieurs interfaces.

### Exemple de classe abstraite :
```java
abstract class Animal {
    abstract void sound();

    void breathe() {
        System.out.println("Breathing");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }

    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
        dog.breathe();
    }
}
```

### Exemple d'interface :
```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Bark");
    }

    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
    }
}
```

---


## 7) Why is Java platform-independent?

Java est indépendant de la plateforme grâce à la machine virtuelle Java (JVM). Le code source Java est compilé en bytecode, qui est exécuté par la JVM, peu importe le système d'exploitation.

### Exemple de code :
Le code source Java (`HelloWorld.java`) est compilé en bytecode (`HelloWorld.class`) qui peut être exécuté sur n'importe quelle plateforme disposant de la JVM.

```bash
javac HelloWorld.java  # Compilation en bytecode
java HelloWorld        # Exécution via la JVM
```

## 8) What is method overloading in Java?

Le surchargement de méthode en Java consiste à définir plusieurs méthodes avec le même nom, mais des paramètres différents (type, nombre ou ordre).

### Exemple de code :
```java
class Example {
    void display(int a) {
        System.out.println("Integer: " + a);
    }

    void display(String b) {
        System.out.println("String: " + b);
    }

    public static void main(String[] args) {
        Example obj = new Example();
        obj.display(10);        // Appelle display(int)
        obj.display("Hello");   // Appelle display(String)
    }
}
```

## 9) What is the difference between C++ and Java?

La principale différence entre C++ et Java est que C++ est un langage compilé, tandis que Java est un langage interprété (avec une étape de compilation en bytecode).

- C++ : Compilation directe en code machine.
- Java : Compilation en bytecode, puis interprétation par la JVM.

## 10) What is JIT compiler?

Le compilateur JIT (Just-In-Time) compile le bytecode Java en code machine au moment de l'exécution, ce qui améliore les performances du programme.

## 11) What is bytecode in Java?

Le bytecode en Java est un code intermédiaire généré après la compilation du code source Java. Il est indépendant de la plateforme et peut être exécuté sur n'importe quelle machine qui possède la Java Virtual Machine (JVM).

### Exemple de code :
```bash
javac HelloWorld.java  # Compilation en bytecode
java HelloWorld        # Exécution du bytecode via la JVM
```

## 12) Difference between `this()` and `super()` in Java?

- **`this()`** : Appelle un autre constructeur de la même classe.
- **`super()`** : Appelle un constructeur de la classe parente.

### Exemple de code :
```java
class Parent {
    Parent() {
        System.out.println("Parent Constructor");
    }
}

class Child extends Parent {
    Child() {
        super();  // Appel du constructeur parent
        System.out.println("Child Constructor");
    }

    public static void main(String[] args) {
        Child obj = new Child();
    }
}
```

## 13) What is a class?

Une classe est un modèle qui définit des objets. Elle contient des attributs (variables) et des méthodes (fonctions).

### Exemple de code :
```java
class Car {
    String model;
    int year;

    void start() {
        System.out.println("Car is starting");
    }
}
```

## 14) What is an object?

Un objet en Java est une instance d'une classe, qui représente un concept ou une entité du monde réel.

### Exemple de code :
```java
class Car {
    String model;
    int year;

    void start() {
        System.out.println("Car is starting");
    }

    public static void main(String[] args) {
        Car car = new Car();  // Création d'un objet
        car.start();           // Appel d'une méthode sur l'objet
    }
}
```

## 15) What is a method in Java?

Une méthode en Java est un bloc de code qui effectue une tâche spécifique. Elle est définie dans une classe et peut être appelée pour exécuter cette tâche.

### Exemple de code :
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();
        int sum = calc.add(5, 3);  // Appel de la méthode add
        System.out.println("Sum: " + sum);
    }
}
```

## 16) What is encapsulation?

L'encapsulation est un concept de la programmation orientée objet qui consiste à cacher les détails internes d'une classe et à ne rendre accessibles que les méthodes nécessaires.

### Exemple de code :
```java
class Person {
    private String name;  // Attribut privé

    public String getName() {  // Méthode publique pour accéder à l'attribut
        return name;
    }

    public void setName(String name) {  // Méthode publique pour modifier l'attribut
        this.name = name;
    }
}
```

## 17) Why is the `main()` method public, static, and void in Java?

- **`public`** : Pour qu'elle soit accessible par la JVM.
- **`static`** : Pour qu'elle soit exécutée sans créer d'objet de la classe.
- **`void`** : Car elle ne renvoie aucune valeur.

## 18) Explain about the `main()` method in Java?

La méthode `main()` est le point d'entrée d'un programme Java. C'est là que l'exécution commence.

### Exemple de code :
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

## 19) What is a constructor in Java?

Un constructeur en Java est une méthode spéciale utilisée pour initialiser les objets. Il a le même nom que la classe et n'a pas de type de retour.

### Exemple de code :
```java
class Car {
    String model;

    Car(String model) {  // Constructeur
        this.model = model;
    }

    public static void main(String[] args) {
        Car car = new Car("Toyota");
        System.out.println("Car model: " + car.model);
    }
}
```

## 20) What is the difference between `length` and `length()` in Java?

- **`length`** : Attribut pour les tableaux.
- **`length()`** : Méthode pour les chaînes de caractères.

### Exemple de code :
```java
// Pour un tableau
int[] arr = {1, 2, 3};
System.out.println("Array length: " + arr.length);

// Pour une chaîne de caractères
String str = "Hello";
System.out.println("String length: " + str.length());
```

## 21) What is ASCII Code?

Le code ASCII (American Standard Code for Information Interchange) est un système de codage qui représente des caractères sous forme de nombres.

## 22) What is Unicode?

Unicode est un système de codage qui permet de représenter tous les caractères de toutes les langues du monde.

## 23) Difference between Character Constant and String Constant in Java?

- **Caractère constant** : Un seul caractère entouré de guillemets simples, comme `'a'`.
- **Chaîne constante** : Une séquence de caractères entourée de guillemets doubles, comme `"Hello"`.

## 24) What are constants and how to create constants in Java?

Les constantes en Java sont des valeurs fixes qui ne changent pas pendant l'exécution du programme. Pour créer une constante, on utilise le mot-clé `final`, suivi du type de la variable.

### Exemple de code :
```java
final int CONSTANT = 100;
```

## 25) Difference between `>>` and `>>>` operators in Java?

- **`>>`** : Déplace les bits vers la droite et garde le signe (les nombres négatifs gardent leur signe).
- **`>>>`** : Déplace les bits vers la droite et remplace les bits vides par des zéros (les nombres négatifs ne gardent pas leur signe).

---

# Java Core Interview Questions - Coding Standards

Ce dépôt contient des questions d'entretien Java sur les normes de codage et la syntaxe de base, accompagnées d'exemples de code pour illustrer chaque concept.

## Table des matières

1. [Java Coding Standards for Classes](#1-java-coding-standards-for-classes)
2. [Java Coding Standards for Interfaces, Methods, Variables, Constants](#2-java-coding-standards-for-interfaces-methods-variables-constants)
3. [IS-A and HAS-A Relationship](#3-is-a-and-has-a-relationship)
4. [instanceof Operator](#4-instanceof-operator)
5. [null in Java](#5-null-in-java)
6. [Multiple Classes in One File](#6-multiple-classes-in-one-file)
7. [Access Modifiers for Top-Level Class](#7-access-modifiers-for-top-level-class)
8. [Package in Java](#8-package-in-java)
9. [Identifiers in Java](#9-identifiers-in-java)
10. [Access Modifiers](#10-access-modifiers)
11. [final Keyword](#11-final-keyword)
12. [Abstract Classes](#12-abstract-classes)

---

## 1. Java Coding Standards for Classes

- **Nom de la classe** : Utiliser le **camel case** avec la première lettre en majuscule.
  Exemple : `MaClasse`.
- **Nom des méthodes** : Utiliser le **camel case** avec la première lettre en minuscule.
  Exemple : `maMethode()`.

### Exemple :
```java
public class MyClass {
    public void myMethod() {
        System.out.println("Method in MyClass");
    }
}
```

---

## 2. Java Coding Standards for Interfaces, Methods, Variables, Constants

- **Interfaces** : Nom de l'interface en majuscule, avec des mots clairs.
  Exemple : `Drawable`.

- **Méthodes** : Utiliser des verbes au présent.
  Exemple : `calculateTotal()`.

- **Variables** : Nom en **camelCase**, début en minuscule.
  Exemple : `int totalAmount;`.

- **Constantes** : En majuscules, séparées par des underscores.
  Exemple : `public static final int MAX_SIZE = 100;`.

### Exemple :
```java
public interface Drawable {
    void draw();
}

public class Rectangle implements Drawable {
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}
```

---

## 3. IS-A and HAS-A Relationship

- **IS-A** : Indique l'héritage. Exemple : `class Car extends Vehicle`.
- **HAS-A** : Indique une relation de composition. Exemple : `class Car has a Engine`.

### Exemple IS-A :
```java
class Vehicle {
    void move() {
        System.out.println("Vehicle is moving");
    }
}

class Car extends Vehicle {
    void move() {
        System.out.println("Car is moving");
    }
}
```

### Exemple HAS-A :
```java
class Engine {
    void start() {
        System.out.println("Engine started");
    }
}

class Car {
    private Engine engine = new Engine();
    
    void startCar() {
        engine.start();
        System.out.println("Car started");
    }
}
```

---

## 4. instanceof Operator

L'opérateur `instanceof` permet de vérifier si un objet est une instance d'une classe ou d'une interface. Il retourne **true** si l'objet est de ce type, sinon **false**.

### Exemple :
```java
class Animal {}

class Dog extends Animal {}

public class Test {
    public static void main(String[] args) {
        Animal a = new Dog();
        System.out.println(a instanceof Dog);  // true
    }
}
```

---

## 5. null in Java

En Java, `null` représente l'absence de valeur. Cela signifie qu'une variable de type objet ne pointe vers aucune instance d'objet.

### Exemple :
```java
String str = null;
if (str == null) {
    System.out.println("The string is null");
}
```

---

## 6. Multiple Classes in One File

Oui, on peut avoir plusieurs classes dans un seul fichier en Java, mais une seule classe doit être publique et porter le même nom que le fichier.

### Exemple :
```java
public class MyClass {
    // Code de la classe MyClass
}

class AnotherClass {
    // Code de la classe AnotherClass
}
```

---

## 7. Access Modifiers for Top-Level Class

En Java, pour une classe en haut niveau, les modificateurs d'accès autorisés sont :
- **public** : Accessible depuis n'importe où.
- **default** (pas de modificateur) : Accessible uniquement dans son propre package.

### Exemple :
```java
public class MyClass {
    // Code de la classe publique
}

class DefaultClass {
    // Code de la classe avec modificateur par défaut
}
```

---

## 8. Package in Java

Un **package** en Java est un ensemble de classes et d'interfaces regroupées sous un même nom. Un fichier source Java ne peut contenir qu'un seul `package` statement au début du fichier.

### Exemple :
```java
package mypackage;

public class MyClass {
    // Code de la classe
}
```

---

## 9. Identifiers in Java

Les identifiants en Java sont des noms donnés aux variables, méthodes, classes, etc. Ils doivent commencer par une lettre, un underscore (_) ou un dollar ($), et peuvent être suivis de lettres, chiffres, underscores ou dollars.

### Exemple :
```java
int totalAmount; // Identifiant valide
int $amount;     // Identifiant valide
int _total;      // Identifiant valide
```

---

## 10. Access Modifiers

Les modificateurs d'accès permettent de définir la visibilité des classes, méthodes, variables, etc. Ils sont : **public**, **protected**, **private**, et **default** (sans modificateur).

### Exemple :
```java
public class MyClass {
    private int value;
    protected void display() {
        System.out.println(value);
    }
}
```

---

## 11. final Keyword

Le mot-clé **final** empêche la modification :
- **Variable** : La valeur ne peut pas être changée après l'initialisation.
- **Méthode** : Elle ne peut pas être redéfinie par une sous-classe.
- **Classe** : Elle ne peut pas être étendue.

### Exemple :
```java
final class MyClass {
    final int MAX_VALUE = 100;

    final void display() {
        System.out.println(MAX_VALUE);
    }
}
```

---

## 12. Abstract Classes

Une **classe abstraite** est une classe qui ne peut pas être instanciée directement. Elle contient souvent des méthodes abstraites qui n'ont pas de corps, donc la sous-classe doit les implémenter.

### Exemple :
```java
abstract class Animal {
    abstract void sound();  // Méthode abstraite

    void breathe() {
        System.out.println("Breathing");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Bark");
    }

    public static void main(String[] args) {
        Animal dog = new Dog();
        dog.sound();
    }
}
```
