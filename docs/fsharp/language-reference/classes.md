---
title: Clases
description: 'Obtenga información sobre cómo las clases de F # son tipos que representan objetos que pueden tener propiedades, métodos y eventos.'
ms.date: 05/16/2016
ms.openlocfilehash: fd6638e0f1c08cf667a73582e19b2bb5bba46e20
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970172"
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

Las clases representan la descripción fundamental de los tipos de objeto .NET; la clase es el concepto de tipo principal que admite la programación orientada a objetos en F #.

En la sintaxis anterior, `type-name` es cualquier identificador válido. El `type-params` describe los parámetros de tipo genérico opcionales. Consta de los nombres de parámetro de tipo y las restricciones entre corchetes angulares ( `<` y `>` ). Para obtener más información, vea [genéricos](./generics/index.md) y [restricciones](./generics/constraints.md). `parameter-list`Describe los parámetros de constructor. El primer modificador de acceso pertenece al tipo; el segundo pertenece al constructor principal. En ambos casos, el valor predeterminado es `public` .

La clase base de una clase se especifica mediante la `inherit` palabra clave. Debe proporcionar argumentos, entre paréntesis, para el constructor de clase base.

Declare los campos o valores de función que son locales de la clase mediante `let` enlaces y debe seguir las reglas generales para los `let` enlaces. `do-bindings`En la sección se incluye el código que se va a ejecutar durante la construcción del objeto.

`member-list`Está formado por constructores adicionales, declaraciones de instancias y métodos estáticos, declaraciones de interfaz, enlaces abstractos y declaraciones de propiedades y eventos. Se describen en [miembros](./members/index.md).

El `identifier` que se usa con la `as` palabra clave opcional proporciona un nombre a la variable de instancia, o Self Identifier, que se puede usar en la definición de tipo para hacer referencia a la instancia del tipo. Para obtener más información, vea la sección identificadores propios más adelante en este tema.

Las palabras clave `class` y `end` que marcan el inicio y el final de la definición son opcionales.

Los tipos mutuamente recursivos, que son tipos que hacen referencia entre sí, se unen junto con la palabra clave, al igual `and` que las funciones recursivas. Para obtener un ejemplo, vea la sección tipos mutuamente recursivos.

## <a name="constructors"></a>Constructores

El constructor es código que crea una instancia del tipo de clase. Los constructores de las clases funcionan de forma ligeramente diferente en F # que en otros lenguajes .NET. En una clase de F #, siempre hay un constructor principal cuyos argumentos se describen en el `parameter-list` que sigue al nombre de tipo y cuyo cuerpo está compuesto de los `let` enlaces (y `let rec` ) al principio de la declaración de clase y los `do` enlaces siguientes. Los argumentos del constructor principal están en el ámbito de la declaración de clase.

Puede Agregar constructores adicionales mediante la `new` palabra clave para agregar un miembro, como se indica a continuación:

`new`(`argument-list`) = `constructor-body`

El cuerpo del nuevo constructor debe invocar el constructor principal que se especifica en la parte superior de la declaración de clase.

En el ejemplo siguiente se muestra este concepto. En el código siguiente, `MyClass` tiene dos constructores, un constructor principal que toma dos argumentos y otro que no toma ningún argumento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a>permitir y realizar enlaces

Los `let` `do` enlaces y de una definición de clase forman el cuerpo del constructor de clase principal y, por lo tanto, se ejecutan cada vez que se crea una instancia de clase. Si un `let` enlace es una función, se compila en un miembro. Si el `let` enlace es un valor que no se usa en ninguna función o miembro, se compila en una variable local para el constructor. De lo contrario, se compila en un campo de la clase. Las `do` expresiones siguientes se compilan en el constructor principal y ejecutan el código de inicialización para cada instancia. Dado que los constructores adicionales siempre llaman al constructor principal, los `let` enlaces y `do` enlaces siempre se ejecutan independientemente del constructor al que se llame.

Se puede tener acceso a los campos que se crean mediante `let` enlaces a través de los métodos y propiedades de la clase; sin embargo, no se puede tener acceso a ellos desde métodos estáticos, incluso si los métodos estáticos toman una variable de instancia como parámetro. No se puede tener acceso a ellos mediante el identificador propio, si existe alguno.

## <a name="self-identifiers"></a>Identificadores propios

Un *identificador propio* es un nombre que representa la instancia actual. Los identificadores propios se asemejan a la `this` palabra clave en C# o C++ o `Me` en Visual Basic. Puede definir un identificador propio de dos maneras diferentes, en función de si desea que el identificador propio esté en el ámbito de la definición de clase completa o solo para un método individual.

Para definir un identificador propio para toda la clase, utilice la `as` palabra clave después del paréntesis de cierre de la lista de parámetros del constructor y especifique el nombre del identificador.

Para definir un identificador propio solo para un método, proporcione el identificador propio en la declaración de miembro, justo antes del nombre del método y un punto (.) como separador.

En el ejemplo de código siguiente se muestran las dos maneras de crear un identificador propio. En la primera línea, la `as` palabra clave se usa para definir el identificador propio. En la quinta línea, el identificador `this` se usa para definir un identificador propio cuyo ámbito está restringido al método `PrintMessage` .

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

A diferencia de otros lenguajes de .NET, puede asignar un nombre al propio identificador si lo desea; no está restringido a nombres como `self` , `Me` o `this` .

El identificador propio que se declara con la `as` palabra clave no se inicializa hasta después del constructor base. Por consiguiente, cuando se utiliza antes o dentro del constructor base, se `System.InvalidOperationException: The initialization of an object or value resulted in an object or value being accessed recursively before it was fully initialized.` generará durante el tiempo de ejecución. Puede usar el identificador propio libremente después del constructor base, como en `let` enlaces o enlaces `do` .

## <a name="generic-type-parameters"></a>Parámetros de tipos genéricos

Los parámetros de tipo genérico se especifican entre corchetes angulares ( `<` y `>` ), en forma de comillas simples seguidos de un identificador. Varios parámetros de tipo genérico se separan mediante comas. El parámetro de tipo genérico está en el ámbito de la declaración. En el ejemplo de código siguiente se muestra cómo especificar parámetros de tipo genérico.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

Los argumentos de tipo se deducen cuando se usa el tipo. En el código siguiente, el tipo deducido es una secuencia de tuplas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a>Especificar herencia

La `inherit` cláusula identifica la clase base directa, si hay alguna. En F #, solo se permite una clase base directa. Las interfaces que implementa una clase no se consideran clases base. Las interfaces se describen en el tema [interfaces](Interfaces.md) .

Puede tener acceso a los métodos y propiedades de la clase base desde la clase derivada mediante el uso de la palabra clave Language `base` como identificador, seguido de un punto (.) y el nombre del miembro.

Para obtener más información, vea [Herencia](inheritance.md).

## <a name="members-section"></a>Sección de miembros

Puede definir métodos estáticos o de instancia, propiedades, implementaciones de interfaz, miembros abstractos, declaraciones de eventos y constructores adicionales en esta sección. Los enlaces Let y do no pueden aparecer en esta sección. Dado que los miembros se pueden agregar a una variedad de tipos de F # además de a las clases, se tratan en un tema independiente, [miembros](./members/index.md).

## <a name="mutually-recursive-types"></a>Tipos recursivos mutuamente

Al definir tipos que se hacen referencia entre sí de forma circular, se concatenan las definiciones de tipos mediante la `and` palabra clave. La `and` palabra clave reemplaza la `type` palabra clave en todas las definiciones excepto la primera, como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

La salida es una lista de todos los archivos del directorio actual.

## <a name="when-to-use-classes-unions-records-and-structures"></a>Cuándo usar clases, uniones, registros y estructuras

Dada la variedad de tipos entre los que elegir, debe tener una buena comprensión de para qué se ha diseñado cada tipo para seleccionar el tipo adecuado para una situación determinada. Las clases están diseñadas para su uso en contextos de programación orientados a objetos. La programación orientada a objetos es el paradigma dominante utilizado en las aplicaciones escritas para el .NET Framework. Si el código de F # tiene que trabajar estrechamente con el .NET Framework u otra biblioteca orientada a objetos, y especialmente si tiene que extender desde un sistema de tipos orientado a objetos como una biblioteca de interfaz de usuario, las clases probablemente sean adecuadas.

Si no está interoperando estrechamente con código orientado a objetos, o si está escribiendo código que es independiente y, por tanto, está protegido contra la interacción frecuente con código orientado a objetos, considere la posibilidad de utilizar registros y uniones discriminadas. A menudo, se puede usar una Unión discriminada única y bien pensada, junto con el código de coincidencia de patrones adecuado, como alternativa más sencilla a una jerarquía de objetos. Para obtener más información sobre las uniones discriminadas, consulte [uniones discriminadas](discriminated-unions.md).

Los registros tienen la ventaja de ser más sencillos que las clases, pero los registros no son adecuados cuando las demandas de un tipo superan lo que se puede lograr con su simplicidad. Los registros son básicamente agregados de valores sencillos, sin constructores independientes que pueden realizar acciones personalizadas, sin campos ocultos y sin las implementaciones de herencia o de interfaz. Aunque se pueden agregar miembros como propiedades y métodos a los registros para que su comportamiento sea más complejo, los campos almacenados en un registro siguen siendo un agregado simple de valores. Para obtener más información sobre los registros, consulte [registros](records.md).

Las estructuras también son útiles para los pequeños agregados de datos, pero difieren de las clases y los registros en que son tipos de valor de .NET. Las clases y los registros son tipos de referencia de .NET. La semántica de los tipos de valor y los tipos de referencia es diferente en que los tipos de valor se pasan por valor. Esto significa que se copian bit de bit cuando se pasan como un parámetro o se devuelven desde una función. También se almacenan en la pila o, si se usan como un campo, se insertan dentro del objeto primario en lugar de almacenarse en su propia ubicación independiente en el montón. Por lo tanto, las estructuras son adecuadas para los datos a los que se accede con frecuencia cuando la sobrecarga de tener acceso al montón es un problema. Para obtener más información sobre las estructuras, vea [estructuras](structures.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Miembros](./members/index.md)
- [Herencia](inheritance.md)
- [Interfaces](interfaces.md)
