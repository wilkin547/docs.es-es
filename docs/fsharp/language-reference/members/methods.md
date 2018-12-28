---
title: Métodos
description: Obtenga información sobre cómo un F# método es una función asociada a un tipo que se utilizan para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.
ms.date: 05/16/2016
ms.openlocfilehash: 03150cc67f79bfde58cf27e4a9d4dfa9e9ff3f55
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614031"
---
# <a name="methods"></a>Métodos

Un *método* es una función que está asociada a un tipo. En la programación orientada a objetos, métodos se usan para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.

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

En la sintaxis anterior, puede ver las distintas formas de definiciones y declaraciones de método. En los cuerpos de método más largo, un salto de línea detrás del signo igual (=) y se aplica sangría al cuerpo del método completo.

Atributos pueden aplicarse a cualquier declaración de método. Que preceden a la sintaxis para una definición de método y normalmente se muestran en una línea independiente. Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).

Se pueden marcar métodos `inline`. Para más información sobre `inline`, vea [Inline Functions](../functions/inline-functions.md) (Funciones insertadas).

Métodos de en línea no se pueden utilizar de forma recursiva dentro del tipo; no es necesario utilizar explícitamente el `rec` palabra clave.

## <a name="instance-methods"></a>Métodos de instancia

Los métodos de instancia se declaran con la `member` palabra clave y un *self-identifier*, seguido de un punto (.) y el nombre del método y los parámetros. Como es el caso de `let` enlaces, el *lista de parámetros* puede ser un modelo. Por lo general, incluya los parámetros entre paréntesis en forma de tupla, los métodos de manera que aparecen en el método F# cuando se crea en otros lenguajes de .NET Framework. Sin embargo, también es común currificada (parámetros separados por espacios) y se admiten otros patrones también.

El ejemplo siguiente muestra la definición y uso de un método de instancia no abstracto.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Dentro de los métodos de instancia, no use el identificador propio para obtener acceso a los campos definidos mediante enlaces. Use el identificador propio al obtener acceso a otros miembros y propiedades.

## <a name="static-methods"></a>Métodos estáticos

La palabra clave `static` se utiliza para especificar que un método se pueda llamar sin una instancia y no está asociado a una instancia de objeto. En caso contrario, los métodos son métodos de instancia.

El ejemplo de la sección siguiente muestra los campos declarados con el `let` palabra clave, los miembros de la propiedad se declaran con el `member` palabra clave y un método estático que se declara con el `static` palabra clave.

El ejemplo siguiente muestra la definición y uso de métodos estáticos. Se supone que estas definiciones de método están en el `SomeType` clase en la sección anterior.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Métodos abstractos y virtuales

La palabra clave `abstract` indica que un método tiene una ranura de la distribución virtual y que no dispongan de una definición de la clase. Un *ranura distribución virtual* es una entrada en una tabla de funciones mantenida internamente que se usa en tiempo de ejecución para buscar la función virtual llamadas en un tipo de objeto. El mecanismo de distribución virtual es el mecanismo que implementa *polimorfismo*, una característica importante de la programación orientada a objetos. Es una clase que tiene al menos un método abstracto sin una definición de un *clase abstracta*, lo que significa que no se puede crear ninguna instancia de esa clase. Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).

Las declaraciones de método abstracto no incluyen un cuerpo de método. En su lugar, el nombre del método es seguido por dos puntos (:) y una signatura de tipo para el método. La signatura de tipo de un método es el mismo que muestra IntelliSense cuando sitúe el puntero del mouse sobre un nombre de método en el Editor de código de Visual Studio, excepto sin los nombres de parámetro. Las signaturas de tipo también se muestran el intérprete, fsi.exe, cuando se trabaja de forma interactiva. La signatura de tipo de un método está formada por enumerando los tipos de los parámetros, seguidos por el tipo de valor devuelto, con símbolos de separador adecuado. Parámetros currificados están separados por `->` y parámetros de tupla se separan mediante `*`. El valor devuelto siempre se separa de los argumentos mediante un `->` símbolos. Pueden usarse paréntesis para agrupar parámetros complejos, por ejemplo, cuando un tipo de función es un parámetro, o para indicar cuándo una tupla se trata como un único parámetro en lugar de dos parámetros.

También puedes usar los métodos abstractos definiciones default agregando la definición de la clase y usando el `default` palabra clave, como se muestra en el bloque de sintaxis en este tema. Un método abstracto que tiene una definición de la misma clase es equivalente a un método virtual en otros lenguajes de .NET Framework. Si existe o no una definición, la `abstract` palabra clave crea una nueva ranura de envío en la tabla de funciones virtuales para la clase.

Independientemente de si una clase base implementa sus métodos abstractos, las clases derivadas pueden proporcionar implementaciones de métodos abstractos. Para implementar un método abstracto en una clase derivada, defina un método que tiene el mismo nombre y la firma de la clase derivada, excepto que use el `override` o `default` palabra clave y proporcione el cuerpo del método. Las palabras clave `override` y `default` exactamente el mismo significado. Usar `override` si el nuevo método reemplaza una implementación de la clase base; use `default` al crear una implementación en la misma clase que la declaración abstracta original. No utilice el `abstract` palabra clave en el método que implementa el método que se ha declarado como abstracto en la clase base.

El ejemplo siguiente muestra un método abstracto `Rotate` que tiene una implementación de forma predeterminada, el equivalente de un método virtual de .NET Framework.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

El ejemplo siguiente muestra una clase derivada que reemplaza un método de clase base. En este caso, la invalidación cambia el comportamiento para que el método no hace nada.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Métodos sobrecargados

Métodos sobrecargados son métodos que tienen nombres idénticos en un tipo determinado, pero que tienen diferentes argumentos. En F#, argumentos opcionales se suelen usar en lugar de métodos sobrecargados. Sin embargo, se permiten métodos sobrecargados en el lenguaje, siempre que los argumentos son en forma de tupla, no currificada.

## <a name="optional-arguments"></a>Argumentos opcionales

A partir de F# 4.1, también puede tener argumentos opcionales con valor de parámetro predeterminado en métodos.  Esto sirve para ayudar a facilitar la interoperación con código C#.  El ejemplo siguiente muestra la sintaxis:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Tenga en cuenta que el valor pasado para `DefaultParameterValue` debe coincidir con el tipo de entrada.  En el ejemplo anterior, es un `int`.  Intenta pasar un valor no entero `DefaultParameterValue` daría lugar a un error de compilación.

## <a name="example-properties-and-methods"></a>Ejemplo: Propiedades y métodos

En el siguiente ejemplo contiene un tipo que contiene algunos ejemplos de campos, funciones privadas, propiedades y un método estático.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Vea también

- [Miembros](index.md)