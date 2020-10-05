---
title: 'Clases: Guía de programación de C#'
description: Obtenga información sobre los tipos de clases y cómo crearlas
ms.date: 08/21/2018
helpviewer_keywords:
- classes [C#]
- C# language, classes
ms.assetid: e8848524-7273-429f-8aba-c658d5eff5ad
ms.openlocfilehash: 68b41eef0b604b80a9659eddf45d6512eac44fd6
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607738"
---
# <a name="classes-c-programming-guide"></a>Clases (Guía de programación de C#)

## <a name="reference-types"></a>Tipos de referencia  

Un tipo que se define como una [clase](../../language-reference/keywords/class.md), es un *tipo de referencia*. Al declarar una variable de un tipo de referencia en tiempo de ejecución, esta contendrá el valor [null](../../language-reference/keywords/null.md) hasta que se cree expresamente una instancia de la clase mediante el operador [new](../../language-reference/operators/new-operator.md) o se le asigne un objeto de un tipo compatible que se ha creado en otro lugar, tal y como se muestra en el ejemplo siguiente:

```csharp
//Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

Cuando se crea el objeto, se asigna suficiente memoria en el montón administrado para ese objeto específico y la variable solo contiene una referencia a la ubicación de dicho objeto. Los tipos del montón administrado producen sobrecarga cuando se asignan y cuando los reclama la función de administración de memoria automática de CLR, conocida como *recolección de elementos no utilizados*. En cambio, la recolección de elementos no utilizados también está muy optimizada y no crea problemas de rendimiento en la mayoría de los escenarios. Para obtener más información sobre la recolección de elementos no utilizados, vea [Administración automática de la memoria y recolección de elementos no utilizados](../../../standard/garbage-collection/fundamentals.md).  
  
## <a name="declaring-classes"></a>Declarar clases

 Las clases se declaran mediante la palabra clave [class](../../language-reference/keywords/class.md) seguida por un identificador único, como se muestra en el siguiente ejemplo:

 ```csharp
//[access modifier] - [class] - [identifier]
 public class Customer
 {
    // Fields, properties, methods and events go here...
 }
```

 La palabra clave `class` va precedida del nivel de acceso. Como en este caso se usa [public](../../language-reference/keywords/public.md), cualquier usuario puede crear instancias de esta clase. El nombre de la clase sigue a la palabra clave `class`. El nombre de la clase debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido. El resto de la definición es el cuerpo de la clase, donde se definen los datos y el comportamiento. Los campos, las propiedades, los métodos y los eventos de una clase se denominan de manera colectiva *miembros de clase*.  
  
## <a name="creating-objects"></a>Creación de objetos

Aunque a veces se usan indistintamente, una clase y un objeto son cosas diferentes. Una clase define un tipo de objeto, pero no es un objeto en sí. Un objeto es una entidad concreta basada en una clase y, a veces, se conoce como una instancia de una clase.  
  
 Los objetos se pueden crear usando la palabra clave [new](../../language-reference/operators/new-operator.md), seguida del nombre de la clase en la que se basará el objeto, como en este ejemplo:  

 ```csharp
 Customer object1 = new Customer();
 ```

 Cuando se crea una instancia de una clase, se vuelve a pasar al programador una referencia al objeto. En el ejemplo anterior, `object1` es una referencia a un objeto que se basa en `Customer`. Esta referencia apunta al objeto nuevo, pero no contiene los datos del objeto. De hecho, puede crear una referencia de objeto sin tener que crear ningún objeto:  

```csharp
 Customer object2;
```

 No se recomienda crear referencias de objeto como esta, que no hace referencia a ningún objeto, ya que, si se intenta obtener acceso a un objeto a través de este tipo de referencia, se producirá un error en tiempo de ejecución. Pero dicha referencia puede haberse creado para hacer referencia a un objeto, ya sea creando un nuevo objeto o asignándola a un objeto existente, como en el siguiente ejemplo:  

 ```csharp
 Customer object3 = new Customer();
 Customer object4 = object3;
```
  
 Este código crea dos referencias de objeto que hacen referencia al mismo objeto. Por lo tanto, los cambios efectuados en el objeto mediante `object3` se reflejan en los usos posteriores de `object4`. Dado que los objetos basados en clases se tratan por referencia, las clases se denominan "tipos de referencia".  
  
## <a name="class-inheritance"></a>Herencia de clases  

Las clases admiten completamente la *herencia*, una característica fundamental de la programación orientada a objetos. Al crear una clase, puede heredar de cualquier otra interfaz o clase que no esté definida como [sealed](../../language-reference/keywords/sealed.md); y otras clases pueden heredar de su clase e invalidar los métodos virtuales de la clase.

La herencia se consigue mediante una *derivación*, en la que se declara una clase mediante una *clase base*, desde la que hereda los datos y el comportamiento. Una clase base se especifica anexando dos puntos y el nombre de la clase base seguido del nombre de la clase derivada, como en el siguiente ejemplo:  

 ```csharp
 public class Manager : Employee
 {
     // Employee fields, properties, methods and events are inherited
     // New Manager fields, properties, methods and events go here...
 }
 ```

Cuando una clase declara una clase base, hereda todos los miembros de la clase base excepto los constructores. Para obtener más información, vea [Herencia](inheritance.md).
  
A diferencia de C++, una clase de C# solo puede heredar directamente de una clase base. En cambio, dado que una clase base puede heredar de otra clase, una clase podría heredar indirectamente varias clases base. Además, una clase puede implementar directamente más de una interfaz. Para obtener más información, vea [Interfaces](../interfaces/index.md).  
  
Una clase puede declararse [abstracta](../../language-reference/keywords/abstract.md). Una clase abstracta contiene métodos abstractos que tienen una definición de firma, pero no tienen ninguna implementación. No se pueden crear instancias de las clases abstractas. Solo se pueden usar a través de las clases derivadas que implementan los métodos abstractos. Por el contrario, la clase [sealed](../../language-reference/keywords/sealed.md) no permite que otras clases se deriven de ella. Para más información, vea [Clases y miembros de clase abstractos y sellados](abstract-and-sealed-classes-and-class-members.md).  
  
Las definiciones de clase se pueden dividir entre distintos archivos de código fuente. Para más información, vea [Clases y métodos parciales](partial-classes-and-methods.md).  
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una clase pública que contiene una [propiedad implementada automáticamente](auto-implemented-properties.md), un método y un método especial denominado constructor. Para obtener más información, consulta los temas [Propiedades](properties.md), [Métodos](methods.md) y [Constructores](constructors.md). Luego, se crea una instancia de las instancias de la clase con la palabra clave `new`.  
  
[!code-csharp[Class Example](~/samples/snippets/csharp/programming-guide/classes-and-structs/class-example.cs)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Programación orientada a objetos](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [Polimorfismo](polymorphism.md)
- [Nombres de identificador](../inside-a-program/identifier-names.md)
- [Miembros](members.md)
- [Métodos](methods.md)
- [Constructores](constructors.md)
- [Finalizadores](destructors.md)
- [Objects](objects.md)
