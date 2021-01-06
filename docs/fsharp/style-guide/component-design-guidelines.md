---
title: Instrucciones de diseño de componentes de F#
description: 'Obtenga información sobre las directrices para escribir componentes de F # destinados a su consumo por otros llamadores.'
ms.date: 05/14/2018
ms.openlocfilehash: 24be2a422c97b9334f749e3d9dfcccd0feec219b
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856112"
---
# <a name="f-component-design-guidelines"></a>Instrucciones de diseño de componentes de F#

Este documento es un conjunto de directrices de diseño de componentes para la programación en F #, en función de las instrucciones de diseño de componentes de F #, V14, Microsoft Research y una versión que originalmente se seleccionada y mantiene con F # Software Foundation.

En este documento se supone que está familiarizado con la programación en F #. Muchas gracias a la comunidad de F # por sus contribuciones e información útil sobre las distintas versiones de esta guía.

## <a name="overview"></a>Información general

En este documento se analizan algunos de los problemas relacionados con el diseño y la codificación de componentes de F #. Un componente puede significar cualquiera de los siguientes:

* Una capa del proyecto de F # que tiene consumidores externos dentro de ese proyecto.
* Biblioteca diseñada para el consumo por código de F # a través de los límites del ensamblado.
* Biblioteca diseñada para su consumo por cualquier lenguaje .NET a través de los límites de los ensamblados.
* Biblioteca diseñada para su distribución a través de un repositorio de paquetes, como [NuGet](https://nuget.org).

Las técnicas descritas en este artículo siguen los [cinco principios de buen código de F #](index.md#five-principles-of-good-f-code)y, por tanto, usan la programación funcional y de objetos según corresponda.

Independientemente de la metodología, el diseñador de componentes y bibliotecas se enfrenta a una serie de problemas prácticos y prosaics al intentar crear una API que es más fácil de usar para los desarrolladores. La aplicación Conscientious de las instrucciones de diseño de la [biblioteca de .net](../../standard/design-guidelines/index.md) le dirigirá a la creación de un conjunto coherente de API que son agradables de consumir.

## <a name="general-guidelines"></a>Directrices generales

Hay algunas directrices universales que se aplican a las bibliotecas de F #, independientemente de la audiencia prevista para la biblioteca.

### <a name="learn-the-net-library-design-guidelines"></a>Obtener información sobre las directrices de diseño de la biblioteca .NET

Independientemente del tipo de código de F # que esté haciendo, es útil tener conocimientos prácticos de las instrucciones de diseño de la [biblioteca de .net](../../standard/design-guidelines/index.md). La mayoría de los programadores de F # y .NET estarán familiarizados con estas directrices y esperamos que el código .NET se ajuste a ellos.

Las instrucciones de diseño de la biblioteca de .NET proporcionan instrucciones generales sobre la nomenclatura, el diseño de clases e interfaces, el diseño de miembros (propiedades, métodos, eventos, etc.) y otros, y son un primer punto de referencia útil para una variedad de instrucciones de diseño.

### <a name="add-xml-documentation-comments-to-your-code"></a>Agregar comentarios de documentación XML al código

La documentación XML de las API públicas garantiza que los usuarios puedan obtener grandes IntelliSense y QuickInfo al usar estos tipos y miembros, y habilitar la creación de archivos de documentación para la biblioteca. Consulte la [documentación XML](../language-reference/xml-documentation.md) sobre las distintas etiquetas XML que se pueden usar para el marcado adicional en los comentarios de XmlDoc.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

Puede usar los comentarios XML de forma corta ( `/// comment` ) o los comentarios XML estándar ( `///<summary>comment</summary>` ).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Considere la posibilidad de usar archivos de signatura explícitos (. FSI) para la biblioteca estable y las API de componentes

El uso de archivos de firmas explícitos en una biblioteca de F # proporciona un resumen conciso de la API pública, lo que ayuda a garantizar que conoce la superficie pública completa de la biblioteca y proporciona una separación limpia entre la documentación pública y los detalles internos de la implementación. Los archivos de signatura agregan fricción al cambio de la API pública, ya que requieren que se realicen cambios en los archivos de implementación y de firma. Como resultado, los archivos de firma normalmente solo deben introducirse cuando una API se ha contratado y ya no se espera que cambie de forma significativa.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Siga siempre los procedimientos recomendados para el uso de cadenas en .NET

Siga las [prácticas recomendadas para usar cadenas en la guía de .net](../../standard/base-types/best-practices-strings.md) . En concreto, indique siempre explícitamente el *objetivo cultural* en la conversión y la comparación de cadenas (si procede).

## <a name="guidelines-for-f-facing-libraries"></a>Directrices para las bibliotecas orientadas a F #

En esta sección se presentan recomendaciones para el desarrollo de bibliotecas públicas con conexión a F #. es decir, las bibliotecas exponen las API públicas que están pensadas para que las usen los desarrolladores de F #. Hay una variedad de recomendaciones de diseño de biblioteca que se aplican específicamente a F #. En ausencia de las recomendaciones específicas que se indican a continuación, las instrucciones de diseño de la biblioteca de .NET son la guía de reserva.

### <a name="naming-conventions"></a>Convenciones de nomenclatura

#### <a name="use-net-naming-and-capitalization-conventions"></a>Usar convenciones de mayúsculas y minúsculas de nomenclatura .NET

En la tabla siguiente se siguen las convenciones de nomenclatura y capitalización de .NET. Hay pequeñas adiciones que también incluyen construcciones de F #.

| Construcción | Caso | Parte | Ejemplos | Notas |
|-----------|------|------|----------|-------|
| Tipos concretos | PascalCase | Nombre/Adjetivo | Lista, doble, complejo | Los tipos concretos son Structs, clases, enumeraciones, delegados, registros y uniones. Aunque los nombres de tipo están tradicionalmente en minúsculas en OCaml, F # ha adoptado el esquema de nomenclatura de .NET para los tipos.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| Etiquetas de Unión     | PascalCase | Nombre | Algunos, agregar, correcto | No use un prefijo en las API públicas. Opcionalmente, use un prefijo cuando sea interno, como `type Teams = TAlpha | TBeta | TDelta.` |
| Evento          | PascalCase | Verbo | ValueChanged/ValueChanging |  |
| Excepciones     | PascalCase |      | WebException | El nombre debe terminar con "Exception". |
| Campo          | PascalCase | Nombre | CurrentName  | |
| Tipos de interfaz |  PascalCase | Nombre/Adjetivo | IDisposable | El nombre debe comenzar por "I". |
| Método |  PascalCase |  Verbo | ToString | |
| Espacio de nombres | PascalCase | |  Microsoft.FSharp.Core | Por lo general `<Organization>.<Technology>[.<Subnamespace>]` , use, aunque Quite la organización si la tecnología es independiente de la organización. |
| Parámetros | camelCase | Nombre |  typeName, transformación, intervalo | |
| permitir valores (interno) | camelCase o PascalCase | Nombre/verbo |  getValue, MyTable |
| permitir valores (externos) | camelCase o PascalCase | Nombre/verbo  | List. map, fechas. hoy | los valores de Let enlazados suelen ser públicos cuando se siguen los patrones de diseño funcionales tradicionales. Sin embargo, por lo general, se usa PascalCase cuando el identificador se puede usar desde otros lenguajes .NET. |
| Propiedad  | PascalCase  | Nombre/Adjetivo  | IsEndOfFile, BackColor  | Normalmente, las propiedades booleanas usan es y pueden y deben ser afirmativas, como en IsEndOfFile, no IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Evitar abreviaturas

Las instrucciones de .NET desaconsejan el uso de abreviaturas (por ejemplo, "usar `OnButtonClick` en lugar de `OnBtnClick` "). Se toleran las abreviaturas comunes, como `Async` "asincrónicas". A veces, esta instrucción se omite en la programación funcional; por ejemplo, `List.iter` usa una abreviatura para "iterar". Por esta razón, el uso de abreviaturas tiende a tolerar un mayor grado en la programación de F # a F #, pero normalmente se debe evitar en el diseño de componentes públicos.

#### <a name="avoid-casing-name-collisions"></a>Evitar conflictos de nombres con mayúsculas y minúsculas

Las directrices de .NET indican que no se puede usar con mayúsculas y minúsculas para eliminar la ambigüedad de los conflictos de nombres, ya que algunos lenguajes de cliente (por ejemplo, Visual Basic) no distinguen mayúsculas de minúsculas.

#### <a name="use-acronyms-where-appropriate"></a>Usar acrónimos cuando corresponda

Los acrónimos como XML no son abreviaturas y se usan ampliamente en las bibliotecas de .NET en formato inversado (XML). Solo se deben usar acrónimos conocidos y ampliamente reconocidos.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Usar PascalCase para nombres de parámetros genéricos

Use PascalCase para los nombres de parámetros genéricos en las API públicas, incluidas las bibliotecas orientadas a F #. En concreto, use nombres como `T` , `U` , `T1` , `T2` para los parámetros genéricos arbitrarios y, cuando tengan sentido los nombres específicos, en el caso de las bibliotecas orientadas a F #, use nombres como `Key` , `Value` , `Arg` (pero no por ejemplo `TKey` ).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Uso de PascalCase o camelCase para funciones y valores públicos en módulos de F #

camelCase se usa para las funciones públicas que están diseñadas para usarse sin calificar (por ejemplo, `invalidArg` ) y para las "funciones de colección estándar" (por ejemplo, List. map). En ambos casos, los nombres de función actúan de forma muy parecida a las palabras clave en el lenguaje.

### <a name="object-type-and-module-design"></a>Diseño de objetos, tipos y módulos

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usar espacios de nombres o módulos para contener los tipos y módulos

Cada archivo de F # de un componente debe comenzar con una declaración de espacio de nombres o una declaración de módulo.

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

o

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

Las diferencias entre el uso de módulos y espacios de nombres para organizar el código en el nivel superior son las siguientes:

* Los espacios de nombres pueden abarcar varios archivos
* Los espacios de nombres no pueden contener funciones de F # a menos que estén dentro de un módulo interno
* El código de cualquier módulo determinado debe estar incluido en un único archivo.
* Los módulos de nivel superior pueden contener funciones de F # sin necesidad de un módulo interno

La elección entre un módulo o un espacio de nombres de nivel superior afecta al formulario compilado del código y, por tanto, afectará a la vista de otros lenguajes .NET en los casos en que la API se consuma fuera del código de F #.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Usar métodos y propiedades para operaciones intrínsecas a tipos de objeto

Al trabajar con objetos, es mejor asegurarse de que la funcionalidad consumible se implementa como métodos y propiedades en ese tipo.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

No es necesario implementar la mayor parte de la funcionalidad para un miembro determinado en ese miembro, pero la parte consumible de esa funcionalidad debe ser.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Usar clases para encapsular el estado mutable

En F #, esto solo se debe hacer si el estado no está encapsulado por otra construcción de lenguaje, como un cierre, una expresión de secuencia o un cálculo asincrónico.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Usar interfaces para agrupar operaciones relacionadas

Use los tipos de interfaz para representar un conjunto de operaciones. Esto es preferible a otras opciones, como tuplas de funciones o registros de funciones.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

En preferencia a:

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

Las interfaces son conceptos de primera clase en .NET, que puede usar para lograr lo que normalmente le daría. Además, se pueden usar para codificar tipos existencial en el programa, que no pueden tener registros de funciones.

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a>Usar un módulo para agrupar funciones que actúan en colecciones

Al definir un tipo de colección, considere la posibilidad de proporcionar un conjunto estándar de operaciones como `CollectionType.map` y `CollectionType.iter` ) para los nuevos tipos de colección.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Si incluye este módulo, siga las convenciones de nomenclatura estándar para las funciones que se encuentran en FSharp. Core.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Usar un módulo para agrupar funciones para funciones canónicas comunes, especialmente en bibliotecas matemáticas y DSL

Por ejemplo, `Microsoft.FSharp.Core.Operators` es una colección abierta automáticamente de funciones de nivel superior (como `abs` y `sin` ) proporcionada por FSharp.Core.dll.

Del mismo modo, una biblioteca de estadísticas podría incluir un módulo con funciones `erf` y `erfc` , donde este módulo está diseñado para que se abra explícita o automáticamente.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>Considere la posibilidad de usar RequireQualifiedAccess y aplicar cuidadosamente los atributos AutoOpen

Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que el módulo no se puede abrir y que las referencias a los elementos del módulo requieren un acceso calificado explícito. Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.

Esto resulta útil cuando las funciones y los valores del módulo tienen nombres que es probable que entren en conflicto con los nombres de otros módulos. Requerir acceso cualificado puede aumentar considerablemente el mantenimiento a largo plazo y la evolución de una biblioteca.

Agregar el `[<AutoOpen>]` atributo a un módulo significa que el módulo se abrirá cuando se abra el espacio de nombres que lo contiene. El `[<AutoOpen>]` atributo también se puede aplicar a un ensamblado para indicar un módulo que se abre automáticamente cuando se hace referencia al ensamblado.

Por ejemplo, una biblioteca de estadísticas **MathsHeaven. Statistics** puede contener una `module MathsHeaven.Statistics.Operators` función contenedora `erf` y `erfc` . Es razonable marcar este módulo como `[<AutoOpen>]` . Esto significa `open MathsHeaven.Statistics` que también abrirá este módulo y incluirá los nombres `erf` y `erfc` en el ámbito. Otro uso adecuado de `[<AutoOpen>]` es para los módulos que contienen métodos de extensión.

`[<AutoOpen>]`El uso excesivo de los clientes potenciales en los espacios de nombres contaminados y el atributo debe usarse con cuidado. En el caso de bibliotecas específicas de dominios específicos, el uso prudente de `[<AutoOpen>]` puede dar lugar a una mejor facilidad de uso.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Considere la posibilidad de definir miembros de operador en clases en las que el uso de operadores Well-Knows sea adecuado.

A veces, las clases se utilizan para modelar construcciones matemáticas como vectores. Cuando el dominio que se está modelando tiene operadores conocidos, es útil definirlos como miembros intrínsecos de la clase.

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Esta guía se corresponde con las instrucciones generales de .NET para estos tipos. Sin embargo, también puede ser importante en la codificación de F #, ya que permite usar estos tipos junto con funciones y métodos de F # con restricciones de miembro, como List. sumBy (.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Considere el uso de Compiledname (para proporcionar un. Nombre descriptivo para otros consumidores del lenguaje .NET

En ocasiones, es posible que desee asignar un nombre a algo en un estilo para los consumidores de F # (por ejemplo, un miembro estático en minúsculas para que aparezca como si fuera una función enlazada a un módulo), pero tener un estilo diferente para el nombre cuando se compila en un ensamblado. Puede usar el `[<CompiledName>]` atributo para proporcionar un estilo diferente para el código que no es de F # que usa el ensamblado.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Mediante el uso de `[<CompiledName>]` , puede usar las convenciones de nomenclatura de .net para los consumidores que no son de F # del ensamblado.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Usar la sobrecarga de métodos para las funciones miembro, si esto proporciona una API más sencilla

La sobrecarga de métodos es una herramienta eficaz para simplificar una API que puede necesitar realizar una funcionalidad similar, pero con diferentes opciones o argumentos.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

En F #, es más común sobrecargar el número de argumentos en lugar de los tipos de argumentos.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Ocultar las representaciones de los tipos de registro y Unión si es probable que evolucione el diseño de estos tipos

Evite revelar representaciones concretas de objetos. Por ejemplo, la <xref:System.DateTime> API pública externa del diseño de la biblioteca de .net no revela la representación concreta de los valores. En tiempo de ejecución, Common Language Runtime conoce la implementación confirmada que se utilizará a lo largo de la ejecución. Sin embargo, el código compilado no selecciona las dependencias en la representación concreta.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Evitar el uso de la herencia de implementación para la extensibilidad

En F #, rara vez se utiliza la herencia de implementación. Además, las jerarquías de herencia suelen ser complejas y difíciles de cambiar cuando llegan nuevos requisitos. La implementación de la herencia todavía existe en F # por compatibilidad y casos raros en los que es la mejor solución para un problema, pero se deben buscar técnicas alternativas en los programas de F # al diseñar el polimorfismo, como la implementación de la interfaz.

### <a name="function-and-member-signatures"></a>Firmas de función y de miembro

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Usar tuplas para valores devueltos al devolver un número pequeño de varios valores no relacionados

Este es un buen ejemplo del uso de una tupla en un tipo de valor devuelto:

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

En el caso de los tipos de valor devueltos que contienen muchos componentes, o en los que los componentes están relacionados con una sola entidad identificable, considere la posibilidad de usar un tipo con nombre en lugar de una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Se usa `Async<T>` para la programación asincrónica en los límites de la API de F #

Si hay una operación sincrónica correspondiente denominada `Operation` que devuelve un `T` , se debe asignar un nombre a la operación asincrónica `AsyncOperation` si devuelve `Async<T>` o `OperationAsync` si devuelve `Task<T>` . En el caso de los tipos de .NET que se usan habitualmente y que exponen métodos Begin/end, considere la posibilidad de usar `Async.FromBeginEnd` para escribir métodos de extensión como una fachada para proporcionar el modelo de programación de F # Async a esas API de .net.

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>Excepciones

Consulte [Administración de errores](conventions.md#error-management) para obtener información sobre el uso adecuado de excepciones, resultados y opciones.

### <a name="extension-members"></a>Miembros de extensión

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Aplicar cuidadosamente los miembros de extensión de F # en componentes de F # a-F #

Normalmente, los miembros de extensión de F # solo se deben usar para las operaciones que se encuentran en el cierre de operaciones intrínsecas asociadas a un tipo en la mayoría de los modos de uso. Un uso común es proporcionar API más idiomático a F # para varios tipos de .NET:

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>Tipos de Unión

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Usar uniones discriminadas en lugar de jerarquías de clases para los datos estructurados por árbol

Las estructuras de tipo árbol se definen de forma recursiva. Esto es complicado con la herencia, pero elegante con uniones discriminadas.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Representar datos similares a los árboles con uniones discriminadas también le permite beneficiarse de la en la coincidencia de patrones.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Usar `[<RequireQualifiedAccess>]` en tipos de Unión cuyos nombres de caso no son suficientemente únicos

Puede que se encuentre en un dominio en el que el mismo nombre sea el mejor para cosas diferentes, como casos de Unión discriminada. Puede usar para eliminar la `[<RequireQualifiedAccess>]` ambigüedad de los nombres de mayúsculas y minúsculas con el fin de evitar que se produzcan errores confusos debido al sombreado dependiente del orden de las `open` instrucciones.

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Ocultar las representaciones de las uniones discriminadas para las API compatibles con binario si es probable que evolucione el diseño de estos tipos

Los tipos uniones se basan en formularios de coincidencia de patrones de F # para un modelo de programación conciso. Como se mencionó anteriormente, debe evitar revelar representaciones de datos concretas si es probable que evolucione el diseño de estos tipos.

Por ejemplo, la representación de una Unión discriminada se puede ocultar mediante una declaración privada o interna, o mediante un archivo de signatura.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Si revela las uniones discriminadas indiscriminadamente, puede que le resulte difícil crear una versión de la biblioteca sin interrumpir el código de usuario. En su lugar, considere la posibilidad de mostrar uno o varios patrones activos para permitir la coincidencia de patrones con los valores de su tipo.

Los modelos activos proporcionan una forma alternativa de proporcionar a los consumidores de F # la coincidencia de patrones, al mismo tiempo que evitan exponer directamente los tipos de unión de F #.

### <a name="inline-functions-and-member-constraints"></a>Funciones insertadas y restricciones de miembro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definir algoritmos numéricos genéricos mediante funciones insertadas con restricciones de miembros implícitas y tipos genéricos resueltos estáticamente

Las restricciones de miembros aritméticos y las restricciones de comparación de F # son un estándar para la programación en F #. Por ejemplo, considere el siguiente código:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

El tipo de esta función es el siguiente:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Se trata de una función adecuada para una API pública en una biblioteca matemática.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Evite el uso de restricciones de miembro para simular clases de tipos y tipos de patos

Es posible simular "Duck Typing" con las restricciones de miembro de F #. Sin embargo, los miembros que hacen uso de esto no deben usarse en general en los diseños de la biblioteca de F # a-F #. Esto se debe a que los diseños de biblioteca basados en restricciones implícitas no conocidas o no estándar tienden a hacer que el código de usuario sea inflexible y vinculado a un patrón de marco de trabajo determinado.

Además, existe la posibilidad de que el uso intensivo de restricciones de miembros de esta manera pueda producir tiempos de compilación muy largos.

### <a name="operator-definitions"></a>Definiciones de operador

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evite definir operadores simbólicos personalizados

Los operadores personalizados son esenciales en algunas situaciones y son dispositivos de notación muy útiles en un gran número de código de implementación. En el caso de los nuevos usuarios de una biblioteca, las funciones con nombre suelen ser más fáciles de usar. Además, los operadores simbólicos personalizados pueden ser difíciles de documentar y los usuarios le resultarán más difíciles de buscar ayuda sobre los operadores, debido a las limitaciones existentes en el IDE y los motores de búsqueda.

Como resultado, es mejor publicar su funcionalidad como funciones y miembros con nombre y, además, exponer operadores para esta funcionalidad solo si las ventajas de la notación son más importantes que la documentación y el costo cognitivo de tenerlos.

### <a name="units-of-measure"></a>Unidades de medida

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Usar cuidadosamente unidades de medida para la seguridad de tipos agregada en código de F #

La información de escritura adicional para las unidades de medida se borra cuando la ven otros lenguajes de .NET. Tenga en cuenta que los componentes, las herramientas y la reflexión de .NET verán tipos-sans-units. Por ejemplo, los consumidores de C# verán `float` en lugar de `float<kg>` .

### <a name="type-abbreviations"></a>Abreviaturas de tipo

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Usar cuidadosamente las abreviaturas de tipo para simplificar el código de F #

Los componentes, las herramientas y la reflexión de .NET no verán los nombres abreviados de los tipos. El uso significativo de las abreviaturas de tipo también puede hacer que un dominio parezca más complejo de lo que realmente es, lo que puede confundir a los consumidores.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evite las abreviaturas de tipo para los tipos públicos cuyos miembros y propiedades deben ser intrínsecamente diferentes a los disponibles en el tipo que se va a abreviar.

En este caso, el tipo que se va a abreviar revela demasiada información sobre la representación del tipo real que se está definiendo. En su lugar, considere la posibilidad de ajustar la abreviatura en un tipo de clase o en una Unión discriminada de un caso (o, cuando el rendimiento sea esencial, considere la posibilidad de usar un tipo de struct para encapsular la abreviatura).

Por ejemplo, es tentador definir un mapa múltiple como un caso especial de un mapa de F #, por ejemplo:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Sin embargo, las operaciones de notación de puntos lógicas de este tipo no son las mismas que las operaciones en un mapa; por ejemplo, es razonable que la asignación del operador de búsqueda. [Key] devuelve la lista vacía si la clave no está en el diccionario, en lugar de generar una excepción.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Directrices para las bibliotecas para su uso desde otros lenguajes .NET

Al diseñar bibliotecas para su uso desde otros lenguajes .NET, es importante cumplir las directrices de [diseño](../../standard/design-guidelines/index.md)de la biblioteca de .net. En este documento, estas bibliotecas se etiquetan como bibliotecas de .NET de vainilla, a diferencia de las bibliotecas de F # orientadas a las que usan construcciones de F # sin restricciones. El diseño de las bibliotecas .NET de vainilla permite proporcionar API conocidas y idiomáticos coherentes con el resto de los .NET Framework al minimizar el uso de construcciones específicas de F # en la API pública. Las reglas se explican en las secciones siguientes.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Espacio de nombres y diseño de tipos (para bibliotecas para su uso desde otros lenguajes .NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Aplicar las convenciones de nomenclatura de .NET a la API pública de los componentes

Preste especial atención al uso de nombres abreviados y a las directrices de capitalización de .NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Usar espacios de nombres, tipos y miembros como la estructura organizativa principal de los componentes

Todos los archivos que contienen funcionalidad pública deben comenzar con una `namespace` declaración y las únicas entidades de acceso público de los espacios de nombres deben ser tipos. No use módulos de F #.

Use módulos no públicos para almacenar el código de implementación, los tipos de utilidad y las funciones de utilidad.

Los tipos estáticos deben ser preferibles a los módulos, ya que permiten la evolución futura de la API para usar la sobrecarga y otros conceptos de diseño de la API de .NET que no se pueden usar en los módulos de F #.

Por ejemplo, en lugar de la siguiente API pública:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

En su lugar, considere:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Usar tipos de registro de F # en las API de .NET de vainilla si el diseño de los tipos no evolucionará

Los tipos de registro de F # se compilan en una clase .NET simple. Son adecuadas para algunos tipos simples y estables en las API. Considere la posibilidad de usar los `[<NoEquality>]` `[<NoComparison>]` atributos y para suprimir la generación automática de interfaces. Evite también el uso de campos de registro mutables en las API de .NET de vainilla, ya que exponen un campo público. Considere siempre si una clase proporcionaría una opción más flexible para la evolución futura de la API.

Por ejemplo, el siguiente código de F # expone la API pública a un consumidor de C#:

F#:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

C#:

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Ocultar la representación de tipos de unión de F # en las API de .NET de vainilla

Los tipos de unión de f # no se usan habitualmente en los límites de los componentes, ni siquiera para la codificación de F # a F #. Son un dispositivo de implementación excelente cuando se usan internamente en componentes y bibliotecas.

Al diseñar una API de .NET de vainilla, considere la posibilidad de ocultar la representación de un tipo de Unión mediante una declaración privada o un archivo de signatura.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

También puede aumentar los tipos que usan internamente una representación de unión con los miembros para proporcionar el deseado. API orientada a redes.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Diseñar GUI y otros componentes mediante los modelos de diseño del marco de trabajo

Hay muchos marcos de trabajo diferentes disponibles en .NET, como WinForms, WPF y ASP.NET. Las convenciones de nomenclatura y diseño de cada una deben usarse si se diseñan componentes para su uso en estos marcos de trabajo. Por ejemplo, para la programación de WPF, adopte patrones de diseño de WPF para las clases que está diseñando. En el caso de los modelos de programación de la interfaz de usuario, utilice patrones de diseño como eventos y colecciones basadas en notificaciones, como las que se encuentran en <xref:System.Collections.ObjectModel> .

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Diseño de objetos y miembros (para bibliotecas para su uso desde otros lenguajes .NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Usar el atributo CLIEvent para exponer eventos de .NET

Construya un `DelegateEvent` con un tipo de delegado .net específico que toma un objeto y `EventArgs` (en lugar de un `Event` , que simplemente usa el `FSharpHandler` tipo de forma predeterminada) para que los eventos se publiquen de la manera más familiar que otros lenguajes .net.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a>Exponer operaciones asincrónicas como métodos que devuelven tareas de .NET

Las tareas se usan en .NET para representar los cálculos asincrónicos activos. En general, las tareas son menos compuestas que los objetos de F # `Async<T>` , ya que representan las tareas que ya se están ejecutando y no se pueden componer juntas de forma que realicen la composición paralela, o que ocultan la propagación de señales de cancelación y otros parámetros contextuales.

Sin embargo, a pesar de ello, los métodos que devuelven tareas son la representación estándar de la programación asincrónica en .NET.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Normalmente, también querrá aceptar un token de cancelación explícito:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Usar tipos de delegado de .NET en lugar de tipos de función de F #

Aquí "tipos de funciones de F #" significan tipos de "flecha" como `int -> int` .

En lugar de esto:

```fsharp
member this.Transform(f: int->int) =
    ...
```

Haga esto:

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

El tipo de función de F # aparece como `class FSharpFunc<T,U>` en otros lenguajes .net y es menos adecuado para las características del lenguaje y las herramientas que comprenden los tipos de delegado. Al crear un método de orden superior que tenga como destino .NET Framework 3,5 o superior, `System.Func` los `System.Action` delegados y son las API adecuadas para publicar y permitir a los desarrolladores de .net usar estas API de manera insuficiente. (Cuando el destino es .NET Framework 2,0, los tipos de delegado definidos por el sistema son más limitados; considere la posibilidad de usar tipos de delegado predefinidos como `System.Converter<T,U>` o definir un tipo de delegado específico).

En el lado de volteo, los delegados de .NET no son naturales para las bibliotecas orientadas a F # (vea la siguiente sección sobre bibliotecas orientadas a F #). Como resultado, una estrategia de implementación común al desarrollar métodos de orden superior para las bibliotecas de .NET de vainilla es crear toda la implementación con los tipos de función de F # y, a continuación, crear la API pública mediante delegados como una fachada fina sobre la implementación real de F #.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Use el patrón TryGetValue en lugar de devolver valores de opción de F # y preferir la sobrecarga del método para tomar los valores de las opciones de F # como argumentos.

Los patrones comunes de uso para el tipo de opción de F # en las API se implementan mejor en las API de .NET de vainilla mediante técnicas de diseño estándar de .NET. En lugar de devolver un valor de opción de F #, considere la posibilidad de usar el tipo de valor devuelto bool junto con un parámetro out como en el patrón "TryGetValue". Y en lugar de tomar los valores de las opciones de F # como parámetros, considere la posibilidad de usar la sobrecarga de métodos o argumentos opcionales.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Usar los tipos de interfaz de colección de .NET IEnumerable \<T\> y IDictionary \<Key,Value\> para los parámetros y valores devueltos

Evite el uso de tipos de colección concretos como matrices de .NET `T[]` , tipos de F # y `list<T>` `Map<Key,Value>` `Set<T>` , y tipos de colección concretos de .net como `Dictionary<Key,Value>` . Las instrucciones de diseño de la biblioteca de .NET tienen buenos consejos sobre Cuándo usar varios tipos de colección como `IEnumerable<T>` . El uso de matrices ( `T[]` ) es aceptable en algunas circunstancias, por motivos de rendimiento. Tenga en cuenta especialmente que `seq<T>` es solo el alias de F # para `IEnumerable<T>` y, por lo tanto, SEQ suele ser un tipo adecuado para una API de .net de vainilla.

En lugar de listas de F #:

```fsharp
member this.PrintNames(names: string list) =
    ...
```

Usar secuencias de F #:

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Use el tipo de unidad como el único tipo de entrada de un método para definir un método de argumento cero, o como el único tipo de valor devuelto para definir un método que devuelve void.

Evite otros usos del tipo de unidad. Estos son buenos:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

Esto no es válido:

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Comprobar si hay valores NULL en los límites de la API de .NET de vainilla

El código de implementación de F # tiende a tener menos valores NULL, debido a las restricciones y patrones de diseño inmutables sobre el uso de literales null para los tipos de F #. Otros lenguajes .NET suelen usar NULL como valor con mucha más frecuencia. Por este motivo, el código de F # que expone una API de .NET de vainilla debe comprobar los parámetros null en el límite de la API y evitar que estos valores fluyan más en el código de implementación de F #. `isNull`Se puede usar la función o coincidencia de patrones en el `null` patrón.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>Evite el uso de tuplas como valores devueltos

En su lugar, se prefiere devolver un tipo con nombre que contenga los datos agregados o usar parámetros out para devolver varios valores. Aunque las tuplas de estructuras y de struct existen en .NET (incluida la compatibilidad con el lenguaje C# para las tuplas de struct), a menudo no proporcionarán la API ideal y la esperada para los desarrolladores de .NET.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Evitar el uso de currificación de parámetros

En su lugar, use convenciones de llamada de .NET `Method(arg1,arg2,…,argN)` .

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Sugerencia: Si está diseñando bibliotecas para su uso desde cualquier lenguaje .NET, no habrá ningún sustituto para realizar realmente alguna programación experimental de C# y Visual Basic para asegurarse de que las bibliotecas "se sienten bien" desde estos lenguajes. También puede usar herramientas como .NET reflector y el Examinador de objetos de Visual Studio para asegurarse de que las bibliotecas y su documentación aparecen como se espera para los desarrolladores.

## <a name="appendix"></a>Apéndice

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Ejemplo de un extremo a otro del diseño de código de F # para su uso por parte de otros lenguajes .NET

Considere la siguiente clase:

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

El tipo de F # deducido de esta clase es el siguiente:

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

Echemos un vistazo a cómo se muestra este tipo de F # a un programador con otro lenguaje .NET. Por ejemplo, la "firma" de C# aproximada es la siguiente:

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

Hay algunos aspectos importantes que se deben tener en cuenta sobre cómo F # representa las construcciones aquí. Por ejemplo:

* Se han conservado los metadatos, como los nombres de los argumentos.

* Los métodos de F # que toman dos argumentos se convierten en métodos de C# que toman dos argumentos.

* Las funciones y las listas se convierten en referencias a los tipos correspondientes de la biblioteca de F #.

En el código siguiente se muestra cómo ajustar este código para tener en cuenta estos aspectos.

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

El tipo de F # deducido del código es el siguiente:

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

La firma de C# es ahora como sigue:

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

Las correcciones realizadas para preparar este tipo para su uso como parte de una biblioteca .NET de vainilla son las siguientes:

* Se han ajustado varios nombres: `Point1` , `n` , y se han convertido en `l` `f` `RadialPoint` , `count` , `factor` y `transform` , respectivamente.

* Se usa un tipo de valor devuelto de en `seq<RadialPoint>` lugar de `RadialPoint list` cambiar una construcción de lista mediante `[ ... ]` a una construcción de secuencia mediante `IEnumerable<RadialPoint>` .

* Se usa el tipo de delegado de .NET `System.Func` en lugar de un tipo de función de F #.

Esto hace que sea mucho más agradable usar en el código de C#.
