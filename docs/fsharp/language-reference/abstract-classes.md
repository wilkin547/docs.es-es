---
title: Clases abstractas
description: Obtenga información F# sobre las clases abstractas, que dejan algunos o todos los miembros no implementados y representan la funcionalidad común de un conjunto diverso de tipos de objeto.
ms.date: 05/16/2016
ms.openlocfilehash: d7fc87178cff7c5c824992c97198b49f87025f00
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082948"
---
# <a name="abstract-classes"></a>Clases abstractas

*Las clases abstractas* son clases que dejan algunos o todos los miembros no implementados, de modo que las implementaciones pueden ser proporcionadas por clases derivadas.

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

En la programación orientada a objetos, una clase abstracta se utiliza como una clase base de una jerarquía y representa la funcionalidad común de un conjunto diverso de tipos de objeto. Como el nombre "abstract" implica, las clases abstractas no suelen corresponder directamente con entidades concretas del dominio del problema. Sin embargo, representan las distintas entidades concretas que tienen en común.

Las clases abstractas deben `AbstractClass` tener el atributo. Pueden tener miembros implementados y no implementados. El uso del término *abstracto* cuando se aplica a una clase es igual que en otros lenguajes .net; sin embargo, el uso del término *abstracto* cuando se aplica a métodos (y propiedades) es un poco F# diferente en respecto a su uso en otros lenguajes .net. En F#, cuando un método se marca con la `abstract` palabra clave, indica que un miembro tiene una entrada, conocida como *ranura de envío virtual*, en la tabla interna de funciones virtuales para ese tipo. En otras palabras, el método es virtual, aunque la `virtual` palabra clave no se usa en F# el lenguaje. La palabra `abstract` clave se usa en métodos virtuales independientemente de si se implementa el método. La declaración de una ranura de envío virtual es independiente de la definición de un método para esa ranura de envío. Por lo tanto F# , el equivalente de una declaración y definición de método virtual en otro lenguaje .net es una combinación de una declaración de método abstracto y una definición independiente `default` , con la `override` palabra clave o la palabra clave. Para obtener más información y ejemplos, vea [métodos](./members/methods.md).

Una clase se considera abstracta solo si hay métodos abstractos que se declaran pero no se definen. Por lo tanto, las clases que tienen métodos abstractos no son necesariamente clases abstractas. A menos que una clase tenga métodos abstractos sin definir, no use el atributo **AbstractClass** .

En la sintaxis anterior, el *modificador de accesibilidad* puede `public`ser `private` , `internal`o. Para más información, vea [Access Control](access-control.md) (Control de acceso).

Como con otros tipos, las clases abstractas pueden tener una clase base y una o varias interfaces base. Cada clase base o interfaz aparece en una línea independiente junto con la `inherit` palabra clave.

La definición de tipo de una clase abstracta puede contener miembros totalmente definidos, pero también puede contener miembros abstractos. La sintaxis de los miembros abstractos se muestra por separado en la sintaxis anterior. En esta sintaxis, la *signatura de tipo* de un miembro es una lista que contiene los tipos de parámetro en orden y los tipos de valor `->` devuelto, separados por `*` tokens o tokens, según corresponda para los parámetros currificados y de tupla. La sintaxis de las signaturas de tipo de miembro abstracto es la misma que la que se usa en los archivos de signatura y que se muestra en IntelliSense en el editor de Visual Studio Code.

En el código siguiente se muestra una forma de clase abstracta, que tiene dos clases derivadas no abstractas, Square y Circle. En el ejemplo se muestra cómo usar clases, métodos y propiedades abstractos. En el ejemplo, la forma de clase abstracta representa los elementos comunes del círculo y el cuadrado de las entidades concretas. Las características comunes de todas las formas (en un sistema de coordenadas bidimensional) se abstraen en la clase de forma: la posición en la cuadrícula, un ángulo de rotación y las propiedades del área y del perímetro. Se pueden invalidar, excepto en el caso de la posición, el comportamiento de las formas individuales que no pueden cambiar.

Se puede invalidar el método de rotación, como en la clase Circle, que es la rotación invariable debido a su simetría. Por lo tanto, en la clase Circle, el método de rotación se reemplaza por un método que no hace nada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Salida:**

```console
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Vea también

- [Clases](classes.md)
- [Miembros](./members/index.md)
- [Métodos](./members/methods.md)
- [Propiedades](./members/Properties.md)
