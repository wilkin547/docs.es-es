---
title: Métodos
description: 'Obtenga información sobre cómo un método de F # es una función asociada a un tipo que se usa para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.'
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224105"
---
# <a name="methods"></a>Métodos

Un *método* es una función que está asociada a un tipo. En la programación orientada a objetos, los métodos se utilizan para exponer e implementar la funcionalidad y el comportamiento de los objetos y tipos.

## <a name="syntax"></a>Sintaxis

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, puede ver las distintas formas de declaraciones y definiciones de método. En cuerpos de método más largos, un salto de línea sigue el signo igual (=) y se aplica sangría al cuerpo del método completo.

Los atributos se pueden aplicar a cualquier declaración de método. Preceden a la sintaxis de una definición de método y suelen aparecer en una línea independiente. Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).

Se pueden marcar los métodos `inline` . Para más información sobre `inline`, vea [Inline Functions](../functions/inline-functions.md) (Funciones insertadas).

Los métodos no insertados se pueden usar de forma recursiva dentro del tipo; no es necesario usar explícitamente la `rec` palabra clave.

## <a name="instance-methods"></a>Métodos de instancia

Los métodos de instancia se declaran con la `member` palabra clave y un *identificador automático*, seguido de un punto (.) y el nombre del método y los parámetros. Como es el caso de los `let` enlaces, la *lista de parámetros* puede ser un patrón. Normalmente, los parámetros de método se delimitan entre paréntesis en una forma de tupla, que es la forma en que los métodos aparecen en F # cuando se crean en otros lenguajes .NET Framework. Sin embargo, también es común la forma currificada (parámetros separados por espacios) y también se admiten otros patrones.

En el ejemplo siguiente se muestra la definición y el uso de un método de instancia no abstracta.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

En los métodos de instancia, no use el identificador propio para tener acceso a los campos definidos mediante el uso de enlaces Let. Use el identificador propio al acceder a otros miembros y propiedades.

## <a name="static-methods"></a>Métodos estáticos

La palabra clave `static` se usa para especificar que se puede llamar a un método sin una instancia de y que no está asociado a una instancia de objeto. De lo contrario, los métodos son métodos de instancia.

En el ejemplo de la sección siguiente se muestran los campos declarados con la `let` palabra clave, los miembros de propiedad declarados con la `member` palabra clave y un método estático declarado con la `static` palabra clave.

En el ejemplo siguiente se muestra la definición y el uso de métodos estáticos. Suponga que estas definiciones de método se encuentran en la `SomeType` clase de la sección anterior.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Métodos abstractos y virtuales

La palabra clave `abstract` indica que un método tiene una ranura de envío virtual y podría no tener una definición en la clase. Una *ranura de envío virtual* es una entrada de una tabla de funciones que se mantiene internamente y que se utiliza en tiempo de ejecución para buscar llamadas a funciones virtuales en un tipo orientado a objetos. El mecanismo de distribución virtual es el mecanismo que implementa el *polimorfismo*, una característica importante de la programación orientada a objetos. Una clase que tiene al menos un método abstracto sin una definición es una *clase abstracta*, lo que significa que no se puede crear ninguna instancia de esa clase. Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).

Las declaraciones de método abstracto no incluyen un cuerpo de método. En su lugar, el nombre del método va seguido de un signo de dos puntos (:) y una firma de tipo para el método. La signatura de tipo de un método es la misma que la que se muestra en IntelliSense al pausar el puntero del mouse sobre un nombre de método en el editor de Visual Studio Code, excepto sin nombres de parámetro. El intérprete también muestra las signaturas de tipo, fsi.exe, cuando se trabaja de forma interactiva. La signatura de tipo de un método se forma enumerando los tipos de los parámetros, seguidos del tipo de valor devuelto, con símbolos de separador adecuados. Los parámetros currificados están separados por `->` y los parámetros de tupla están separados por `*` . El valor devuelto siempre está separado de los argumentos por un `->` símbolo. Los paréntesis se pueden usar para agrupar parámetros complejos, como cuando un tipo de función es un parámetro, o para indicar si una tupla se trata como un parámetro único en lugar de como dos parámetros.

También puede proporcionar definiciones default de métodos abstractos agregando la definición a la clase y usando la `default` palabra clave, tal como se muestra en el bloque de sintaxis de este tema. Un método abstracto que tiene una definición en la misma clase es equivalente a un método virtual en otros lenguajes .NET Framework. Tanto si existe una definición como si no, la `abstract` palabra clave crea una nueva ranura de envío en la tabla de funciones virtuales para la clase.

Independientemente de si una clase base implementa sus métodos abstractos, las clases derivadas pueden proporcionar implementaciones de métodos abstractos. Para implementar un método abstracto en una clase derivada, defina un método que tenga el mismo nombre y la misma firma en la clase derivada, excepto use la `override` `default` palabra clave o y proporcione el cuerpo del método. Las palabras clave `override` y `default` significan exactamente lo mismo. Use `override` si el nuevo método invalida una implementación de clase base; Utilice `default` cuando cree una implementación en la misma clase que la declaración abstracta original. No use la `abstract` palabra clave en el método que implementa el método que se declaró Abstract en la clase base.

En el ejemplo siguiente se muestra un método abstracto `Rotate` que tiene una implementación predeterminada, que es el equivalente de un método virtual .NET Framework.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

En el ejemplo siguiente se muestra una clase derivada que reemplaza un método de clase base. En este caso, la invalidación cambia el comportamiento para que el método no hace nada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Métodos sobrecargados

Los métodos sobrecargados son métodos que tienen nombres idénticos en un tipo determinado pero que tienen argumentos diferentes. En F #, normalmente se usan argumentos opcionales en lugar de métodos sobrecargados. Sin embargo, los métodos sobrecargados se permiten en el lenguaje, siempre que los argumentos estén en forma de tupla, no en formato currificados.

## <a name="optional-arguments"></a>Argumentos opcionales

A partir de F # 4,1, también puede tener argumentos opcionales con un valor de parámetro predeterminado en los métodos.  Esto ayuda a facilitar la interoperación con el código de C#.  En el ejemplo siguiente se muestra la sintaxis:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Tenga en cuenta que el valor pasado para `DefaultParameterValue` debe coincidir con el tipo de entrada.  En el ejemplo anterior, es un `int` .  Si se intenta pasar un valor no entero a, se `DefaultParameterValue` producirá un error de compilación.

## <a name="example-properties-and-methods"></a>Ejemplo: propiedades y métodos

El ejemplo siguiente contiene un tipo que tiene ejemplos de campos, funciones privadas, propiedades y un método estático.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Consulte también

- [Miembros](index.md)
