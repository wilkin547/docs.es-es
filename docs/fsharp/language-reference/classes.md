---
title: Clases (F#)
description: 'Obtenga información acerca de cómo las clases de F # son tipos que representan objetos que pueden tener propiedades, métodos y eventos.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0bfb45b6481576729bfe8d4bd016fb151757660a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="classes"></a>Clases

*Clases* son tipos que representan objetos que pueden tener propiedades, métodos y eventos.


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
Clases que representan la descripción fundamental de los tipos de objeto. NET; la clase es el concepto de tipos primaria que admite la programación orientada a objetos en F #.

En la sintaxis anterior, el `type-name` es cualquier identificador válido. El `type-params` se describen los parámetros de tipo genérico opcionales. Se compone de los nombres de parámetro de tipo y restricciones entre corchetes angulares (`<` y `>`). Para obtener más información, consulte [genéricos](generics/index.md) y [restricciones](generics/constraints.md). El `parameter-list` se describen los parámetros de constructor. El modificador de acceso primera pertenece al tipo; el segundo pertenece al constructor primario. En ambos casos, el valor predeterminado es `public`.

Especificar la clase base para una clase mediante el `inherit` palabra clave. Debe proporcionar argumentos entre paréntesis, constructor de clase base.

Declarar campos o valores que son locales a la clase mediante el uso de función `let` enlaces y se deben seguir las reglas generales para `let` enlaces. El `do-bindings` sección incluye código que se ejecuta en la construcción del objeto.

El `member-list` consta de los constructores adicionales, instancia y declaraciones de método estático, declaraciones de interfaz, enlaces abstractos y declaraciones de propiedad y evento. Se describen en [miembros](members/index.md).

El `identifier` que se utiliza con la parte opcional `as` palabra clave da un nombre a la variable de instancia, o identificador propio, lo que puede usarse en la definición de tipo para hacer referencia a la instancia del tipo. Para obtener más información, vea la sección Autoidentificadores más adelante en este tema.

Las palabras clave `class` y `end` que marca el inicio y final de la definición son opcionales.

Mutuamente recursivas tipos, que son tipos que hacen referencia a entre sí, se combinan junto con el `and` palabra clave como mutuamente son funciones recursivas. Para obtener un ejemplo, vea la sección tipos mutuamente recursivos.


## <a name="constructors"></a>Constructores
El constructor es código que crea una instancia del tipo de clase. Constructores de clases funcionan de forma ligeramente diferente en F # en otros lenguajes. NET. En una clase de F #, siempre hay un constructor primario cuyos argumentos se describen en la `parameter-list` que sigue el nombre de tipo y cuyo cuerpo está formada por el `let` (y `let rec`) enlaces al principio de la declaración de clase y el `do`enlaces que siguen. Los argumentos del constructor primario están en ámbito a lo largo de la declaración de clase.

Puede agregar constructores adicionales mediante la `new` palabra clave que se va a agregar un miembro, como se indica a continuación:

`new`(`argument-list`) = `constructor-body`

El cuerpo del nuevo constructor debe invocar el constructor primario que se especifica en la parte superior de la declaración de clase.

En el ejemplo siguiente se muestra este concepto. En el código siguiente, `MyClass` tiene dos constructores, un constructor primario que toma dos argumentos y otro constructor que no toma ningún argumento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]
    
## <a name="let-and-do-bindings"></a>Enlaces let y do

El `let` y `do` enlaces en una definición de clase forman el cuerpo del constructor de clase principal y, por lo tanto, se ejecutan cada vez que se crea una instancia de clase. Si un `let` enlace es una función, a continuación, se compila en un miembro. Si el `let` enlace es un valor que no se utiliza en cualquier función o un miembro, a continuación, se compila en una variable local en el constructor. En caso contrario, se compila en un campo de la clase. La `do` expresiones que van a continuación se compilan en el constructor primario y ejecutar el código de inicialización para cada instancia. Dado que todos los constructores adicionales siempre llaman al constructor principal, el `let` enlaces y `do` enlaces ejecutarán siempre, independientemente de que se llama al constructor.

Campos que se crean mediante `let` enlaces son accesibles a lo largo de los métodos y propiedades de la clase; sin embargo, no son accesibles desde métodos estáticos, aunque los métodos estáticos toman una variable de instancia como un parámetro. No es accesible mediante el identificador propio, si existe alguno.


## <a name="self-identifiers"></a>Autoidentificadores

A *identificador propio* es un nombre que representa la instancia actual. Autoidentificadores son similares a los `this` palabra clave en C# o C++ o `Me` en Visual Basic. Puede definir un identificador propio de dos maneras diferentes, dependiendo de si desea que el identificador propio para estar en el ámbito para la definición de clase completo o solo para un método individual.

Para definir un identificador propio para toda la clase, use la `as` palabra clave después del paréntesis de cierre del parámetro de constructor de lista y especifique el nombre del identificador.

Para definir un identificador propio para un solo método, proporcione el identificador propio en la declaración de miembro, justo antes del nombre del método y un punto (.) como separador.

En el ejemplo de código siguiente se muestra las dos maneras de crear un identificador propio. En la primera línea, la `as` palabra clave se utiliza para definir el identificador propio. En la quinta línea, el identificador `this` se utiliza para definir un identificador propio cuyo ámbito está restringido al método `PrintMessage`.

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

A diferencia de otros lenguajes. NET, puede asignar un nombre el identificador propio como quiera; no están limitados a nombres como `self`, `Me`, o `this`.

El identificador propio que se declara con el `as` palabra clave no se inicializa hasta después de la `let` enlaces se ejecutan. Por lo tanto, no se puede usar en el `let` enlaces. Puede usar el identificador propio en la `do` sección de enlaces.


## <a name="generic-type-parameters"></a>Parámetros de tipos genéricos

Parámetros de tipo genérico se especifican entre corchetes angulares (`<` y `>`), en forma de una comilla simple seguida de un identificador. Varios parámetros de tipo genérico se separan mediante comas. El parámetro de tipo genérico está en ámbito a lo largo de la declaración. En el ejemplo de código siguiente se muestra cómo especificar parámetros de tipo genérico.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Argumentos de tipo se deducen cuando se utiliza el tipo. En el código siguiente, el tipo deducido es una secuencia de tuplas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]
    
## <a name="specifying-inheritance"></a>Especificación de herencia

El `inherit` cláusula identifica la clase base directa, si hay alguno. En F #, se permite solo una clase base directa. Interfaces que implementa una clase no se consideran clases base. Interfaces se describen en la [Interfaces](Interfaces.md) tema.

Se pueden tener acceso a los métodos y propiedades de la clase base desde la clase derivada mediante el uso de la palabra clave language `base` como un identificador, seguido por un punto (.) y el nombre del miembro.

Para obtener más información, vea [Herencia](inheritance.md).


## <a name="members-section"></a>Sección de miembros
Puede definir estático o métodos de instancia, propiedades, implementaciones de interfaz, miembros abstractos, declaraciones de evento y constructores adicionales en esta sección. Permiten y no enlaces no aparecen en esta sección. Dado que se pueden agregar miembros a una variedad de tipos de F # además de las clases, se analizan en otro tema, [miembros](members/index.md).


## <a name="mutually-recursive-types"></a>Tipos mutuamente recursivos
Al definir tipos que hacen referencia a entre sí de forma circular, encadenar las definiciones de tipos mediante el uso de la `and` (palabra clave). El `and` palabra clave reemplaza el `type` palabra clave en todos excepto la primera definición, como se indica a continuación.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

El resultado es una lista de todos los archivos en el directorio actual.


## <a name="when-to-use-classes-unions-records-and-structures"></a>Cuándo utilizar las clases, uniones, registros y estructuras
Dada la variedad de tipos que puede elegir, debe tener un buen conocimiento de lo que cada tipo está diseñado para seleccionar el tipo adecuado para cada situación concreta. Clases están diseñadas para su uso en contextos de programación orientada a objetos. Programación orientada a objetos es el paradigma dominante usar en aplicaciones que se escriben para .NET Framework. Si el código de F # tiene que trabajar en estrecha colaboración con .NET Framework u otra biblioteca orientada a objetos y, sobre todo si tiene que se extienden desde un sistema de tipos orientado a objetos, como una biblioteca de interfaz de usuario, las clases son suele ser apropiadas.

Si no se interopera estrechamente con código orientado a objetos, o si está escribiendo código que es independiente y, por tanto, protegidos contra la interacción frecuente con código orientado a objetos, se debe considerar el uso de registros y uniones discriminadas. Un único, también pensamiento – fuera unión discriminada, junto con el código, coincidencia adecuada a menudo puede usarse como una alternativa más sencilla a una jerarquía de objetos. Para obtener más información sobre las uniones discriminadas, vea [uniones discriminadas](discriminated-unions.md).

Registros tienen la ventaja de ser más fácil que las clases, pero los registros no son adecuados cuando las demandas de un tipo superan lo que se puede lograr con su simplicidad. Los registros son básicamente simples agregados de valores, sin constructores independientes que puedan realizar acciones personalizadas, sin campos ocultos y sin implementaciones de interfaces ni herencia. Aunque se pueden agregar miembros como propiedades y métodos a los registros para hacer su comportamiento más complejo, los campos que se almacena en un registro siguen siendo un agregado simple de valores. Para obtener más información acerca de los registros, vea [registros](records.md).

Las estructuras también resultan útiles para pequeños agregados de datos, pero se diferencian de las clases y los registros que son tipos de valor. NET. Registros y las clases son tipos de referencia. NET. La semántica de tipos de valor y tipos de referencia es diferente en que los tipos de valor se pasan por valor. Esto significa que se copian bit a bit cuando se pasa como un parámetro o se devuelve de una función. Son también almacenadas en la pila o, si se usan como un campo, se incrustan dentro del objeto primario en lugar de en su propia ubicación independiente en el montón. Por lo tanto, las estructuras son adecuadas para los datos que se accede con frecuencia cuando la sobrecarga de tener acceso al montón es un problema. Para obtener más información acerca de las estructuras, vea [estructuras](structures.md).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Miembros](members/index.md)

[Herencia](inheritance.md)

[Interfaces](interfaces.md)

