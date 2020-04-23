---
title: Instrucciones de formato de código de F#
description: Obtenga información sobre las directrices para dar formato al código de F.
ms.date: 11/04/2019
ms.openlocfilehash: dd48380a90ee92b2c1edaaabc116fa1cd8010390
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102494"
---
# <a name="f-code-formatting-guidelines"></a>Instrucciones de formato de código de F#

En este artículo se ofrecen directrices sobre cómo dar formato al código para que el código de F es:

* Más legible
* De acuerdo con las convenciones aplicadas por las herramientas de formato en Visual Studio y otros editores
* Similar a otro código en línea

Estas directrices se basan en una guía completa de las [convenciones](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) de formato de F de [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Reglas generales para la sangría

De forma predeterminada, F- utiliza espacios en blanco significativos. Las siguientes pautas están destinadas a proporcionar orientación sobre cómo hacer malabares con algunos desafíos que esto puede imponer.

### <a name="using-spaces"></a>Uso de espacios

Cuando se requiere sangría, debe utilizar espacios, no tabulaciones. Se requiere al menos un espacio. Su organización puede crear estándares de codificación para especificar el número de espacios que se utilizarán para la sangría; dos, tres o cuatro espacios de sangría en cada nivel donde se produce la sangría es típico.

**Recomendamos cuatro espacios por sangría.**

Dicho esto, la sangría de los programas es un asunto subjetivo. Las variaciones están bien, pero la primera regla que debe seguir es la coherencia de la *sangría.* Elija un estilo de sangría generalmente aceptado y utilícelo sistemáticamente en todo el código base.

## <a name="formatting-white-space"></a>Formato de espacios en blanco

F es sensible al espacio en blanco. Aunque la mayoría de la semántica del espacio en blanco está cubierta por una sangría adecuada, hay algunas otras cosas a considerar.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Operadores de formato en expresiones aritméticas

Utilice siempre espacios en blanco alrededor de expresiones aritméticas binarias:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Los `-` operadores unarios siempre deben ir seguidos inmediatamente por el valor que están negando:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Agregar un carácter de `-` espacio en blanco después del operador puede llevar a confusión para otros.

En resumen, es importante:

* Operadores binarios envolventes con espacio en blanco
* Nunca tenga un espacio en blanco final después de un operador unario

La directriz del operador aritmético binario es especialmente importante. Si no se `-` rodea un operador binario, cuando se combina con ciertas opciones de formato, podría conducir a interpretarlo como unario `-`.

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Rodee una definición de operador personalizada con espacios en blanco

Utilice siempre espacios en blanco para rodear una definición de operador:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Para cualquier operador personalizado `*` que comience con y que tenga más de un carácter, debe agregar un espacio en blanco al principio de la definición para evitar una ambiguedad del compilador. Por este caso, se recomienda simplemente rodear las definiciones de todos los operadores con un único carácter de espacio en blanco.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Flechas de parámetros de función envolvente con espacio en blanco

Al definir la firma de una función, utilice un espacio en blanco alrededor del `->` símbolo:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Argumentos de función envolvente con espacio en blanco

Al definir una función, utilice espacios en blanco alrededor de cada argumento.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a>Coloque los parámetros en una nueva línea para las definiciones de miembros largos

Si tiene una definición de miembro muy larga, coloque los parámetros en nuevas líneas y indentelas un ámbito.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

Esto también se aplica a los constructores:

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>Anotaciones de tipo

#### <a name="right-pad-function-argument-type-annotations"></a>Anotaciones de tipo de argumento de función del botón derecho

Al definir argumentos con anotaciones de `:` tipo, utilice el espacio en blanco después del símbolo:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Anotaciones de tipo de valor devuelto envolvente con espacio en blanco

En una función enlazada a let o anotación de tipo de valor `:` (tipo de valor devuelto en el caso de una función), utilice el espacio en blanco antes y después del símbolo:

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>Formato de líneas en blanco

* Separe las definiciones de clase y función de nivel superior con dos líneas en blanco.
* Las definiciones de método dentro de una clase están separadas por una sola línea en blanco.
* Se pueden utilizar líneas en blanco adicionales (con moderación) para separar grupos de funciones relacionadas. Las líneas en blanco se pueden omitir entre un montón de líneas de una (por ejemplo, un conjunto de implementaciones ficticias).
* Utilice líneas en blanco en las funciones, con moderación, para indicar secciones lógicas.

## <a name="formatting-comments"></a>Formato de comentarios

Por lo general, prefiere varios comentarios de doble barra diagonal a los comentarios de bloque de estilo ML.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Los comentarios en línea deben capitalizar la primera letra.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenciones de nomenclatura

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Utilice camelCase para funciones y valores enlazados a clases, enlazados a expresiones y enlazados a patrones

Es común y aceptado estilo de F - para usar camelCase para todos los nombres enlazados como variables locales o en coincidencias de patrones y definiciones de función.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Las funciones enlazadas localmente en las clases también deben usar camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Utilice camelCase para funciones públicas enlazadas a módulos

Cuando una función enlazada a un módulo forma parte de una API pública, debe utilizar camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Utilice camelCase para funciones y valores internos y privados enlazados a módulos

Utilice camelCase para valores enlazados a módulos privados, incluidos los siguientes:

* Funciones ad hoc en scripts

* Valores que componen la implementación interna de un módulo o tipo

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Utilice camelCase para los parámetros

Todos los parámetros deben usar camelCase de acuerdo con las convenciones de nomenclatura de .NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Utilice PascalCase para módulos

Todos los módulos (de nivel superior, internos, privados, anidados) deben utilizar PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Utilice PascalCase para declaraciones de tipo, miembros y etiquetas

Las clases, interfaces, estructuras, enumeraciones, delegados, registros y uniones discriminadas deben denominarse con PascalCase. Los miembros dentro de tipos y etiquetas para registros y uniones discriminadas también deben usar PascalCase.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Utilice PascalCase para construcciones intrínsecas a .NET

Los espacios de nombres, excepciones, eventos y nombres de proyecto/proyectos`.dll` también deben usar PascalCase. Esto no solo hace que el consumo de otros lenguajes .NET se sienta más natural para los consumidores, sino que también es coherente con las convenciones de nomenclatura de .NET que es probable que encuentre.

### <a name="avoid-underscores-in-names"></a>Evite los guiones bajos en los nombres

Históricamente, algunas bibliotecas de F - han utilizado guiones bajos en los nombres. Sin embargo, esto ya no se acepta ampliamente, en parte porque entra en conflicto con las convenciones de nomenclatura de .NET. Dicho esto, algunos programadores de F - utilizan subrayados en gran medida, en parte por razones históricas, y la tolerancia y el respeto es importante. Sin embargo, ten en cuenta que el estilo a menudo no es del agrado por otros que tienen la opción de usarlo.

Una excepción incluye la interoperación con componentes nativos, donde los guiones bajos son comunes.

### <a name="use-standard-f-operators"></a>Utilice operadores estándar de F -

Los siguientes operadores se definen en la biblioteca estándar de F y se deben usar en lugar de definir equivalentes. Se recomienda el uso de estos operadores, ya que tiende a hacer que el código sea más legible e idiomático. Los desarrolladores con experiencia en OCaml u otro lenguaje de programación funcional pueden estar acostumbrados a diferentes modismos. En la lista siguiente se resumen los operadores de F.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Utilice la sintaxis`Foo<T>`de prefijo para genéricos`T Foo`( ) en preferencia a la sintaxis de postfijo ( )

El estilo de valor de ML de postfijo de `int list`los tipos genéricos de patrón `list<int>`(por ejemplo, ) como el estilo de .NET del prefijo (por ejemplo, ). Prefiere el estilo .NET, excepto para cinco tipos específicos:

1. Para las listas de F, `int list` utilice `list<int>`el formulario de postfijo: en lugar de .
2. Para Opciones de F, utilice `int option` el `option<int>`formulario de postfijo: en lugar de .
3. Para Opciones de valor de F, `int voption` utilice `voption<int>`el formulario de postfijo: en lugar de .
4. Para las matrices de F, utilice `int[]` el `int array` `array<int>`nombre sintáctico en lugar de o .
5. Para Celdas `int ref` de `ref<int>` referencia, utilice en lugar de o `Ref<int>`.

Para todos los demás tipos, utilice el formulario de prefijo.

## <a name="formatting-tuples"></a>Tuplas de formato

Una creación de instancias de tupla debe ser entreparénte, y las comas delimitadoras dentro de ella deben ir seguidas de un único espacio, por ejemplo: `(1, 2)`, `(x, y, z)`.

Se acepta comúnmente para omitir paréntesis en la coincidencia de patrones de tuplas:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

También se acepta comúnmente para omitir paréntesis si la tupla es el valor devuelto de una función:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

En resumen, prefiere las instancias de tupla entre paréntesis, pero cuando se usan tuplas para la coincidencia de patrones o un valor devuelto, se considera fino evitar paréntesis.

## <a name="formatting-discriminated-union-declarations"></a>Formato de declaraciones sindicales discriminadas

Sangría `|` en la definición de tipo por cuatro espacios:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>Formato de uniones discriminadas

Las uniones discriminadas con instancias que se dividen en varias líneas deben proporcionar a los datos contenidos un nuevo ámbito con sangría:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

El paréntesis de cierre también puede estar en una nueva línea:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Formato de declaraciones de registros

Sangra `{` en la definición de tipo por cuatro espacios e inicia la lista de campos en la misma línea:

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

Colocar el token de apertura en una nueva línea y el token de cierre en una nueva línea es preferible si está declarando implementaciones de interfaz o miembros en el registro:

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>Formato de registros

Los registros cortos se pueden escribir en una línea:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Los registros que son más largos deben usar nuevas líneas para las etiquetas:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Colocar el token de apertura en una nueva línea, el contenido tabulado sobre un ámbito y el token de cierre en una nueva línea es preferible si:

* Mover registros en código con diferentes ámbitos de sangría
* Convertirlos en una función

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

Se aplican las mismas reglas para los elementos de lista y matriz.

## <a name="formatting-copy-and-update-record-expressions"></a>Formato de expresiones de registro de copia y actualización

Una expresión de registro de copia y actualización sigue siendo un registro, por lo que se aplican directrices similares.

Las expresiones cortas pueden caber en una línea:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Las expresiones más largas deben utilizar nuevas líneas:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Y al igual que con la guía de registros, es posible que desee dedicar líneas separadas para las llaves y aplicar sangría a un ámbito a la derecha con la expresión. En algunos casos especiales, como ajustar un valor con un valor opcional sin paréntesis, es posible que deba mantener una llave en una línea:

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>Formato de listas y matrices

Escribir `x :: l` con espacios `::` alrededor`::` del operador ( es un operador de infijo, por lo tanto rodeado de espacios).

La lista y las matrices declaradas en una sola línea deben tener un espacio después del corchete de apertura y antes del corchete de cierre:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Utilice siempre al menos un espacio entre dos operadores distintos de tipo llaves. Por ejemplo, deje un `[` espacio `{`entre a y a .

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

La misma directriz se aplica a listas o matrices de tuplas.

Las listas y matrices que se dividen en varias líneas siguen una regla similar a la de los registros:

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

Y al igual que con los registros, la declaración de los corchetes de apertura y cierre en su propia línea hará que mover el código y la canalización en funciones sea más fácil.

Al generar matrices y listas `->` mediante `do ... yield` programación, prefiera sobre cuándo siempre se genera un valor:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

Las versiones anteriores del `yield` lenguaje F- requerían especificar en situaciones en las que los datos se pueden generar condicionalmente o puede haber expresiones consecutivas que se evaluarán. Prefiere omitir `yield` estas palabras clave a menos que deba compilar con una versión de lenguaje de F. anterior:

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

En algunos `do...yield` casos, puede ayudar en la legibilidad. Estos casos, aunque subjetivos, deben tenerse en cuenta.

## <a name="formatting-if-expressions"></a>Formato si las expresiones

La sangría de condicionales depende de los tamaños de las expresiones que las componen. Si `cond` `e1` , `e2` y son cortos, simplemente escríbalos en una línea:

```fsharp
if cond then e1 else e2
```

Si `cond`, `e1` `e2` o son más largos, pero no multilínea:

```fsharp
if cond
then e1
else e2
```

Si alguna de las expresiones es de varias líneas:

```fsharp
if cond then
    e1
else
    e2
```

Múltiples condicionales con `elif` y `else` se indentan `if`en el mismo ámbito que:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Construcciones de coincidencia de patrones

Use `|` a para cada cláusula de una coincidencia sin sangría. Si la expresión es corta, puede considerar el uso de una sola línea si cada subexpresión también es simple.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Si la expresión de la derecha de la flecha de coincidencia de patrón es `match` / `|`demasiado grande, muévala a la línea siguiente, con sangría a un paso del archivo .

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

La coincidencia de patrones `function`de funciones anónimas, empezando por , generalmente no debe aplicar sangría demasiado. Por ejemplo, la sangría de un ámbito de la siguiente manera está bien:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

La coincidencia de `let` patrones `let rec` en funciones definidas por `let`o `function` debe sangrar cuatro espacios después de iniciar , incluso si se utiliza la palabra clave:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

No se recomienda alinear las flechas.

## <a name="formatting-trywith-expressions"></a>Formato try/with expressions

La coincidencia de patrones en el tipo de `with`excepción debe sangrar en el mismo nivel que .

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>Aplicación de parámetros de función de formato

En general, la mayoría de la aplicación de parámetros de función se realiza en la misma línea.

Si desea aplicar parámetros a una función en una nueva línea, indentarlos por un ámbito.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

Las mismas directrices se aplican a las expresiones lambda como argumentos de función. Si el cuerpo de una expresión lambda, el cuerpo puede tener otra línea, con sangría por un ámbito

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

Sin embargo, si el cuerpo de una expresión lambda es más de una línea, considere la posibilidad de factorizarla en una función independiente en lugar de tener una construcción de varias líneas aplicada como un único argumento a una función.

### <a name="formatting-infix-operators"></a>Formatear operadores de infijos

Separe los operadores por espacios. Excepciones obvias a `!` esta `.` regla son los operadores y.

Las expresiones de infijo están bien para alinearse en la misma columna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formato de operadores de tuberías

Los `|>` operadores de canalización deben ir por debajo de las expresiones en las que operan.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>Módulos de formato

El código de un módulo local debe sangrar en relación con el módulo, pero el código de un módulo de nivel superior no se debe aplicar sangría. No es necesario aplicar sangría a los elementos de espacio de nombres.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Formato de expresiones e interfaces de objetos

Las expresiones e interfaces de objeto `member` deben alinearse de la misma manera con sangría después de cuatro espacios.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Formato de espacios en blanco en expresiones

Evite espacios en blanco extraños en expresiones de F.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Los argumentos con nombre tampoco deben tener espacio en torno a: `=`

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Formato de atributos

[Los atributos](../language-reference/attributes.md) se colocan encima de una construcción:

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>Formato de atributos en parámetros

Los atributos también se pueden colocar en los parámetros. En este caso, coloque entonces en la misma línea que el parámetro y antes del nombre:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Dar formato a múltiples atributos

Cuando se aplican varios atributos a una construcción que no es un parámetro, deben colocarse de tal forma que haya un atributo por línea:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

Cuando se aplican a un parámetro, deben estar `;` en la misma línea y separados por un separador.

## <a name="formatting-literals"></a>Formato de literales

Los [literales](../language-reference/literals.md) de `Literal` F- que utilizan el atributo deben colocar el atributo en su propia línea y utilizar la nomenclatura PascalCase:

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Evite colocar el atributo en la misma línea que el valor.
