---
title: Clases (F#)
description: 'Obtenga información sobre cómo las clases de F # son tipos que representan objetos que pueden tener propiedades, métodos y eventos.'
ms.date: 05/16/2016
ms.openlocfilehash: 71cd713d192d28565e879b79b2fc9e0530e5f841
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43802113"
---
# <a name="classes"></a>Clases

*Las clases* son tipos que representan objetos que pueden tener propiedades, métodos y eventos.

## <a name="syntax"></a>Sintaxis

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a>Comentarios

Las clases representan la descripción fundamental de los tipos de objetos. NET; la clase es el concepto de tipo principal que admite la programación orientada a objetos en F #.

En la sintaxis anterior, el `type-name` es cualquier identificador válido. El `type-params` se describen los parámetros de tipo genérico opcionales. Consta de los nombres de parámetro de tipo y restricciones entre corchetes angulares (`<` y `>`). Para obtener más información, consulte [genéricos](generics/index.md) y [restricciones](generics/constraints.md). El `parameter-list` se describen los parámetros del constructor. El primer modificador de acceso pertenece al tipo; el segundo se refiere al constructor principal. En ambos casos, el valor predeterminado es `public`.

Especificar la clase base para una clase mediante el `inherit` palabra clave. Debe proporcionar argumentos para el constructor de clase base, entre paréntesis.

Declare los campos o valores que son locales a la clase mediante el uso de función `let` enlaces y se deben seguir las reglas generales para `let` enlaces. El `do-bindings` sección incluye código que se ejecutará en la construcción del objeto.

El `member-list` consta de los constructores adicionales, instancia y declaraciones de método estático, declaraciones de interfaz, enlaces abstractos y declaraciones de propiedad y el evento. Estos métodos se describen en [miembros](members/index.md).

El `identifier` que se utiliza con el elemento opcional `as` palabra clave da un nombre a la variable de instancia, o el identificador propio, que se puede usar en la definición de tipo para hacer referencia a la instancia del tipo. Para obtener más información, vea la sección Autoidentificadores más adelante en este tema.

Las palabras clave `class` y `end` que marcar el comienzo y final de la definición son opcionales.

Mutuamente recursivas tipos, que son tipos que hacen referencia entre sí, se unen junto con el `and` palabra clave igual que mutuamente son funciones recursivas. Para obtener un ejemplo, vea la sección tipos mutuamente recursivos.

## <a name="constructors"></a>Constructores

El constructor es código que crea una instancia del tipo de clase. Constructores de clases funcionan de forma ligeramente diferente en F # en otros lenguajes. NET. En una clase de F #, siempre hay un constructor primario cuyos argumentos se describen en la `parameter-list` que sigue el nombre de tipo y cuyo cuerpo se compone de la `let` (y `let rec`) enlaces al principio de la declaración de clase y el `do`enlaces que siguen. Los argumentos del constructor principal están en el ámbito de la declaración de clase.

Puede agregar constructores adicionales mediante el `new` palabra clave para agregar un miembro, como se indica a continuación:

`new`(`argument-list`) = `constructor-body`

El cuerpo del nuevo constructor debe invocar el constructor principal que se especifica en la parte superior de la declaración de clase.

El ejemplo siguiente ilustra este concepto. En el código siguiente, `MyClass` tiene dos constructores, un constructor primario que toma dos argumentos y otro constructor que no toma ningún argumento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>Enlaces let y do

El `let` y `do` enlaces en una definición de clase forman el cuerpo del constructor de clase principal y, por lo tanto, se ejecutan cada vez que se crea una instancia de clase. Si un `let` enlace es una función, a continuación, se compila en un miembro. Si el `let` enlace es un valor que no se utiliza en cualquier función o miembro, a continuación, se compila en una variable local en el constructor. En caso contrario, se compila en un campo de la clase. El `do` expresiones que siguen se compilan en el constructor principal y ejecutar código de inicialización para cada instancia. Dado que los constructores adicionales siempre llaman al constructor principal, el `let` enlaces y `do` enlaces siempre se ejecutan independientemente de que se llama al constructor.

Los campos que se crean mediante `let` enlaces se pueden tener acceso a lo largo de los métodos y propiedades de la clase; sin embargo, no es accesible desde los métodos estáticos, aunque los métodos estáticos toman una variable de instancia como un parámetro. No son accesibles mediante el identificador propio, si existe alguno.

## <a name="self-identifiers"></a>Autoidentificadores

Un *identificador propio* es un nombre que representa la instancia actual. Autoidentificadores son similares a los `this` palabra clave en C# o C++ o `Me` en Visual Basic. Puede definir un identificador de dos maneras diferentes, dependiendo de si el identificador propio dentro del ámbito para la definición de clase completo o sólo para los métodos individuales.

Para definir un identificador propio para toda la clase, use el `as` palabra clave tras el paréntesis de cierre del parámetro de constructor de lista y especifique el nombre del identificador.

Para definir un identificador para un solo método propio, proporcione el identificador propio en la declaración de miembro, justo antes del nombre del método y un punto (.) como separador.

El ejemplo de código siguiente muestra las dos maneras de crear un identificador propio. En la primera línea, el `as` palabra clave se usa para definir el identificador propio. En la quinta línea, el identificador `this` se utiliza para definir un identificador propio cuyo ámbito está limitado al método `PrintMessage`.

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

A diferencia de otros lenguajes. NET, puede asignar el nombre el identificador propio como quiera; no están restringidos a los nombres como `self`, `Me`, o `this`.

El identificador propio que se declara con el `as` palabra clave no se inicializa hasta después de que el `let` enlaces se ejecutan. Por lo tanto, no puede utilizarse en el `let` enlaces. Puede usar el identificador propio en la `do` sección de enlaces.

## <a name="generic-type-parameters"></a>Parámetros de tipos genéricos

Parámetros de tipo genérico se especifican en corchetes angulares (`<` y `>`), en forma de una comilla seguida por un identificador. Varios parámetros de tipo genérico se separan mediante comas. El parámetro de tipo genérico es en el ámbito de la declaración. El ejemplo de código siguiente muestra cómo especificar parámetros de tipo genérico.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Argumentos de tipo se deducen cuando se usa el tipo. En el código siguiente, el tipo inferido es una secuencia de tuplas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>Especificación de herencia

El `inherit` cláusula identifica la clase base directa, si hay alguno. En F #, se permite solo una clase base directa. Las interfaces que implementa una clase no se consideran clases base. Las interfaces se describen en la [Interfaces](Interfaces.md) tema.

Se pueden tener acceso a los métodos y propiedades de la clase base desde la clase derivada mediante el uso de la palabra clave del lenguaje `base` como un identificador, seguido por un punto (.) y el nombre del miembro.

Para obtener más información, vea [Herencia](inheritance.md).

## <a name="members-section"></a>Sección de miembros

Puede definir estático o métodos de instancia, propiedades, implementaciones de interfaz, los miembros abstractos, declaraciones de eventos y constructores adicionales en esta sección. Let y realizan enlaces no puede aparecer en esta sección. Dado que se pueden agregar miembros a una variedad de tipos de F # además de las clases, se tratan en otro tema, [miembros](members/index.md).

## <a name="mutually-recursive-types"></a>Tipos mutuamente recursivos

Al definir tipos que hacen referencia entre sí de forma circular, encadenar las definiciones de tipos mediante el uso de la `and` palabra clave. El `and` reemplaza la palabra clave el `type` palabra clave en todos, excepto la primera definición, como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

El resultado es una lista de todos los archivos en el directorio actual.

## <a name="when-to-use-classes-unions-records-and-structures"></a>Cuándo usar las clases, uniones, registros y estructuras

Dada la variedad de tipos que puede elegir, deberá tener una buena comprensión de lo que cada tipo está diseñado para seleccionar el tipo adecuado para una situación específica. Las clases están diseñadas para su uso en contextos de programación orientada a objetos. Programación orientada a objetos es el paradigma dominante que se utilizan en las aplicaciones escritas para .NET Framework. Si el código de F # tiene que trabajar estrechamente con .NET Framework u otra biblioteca orientada a objetos y, especialmente si tiene que ampliar desde un sistema orientado a objetos de tipo como una biblioteca de interfaz de usuario, las clases son probablemente adecuadas.

Si no está interoperando estrechamente con código orientado a objetos, o si está escribiendo código que es independiente y, por tanto, esté protegido contra la interacción frecuente con código orientado a objetos, debe considerar el uso de registros y uniones discriminadas. Una sola, bien pensamiento – fuera una unión discriminada, junto con el código, coincidencia adecuada a menudo se puede usar como una alternativa más sencilla a una jerarquía de objetos. Para obtener más información sobre las uniones discriminadas, vea [uniones discriminadas](discriminated-unions.md).

Los registros tienen la ventaja de ser más sencillo que las clases, pero los registros no son adecuados cuando las demandas de un tipo superan lo que se puede lograr con su simplicidad. Los registros son básicamente simples agregados de valores, sin constructores independientes que pueden realizar acciones personalizadas, los campos ocultos ni implementaciones de herencia o interfaz. Aunque se pueden agregar miembros como propiedades y métodos a los registros para hacer que su comportamiento más complejo, los campos que se almacena en un registro siguen siendo un agregado simple de valores. Para obtener más información acerca de los registros, vea [registros](records.md).

Las estructuras también son útiles para pequeños agregados de datos, pero se diferencian de las clases y los registros que son tipos de valor. NET. Registros y las clases son tipos de referencia. NET. La semántica de tipos de valor y tipos de referencia es diferente en que los tipos de valor se pasan por valor. Esto significa que se copian bit a bit cuando se pasa como un parámetro o se devuelve de una función. Están también almacena en la pila o, si se usan como un campo, incrustado en el objeto primario en lugar de que se almacenan en su propia ubicación independiente en el montón. Por lo tanto, las estructuras son adecuadas para los datos a los que accede con frecuencia cuando la sobrecarga de tener acceso al montón es un problema. Para obtener más información acerca de las estructuras, vea [estructuras](structures.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Miembros](members/index.md)
- [Herencia](inheritance.md)
- [Interfaces](interfaces.md)
