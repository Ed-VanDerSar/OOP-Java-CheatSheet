# $\color{Apricot}{Herencia\ en\ Java}$

## Qué es la herencia?
La herencia es una manera de clasificar los objetos en distintintos niveles, siguiento una 
jerarquía: El objeto más abstracto esta en la cima de la jerarquía y los mås detallados en la base.

El término herencia es usado para indicar que cuando nos movemos hacia abajo en la jerarquía,
cada clasde hereda las características de la clase de arriba y, además añade niveles extra 
de detalles y compartamentisn específicos de clase.


Las relaciones de herencia se especifican con las siguientes keywords:
```java
class Superclass {
    // Atributos y métodos de la superclase
}

class Subclass extends Superclass {
    // tributos y métodos adicionales o en override 
}
```

## Ejemplo

```java
class Animal {
    void come() {
        System.out.println("El animal se alimenta.");
    }
}

class Perro extends Animal {
    void ladra() {
        System.out.println("El perro ladra.");
    }
}
```
En este ejemplo, `Perro` es una subclase de `Animal`. La clase perro hereda el el método `come` de `Animal`
y añade el nuevo método `ladra`.

<br>

> [!IMPORTANT]> Las subclases tienen acceso a todos los atributos y métodos no privados de la superclase 
> Cuando se crean instancias de la subclase es posible llamar a sus propios métodos 
> y a los métodos heradados

```java
Perro miPerro = new Perro();
miPerro.come();  // Método de clase Animal
miPerro.ladra(); // Método de clase Perro
```

> [!IMPORTANT]
> Un especto muy importante de la herencia es el método `overriding`. Esto permite a una subclase
>implementar de manera específica un método que ya esta de hecho defindo 
> en la supercalse.
> Esto se hace definiendo un método en la subclase con la misma firma y nombre del método 
> de la superclase.

```java
class Perro extends Animal {
    void come() {
        System.out.println("El perro come croquetas.");
    }
}
```

El método `come` de la clase `Perro` sobrescribir _(overrides)_ al método `come`
de la clase `Animal`, de manera que cuando `miPerro.come()` es llamado, este usa
el método sobrescrito de la clase `Perro`.

## Cómo funcion?

- Métodos y atributos _privados_ de la superclase no pueden ser alcanzados directamete por la 
subclases.
- Métodos y atributos _públicos_ de la superclase __son accesibles por__ todas
  subclases.


## Ventajas

- La herencia nos permite usar céodigo de las superclases sin la necesidad de reescribrilos.
- Se pueden extender facilmente clases ya creadas y añadir nuevas funcionalidades.

