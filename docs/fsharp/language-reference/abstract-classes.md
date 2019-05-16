---
title: Clases abstractas
description: Obtenga información sobre F# abstraer las clases, que deja algunos o todos los miembros sin implementar y representan la funcionalidad común de un conjunto diverso de tipos de objeto.
ms.date: 05/16/2016
ms.openlocfilehash: 8251d481c9056d40a0b13ae3c89353406986c116
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645543"
---
# <a name="abstract-classes"></a>Clases abstractas

*Clases abstractas* son clases que dejan algunos o todos los miembros sin implementar para que se pueden proporcionar implementaciones de las clases derivadas.

## <a name="syntax"></a>Sintaxis

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>Comentarios

En la programación orientada a objetos, una clase abstracta se usa como clase base de una jerarquía y representa la funcionalidad común de un conjunto diverso de tipos de objeto. Como el nombre "abstract" implica, las clases abstractas a menudo no se corresponden directamente a entidades concretas en el dominio del problema. Sin embargo, representan lo que muchas entidades concretas diferentes tienen en común.

Las clases abstractas deben tener el `AbstractClass` atributo. Puede haber miembros implementados y. El uso del término *abstracta* cuando se aplica a una clase es el mismo que en otros lenguajes. NET; sin embargo, el uso del término *abstracta* cuando se aplica a los métodos (y propiedades) es un poco diferente en F# desde su uso en otros lenguajes. NET. En F#, cuando un método está marcado con el `abstract` palabra clave, esto indica que un miembro tiene una entrada, conocida como un *ranura distribución virtual*, en la tabla interna de funciones virtuales de ese tipo. En otras palabras, el método es virtual, aunque el `virtual` no se utiliza la palabra clave en el F# lenguaje. La palabra clave `abstract` se utiliza en los métodos virtuales, independientemente de si se implementa el método. La declaración de una ranura de distribución virtual es independiente de la definición de un método para esa ranura de envío. Por lo tanto, el F# equivalente de una declaración de método virtual y una definición en otro lenguaje de .NET es una combinación de una declaración de método abstracto y una definición independiente, con cualquiera el `default` palabra clave o el `override` palabra clave. Para obtener más información y ejemplos, vea [métodos](members/methods.md).

Una clase se considera abstracta solo si hay métodos abstractos que se declaran pero no definidos. Por lo tanto, las clases que tienen métodos abstractos no son necesariamente clases abstractas. A menos que una clase no definido métodos abstractos, no use la **AbstractClass** atributo.

En la sintaxis anterior, *modificador de accesibilidad* puede ser `public`, `private` o `internal`. Para más información, vea [Access Control](access-control.md) (Control de acceso).

Al igual que con otros tipos, clases abstractas pueden tener una clase base y una o varias interfaces base. Cada clase base o interfaz aparece en una línea independiente, junto con el `inherit` palabra clave.

La definición de tipo de una clase abstracta puede contener miembros definidos completamente, pero también puede contener a miembros abstractos. La sintaxis de los miembros abstractos se muestra por separado en la sintaxis anterior. En esta sintaxis, el *signatura de tipo* de un miembro es una lista que contiene los tipos de parámetros en orden y los tipos de valor devueltos, separada por `->` tokens o `*` tokens según corresponda para currificadas y la tupla parámetros. La sintaxis de las signaturas de tipo de miembro abstracto es el mismo que el se usa en los archivos de firma y que muestra IntelliSense en el Editor de código de Visual Studio.

El código siguiente muestra una clase abstracta Shape, que tiene dos clases derivadas de no abstracta, Square y Circle. El ejemplo muestra cómo usar las propiedades, métodos y clases abstractas. En el ejemplo, la forma de clase abstracta representa los elementos comunes de las entidades concretas circle y square. Las características comunes de todas formas (en un sistema de coordenadas bidimensional) se abstraen en la clase Shape: la posición en la cuadrícula, un ángulo de giro y las propiedades de área y el perímetro. Estos se pueden invalidar, salvo la posición, el comportamiento de los cuales no se pueden cambiar las formas individuales.

Puede invalidar el método de rotación, como se muestra en la clase Circle, que es la rotación invariable dada su simetría. Por lo que en la clase Circle, el método de rotación se reemplaza por un método que no hace nada.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Salida:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Vea también

- [Clases](classes.md)
- [Miembros](members/index.md)
- [Métodos](members/methods.md)
- [Propiedades](members/Properties.md)
