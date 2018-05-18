---
title: 'Instrucciones de diseño del componente de F #'
description: 'Obtenga información acerca de las instrucciones para escribir componentes de F # previstos para su uso por otros llamadores.'
ms.date: 05/14/2018
ms.openlocfilehash: 7859baac76be01b2cfbdc8602b6cc417cfe5106f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="f-component-design-guidelines"></a>Instrucciones de diseño del componente de F #

Este documento es un conjunto de instrucciones de diseño del componente de F # de programación, tomando como base la F # componente directrices de diseño, v14, Microsoft Research, y [otra versión](https://fsharp.org/specs/component-design-guidelines/) originalmente seleccionada y mantiene la base de Software de F #.

Este documento se supone que está familiarizado con la programación en F #. Muchas gracias a la Comunidad de F # para obtener comentarios útiles en diferentes versiones de esta guía y sus contribuciones.

## <a name="overview"></a>Información general

Este documento se examina algunos de los problemas relacionados con el diseño del componente de F # y la codificación. Un componente puede dar lugar a cualquiera de las siguientes acciones:

* Una capa en el proyecto de F # que tiene los consumidores externos dentro de ese proyecto.
* Una biblioteca prevista para su uso en código de F # en los límites del ensamblado.
* Una biblioteca prevista para su uso por cualquier lenguaje .NET Framework en los límites del ensamblado.
* Una biblioteca destinada para su distribución a través de un repositorio de paquetes, como [NuGet](https://nuget.org).

Siguen técnicas descritas en este artículo la [cinco principios de buen código F #](index.md#five-principles-of-good-f-code)y, por tanto, usar ambos funcional y objeto de programación según corresponda.

Independientemente de la metodología, el Diseñador de componentes y la biblioteca enfrenta una serie de problemas prácticas y explicaciones al intentar crear una API que sea más fácilmente utilizable por los desarrolladores. Una aplicación muy consciente de la [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/index.md) se dirigen hacia la creación de un conjunto coherente de API que forman agradables a consumir.

## <a name="general-guidelines"></a>Instrucciones generales

Hay algunas directrices universales que se aplican a las bibliotecas de F #, sin tener en cuenta el público previsto para la biblioteca.

### <a name="learn-the-net-library-design-guidelines"></a>Obtenga información acerca de las instrucciones de diseño de la biblioteca de .NET

Independientemente del tipo de F # codificación está realizando, es útil tener conocimientos prácticos de los [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/index.md). Mayoría otros F # y los programadores de .NET se estar familiarizado con estas instrucciones y esperar que el código de .NET para que se ajuste a ellos.

Las instrucciones de diseño de la biblioteca de .NET proporcionan orientación general sobre nomenclatura, diseño de clases y interfaces, diseño de miembros (propiedades, métodos, eventos, etc.) y mucho más y son útil primer punto de referencia para una amplia variedad de instrucciones de diseño.

### <a name="add-xml-documentation-comments-to-your-code"></a>Agregar comentarios de documentación XML en el código

Documentación XML en las API públicas Asegúrese de que los usuarios pueden obtener gran Intellisense y Quickinfo al usar estos tipos y miembros así como documentación de creación de habilitar los archivos de la biblioteca. Consulte la [documentación XML](../language-reference/xml-documentation.md) sobre diversas etiquetas xml que pueden usarse para marcado adicional dentro de xmldoc comentarios.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

Puede usar los comentarios XML de forma abreviada (`/// comment`), o los comentarios XML estándares (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Considere el uso de archivos de firma explícitas (.fsi) de biblioteca estable y las API de componentes

Uso de archivos de firmas explícita en la biblioteca de F # proporciona un resumen conciso de la API pública, que ayuda a garantizar que se conoce la superficie pública completa de la biblioteca, así como proporciona una separación clara entre documentación público e internos detalles de la implementación. Tenga en cuenta que los archivos de firma agregan fricción ante las cambiantes de la API pública, exigiendo cambios que se realizan en los archivos de la implementación y la firma. Como resultado, archivos de signatura deben normalmente se incorpora únicamente cuando una API se convierten en ha fortalecido y ya no se espera que cambie significativamente.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Siempre siga las prácticas recomendadas para el uso de cadenas en .NET

Siga [prácticas recomendadas para el uso de cadenas en .NET](../../standard/base-types/best-practices-strings.md) instrucciones. En concreto, indicar siempre explícitamente *intención cultural* en la conversión y la comparación de cadenas (si procede).

## <a name="guidelines-for-f-facing-libraries"></a>Directrices para F #-orientada hacia el bibliotecas

Esta sección contiene recomendaciones para el desarrollo de F # pública-orientada hacia el bibliotecas; es decir, las bibliotecas de exponer las API públicas que están destinadas a ser consumidos por los desarrolladores de F #. Hay una variedad de recomendaciones de diseño de la biblioteca aplicable específicamente para F #. En ausencia de las recomendaciones específicas que van a continuación, las instrucciones de diseño de la biblioteca de .NET son las instrucciones de reserva.

### <a name="naming-conventions"></a>Convenciones de nomenclatura

#### <a name="use-net-naming-and-capitalization-conventions"></a>Utilice convenciones de nomenclatura y mayúsculas y minúsculas de .NET

En la tabla siguiente sigue las convenciones de nomenclatura y uso de mayúsculas. NET. Existen pequeñas adiciones al también incluye construcciones de F #.

| Construcción | Caso | Parte | Ejemplos | Notas |
|-----------|------|------|----------|-------|
| Tipos concretos | PascalCase | Sustantivo o adjetivo | Lista, doble, complejo | Tipos concretos son estructuras, clases, enumeraciones, delegados, registros y uniones. Aunque los nombres de tipo son tradicionalmente en minúsculas en OCaml, F # ha adoptado el esquema de nomenclatura de .NET para los tipos.
| DLL           | PascalCase |                 | Fabrikam.Core.dll |  |
| Etiquetas de unión     | PascalCase | nombre | Algunos, agregar, correcto | No utilice un prefijo en las API públicas. Utilizar opcionalmente un prefijo cuando interno, como ''' Escriba los equipos = TAlpha | TBeta | TDelta.'' ' |
| evento          | PascalCase | Verbo | ValueChanged / ValueChanging |  |
| Excepciones     | PascalCase |      | WebException | Nombre debe terminar con "Exception". |
| Campo          | PascalCase | nombre | CurrentName  | |
| Tipos de interfaz |  PascalCase | Sustantivo o adjetivo | IDisposable | Nombre debe comenzar con "I". |
| Método |  PascalCase |  Verbo | ToString | |
| Espacio de nombres | PascalCase | | Microsoft.FSharp.Core | Generalmente se utiliza `<Organization>.<Technology>[.<Subnamespace>]`, drop aunque la organización si la tecnología es independiente de la organización. |
| Parámetros | camelCase | nombre |  typeName, transformar, de intervalo | |
| permitir que los valores (internos) | camelCase o PascalCase | Nombre / verbo |  getValue, myTable |
| permitir que los valores (externo) | camelCase o PascalCase | Nombre/verbo  | List.Map, Dates.Today | valores de límite permiten a menudo son públicos al seguir los patrones de diseño funcional tradicional. Sin embargo, generalmente se utiliza PascalCase cuando el identificador se puede usar en otros lenguajes. NET. |
| Property  | PascalCase  | Sustantivo o adjetivo  | IsEndOfFile, color de fondo  | Propiedades booleanas por lo general uso y puede y debe ser afirmativa, como en IsEndOfFile, no IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Evite las abreviaturas

Las instrucciones de .NET desaconseja el uso de las abreviaturas (por ejemplo, "usar `OnButtonClick` en lugar de `OnBtnClick`"). Abreviaturas comunes, como `Async` para "Asincrónico", que se tolera. A veces se pasa por alto esta directriz para la programación funcional; Por ejemplo, `List.iter` usa una abreviatura de "repetir". Por este motivo, con abreviaturas tiende a tolerar un mayor grado de F #-a-programación en F #, pero se deben evitar en general todavía en el diseño de los componentes públicos.

#### <a name="avoid-casing-name-collisions"></a>Evitar conflictos de nombres las mayúsculas y minúsculas

Las instrucciones de .NET decir que las mayúsculas y minúsculas por sí solo no se puede usar para eliminar la ambigüedad de conflictos de nombres, ya que algunos lenguajes de cliente (por ejemplo, Visual Basic) distinguen entre mayúsculas y minúsculas.

#### <a name="use-acronyms-where-appropriate"></a>Utilice acrónimos cuando resulte apropiado

Acrónimos como XML no son las abreviaturas y se usan ampliamente en las bibliotecas de .NET en forma sin mayúsculas (Xml). Solo deben utilizarse acrónimos conocidos, ampliamente reconocidos.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Utilice PascalCase para los nombres de parámetro genérico

Utilice PascalCase para nombres de parámetro genérico en las API públicas, incluidos los de F #-orientada hacia las bibliotecas. En concreto, use nombres como `T`, `U`, `T1`, `T2` para los parámetros genéricos arbitrarios y nombres específicos tienen sentido, a continuación, en F #-orientados al público bibliotecas usen nombres como `Key`, `Value`, `Arg`(pero no por ejemplo, `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Utilizar PascalCase o camelCase para funciones públicas y valores en los módulos de F #

camelCase se utiliza para funciones públicas que están diseñadas para utilizarse sin calificar (por ejemplo, `invalidArg`) y para las funciones de colección estándar de"" (por ejemplo, List.map). En ambos de estos casos, los nombres de función actúan como palabras clave en el lenguaje.

### <a name="object-type-and-module-design"></a>Diseño de objeto, el tipo y el módulo

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Usar espacios de nombres o módulos para contener los tipos y módulos

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

* Espacios de nombres pueden abarcar varios archivos
* Espacios de nombres no pueden contener funciones de F # a menos que estén dentro de un módulo interno
* El código de cualquier módulo determinado debe estar dentro de un único archivo
* Módulos de nivel superior pueden contener funciones de F # sin necesidad de un módulo interno

La elección entre un módulo o espacio de nombres de nivel superior afecta a la forma compilada del código y, por tanto, afectará a la vista de otros lenguajes .NET su API finalmente se debe consumir fuera del código de F #.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Usar métodos y propiedades para las operaciones intrínsecas a tipos de objeto

Cuando se trabaja con objetos, es mejor para asegurarse de que se implementa funcionalidad consumible como métodos y propiedades de ese tipo.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

La mayor parte de la funcionalidad para un miembro determinado necesita no necesariamente se implementan en ese miembro, pero debe ser la pieza consumible de esa funcionalidad.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Usar las clases para encapsular el estado mutable

En F #, esto solo debe hacerse donde que estado no está ya encapsulado por otra construcción del lenguaje, como un cierre, la expresión de secuencia o el cálculo asincrónico.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Usar interfaces para agrupar las operaciones relacionadas con

Usar tipos de interfaz para representar un conjunto de operaciones. Esto es preferible a otras opciones, como las tuplas de funciones o registros de funciones.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

Prioridad para:

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

Las interfaces son conceptos de primera clase en. NET, que puede usar para lograr qué funciones normalmente le proporcionaría. Además, puede utilizarse para codificar tipos existenciales en el programa, que no puedan registros de funciones.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>Usar un módulo a las funciones de grupo que actúan en colecciones

Cuando se define un tipo de colección, considere la posibilidad de proporcionar un conjunto estándar de operaciones, como `CollectionType.map` y `CollectionType.iter`) para los nuevos tipos de colección.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Si incluye un módulo de este tipo, siga las convenciones de nomenclatura estándares para las funciones que se encuentra en FSharp.Core.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Usar un módulo a las funciones de grupo para funciones comunes canónicas, especialmente en matemáticas y bibliotecas DSL

Por ejemplo, `Microsoft.FSharp.Core.Operators` es una colección automáticamente abierta de funciones de nivel superior (como `abs` y `sin`) proporcionada por FSharp.Core.dll.

Igualmente, una biblioteca de las estadísticas podría incluir un módulo con funciones `erf` y `erfc`, donde este módulo está diseñado para que se abran explícitamente o automáticamente.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>Considere el uso de RequireQualifiedAccess y cuidadosamente aplicar atributos AutoOpen

Agregar el `[<RequireQualifiedAccess>]` atributo a un módulo indica que no se puede abrir el módulo y que las referencias a los elementos del módulo requieren explícita calificar el acceso. Por ejemplo, el `Microsoft.FSharp.Collections.List` módulo tiene este atributo.

Esto es útil cuando las funciones y los valores en el módulo tienen nombres que es probables que entran en conflicto con los nombres de otros módulos. Que necesiten acceso completo puede aumentar considerablemente el mantenimiento a largo plazo y evolvability de una biblioteca.

Agregar el `[<AutoOpen>]` atributo a un módulo significa que el módulo se abrirá cuando se abre el espacio de nombres contenedor. El `[<AutoOpen>]` también se puede aplicar el atributo a un ensamblado para indicar un módulo que se abrirá automáticamente cuando se hace referencia al ensamblado.

Por ejemplo, una biblioteca de estadísticas **MathsHeaven.Statistics** podría contener una `module MathsHeaven.Statistics.Operators` que contienen funciones `erf` y `erfc`. Es razonable marcar este módulo como `[<AutoOpen>]`. Esto significa `open MathsHeaven.Statistics` también abrirá este módulo y poner los nombres `erf` y `erfc` en el ámbito. Otra buena el uso de `[<AutoOpen>]` es para módulos que contienen métodos de extensión.

Un uso excesivo de `[<AutoOpen>]` hace que las contaminado espacios de nombres y el atributo debe utilizarse con cuidado. Para determinadas bibliotecas en dominios específicos, un uso razonable de `[<AutoOpen>]` puede dar lugar a una mejor utilización.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Considere la posibilidad de definir miembros de operador en las clases donde es adecuado usar operadores conocidos

A veces las clases se usan para crear estructuras matemáticas como vectores. Cuando el dominio que se está modelando tiene operadores conocidos, definiéndolos como miembros intrínsecos de la clase es útil.

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Esta guía se corresponde con las instrucciones generales de .NET para estos tipos. Sin embargo, puede ser importante además en F # codificaciones, ya que esto permite que estos tipos para usarse en métodos con restricciones de miembro, como List.sumBy y junto con funciones de F #.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Considere la posibilidad de usar CompiledName para proporcionar una. Nombre descriptivo de la red para otros consumidores de lenguaje de .NET

En ocasiones, puede que desee algo en un estilo de nombre para los consumidores de F # (por ejemplo, un miembro estático en minúscula para que aparezca como si fuera una función de módulo enlazada), pero tienen un estilo diferente para el nombre cuando se compila en un ensamblado. Puede usar el `[<CompiledName>]` atributo para proporcionar un estilo diferente para consumir el ensamblado de código no F #.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Mediante el uso de `[<CompiledName>]`, puede utilizar las convenciones de nomenclatura .NET para F # no los consumidores del ensamblado.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Utilizar una sobrecarga de método para las funciones de miembro, si al hacerlo consigue una API más sencilla

Sobrecarga de métodos es una herramienta eficaz para simplificar una API que quizás deba realizar una funcionalidad similar, pero con argumentos u opciones diferentes.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

En F #, es más habitual de sobrecarga en el número de argumentos en lugar de tipos de argumentos.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Ocultar las representaciones de registro y tipos de unión si el diseño de estos tipos tiene susceptibles de evolucionar

Evitar revelar representaciones concretas de objetos. Por ejemplo, la representación concreta de <xref:System.DateTime> por la API externa, pública del diseño de biblioteca de .NET no se revelen los valores. En tiempo de ejecución, Common Language Runtime sabe la implementación confirma que se utilizará a lo largo de la ejecución. Sin embargo, código compilado no propio recoge las dependencias de la representación en forma concreta.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Evite el uso de la herencia de implementación para la extensibilidad

En F #, apenas se usa la herencia de implementación. Además, las jerarquías de herencia son a menudo complejo y difícil de modificar cuando llegan los nuevos requisitos. Implementación de la herencia sigue existiendo en F # para la compatibilidad y raros casos donde es la mejor solución para un problema, pero técnicas alternativas deben obtenerse en los programas de F # cuando se diseña para polimorfismo, como la implementación de interfaz.

### <a name="function-and-member-signatures"></a>Firmas de función y miembro

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Tuplas de uso para los valores devueltos cuando se devuelve un número reducido de varios valores no relacionados

Este es un buen ejemplo del uso de una tupla en un tipo de valor devuelto:

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

Para devolver los tipos que contiene muchos componentes o, si los componentes están relacionadas con una sola entidad de identificación, considere la posibilidad de usar un tipo con nombre en lugar de una tupla.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Use `Async<T>` para programación asincrónica en los límites de API de F #

Si hay una operación sincrónica correspondiente denominada `Operation` que devuelve un `T`, a continuación, la operación asincrónica debe denominarse `AsyncOperation` si devuelve `Async<T>` o `OperationAsync` si devuelve `Task<T>`. Los tipos utilizados frecuentemente de .NET que exponen métodos Begin/End, considere la posibilidad de usar `Async.FromBeginEnd` para escribir métodos de extensión como una fachada para proporcionar el F # async modelo de programación a las API de .NET.

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

Las excepciones son excepcionales en. NET; es decir, no deben ocurrir con frecuencia en tiempo de ejecución. Cuando lo hacen, es útil la información que contienen. Las excepciones son un núcleo de primera clase concepto de. NET; TI, por lo que se indica a continuación que corresponda de la aplicación de las excepciones que debe usarse como parte del diseño de la interfaz de un componente.

#### <a name="follow-the-net-guidelines-for-exceptions"></a>Siga las instrucciones de .NET para las excepciones

El [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/exceptions.md) ofrece excelente consejos sobre el uso de las excepciones producidas en el contexto de toda la programación. NET. Algunas de estas instrucciones son las siguientes:

* No uses excepciones para el flujo de control normal. Aunque esta técnica suele utilizarse en lenguajes como OCaml, es propensa a errores y puede ser ineficaz en. NET. En su lugar, considere la posibilidad de devolver un `None` valor para indicar un error que es común o se espera algo de la opción.

* Documente las excepciones producidas por los componentes cuando se utiliza una función de forma incorrecta.

* Siempre que sea posible, emplear excepciones existentes de los espacios de nombres del sistema. Evitar <xref:System.ApplicationException>, aunque.

* No genere <xref:System.Exception> cuando escaparán al código de usuario. Esto incluye evitar el uso de `failwith`, `failwithf`, que son funciones útiles para su uso en secuencias de comandos y código en desarrollo, pero se deben quitar del código de biblioteca de F # en favor de producir un tipo de excepción más específico.

* Use `nullArg`, `invalidArg`, y `invalidOp` como mecanismo para producir <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, y <xref:System.InvalidOperationException> cuando sea necesario.

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a>Considere el uso de valores de las opciones para los tipos de valor devueltos cuando no hay una situación excepcional

El método de .NET a las excepciones es que debe ser "excepcionales;" es decir, que ocurran relativamente con poca frecuencia. Sin embargo, algunas operaciones (por ejemplo, la búsqueda de una tabla) pueden producir errores con frecuencia. Los valores de opción de F # son una excelente forma para representar los tipos devueltos de estas operaciones. Estas operaciones convencionalmente empiezan con el prefijo de nombre "try":

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a>Miembros de extensión

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Aplicar cuidadosamente los miembros de extensión de F # en F #-a-F # componentes

Miembros de extensión de F # normalmente deben usarse solo para las operaciones que se encuentran en el cierre de operaciones intrínsecos asociado a un tipo en la mayoría de los modos de uso. Un uso habitual consiste en proporcionan API que son más idiomáticas a F # para varios tipos. NET:

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

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Usar uniones discriminadas en lugar de jerarquías de clases para los datos de estructura de árbol

Las estructuras de árbol son definidos de forma recursiva. Esto es difícil con herencia, pero elegante con uniones discriminadas.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Que representa los datos en forma de árbol con uniones discriminadas también permite beneficiarse de exhaustiveness de coincidencia de patrones.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Use `[<RequireQualifiedAccess>]` en tipos de unión cuyos nombres casos no son lo suficientemente exclusivos

Es probable que se encuentre en un dominio donde el mismo nombre es el nombre más adecuado para realizar diferentes tareas, como casos de unión discriminada. Puede usar `[<RequireQualifiedAccess>]` para eliminar la ambigüedad de los nombres de casos con el fin de evitar que se produzca errores confusos debido al sombreado depende de la ordenación de `open` instrucciones

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Ocultar las representaciones de las uniones discriminadas para las API compatibles binarias si el diseño de estos tipos tiene susceptibles de evolucionar

Tipos de uniones se basan en F # coincidencia formularios para un modelo de programación conciso. Como se mencionó anteriormente, debe evitar revelar representaciones de datos concretos si es probable que evolucione el diseño de estos tipos.

Por ejemplo, se puede ocultar la representación de una unión discriminada con una declaración privada o interna, o mediante un archivo de signatura.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Si revelan uniones discriminadas forma indiscriminada, quizá le resulte difícil versión la biblioteca sin interrumpir el código de usuario. En su lugar, considere la posibilidad de que revelen uno o varios modelos activos para permitir la coincidencia sobre los valores de los tipos de patrones.

Modelos activos proporcionan un mecanismo alternativo para proporcionar a los consumidores de F # con el patrón de búsqueda de coincidencias al evitar exponer directamente los tipos de unión de F #.

### <a name="inline-functions-and-member-constraints"></a>Las funciones insertadas y las restricciones de miembro

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definir los algoritmos numéricos genéricos mediante funciones inline con restricciones de miembro implícito y tipos genéricos resueltos estáticamente

Las restricciones de miembro aritméticos y las restricciones de comparación de F # son un estándar para la programación de F #. Por ejemplo, considere el siguiente código:

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

Se trata de una función adecuada para una API pública en una biblioteca de matemática.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Evite el uso de restricciones de miembro para simular las clases de tipos y duck escribiendo

Es posible simular "agacha escribiendo" mediante las restricciones de miembro de F #. Sin embargo, los miembros que hacen que utilizar esta propiedad no está en general se utiliza en F #-a-diseños de biblioteca de F #. Esto es porque los diseños de biblioteca en función de las restricciones implícitas desconocidas o no estándares tienden a hacer que el código de usuario se conviertan en inflexibles y ligada al patrón de un marco de trabajo concreto.

Además, hay una gran probabilidad de que un uso intensivo de las restricciones de miembro de esta manera puede dar lugar a tiempos de compilación mucho.

### <a name="operator-definitions"></a>Definiciones de operador

#### <a name="avoid-defining-custom-symbolic-operators"></a>Evite la definición de operadores simbólicos personalizados

Operadores personalizados son esenciales en algunas situaciones y dispositivos notacionales muy útiles dentro de un cuerpo grande del código de implementación. Para los nuevos usuarios de una biblioteca, funciones con nombre son a menudo más fáciles de usar. Además, operadores simbólicos personalizados pueden ser difíciles de documento y usuarios les resulta más difícil buscar ayuda sobre operadores, debido a las limitaciones existentes en los motores de IDE y búsqueda.

Como resultado, es mejor publicar su funcionalidad como funciones con nombre y miembros y además exponer operadores para esta funcionalidad solo si el beneficio notacional superan el costo cognitivo indica que existen y documentación.

### <a name="units-of-measure"></a>Unidades de medida

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Detenidamente utilizar unidades de medida de seguridad de tipos agregados en código de F #

Información de tipo adicional para unidades de medida se borra cuando se ve por otros lenguajes. NET. Tenga en cuenta que reflexión, herramientas y componentes .NET verán tipos de redes SAN unidades. Por ejemplo, verá los consumidores de C# `float` en lugar de `float<kg>`.

### <a name="type-abbreviations"></a>Abreviaturas de tipo

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Utilizar con cuidado las abreviaturas de tipo para simplificar el código de F #

Reflexión, herramientas y componentes de .NET no podrán ver los nombres abreviados para los tipos. Un uso significativo de abreviaturas de tipo también puede hacer que un dominio aparezca más complejo de lo es realmente, lo que podría confundir a los consumidores.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Evite las abreviaturas de tipo para los tipos públicos deben intrínsecamente diferentes a los que están disponibles en el tipo que se va a abreviar cuyos miembros y propiedades

En este caso, el tipo que se va a abreviar revela demasiado sobre la representación del tipo real que se está definiendo. En su lugar, considere la posibilidad de ajustar la abreviatura en un tipo de clase o una unión discriminada de caso único (o bien, cuando el rendimiento es fundamental, considere el uso de un tipo de estructura que va a contener la abreviatura).

Por ejemplo, es tentador para definir una asignación múltiple como un caso especial de un mapa de F #, por ejemplo:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Sin embargo, las operaciones lógicas de notación de puntos de este tipo no son los mismos que las operaciones en un mapa: por ejemplo, resulta razonable de que el operador de búsqueda están asignados. [clave] devuelve la lista vacía si la clave no está en el diccionario, en lugar de cuando se genera una excepción.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Directrices para las bibliotecas para su uso desde otros lenguajes de .NET

Cuando diseñe bibliotecas para usarlas en otros lenguajes. NET, es importante cumplir con la [instrucciones de diseño de biblioteca de .NET](../../standard/design-guidelines/index.md). En este documento, estas bibliotecas se etiquetan como vainilla bibliotecas de. NET, en lugar de F #-orientada hacia las bibliotecas que usen F # construye sin restricciones. Diseñar vainilla bibliotecas de .NET significa proporciona las API conocidas e idiomáticas coherentes con el resto de .NET Framework, pues minimiza el uso de F #-construcciones específicas de la API pública. Las reglas se explican en las secciones siguientes.

### <a name="namespace-and-type-sesign-for-libraries-for-use-from-other-net-languages"></a>Sesign Namespace y el tipo (para las bibliotecas para su uso desde otros lenguajes. NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Las convenciones de nomenclatura de .NET se aplican a la API pública de los componentes

Preste especial atención al uso de abreviaturas de nombres y las directrices de uso de mayúsculas. NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Usar espacios de nombres, tipos y miembros como la estructura organizativa principal para los componentes de

Todos los archivos que contiene la funcionalidad pública deben comenzar por un `namespace` declaración y las únicas entidades orientados al público en espacios de nombres deben ser tipos. No utilice los módulos de F #.

Utilizar módulos de no públicos para contener código de implementación, utilidad tipos y funciones de utilidad.

Los tipos estáticos debe preferirse sobre módulos, ya que permiten para la futura evolución de la API para usar la sobrecarga y otros conceptos de diseño de API de .NET que no se pueden usar dentro de los módulos de F #.

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

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Usar tipos de registro de F # en las API de .NET de vainilla si el diseño de los tipos no evolucionar

Tipos de registro de F # se compilan en una clase simple de. NET. Estos son idóneos para algunos tipos simples, estables en las API. Puede utilizar el `[<NoEquality>]` y `[<NoComparison>]` atributos para suprimir la generación automática de interfaces. Además, evite usar campos de registro mutable de vainilla las API de .NET como estos expone un campo público. Siempre tenga en cuenta si una clase proporcionaría una opción más flexible para la futura evolución de la API.

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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Ocultar la representación de tipos de unión de F # en las API de .NET de vainilla

Tipos de unión de F # no se usan habitualmente en los límites del componente, incluso para F #-a-F # de codificación. Son un dispositivo de implementación excelente cuando se utiliza internamente en componentes y bibliotecas.

Al diseñar una API de .NET de vainilla, considere la posibilidad de ocultar la representación de un tipo de unión mediante una declaración privada o un archivo de signatura.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

También puede aumentar los tipos que usan una representación en forma de unión internamente con miembros para proporcionar un deseado. API de NET orientado.

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Diseño de interfaz gráfica de usuario y otros componentes por medio de los patrones de diseño de framework

Hay muchos marcos de trabajo diferentes dentro de. NET, como formularios Windows Forms, WPF y ASP.NET. Convenciones de nomenclatura y diseño para cada uno de ellos deben utilizarse si va a diseñar componentes para su uso en estos marcos de trabajo. Por ejemplo, para la programación en WPF, adopte patrones de diseño WPF para las clases que se está diseñando. Para los modelos de programación de la interfaz de usuario, utilizar modelos de diseño como los eventos y colecciones basadas en notificaciones como los que se encuentran en <xref:System.Collections.ObjectModel>.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Diseño de objeto y el miembro (para las bibliotecas para su uso desde otros lenguajes. NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Usar CLIEvent (atributo) para exponer los eventos de .NET

Construir un `DelegateEvent` con .NET específicos de tipo que toma un objeto de delegado y `EventArgs` (en lugar de un `Event`, que simplemente utiliza el `FSharpHandler` tipo de forma predeterminada) para que los eventos se publican en la forma familiar de otros lenguajes. NET.

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

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>Exponer operaciones asincrónicas como métodos que devuelven las tareas de .NET

Las tareas se usan en .NET para representar los cálculos asincrónicos activos. Las tareas son en general menos composicional que F # `Async<T>` objetos, ya que representan tareas "ya está ejecutando" y no pueden estar compuestos juntos de forma que realizar la composición paralelo o que ocultar la propagación de señales de cancelación y otros parámetros contextuales.

Sin embargo, a pesar de ello, los métodos que devuelven las tareas son la representación estándar de la programación asincrónica en .NET.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Que se van a menudo también va a aceptar un token de cancelación explícita:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Usar tipos de delegado de .NET en lugar de tipos de función de F #

Aquí "tipos de función de F #" significan que los tipos de "flecha" como `int -> int`.

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

El tipo de función de F # aparece como `class FSharpFunc<T,U>` a otros lenguajes. NET y es menos adecuado para las características del lenguaje y herramientas que entender los tipos de delegado. Al crear un método de orden superior como destino .NET Framework 3.5 o superior, el `System.Func` y `System.Action` los delegados son las API derecho a publicar para permitir que los desarrolladores de .NET usar estas API en forma de baja fricción. (Cuando el destino es .NET Framework 2.0, los tipos de delegado definido por el sistema son más limitados; considere el uso de los tipos de delegado predefinido, como `System.Converter<T,U>` o definir un tipo delegado específico.)

En el otro lado, los delegados de .NET no son naturales para F #-orientada hacia el bibliotecas (vea la sección siguiente sobre F #-orientada hacia el bibliotecas). Como resultado, una estrategia de implementación habitual al desarrollar métodos de orden superior para las bibliotecas de .NET vainilla es cree todas la implementación mediante los tipos de función de F # y, a continuación, la API pública mediante delegados como una fachada fina sobre la real de F # implementación de.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Usar el patrón TryGetValue en lugar de devolver los valores de opción de F # y prefiere sobrecargar el método que toma los valores de opción de F # como argumentos

Patrones comunes de uso para el tipo de opción de F # en las API son mejores implementado en vainilla técnicas de diseño de las API de .NET con .NET estándar. En lugar de devolver un valor de opción de F #, considere la posibilidad de usar el tipo de valor devuelto bool suma un parámetro de salida como se muestra en el patrón "TryGetValue". Y, en lugar de tomar valores de opción de F # como parámetros, considere el uso de la sobrecarga de métodos o argumentos opcionales.

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Utilice la interfaz de colección de .NET tipos IEnumerable\<T\> y IDictionary\<clave, valor\> para parámetros y valores devueltos

Evite el uso de tipos de colección concretos, como matrices de .NET `T[]`, tipos de F # `list<T>`, `Map<Key,Value>` y `Set<T>`, y tipos de colección concretos. NET, como `Dictionary<Key,Value>`. Las instrucciones de diseño de la biblioteca de .NET tienen un buen consejo acerca de cuándo se utilizan varios tipos de colección como `IEnumerable<T>`. Algunos uso de matrices (`T[]`) es aceptable en algunos casos, por motivos de rendimiento. Tenga en cuenta especialmente que `seq<T>` es simplemente la F # alias de `IEnumerable<T>`, y, por tanto, a menudo es un tipo adecuado para una API de .NET de vainilla seq.

En lugar de F # listas:

```fsharp
member this.PrintNames(names : string list) =
    ...
```

Usar secuencias de F #:

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Utilice el tipo de unidad como el único tipo de entrada de un método para definir un método de argumento de cero, o como el único tipo para definir un método que devuelve void de valor devuelto

Evite otros usos del tipo de unidad. Se trata de un buen:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

Esto es incorrecto:

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Comprobar si hay valores null en vainilla límites de API de .NET

Código de implementación de F # suele tener menos valores null, debido a los patrones de diseño inmutable y las restricciones en el uso de los literales null para tipos de F #. Otros lenguajes de .NET a menudo utilizan null como un valor mucha más frecuencia. Por este motivo, código de F # que expone una API de .NET de vainilla debe comprobar los parámetros si hay valores null en el límite de API y evitar que estos valores fluyendo más profunda en el código de implementación de F #. El `isNull` función o coincidencia de patrones en el `null` puede utilizar el modelo.

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

En su lugar, preferible devolver un tipo con nombre que contiene los datos agregados o usar los parámetros de salida para devolver varios valores. Si bien existen tuplas y struct tuplas en .NET (incluida la compatibilidad de lenguaje C# para struct tuplas), con mayor frecuencia no proporcionará la API ideal y esperada para los desarrolladores de .NET.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Evite el uso de la currificación de parámetros

En su lugar, use .NET convenciones de llamada ``Method(arg1,arg2,…,argN)``.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Sugerencia: Si está diseñando bibliotecas para usarlas desde cualquier lenguaje. NET, a continuación, no hay ningún sustituto para hacer realidad algunos experimental C# y Visual Basic de programación para asegurarse de que las bibliotecas "apariencia derecha" de estos lenguajes. También puede usar herramientas como .NET Reflector y el Examinador de objetos de Visual Studio para asegurarse de que su documentación y las bibliotecas de aparecen como se esperaba a los desarrolladores.

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

¡Eche un vistazo a cómo aparece este tipo de F # para un programador que use otro lenguaje. NET. Por ejemplo, aproximado C# "firma" es como sigue:

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

Hay algunas cuestiones importantes deben tener en cuenta cómo F # representa construcciones aquí. Por ejemplo:

* Se ha conservado los metadatos como nombres de argumento.

* F # métodos que toman dos argumentos se convierten en métodos de C# que toman dos argumentos.

* Las funciones y las listas se convierten en las referencias a los tipos correspondientes en la biblioteca de F #.

El código siguiente muestra cómo ajustar este código para aprovechar todo esto en cuenta.

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

El tipo F # deducido del código es como sigue:

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

Las correcciones realizan preparar este tipo para su uso como parte de una biblioteca .NET vainilla son los siguientes:

* Ajustar varios nombres: `Point1`, `n`, `l`, y `f` pasara a ser `RadialPoint`, `count`, `factor`, y `transform`, respectivamente.

* Usa un tipo de valor devuelto de `seq<RadialPoint>` en lugar de `RadialPoint list` cambiando una construcción de lista mediante `[ ... ]` a una secuencia de la construcción utilizando `IEnumerable<RadialPoint>`.

* Usa el tipo de delegado .NET `System.Func` en lugar de un tipo de función de F #.

Esto hace mucho más adecuada consumir en código C#.
