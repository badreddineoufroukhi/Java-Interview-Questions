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

## Installation

Clonez le repo et exécutez le code dans votre IDE ou terminal.

```bash
git clone https://github.com/ton-repo.git
cd ton-repo
# Compiler et exécuter les exemples dans chaque fichier
```

## Contribuer

Si vous avez des questions ou des suggestions, n'hésitez pas à ouvrir un ticket ou à proposer des pull requests.

---

Ceci est un modèle que tu peux adapter et utiliser pour ton repo GitHub. Il fournit des explications, des exemples de code, et une structure pour faciliter la compréhension des concepts Java.
