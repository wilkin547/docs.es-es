---
title: Métodos (F#)
description: 'Obtenga información acerca de cómo un método de F # es una función asociada a un tipo que se utilizan para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.'
ms.date: 05/16/2016
ms.openlocfilehash: e30300b4dd6cc26712a5adbc8abf720f2c312a6f
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2018
---
# <a name="methods"></a>Métodos

A *método* es una función que está asociada a un tipo. En la programación orientada a objetos, los métodos se utilizan para exponer e implementar la funcionalidad y el comportamiento de objetos y tipos.


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
En la sintaxis anterior, puede ver las distintas formas de definiciones y declaraciones de método. En los cuerpos de método más largos, el signo igual (=) después de un salto de línea y se aplica sangría al cuerpo del método completo.

Atributos se pueden aplicar a cualquier declaración de método. Que preceden a la sintaxis para una definición de método y normalmente se muestran en una línea independiente. Para obtener más información, consulte [Attributes](../attributes.md) (Atributos).

Se pueden marcar métodos `inline`. Para más información sobre `inline`, vea [Inline Functions](../functions/inline-functions.md) (Funciones insertadas).

Métodos de inline no se pueden utilizar de forma recursiva dentro del tipo; no es necesario utilizar explícitamente la `rec` palabra clave.


## <a name="instance-methods"></a>Métodos de instancia
Métodos de instancia se declaran con la `member` palabra clave y un *self-identifier*, seguido de un punto (.) y el nombre de método y parámetros. Como es el caso de `let` enlaces, el *lista de parámetros* puede ser un modelo. Por lo general, incluya método parámetros entre paréntesis en forma de tupla, que lo constituyen los métodos de manera aparecen en F # cuando se crean en otros lenguajes de .NET Framework. Sin embargo, el formulario currificado (parámetros separados por espacios) también es común y se admiten también otros patrones.

En el ejemplo siguiente se muestra la definición y uso de un método de instancia no abstracta.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

Dentro de los métodos de instancia, no utilice el identificador propio para campos de acceso definidos mediante enlaces. Use el identificador propio al obtener acceso a otros miembros y propiedades.


## <a name="static-methods"></a>Métodos estáticos
La palabra clave `static` se utiliza para especificar que un método se pueda llamar sin una instancia y no está asociado a una instancia de objeto. De lo contrario, son métodos de instancia.

El ejemplo en la siguiente sección muestra los campos declarados con la `let` palabra clave, los miembros de propiedad declarados con la `member` palabra clave y un método estático que se declara con el `static` palabra clave.

En el ejemplo siguiente se muestra la definición y uso de métodos estáticos. Se supone que estas definiciones de método están en la `SomeType` clase en la sección anterior.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>Métodos abstractos y virtuales
La palabra clave `abstract` indica que un método tiene una entrada de distribución virtual y no puede tener una definición de la clase. A *entrada de distribución virtual* es una entrada en una tabla de funciones mantenida internamente que se utiliza en tiempo de ejecución para buscar una función virtual a la que se llama en un tipo orientado a objetos. El mecanismo de distribución virtual es el que implementa *polimorfismo*, una característica importante de la programación orientada a objetos. Es una clase que tiene al menos un método abstracto sin una definición de un *clase abstracta*, lo que significa que no se puede crear ninguna instancia de esa clase. Para obtener más información sobre las clases abstractas, vea [clases abstractas](../abstract-classes.md).

Declaraciones de métodos abstractos no incluyen un cuerpo de método. En su lugar, el nombre del método va seguido de dos puntos (:) y una signatura de tipo para el método. La firma de tipo de un método es el mismo que se muestra con IntelliSense cuando sitúe el puntero del mouse sobre un nombre de método en el Editor de código de Visual Studio, excepto sin nombres de parámetro. Las signaturas de tipo también se muestran el intérprete, fsi.exe, cuando se trabaja de forma interactiva. La firma de tipo de un método está formada por enumerando los tipos de los parámetros, seguidos por el tipo de valor devuelto, con símbolos separadores adecuados. Currificadas parámetros se separan mediante `->` y parámetros de tupla se separan mediante `*`. El valor devuelto siempre se separa de los argumentos mediante un `->` símbolos. Puede utilizar paréntesis para agrupar parámetros complejos, por ejemplo, cuando un tipo de función es un parámetro, o para indicar cuándo una tupla se trata como un solo parámetro y no como dos parámetros.

También puede proporcionar las definiciones default de métodos abstractos agregando la definición a la clase y usando el `default` palabra clave, como se muestra en el bloque de sintaxis en este tema. Un método abstracto que tiene una definición de la misma clase es equivalente a un método virtual de otros lenguajes de .NET Framework. Si no existe una definición, la `abstract` palabra clave, crea un nuevo espacio de envío en la tabla de funciones virtuales para la clase.

Independientemente de si una clase base implementa sus métodos abstractos, las clases derivadas pueden proporcionar implementaciones de métodos abstractos. Para implementar un método abstracto en una clase derivada, defina un método que tiene el mismo nombre y la firma de la clase derivada, excepto el uso del `override` o `default` (palabra clave) y proporcionar el cuerpo del método. Las palabras clave `override` y `default` significan exactamente lo mismo. Usar `override` si el nuevo método reemplaza la implementación de una clase base; use `default` al crear una implementación en la misma clase que la declaración abstracta original. No utilice la `abstract` palabra clave en el método que implementa el método que se declaró como abstracto en la clase base.

En el ejemplo siguiente se muestra un método abstracto `Rotate` que tiene una implementación de forma predeterminada, el equivalente de un método virtual de .NET Framework.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

En el ejemplo siguiente se muestra una clase derivada que reemplaza un método de clase base. En este caso, el reemplazo cambia el comportamiento para que el método no hace nada.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>Métodos sobrecargados
Métodos sobrecargados son métodos que tienen nombres idénticos en un tipo determinado, pero que tiene argumentos diferentes. En F #, los argumentos opcionales se suelen utilizar en lugar de métodos sobrecargados. Sin embargo, se permiten métodos sobrecargados en el lenguaje, siempre que los argumentos estén en forma de tupla, no currificada formulario.

## <a name="optional-arguments"></a>Argumentos opcionales

A partir de F # 4.1, también puede tener argumentos opcionales con un valor de parámetro predeterminado en métodos.  Esto sirve para ayudar a facilitar la interoperación con código C#.  En el ejemplo siguiente se muestra la sintaxis:

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

Tenga en cuenta que el valor pasado en para `DefaultParameterValue` debe coincidir con el tipo de entrada.  En el ejemplo anterior, es un `int`.  Intenta pasar un valor no entero en `DefaultParameterValue` produciría un error de compilación.

## <a name="example-properties-and-methods"></a>Ejemplo: Propiedades y métodos
El ejemplo siguiente contiene un tipo que tiene ejemplos de campos, funciones privadas, propiedades y un método estático.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>Vea también
[Miembros](index.md)
