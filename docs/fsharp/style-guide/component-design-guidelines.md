---
title: 'Instrucciones de diseño del componente de F #'
description: 'Obtenga información sobre las directrices para escribir componentes de F # pensados para su uso por otros llamadores.'
ms.date: 05/14/2018
ms.openlocfilehash: 446cba0f810af9517b655ef5741ddf7a919676d5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488292"
---
# <a name="f-component-design-guidelines"></a>Instrucciones de diseño del componente de F #

Este documento es un conjunto de directrices de diseño del componente de F # de programación, en función de la F # componente instrucciones de diseño, v14, Microsoft Research, y [otra versión](https://fsharp.org/specs/component-design-guidelines/) originalmente seleccionada y mantenido por F # Software Foundation.

Este documento se da por supuesto que está familiarizado con la programación en F #. Muchas gracias a la Comunidad de F # por sus aportaciones y comentarios útiles en varias versiones de esta guía.

## <a name="overview"></a>Información general

Este documento se examina algunos de los problemas relacionados con la codificación y diseño del componente de F #. Un componente puede significar cualquiera de las siguientes acciones:

* Una capa en el proyecto de F # que tiene los consumidores externos dentro de ese proyecto.
* Una biblioteca pensada para su uso por código de F # a través de límites de ensamblado.
* Una biblioteca diseñada para su uso en cualquier lenguaje .NET entre límites de ensamblado.
* Una biblioteca diseñada para su distribución a través de un repositorio de paquetes, tales como [NuGet](https://nuget.org).

Las técnicas descritas en este artículo siguen el [cinco principios del buen código de F #](index.md#five-principles-of-good-f-code)y, por tanto, usar ambos funcional y objeto de programación según corresponda.

Independientemente de la metodología, el Diseñador de componentes y la biblioteca enfrenta una serie de problemas prácticas y prosaicos al tratar de diseñar una API que se puede usar más fácilmente los desarrolladores. Una aplicación muy consciente de la [instrucciones de diseño de bibliotecas de .NET](../../standard/design-guidelines/index.md) encaminarse hacia la creación de un conjunto coherente de API que están agradables para consumir.

## <a name="general-guidelines"></a>Instrucciones generales

Hay algunas instrucciones universales que se aplican a las bibliotecas F #, independientemente de la audiencia objetivo de la biblioteca.

### <a name="learn-the-net-library-design-guidelines"></a>Obtenga información sobre las instrucciones de diseño de la biblioteca de .NET

Independientemente del tipo de F # de codificación está realizando, es útil tener conocimientos prácticos de la [instrucciones de diseño de bibliotecas de .NET](../../standard/design-guidelines/index.md). La mayoría otros F # y los programadores de .NET se está familiarizado con estas directrices y esperar que el código de .NET para ajustarse a ellos.

Las instrucciones de diseño de la biblioteca de .NET proporcionan información general sobre la nomenclatura, diseño de clases y las interfaces, diseño de miembros (propiedades, métodos, eventos, etc.) y mucho más y son útil primer punto de referencia para una variedad de instrucciones de diseño.

### <a name="add-xml-documentation-comments-to-your-code"></a>Agregar comentarios de documentación XML en el código

Documentación XML en las API públicas Asegúrese de que los usuarios pueden obtener gran Intellisense y Quickinfo al utilizar estos tipos y miembros y habilitar documentación para crear archivos de la biblioteca. Consulte la [documentación XML](../language-reference/xml-documentation.md) sobre diversas etiquetas xml que se pueden usar para el marcado adicional dentro de los comentarios de xmldoc.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

Puede usar los comentarios XML de forma abreviada (`/// comment`), o los comentarios XML estándar (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Considere el uso de archivos explícita signatura (.fsi) para la biblioteca estable y las API de componentes

Uso de archivos de firmas explícita en una biblioteca de F # proporciona un breve resumen de API pública, que ayuda a garantizar que se conoce la superficie pública completa de la biblioteca, así como proporciona una separación limpia entre documentación pública e internos detalles de implementación. Tenga en cuenta que los archivos de firma agregan fricción al cambio de la API pública, al requerir que los cambios que se realizan en los archivos de la implementación y la firma. Como resultado, los archivos de firma normalmente solo se deben agregar cuando una API ha consolidado a convertirse en y ya no se espera que cambie significativamente.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Siga siempre las prácticas recomendadas para el uso de cadenas en .NET

Siga [prácticas recomendadas para el uso de cadenas en .NET](../../standard/base-types/best-practices-strings.md) orientación. En concreto, siempre explícitamente *intención cultural* en la conversión y la comparación de cadenas (si procede).

## <a name="guidelines-for-f-facing-libraries"></a>Directrices para F #-orientado a las bibliotecas

En esta sección se presenta recomendaciones para el desarrollo de F # pública-orientado a las bibliotecas; es decir, las bibliotecas de exponer las API públicas que vayan a ser consumidos por los desarrolladores de F #. Hay una variedad de recomendaciones de diseño de la biblioteca aplicables específicamente a F #. En ausencia de las recomendaciones específicas que siguen, las instrucciones de diseño de la biblioteca de .NET son las instrucciones de reserva.

### <a name="naming-conventions"></a>Convenciones de nomenclatura

#### <a name="use-net-naming-and-capitalization-conventions"></a>Usar las convenciones de mayúsculas y minúsculas y nomenclatura de .NET

La siguiente tabla sigue las convenciones de mayúsculas y minúsculas y nomenclatura. NET. Existen adiciones pequeño para incluir también las construcciones de F #.

| Construcción | Caso | Parte | Ejemplos | Notas |
|-----------|------|------|----------|-------|
| Tipos concretos | PascalCase | Sustantivo o adjetivo | Lista, Double, complejo | Tipos concretos son clases, structs, enumeraciones, delegados, registros y uniones. Aunque los nombres de tipo son tradicionalmente en minúsculas en OCaml, F # ha adoptado el esquema de nomenclatura .NET para los tipos.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| Etiquetas de unión     | PascalCase | Sustantivo | Algunos, agregar, correcto | No use un prefijo en las API públicas. Utilizar opcionalmente un prefijo cuando interno, como ''' Escriba equipos = TAlpha | TBeta | TDelta.'' ' |
| evento          | PascalCase | Verbo | ValueChanged / ValueChanging |  |
| Excepciones     | PascalCase |      | WebException | Nombre debe terminar con "Exception". |
| Campo          | PascalCase | Sustantivo | CurrentName  | |
| Tipos de interfaz |  PascalCase | Sustantivo o adjetivo | IDisposable | Nombre debe comenzar por "I". |
| Método |  PascalCase |  Verbo | ToString | |
| Espacio de nombres | PascalCase | | Microsoft.FSharp.Core | Generalmente se utiliza `<Organization>.<Technology>[.<Subnamespace>]`, drop aunque la organización si la tecnología es independiente de la organización. |
| Parámetros | camelCase | Sustantivo |  typeName, transformación, intervalo | |
| permitir que los valores (internos) | camelCase o PascalCase | Sustantivo o verbo |  getValue, myTable |
| permitir que los valores (externo) | camelCase o PascalCase | Verbo y sustantivo  | List.Map, Dates.Today | a menudo son públicos enlazado a Let valores al seguir los patrones de diseño funcionales tradicional. Sin embargo, normalmente usar PascalCase cuando el identificador puede usarse desde otros lenguajes. NET. |
| Property  | PascalCase  | Sustantivo o adjetivo  | IsEndOfFile, color de fondo  | Las propiedades booleanas generalmente uso es y puede y debe ser afirmativa, como en IsEndOfFile, no IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Evitar las abreviaturas

Las instrucciones de .NET desaconseja el uso de abreviaturas de (por ejemplo, "usar `OnButtonClick` lugar `OnBtnClick`"). Abreviaturas comunes, como `Async` para "Asynchronous", se tolera. A veces se pasa por alto esta directriz de programación funcional; Por ejemplo, `List.iter` usa una abreviatura para "recorrer en iteración". Por este motivo, con abreviaturas tiende a tolerar un mayor grado de F #-a-programación en F #, pero aún por lo general debe evitarse en el diseño del componente público.

#### <a name="avoid-casing-name-collisions"></a>Evitar las mayúsculas y minúsculas de las colisiones de nombres

Las instrucciones de .NET dicen que las mayúsculas y minúsculas por sí solo no pueden usarse para eliminar la ambigüedad de las colisiones de nombres, ya que algunos idiomas de cliente (por ejemplo, Visual Basic) distinguen mayúsculas de minúsculas.

#### <a name="use-acronyms-where-appropriate"></a>Utilizar acrónimos cuando sea apropiado

Acrónimos como XML no son abreviaturas y se usan ampliamente en las bibliotecas de .NET de forma sin mayúsculas (Xml). Solo deben usarse acrónimos conocidos y ampliamente reconocidos.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Uso PascalCase para los nombres de parámetro genérico

Usar PascalCase para nombres de parámetro genérico en las API públicas, incluido para F #-orientado a las bibliotecas. En concreto, use nombres como `T`, `U`, `T1`, `T2` para los parámetros genéricos arbitrarios y nombres específicos tienen sentido, a continuación, para F #-accesibles desde bibliotecas usen nombres como `Key`, `Value`, `Arg`(pero no por ejemplo, `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Usar PascalCase o camelCase para funciones públicas y valores en los módulos de F #

camelCase se utiliza para funciones públicas que están diseñadas para usarse incompletos (por ejemplo, `invalidArg`) y para las funciones de colección estándar de"" (por ejemplo, List.map). En ambos casos, los nombres de función actúan como palabras clave en el lenguaje.

### <a name="object-type-and-module-design"></a>Diseño de objeto, tipo y módulo

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usar módulos o espacios de nombres para contener los tipos y módulos

Cada archivo de F # en un componente debe comenzar con una declaración de espacio de nombres o una declaración de módulo.

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

Las diferencias entre el uso de módulos y espacios de nombres para organizar el código en el nivel superior son como sigue:

* Los espacios de nombres pueden abarcar varios archivos
* Los espacios de nombres no pueden contener funciones de F # a menos que estén dentro de un módulo interno
* El código de cualquier módulo determinado debe estar dentro de un solo archivo
* Módulos de nivel superior pueden contener funciones de F # sin necesidad de un módulo interno

La elección entre un espacio de nombres de nivel superior o un módulo afecta a la forma compilada del código y, por tanto, afectará a la vista de otros lenguajes .NET su API, finalmente, se debe consumir fuera del código de F #.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Usar métodos y propiedades para las operaciones intrínsecas a tipos de objeto

Cuando se trabaja con objetos, es mejor asegurarse de que pueda consumir funcionalidad se implementa como métodos y propiedades de dicho tipo.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

La mayor parte de la funcionalidad para un miembro determinado necesita no necesariamente se implementarán en ese miembro, pero debe ser el fragmento consumible de esa funcionalidad.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Usar las clases para encapsular el estado mutable

En F #, esto solo debe hacerse donde que no está encapsulado ya estado por otra construcción del lenguaje, como una clausura, la expresión de secuencia o el cálculo asincrónico.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Usar interfaces para agrupar las operaciones relacionadas con

Usar tipos de interfaz para representar un conjunto de operaciones. Esto es preferible a otras opciones, como las tuplas de funciones o los registros de funciones.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

En el lugar para:

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

Las interfaces son conceptos de primera clase en. NET, que puede usar para lograr lo Functors normalmente le aportara. Además, puede utilizarse para codificar tipos existenciales en el programa, que no puede ser de los registros de funciones.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>Usar un módulo para las funciones del grupo que actúan en colecciones

Al definir un tipo de colección, considere la posibilidad de proporcionar un conjunto estándar de operaciones como `CollectionType.map` y `CollectionType.iter`) para los nuevos tipos de colección.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Si incluye un módulo de este tipo, siga las convenciones de nomenclatura estándares para las funciones que se encuentra en FSharp.Core.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Usar un módulo para las funciones del grupo para funciones comunes canónicas, especialmente en matemáticas y las bibliotecas DSL

Por ejemplo, `Microsoft.FSharp.Core.Operators` es una colección de funciones de nivel superior abierta automáticamente (como `abs` y `sin`) proporcionada por FSharp.Core.dll.

Del mismo modo, una biblioteca de estadísticas podría incluir un módulo con funciones `erf` y `erfc`, donde este módulo está diseñado para que se abran explícitamente o automáticamente.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>Considere el uso de RequireQualifiedAccess y aplicar con cuidado AutoOpen atributos

Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso. Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.

Esto es útil cuando las funciones y los valores del módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos. Necesidad de tener acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y la capacidad de evolución de una biblioteca.

Agregar el `[<AutoOpen>]` atributo a un módulo, significa que el módulo se abrirá cuando se abre el espacio de nombres contenedor. El `[<AutoOpen>]` el atributo puede aplicarse a un ensamblado para indicar un módulo que se abre automáticamente cuando se hace referencia al ensamblado.

Por ejemplo, una biblioteca de estadísticas **MathsHeaven.Statistics** podría contener un `module MathsHeaven.Statistics.Operators` que contienen funciones `erf` y `erfc`. Es razonable marcar este módulo como `[<AutoOpen>]`. Esto significa `open MathsHeaven.Statistics` también abrirá este módulo y poner los nombres `erf` y `erfc` en el ámbito. Otro buen uso de `[<AutoOpen>]` es para los módulos que contienen métodos de extensión.

Uso excesivo de `[<AutoOpen>]` clientes potenciales a contaminado espacios de nombres y el atributo deberían usarse con cuidado. Para las bibliotecas específicas de dominios concretos, un uso razonable de `[<AutoOpen>]` puede dar lugar a una mejor utilización.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Considere la posibilidad de definir los miembros de operador en las clases donde es adecuado utilizar operadores conocidos

A veces clases se utilizan para modelar matemáticas construcciones como vectores. Cuando el dominio que se está modelando tiene operadores conocidos, que definirlas como miembros intrínsecos a la clase es útil.

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Esta guía se corresponde con las instrucciones generales de .NET para estos tipos. Sin embargo, puede ser importante además en F # codificaciones, ya que esto permite que estos tipos para usarse en métodos con restricciones de miembro, como List.sumBy y junto con las funciones de F #.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Considere el uso de CompiledName para proporcionar una. Nombre descriptivo de la red para otros consumidores de idioma de .NET

En ocasiones, puede nombrar algo en un estilo para los consumidores de F # (por ejemplo, un miembro estático en minúsculas para que aparezca como si fuera una función de módulo enlazados), pero tienen un estilo diferente para el nombre cuando se compila en un ensamblado. Puede usar el `[<CompiledName>]` atributo para proporcionar un estilo diferente de F # que no es código que consume el ensamblado.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Mediante el uso de `[<CompiledName>]`, puede usar las convenciones de nomenclatura .NET para F # que no son los consumidores del ensamblado.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Use la sobrecarga de métodos para funciones miembro, si al hacerlo proporciona una API más sencilla

La sobrecarga de método es una herramienta eficaz para simplificar una API que puede necesitar realizar una funcionalidad similar, pero con distintas opciones o argumentos.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

En F #, es más habitual de sobrecarga en el número de argumentos en lugar de tipos de argumentos.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Ocultar las representaciones de registro y los tipos de unión si es probable que evolucione el diseño de estos tipos

Evitar revelar representaciones concretas de objetos. Por ejemplo, la representación concreta de <xref:System.DateTime> la API pública externa del diseño de biblioteca de .NET no revelan los valores. En tiempo de ejecución, Common Language Runtime sabe la implementación confirma que se usará en toda la ejecución. Sin embargo, código compilado no propio recoge las dependencias de la representación concreta.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Evite el uso de la herencia de implementación para la extensibilidad

En F #, rara vez se usa la herencia de la implementación. Además, las jerarquías de herencia son a menudo complejo y difícil de cambiar cuando lleguen nuevos requisitos. Implementación de la herencia sigue existiendo en F # de compatibilidad y raras ocasiones donde es la mejor solución a un problema, pero deben buscarse técnicas alternativas en los programas de F # cuando se diseña para polimorfismo, como la implementación de la interfaz.

### <a name="function-and-member-signatures"></a>Firmas de función y miembro

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Uso de tuplas para los valores devueltos cuando se devuelve un número pequeño de varios valores no relacionados

Este es un buen ejemplo del uso de una tupla en un tipo de valor devuelto:

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

Para devolver tipos que contengan muchos componentes, o donde los componentes están relacionados con una sola entidad identificable, plantéese el uso de un tipo con nombre en lugar de una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Use `Async<T>` para programación asincrónica en los límites de API de F #

Si hay una operación sincrónica correspondiente denominada `Operation` que devuelve un `T`, a continuación, la operación asincrónica debe denominarse `AsyncOperation` si devuelve `Async<T>` o `OperationAsync` si devuelve `Task<T>`. Para los tipos de .NET utilizados frecuentemente que exponen métodos Begin/End, considere el uso de `Async.FromBeginEnd` escribir métodos de extensión como una fachada para proporcionar la F # async modelo de programación a las API de .NET.

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>Excepciones

Consulte [administración de errores](conventions.md#error-management) para obtener información sobre el uso adecuado de las excepciones, los resultados y opciones.

### <a name="extension-members"></a>Miembros de extensión

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Aplicar con cuidado los miembros de extensión de F # en F #-a-F # componentes

Los miembros de extensión de F # por lo general deben usarse solo para las operaciones que se encuentran en el cierre de operaciones intrínsecos asociado con un tipo en la mayoría de los modos de uso. Un uso común es proporcionar las API que son más idiomáticas de F # para varios tipos. NET:

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>Tipos de unión

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Usar uniones discriminadas en lugar de jerarquías de clases para los datos de la estructura de árbol

Las estructuras de árbol están definidos de forma recursiva. Esto es difícil con herencia, pero elegante con uniones discriminadas.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Que representa los datos en forma de árbol con uniones discriminadas también permite beneficiarse de exhaustiveness en coincidencia de patrones.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Use `[<RequireQualifiedAccess>]` en tipos de unión cuyos nombres casos no son lo suficientemente exclusivos

Puede buscar por sí mismo en un dominio donde el mismo nombre es el nombre más adecuado para diferentes operaciones, como casos de unión discriminada. Puede usar `[<RequireQualifiedAccess>]` para eliminar la ambigüedad con el fin de evitar que se produzca errores confusos debido al sombreado dependientes en el orden de los nombres de casos `open` instrucciones

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Ocultar las representaciones de las uniones discriminadas de API compatibles binarias si es probable que evolucione el diseño de estos tipos

Tipos de uniones se basan en F # coincidencia formularios para un modelo de programación conciso. Como se mencionó anteriormente, debe evitar revelar las representaciones de datos concreta si es probable que evolucione el diseño de estos tipos.

Por ejemplo, se puede ocultar la representación de una unión discriminada con una declaración interna o privada, o mediante un archivo de signatura.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Si revelan las uniones discriminadas forma indiscriminada, le resultará difícil de versión de la biblioteca sin interrumpir el código de usuario. En su lugar, considere la posibilidad de que revelen uno o varios modelos activos para permitir a través de los valores de su tipo de coincidencia de patrones.

Modelos activos proporcionan una alternativa para proporcionar a los consumidores de F # al tiempo que evita exponer directamente los tipos de unión de F # de coincidencia de patrones.

### <a name="inline-functions-and-member-constraints"></a>Las funciones insertadas y restricciones de miembro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definir los algoritmos genéricos numéricos mediante las funciones insertadas con restricciones de miembro implícito y tipos genéricos resueltos estáticamente

Restricciones de miembro aritméticos y las restricciones de comparación de F # son un estándar para la programación en F #. Por ejemplo, considere el siguiente código:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

El tipo de esta función es como sigue:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Se trata de una función adecuada para una API pública en una biblioteca matemática.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Evite el uso de restricciones de miembro para simular las clases de tipos y pato

Es posible simular "agacha escribiendo" mediante restricciones de miembro de F #. Sin embargo, los miembros que hacen que utilizar esta propiedad no está en general se debe usar en F #-a-diseños de biblioteca de F #. Esto es porque los diseños de biblioteca en función de las restricciones implícitas no estándares o desconocidas tienden a producir código de usuario para ser inflexibles y están vinculados al patrón de un marco de trabajo concreto.

Además, hay muchas posibilidades de que un uso intensivo de restricciones de miembro de esta manera puede dar lugar a tiempos de compilación muy largos.

### <a name="operator-definitions"></a>Definiciones de operador

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evite la definición de operadores simbólicos personalizados

Operadores personalizados son esenciales en algunas situaciones y son muy útiles notacionales dispositivos dentro de un gran bloque de código de implementación. Para los nuevos usuarios de una biblioteca, las funciones con nombre suelen ser más fáciles de usar. Además, operadores simbólicos personalizados pueden ser difíciles de documento y usuarios les resulta más difícil buscar ayuda sobre operadores, debido a las limitaciones existentes en los motores de IDE y búsqueda.

Como resultado, es mejor para su funcionalidad como miembros y funciones con nombre de la publicación y además exponer operadores para esta funcionalidad solo si el beneficio notacional superan a la documentación y el costo de cognitive de disponer de ellos.

### <a name="units-of-measure"></a>Unidades de medida

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Usar cuidadosamente las unidades de medida de seguridad de tipos se ha agregado código de F #

Información adicional de escritura para las unidades de medida se borra cuando se ven por otros lenguajes. NET. Tenga en cuenta que reflexión, herramientas y componentes .NET verán tipos sans unidades. Por ejemplo, verá los consumidores de C# `float` lugar `float<kg>`.

### <a name="type-abbreviations"></a>Abreviaturas de tipo

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Utilizar con cuidado las abreviaturas de tipo para simplificar el código de F #

Reflexión, herramientas y componentes de .NET no verán los nombres abreviados para los tipos. Un uso significativo de abreviaturas de tipo también puede hacer que un dominio aparezca más complejo de lo es en realidad, lo que podría ser confuso para los consumidores.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evitar las abreviaturas de tipo para tipos públicos cuyos miembros y propiedades deben ser intrínsecamente diferentes a los que están disponibles en el tipo que se va a abreviar

En este caso, el tipo que se va a abreviar revela demasiado sobre la representación del tipo real que se está definiendo. En su lugar, considere la posibilidad de ajustar la abreviatura en un tipo de clase o una unión discriminada de caso único (o bien, cuando el rendimiento es esencial, considere el uso de un tipo de estructura para ajustar la abreviatura).

Por ejemplo, es tentador para definir un mapa múltiple como un caso especial de un mapa de F #, por ejemplo:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Sin embargo, las operaciones lógicas de notación de puntos en este tipo no son los mismos que las operaciones en un mapa: por ejemplo, es razonable que se asignan el operador de búsqueda. la lista vacía si la clave no está en el diccionario, en lugar de producir una excepción de devolución [clave].

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Directrices para las bibliotecas para su uso desde otros lenguajes de .NET

Cuando diseñe bibliotecas para su uso desde otros lenguajes. NET, es muy importante seguir el [instrucciones de diseño de bibliotecas de .NET](../../standard/design-guidelines/index.md). En este documento, estas bibliotecas se etiquetan como vainilla bibliotecas. NET, en lugar de F #-orientado a las bibliotecas que usar F # construye sin restricciones. Diseñar vainilla bibliotecas de .NET significa que proporciona las API familiares e idiomáticas coherentes con el resto de .NET Framework, ya que minimiza el uso de F #-construcciones específicas de la API pública. Las reglas se explican en las secciones siguientes.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace y el tipo de diseño (para las bibliotecas para su uso desde otros lenguajes. NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Se aplican las convenciones de nomenclatura de .NET a la API pública de los componentes

Preste especial atención al uso de abreviaturas de nombres y las directrices de mayúsculas y minúsculas. NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Usar espacios de nombres, tipos y miembros como la estructura organizativa principal para los componentes de

Todos los archivos que contiene la funcionalidad pública deben comenzar con un `namespace` declaración y las únicas entidades orientados al público en espacios de nombres deben ser tipos. No utilice los módulos de F #.

Utilice los módulos que no sean públicos para contener código de implementación, utilidad tipos y funciones de utilidad.

Los tipos estáticos debe preferirse a través de módulos, ya que permiten para la futura evolución de la API para usar la sobrecarga y otros conceptos de diseño de API de .NET que no se pueden usar dentro de los módulos de F #.

Por ejemplo, en lugar de la API pública de la siguiente:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

Tenga en cuenta en su lugar:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Usar tipos de registro de F # en las API de .NET de vainilla si el diseño de los tipos no evolucionan

Tipos de registro de F # se compilan en una clase .NET simple. Estos son adecuados para algunos tipos simples y estables en las API. Puede utilizar el `[<NoEquality>]` y `[<NoComparison>]` atributos para suprimir la generación automática de interfaces. También evite usar campos de registro mutable de vainilla las API de .NET como estos expone un campo público. Siempre tenga en cuenta si una clase proporcionaría una opción más flexible para la futura evolución de la API.

Por ejemplo, el siguiente código de F # expone la API pública a un consumidor de C#:

F #:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Ocultar la representación de tipos de unión de F # de vainilla las API de .NET

Tipos de unión de F # no se usan habitualmente en los límites del componente, incluso para F #-a-F # de codificación. Son un dispositivo de implementación excelente cuando se usa internamente en componentes y bibliotecas.

Al diseñar una API de .NET de vainilla, considere la posibilidad de ocultar la representación de un tipo de unión mediante una declaración privada o un archivo de signatura.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

También puede aumentar los tipos que usan una representación de unión internamente con miembros para proporcionar un deseado. API de NET orientadas.

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Diseño de interfaz gráfica de usuario y otros componentes con los patrones de diseño de framework

Hay muchos marcos en. NET, como ASP.NET, WPF y WinForms. Si va a diseñar los componentes para su uso en estos marcos de trabajo, se deben usar las convenciones de nomenclatura y diseño para cada uno. Por ejemplo, para la programación en WPF, adopte los patrones de diseño WPF para las clases que se está diseñando. Para los modelos de programación de la interfaz de usuario, usar patrones de diseño, como los eventos y las colecciones basadas en la notificación como las que se encuentran en <xref:System.Collections.ObjectModel>.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Diseño de objeto y miembro (para las bibliotecas para su uso desde otros lenguajes. NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Usar CLIEvent (atributo) para exponer los eventos de .NET

Construir un `DelegateEvent` con específica de .NET de tipo que toma un objeto de delegado y `EventArgs` (en lugar de un `Event`, que simplemente utiliza el `FSharpHandler` tipo de forma predeterminada) para que se publican los eventos de la manera familiar para otros lenguajes. NET.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>Exponer operaciones asincrónicas, como los métodos que devuelven tareas de .NET

Las tareas se usan en .NET para representar los cálculos asincrónicos activos. Las tareas son en general menos composicional que F # `Async<T>` objetos, ya que representan tareas "ya está ejecutando" y no pueden componerse entre sí de maneras que realizar la composición paralela o que ocultar la propagación de las señales de cancelación y otros parámetros contextuales.

Sin embargo, a pesar de esto, los métodos que devuelven tareas son la representación estándar de la programación asincrónica en .NET Framework.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Con frecuencia tendrá también desea aceptar un token de cancelación explícito:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Usar tipos de delegados de .NET en lugar de tipos de función de F #

Aquí, "tipos de función de F #" significan "flecha" tipos como `int -> int`.

En lugar de esto:

```fsharp
member this.Transform(f:int->int) =
    ...
```

Haga lo siguiente:

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

El tipo de función de F # aparece como `class FSharpFunc<T,U>` para otros lenguajes. NET y es menos adecuada para las características del lenguaje y las herramientas que comprender los tipos de delegado. Al crear un método de orden superior como destino .NET Framework 3.5 o posterior, el `System.Func` y `System.Action` los delegados son las API de derechos a publicar para permitir que los desarrolladores de .NET consumir estas API de una manera de baja fricción. (Cuando el destino es .NET Framework 2.0, los tipos de delegado definido por el sistema son más limitados; considere el uso de tipos de delegado predefinido, como `System.Converter<T,U>` o definir un tipo delegado específico.)

En el otro lado, los delegados de .NET no son naturales para F #-orientado a las bibliotecas (consulte la sección siguiente sobre F #-orientado a las bibliotecas). Como resultado, es una estrategia de implementación común al desarrollar métodos de orden superior para vainilla bibliotecas de .NET crear toda la implementación mediante los tipos de función de F # y, a continuación, crear la API pública de uso de delegados como una fachada delgada encima real F # implementación de.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Usar el patrón de TryGetValue en lugar de devolver los valores de opción de F # y prefiere la sobrecarga de método para tomar los valores de opción de F # como argumentos

Patrones comunes de uso para el tipo de opción de F # en las API son mejores implementado en vainilla técnicas de diseño de las API de .NET con .NET standard. En lugar de devolver un valor de opción de F #, considere el uso del tipo de valor devuelto bool además de un parámetro de salida como se muestra en el patrón "TryGetValue". Y, en lugar de tomar valores de opción de F # como parámetros, considere el uso de la sobrecarga de métodos o argumentos opcionales.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Usar la interfaz de colección .NET tipos IEnumerable\<T\> e IDictionary\<clave, valor\> para los parámetros y valores devueltos

Evite el uso de tipos de colección concretos, como matrices .NET `T[]`, tipos de F # `list<T>`, `Map<Key,Value>` y `Set<T>`, y tipos de colección concretos. NET, como `Dictionary<Key,Value>`. Las instrucciones de diseño de la biblioteca de .NET tienen buenos consejos sobre cuándo usar diversos tipos de colecciones como `IEnumerable<T>`. Algún uso de matrices (`T[]`) es aceptable en algunas circunstancias, por motivos de rendimiento. Tenga en cuenta especialmente que `seq<T>` es simplemente la F # alias de `IEnumerable<T>`, y, por tanto, a menudo es un tipo adecuado para una API de .NET de vainilla seq.

En lugar de la lista de F #:

```fsharp
member this.PrintNames(names : string list) =
    ...
```

Use las secuencias de F #:

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Usar el tipo de unidad como el único tipo de entrada de un método para definir un método de argumento de cero, o como el único tipo para definir un método que devuelve void de valor devuelto

Evitar otros usos del tipo de unidad. Estas son buenas:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

Esto es incorrecto:

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Comprobar si hay valores null en los límites de API de .NET básica

Código de implementación de F # suele tener menos valores null, debido a los patrones de diseño inmutable y restricciones de uso de literales null para los tipos de F #. Otros lenguajes de .NET a menudo usan null como valor mucha más frecuencia. Por este motivo, código F # que expone una API de .NET de vainilla debe comprobar los parámetros de null en el límite de API y evitar que estos valores fluye más profunda en el código de implementación de F #. El `isNull` función o coincidencia de patrones en el `null` se puede usar el patrón.

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

En su lugar, preferible devolver un tipo con nombre que contiene los datos agregados, o mediante los parámetros de salida para devolver varios valores. Aunque existen tuplas y las tuplas de struct en .NET (incluida la compatibilidad de lenguaje C# para las tuplas de struct), suelen no proporcionará la API ideal y esperada para desarrolladores de .NET.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Evite el uso de la currificación de parámetros

En su lugar, utilice las convenciones de llamada de .NET ``Method(arg1,arg2,…,argN)``.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Sugerencia: Si va a diseñar bibliotecas para su uso en cualquier lenguaje. NET, a continuación, hay ningún sustituto para realmente hacer algunas experimental C# y Visual Basic de programación para asegurarse de que las bibliotecas de "la frase derecha" de estos lenguajes. También puede usar herramientas como .NET Reflector y del Examinador de objetos de Visual Studio para asegurarse de que las bibliotecas y su documentación aparecen según lo esperado para los desarrolladores.

## <a name="appendix"></a>Apéndice

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Ejemplo to-end del diseño de código de F # para su uso por otros lenguajes de .NET

Tenga en cuenta la siguiente clase:

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

El tipo F # deducido de esta clase es como sigue:

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

Echemos un vistazo a cómo aparece este tipo de F # para un programador que use otro lenguaje. NET. Por ejemplo, aproximado de C# "firma" es como sigue:

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

Hay algunos puntos importantes a tener en cuenta acerca de cómo F # representa construcciones aquí. Por ejemplo:

* Se ha conservado los metadatos como nombres de argumento.

* Métodos de F # que toman dos argumentos se convierten en métodos de C# que toman dos argumentos.

* Las funciones y las listas se convierten en las referencias a los tipos correspondientes en la biblioteca de F #.

El código siguiente muestra cómo ajustar este código para tener todo esto en cuenta.

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

El tipo F # inferido del código es como sigue:

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

La firma de C# ahora es como sigue:

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

Las correcciones realizan preparar este tipo para su uso como parte de una biblioteca básica de .NET son los siguientes:

* Ajustar varios nombres: `Point1`, `n`, `l`, y `f` se convirtió en `RadialPoint`, `count`, `factor`, y `transform`, respectivamente.

* Usa un tipo de valor devuelto de `seq<RadialPoint>` en lugar de `RadialPoint list` cambiando una construcción de la lista mediante `[ ... ]` a una construcción de secuencia mediante `IEnumerable<RadialPoint>`.

* Usa el tipo de delegado .NET `System.Func` en lugar de un tipo de función de F #.

Esto facilita mucho más atractiva para consumir en código C#.
