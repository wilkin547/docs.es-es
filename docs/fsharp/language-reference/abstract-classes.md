---
title: Clases abstractas (F#)
description: 'Obtenga información acerca de clases abstractas de F #, lo cual dejar a algunos o todos los miembros no implementados y representa la funcionalidad común de un conjunto diverso de tipos de objeto.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0d7ca996de89c44a5cfb9197c1b515741a2303df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="abstract-classes"></a>Clases abstractas

*Clases abstractas* son clases que dejan algunos o todos los miembros sin implementar para que las clases derivadas pueden proporcionar implementaciones.

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
En la programación orientada a objetos, una clase abstracta sirve como clase base de una jerarquía y representa la funcionalidad común de un conjunto diverso de tipos de objeto. Como el nombre "abstract" implica, clases abstractas a menudo no corresponden directamente a entidades concretas en el dominio del problema. Sin embargo, representan lo que muchas entidades concretas diferentes tienen en común.

Las clases abstractas deben tener el `AbstractClass` atributo. Puede haber miembros implementados y. El uso del término *abstracta* cuando se aplica a una clase es el mismo que en otros lenguajes. NET; sin embargo, el uso del término *abstracta* cuando se aplica a los métodos (y propiedades) es un poco diferente en F # de su usar en otros lenguajes. NET. En F #, cuando un método está marcado con el `abstract` (palabra clave), esto indica que un miembro tiene una entrada, conocida como un *entrada de distribución virtual*, en la tabla interna de funciones virtuales de ese tipo. En otras palabras, el método es virtual, aunque la `virtual` no se utiliza la palabra clave en el lenguaje F #. La palabra clave `abstract` se utiliza en los métodos virtuales, independientemente de si se implementa el método. La declaración de una ranura de distribución virtual es independiente de la definición de un método para esa ranura de envío. Por lo tanto, el equivalente de F # de una declaración de método virtual y la definición en otro lenguaje de .NET es una combinación de una declaración de método abstracto y una definición independiente, con cualquiera el `default` palabra clave o el `override` (palabra clave). Para obtener más información y ejemplos, vea [métodos](members/methods.md).

Una clase se considera abstracta únicamente si hay métodos abstractos que se han declarado pero no definido. Por lo tanto, las clases que tienen métodos abstractos no son necesariamente clases abstractas. A menos que una clase tiene un indefinido métodos abstractos, no utilice la **AbstractClass** atributo.

En la sintaxis anterior, *modificador de accesibilidad* puede ser `public`, `private` o `internal`. Para más información, vea [Access Control](access-control.md) (Control de acceso).

Como ocurre con otros tipos, las clases abstractas pueden tener una clase base y una o varias interfaces base. Cada clase base o interfaz aparece en una línea independiente junto con el `inherit` palabra clave.

La definición de tipo de una clase abstracta puede contener miembros totalmente definidos, pero también puede contener a miembros abstractos. La sintaxis de miembros abstractos se muestran por separado en la sintaxis anterior. En esta sintaxis, la *signatura de tipo* de un miembro es una lista que contiene los tipos de parámetros en orden y los tipos de valor devueltos, separada por `->` tokens o `*` tokens según corresponda para currificadas y tupla parámetros. La sintaxis de las signaturas de tipo de miembro abstracto es el mismo que el se usa en los archivos de firma y se muestra en IntelliSense en el Editor de código de Visual Studio.

El código siguiente muestra una clase abstracta forma, que tiene dos clases derivadas de no abstracta, cuadrado y un círculo. En el ejemplo se muestra cómo utilizar propiedades, métodos y clases abstractas. En el ejemplo, la forma de clase abstracta representa los elementos comunes de las entidades concretas circle y square. Las características comunes de todas las formas (en un sistema de coordenadas bidimensional) se abstraen en la clase Shape: la posición en la cuadrícula, un ángulo de giro y las propiedades de área y el perímetro. Estos pueden ser invalidados, salvo la posición, el comportamiento de los cuales no se pueden cambiar las formas individuales.

Puede invalidar el método de rotación, como en la clase Circle, que es invariable rotación dada su simetría. Por lo que en la clase de círculo, el método de rotación se reemplaza por un método que no hace nada.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Salida:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Vea también
[Clases](classes.md)

[Miembros](members/index.md)

[Métodos](members/methods.md)

[Propiedades](members/Properties.md)
