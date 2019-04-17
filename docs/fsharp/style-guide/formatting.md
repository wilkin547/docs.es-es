---
title: F#instrucciones de formato de código
description: Obtenga información sobre las directrices para dar formato a F# código.
ms.date: 02/08/2019
ms.openlocfilehash: 259d4bb2147d1fc8bc5d35d7ff2e3c34ec2185d0
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613829"
---
# <a name="f-code-formatting-guidelines"></a>F#instrucciones de formato de código

En este artículo ofrece instrucciones acerca de cómo dar formato al código para que su F# código es:

* Por lo general se ven como más legible
* Está de acuerdo con las convenciones que se aplica al dar formato a otros editores y herramientas en Visual Studio
* Similar a otro código en línea

Estas instrucciones se basan en [una guía completa sobre F# convenciones de formato](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) por [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Reglas generales para la sangría

F#usa el espacio en blanco significativo de forma predeterminada. Las instrucciones siguientes están diseñadas para proporcionar una orientación acerca de cómo jugar con algunos desafíos que esto puede imponer.

### <a name="using-spaces"></a>Uso de espacios

Cuando se requiere la sangría, debe usar espacios, tabulaciones no. Se requiere al menos un espacio. Su organización puede crear los estándares de codificación para especificar el número de espacios que se usará para la sangría; dos, tres o cuatro espacios de sangría en cada nivel donde se produce la sangría es habitual.

**Se recomienda 4 espacios por sangría.**

Es decir, la sangría de programas es algo subjetivo. Las variaciones son correctos, pero la primera regla que debería seguir es *coherencia de sangría*. Elegir un estilo de sangría generalmente aceptado y utilícela sistemáticamente en el código base.

## <a name="formatting-white-space"></a>Aplicar formato a un espacio en blanco

F#distingue espacios en blanco. Aunque la semántica de la mayoría de los espacios en blanco está cubierta por la sangría adecuada, hay algunas cosas a tener en cuenta.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Aplicar formato a los operadores en expresiones aritméticas

Usar siempre el espacio en blanco en torno a expresiones aritméticas binarios:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Unario `-` los operadores deben tener siempre el valor que se negación siguen inmediatamente:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Adición de un carácter de espacio en blanco después de la `-` operador puede dar lugar a confusión para que otros usuarios.

En resumen, es importante siempre:

* Operadores binarios rodear con espacios en blanco
* Nunca tienen espacio en blanco final después de un operador unario

La pauta del operador aritmético binaria es especialmente importante. No se puede delimitar un binario `-` operador cuando se combina con determinadas opciones de formato, podría dar lugar a interpretar como unario `-`.

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Rodear una definición de operador personalizado con espacios en blanco

Usar siempre el espacio en blanco para delimitar una definición de operador:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Para todos los operadores personalizados que se inicia con `*` y que tiene más de un carácter, deberá agregar un espacio en blanco al principio de la definición para evitar la ambigüedad de un compilador. Por este motivo, se recomienda que simplemente rodean las definiciones de todos los operadores con un único carácter de espacio en blanco.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Rodear flechas de parámetro de función con un espacio en blanco

Al definir la firma de una función, use el espacio en blanco que rodea el `->` símbolo:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

## <a name="formatting-blank-lines"></a>Aplicar formato a líneas en blanco

* Independiente nivel superior (función) y la clase de definiciones con dos líneas en blanco.
* Las definiciones de método dentro de una clase se separan mediante una sola línea en blanco.
* Líneas en blanco adicionales pueden usarse (con moderación) para separar los grupos de funciones relacionadas. Pueden omitirse las líneas en blanco entre una serie de líneas de código relacionadas (por ejemplo, un conjunto de implementaciones ficticias).
* Use líneas en blanco en las funciones, con moderación, para indicar secciones lógicas.

## <a name="formatting-comments"></a>Aplicar formato a los comentarios

Generalmente prefieren varios comentarios de barra diagonal doble a través de comentarios del bloque de estilo de aprendizaje automático.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Comentarios en línea deben poner en mayúsculas la primera letra.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenciones de nomenclatura

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Usar camelCase para funciones y los valores de límite de clase, expresión enlazados y patrón enlazadas

Es habitual y aceptado F# estilo usar camelCase para todos los nombres enlazado como variables locales o en coincidencias de patrones y definiciones de función.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Localmente las funciones enlazadas en clases también deben usar camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Usar camelCase para funciones públicas de módulo enlazados

Cuando una función de módulo enlazados es parte de una API pública, debe usar camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Usar camelCase para las funciones y los valores de módulo enlazados internos y privados

Usar camelCase para los valores de módulo enlazados privados, incluidas las siguientes:

* Funciones ad hoc en secuencias de comandos

* Valores que conforman la implementación interna de un tipo o módulo

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Usar camelCase para los parámetros

Todos los parámetros deben usar camelCase según las convenciones de nomenclatura. NET.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Usar PascalCase para los módulos

Todos los módulos (nivel superior, internos, privados, anidados) deben usar PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Uso PascalCase para las declaraciones de tipos, miembros y etiquetas

Las clases, interfaces, estructuras, enumeraciones, delegados, registros y uniones discriminadas deben denominarse con PascalCase. Los miembros de tipos y las etiquetas para los registros y uniones discriminadas también deben usar PascalCase.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Usar PascalCase para construcciones intrínsecas para .NET

Espacios de nombres, las excepciones, eventos y proyecto /`.dll` nombres también deben usar PascalCase. No sólo hace esto que el consumo de otros lenguajes .NET resultar más natural a los consumidores, también es coherente con las convenciones de nomenclatura de .NET que es probable que encuentre.

### <a name="avoid-underscores-in-names"></a>Evite los caracteres de subrayado en nombres

Históricamente, algunos F# bibliotecas han usado caracteres de subrayado en nombres. Sin embargo, esto es ya no amplia aceptación, en parte porque entra en conflicto con las convenciones de nomenclatura. NET. Dicho esto, algunos F# los programadores usan los caracteres de subrayado mucho, en parte por motivos históricos y respeto y la tolerancia es importante. Sin embargo, tenga en cuenta que el estilo a menudo no me gustó por otros usuarios que tienen la opción de elegir si desea usarlo.

Algunas excepciones incluye interoperar con componentes nativos, en caracteres de subrayado son muy comunes.

### <a name="use-standard-f-operators"></a>Estándar de uso F# operadores

Los operadores siguientes se definen en el F# biblioteca estándar y deben usarse en lugar de definir equivalentes. Uso de estos operadores se recomienda que tiende a hacer el código más legible e idiomático. Estar acostumbrados a idiomas distintos a los desarrolladores con experiencia en OCaml o en otro lenguaje de programación funcional. La lista siguiente resume la recomendada F# operadores.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Use la sintaxis de prefijo para los genéricos (`Foo<T>`) con preferencia a la sintaxis de postfijo (`T Foo`)

F#hereda tanto el estilo de aprendizaje automático de postfijo de asignación de nombres de tipos genéricos (por ejemplo, `int list`), así como el prefijo de estilo .NET (por ejemplo, `list<int>`). Se prefiere el estilo. NET, excepto los cuatro tipos específicos:

1. Para F# listas, utilice la forma de postfijo: `int list` lugar `list<int>`.
2. Para F# opciones, utilice la forma de postfijo: `int option` lugar `option<int>`.
3. Para F# matrices, use el nombre sintáctico `int[]` lugar `int array` o `array<int>`.
4. Para las celdas de referencia, utilice `int ref` lugar `ref<int>` o `Ref<int>`.

Para los demás tipos, use el formato de prefijo.

## <a name="formatting-tuples"></a>Aplicar formato a las tuplas

Creación de instancias de una tupla debe incluirse entre paréntesis, y las comas dentro de delimitadores deben ir seguidas por un espacio, por ejemplo: `(1, 2)`, `(x, y, z)`.

Normalmente se acepta para omitir los paréntesis en la coincidencia de patrones de tuplas:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

Normalmente también se acepta para omitir los paréntesis si la tupla es el valor devuelto de una función:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

En resumen, prefiere creaciones de instancias de tupla entre paréntesis, pero al usar tuplas para la coincidencia de patrones o un valor devuelto, se considera bien evitar los paréntesis.

## <a name="formatting-discriminated-union-declarations"></a>Formato discriminadas declaraciones de unión

Aplicar sangría a `|` en la definición de tipo por 4 espacios:

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

Uniones discriminadas con instancias que se dividen en varias líneas debe proporcionar datos contenidos en un nuevo ámbito con sangría:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

También puede ser el paréntesis de cierre en una nueva línea:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Aplicar formato a las declaraciones de registro

Aplicar sangría a `{` en el tipo de definición por 4 espacios e iniciar la lista de campos en la misma línea:

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

Al colocar el símbolo (token) de apertura en una nueva línea y el token de cierre en una línea nueva es preferible si va a declarar implementaciones de interfaz o los miembros en el registro:

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>Formato de registros

Registros cortos pueden escribirse en una sola línea:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Los registros que son más largas deben usar nuevas líneas para etiquetas:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Colocar la apertura token en una nueva línea, el contenido con pestañas en un ámbito, y es preferible si es el token de cierre en una nueva línea:

* Mover los registros en el código con ámbitos diferentes de sangría
* Canalización de en una función

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

## <a name="formatting-copy-and-update-record-expressions"></a>Da formato a expresiones de registro de copia y actualización

Una expresión de registro de copia y actualización sigue siendo un registro, por lo que se aplican las directrices similar.

Expresiones cortas pueden caber en una sola línea:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Expresiones más largas deben usar las nuevas líneas:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Y como con las instrucciones de registro, es posible que desea dedicar líneas separadas para las llaves y aplicar sangría a un ámbito a la derecha con la expresión. Tenga en cuenta que en algunos casos especiales, como el ajuste de un valor con un elemento opcional sin paréntesis, es posible que deberá mantener una llave en una sola línea:

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

## <a name="formatting-lists-and-arrays"></a>Aplicar formato a las listas y matrices

Escribir `x :: l` con espacios alrededor de la `::` operador (`::` es un operador infijo, por lo tanto, rodeado por espacios).

Las matrices declaradas en una sola línea y lista deben tener un espacio después del corchete de apertura y antes del corchete de cierre:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Use siempre al menos un espacio entre dos operadores llave similar a distinct. Por ejemplo, deje un espacio entre un `[` y un `{`.

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

Se aplica a las mismas directrices listas o matrices de tuplas.

Listas y matrices que se dividen en varias líneas siguen una regla similar como hacen los registros:

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

Y al igual que con los registros, declarar la apertura y el corchete de cierre en su propia línea facilitarán mover código alrededor y canalizar en funciones.

## <a name="formatting-if-expressions"></a>Formato if expresiones

Sangría de condicionales depende de los tamaños de las expresiones que los componen. Si `cond`, `e1` y `e2` son a corto, basta con escribirlos en una sola línea:

```fsharp
if cond then e1 else e2
```

Si bien `cond`, `e1` o `e2` son más larga, pero no de varias líneas:

```fsharp
if cond
then e1
else e2
```

Si alguna de las expresiones de varias líneas:

```fsharp
if cond then
    e1
else
    e2
```

Varias instrucciones condicionales con `elif` y `else` se les aplica sangría en el mismo ámbito que la `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Construcciones de coincidencia de patrón

Use un `|` para cada cláusula de una coincidencia con ninguna sangría. Si la expresión es corta, puede usar una sola línea, si cada subexpresión también es sencillo.

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

Si la expresión a la derecha de la flecha de coincidencia es demasiado grande, se moverá a la siguiente línea, un paso con sangría desde el `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Coincidencia de las funciones anónimas, empezando por `function`, por lo general debe no aplicar sangría demasiado lejos. Por ejemplo, está bien aplicar sangría a un ámbito como sigue:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Coincidencia de patrones en las funciones definidas por `let` o `let rec` debe ser con sangría 4 espacios después de iniciar de `let`, incluso si `function` se utiliza la palabra clave:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

No se recomienda alinear las flechas.

## <a name="formatting-trywith-expressions"></a>Formato try / with expresiones

Coincidencia de patrones en el tipo de excepción deben aplicarse sangría en el mismo nivel que `with`.

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

## <a name="formatting-function-parameter-application"></a>Aplicar formato a la aplicación de parámetro de función

En general, la mayoría de los aplicaciones de parámetro de función se realiza en la misma línea.

Si desea aplicar los parámetros a una función en una nueva línea, sangría por un ámbito.

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

Se aplican las mismas instrucciones para las expresiones lambda como argumentos de función. Si el cuerpo de una expresión lambda, el cuerpo puede tener la siguiente línea, aplica sangría a un ámbito

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

Sin embargo, si el cuerpo de una expresión lambda tiene más de una línea, considere la posibilidad de factorización a probarlo en una función independiente en lugar de tener una construcción de varias líneas, aplicarse como un único argumento a una función.

### <a name="formatting-infix-operators"></a>Aplicar formato a los operadores de infijo

Operadores separados por espacios. Obvias excepciones a esta regla son los `!` y `.` operadores.

Las expresiones de infijo son Aceptar a línea en la misma columna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Aplicar formato a los operadores de canalización

Canalización `|>` operadores deben ir debajo de las expresiones que operan en.

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

### <a name="formatting-modules"></a>Aplicar formato a los módulos

Código de un módulo local se debe aplicar sangría en relación con el módulo, pero no debe aplicarse sangría a código en un módulo de nivel superior. Elementos Namespace no es necesario que tenga la sangría.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Aplicar formato a expresiones de objeto e interfaces

Expresiones de objeto y las interfaces deben alinearse de la misma manera con `member` que se aplica sangría después de 4 espacios.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Espacio en blanco en las expresiones de formato

Evite los espacios en blanco en F# expresiones.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Argumentos con nombre también no deben tener espacio que rodea el `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Atributos de formato

[Atributos](../language-reference/attributes.md) se colocan por encima de una construcción:

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

### <a name="formatting-attributes-on-parameters"></a>Atributos de formato de parámetros

Los atributos también pueden ser lugares en los parámetros. En este caso, a continuación, coloque en la misma línea como parámetro y antes del nombre:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Varios atributos de formato

Cuando se aplican varios atributos a una construcción que no es un parámetro, se deben colocar, como que hay un atributo por línea:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

Cuando se aplica a un parámetro, deben estar en la misma línea y separadas por un `;` separador.

## <a name="formatting-literals"></a>Formato de literales

[F#literales](../language-reference/literals.md) utilizando el `Literal` atributo debe colocar el atributo en su propia línea y usar camelCase de nomenclatura:

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

Evite colocar el atributo en la misma línea que el valor.
