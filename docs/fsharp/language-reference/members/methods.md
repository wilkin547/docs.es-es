---
title: Métodos
description: Obtenga información sobre cómo un método de F es una función asociada a un tipo que se usa para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401068"
---
# <a name="methods"></a>Métodos

Un *método* es una función que está asociada a un tipo. En la programación orientada a objetos, se utilizan métodos para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.

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

## <a name="remarks"></a>Observaciones

En la sintaxis anterior, puede ver las diversas formas de declaraciones y definiciones de método. En los cuerpos de método más largos, un salto de línea sigue el signo igual (-) y se sangra todo el cuerpo del método.

Los atributos se pueden aplicar a cualquier declaración de método. Preceden a la sintaxis de una definición de método y normalmente se enumeran en una línea independiente. Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).

Los métodos `inline`se pueden marcar . Para más información sobre `inline`, vea [Inline Functions](../functions/inline-functions.md) (Funciones insertadas).

Los métodos no en línea se pueden utilizar de forma recursiva dentro del tipo; no hay necesidad de usar `rec` explícitamente la palabra clave.

## <a name="instance-methods"></a>Métodos de instancia

Los métodos de `member` instancia se declaran con la palabra clave y un *autoidentificador,* seguido de un punto (.) y el nombre y los parámetros del método. Como es el `let` caso de los enlaces, la *lista de parámetros* puede ser un patrón. Normalmente, se incluyen los parámetros de método entre paréntesis en un formulario de tupla, que es la forma en que aparecen los métodos en F - cuando se crean en otros lenguajes de .NET Framework. Sin embargo, la forma curried (parámetros separados por espacios) también es común, y también se admiten otros patrones.

En el ejemplo siguiente se muestra la definición y el uso de un método de instancia no abstracto.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Dentro de los métodos de instancia, no utilice el identificador propio para tener acceso a los campos definidos mediante el uso de enlaces let. Utilice el identificador automático al acceder a otros miembros y propiedades.

## <a name="static-methods"></a>Métodos estáticos

La `static` palabra clave se utiliza para especificar que se puede llamar a un método sin una instancia y no está asociado a una instancia de objeto. De lo contrario, los métodos son métodos de instancia.

En el ejemplo de la siguiente `let` sección se muestran `member` los campos declarados con `static` la palabra clave, los miembros de propiedad declarados con la palabra clave y un método estático declarado con la palabra clave.

En el ejemplo siguiente se muestra la definición y el uso de métodos estáticos. Supongamos que estas definiciones `SomeType` de método están en la clase de la sección anterior.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Métodos abstractos y virtuales

La `abstract` palabra clave indica que un método tiene una ranura de envío virtual y es posible que no tenga una definición en la clase. Una ranura de *distribución virtual* es una entrada en una tabla de funciones mantenida internamente que se utiliza en tiempo de ejecución para buscar llamadas de función virtual en un tipo orientado a objetos. El mecanismo de envío virtual es el mecanismo que implementa el *polimorfismo,* una característica importante de la programación orientada a objetos. Una clase que tiene al menos un método abstracto sin una definición es una *clase abstracta,* lo que significa que no se puede crear ninguna instancia de esa clase. Para obtener más información acerca de las clases abstractas, vea [Clases abstractas](../abstract-classes.md).

Las declaraciones de método abstracto no incluyen un cuerpo de método. En su lugar, el nombre del método va seguido de dos puntos (:) y una firma de tipo para el método. La firma de tipo de un método es la misma que la que muestra IntelliSense al pausar el puntero del mouse sobre un nombre de método en el Editor de código de Visual Studio, excepto sin nombres de parámetro. El intérprete, fsi.exe, también muestra las firmas de tipo cuando se trabaja de forma interactiva. La firma de tipo de un método se forma enumerando los tipos de los parámetros, seguido por el tipo de valor devuelto, con los símbolos de separador adecuados. Los parámetros curridos están separados por `->` y los parámetros de tupla están separados por `*`. El valor devuelto siempre está separado `->` de los argumentos por un símbolo. Los paréntesis se pueden utilizar para agrupar parámetros complejos, como cuando un tipo de función es un parámetro, o para indicar cuándo una tupla se trata como un único parámetro en lugar de como dos parámetros.

También puede dar definiciones predeterminadas de métodos abstractos agregando la definición a la clase y usando la `default` palabra clave, como se muestra en el bloque de sintaxis de este tema. Un método abstracto que tiene una definición en la misma clase es equivalente a un método virtual en otros lenguajes de .NET Framework. Independientemente de si existe `abstract` o no una definición, la palabra clave crea una nueva ranura de distribución en la tabla de funciones virtuales para la clase.

Independientemente de si una clase base implementa sus métodos abstractos, las clases derivadas pueden proporcionar implementaciones de métodos abstractos. Para implementar un método abstracto en una clase derivada, defina un método que tenga `override` el `default` mismo nombre y firma en la clase derivada, excepto use la palabra clave or y proporcione el cuerpo del método. Las `override` palabras `default` clave significan exactamente lo mismo. Se `override` usa si el nuevo método reemplaza una implementación de clase base; se `default` usa cuando se crea una implementación en la misma clase que la declaración abstracta original. No utilice `abstract` la palabra clave en el método que implementa el método que se declaró abstracto en la clase base.

En el ejemplo siguiente `Rotate` se muestra un método abstracto que tiene una implementación predeterminada, el equivalente a un método virtual de .NET Framework.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

En el ejemplo siguiente se muestra una clase derivada que reemplaza un método de clase base. En este caso, la invalidación cambia el comportamiento para que el método no haga nada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Métodos sobrecargados

Los métodos sobrecargados son métodos que tienen nombres idénticos en un tipo determinado pero que tienen argumentos diferentes. Normalmente se usan argumentos opcionales en lugar de métodos sobrecargados. Sin embargo, se permiten métodos sobrecargados en el lenguaje, siempre que los argumentos estén en forma de tupla, no en forma de cuajada.

## <a name="optional-arguments"></a>Argumentos opcionales

Comenzando con F 4.1, también puede tener argumentos opcionales con un valor de parámetro predeterminado en los métodos.  Esto es para ayudar a facilitar la interoperación con el código de C.  En el ejemplo siguiente se muestra la sintaxis:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Tenga en cuenta que `DefaultParameterValue` el valor pasado para debe coincidir con el tipo de entrada.  En la muestra anterior, `int`es un archivo .  Si se intenta pasar un `DefaultParameterValue` valor no entero, se produciría un error de compilación.

## <a name="example-properties-and-methods"></a>Ejemplo: Propiedades y métodos

El ejemplo siguiente contiene un tipo que tiene ejemplos de campos, funciones privadas, propiedades y un método estático.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Consulte también

- [Miembros](index.md)
