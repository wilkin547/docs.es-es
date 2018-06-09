---
title: 'Instrucciones de formato de código de F #'
description: 'Obtenga información acerca de las directrices para dar formato al código de F #.'
ms.date: 05/14/2018
ms.openlocfilehash: 6c8e4059fd4bf1e7450118a6df02609217c4f4db
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231517"
---
# <a name="f-code-formatting-guidelines"></a>Instrucciones de formato de código de F #

Este artículo proporciona instrucciones acerca de cómo aplicar formato al código para que el código de F # es:

* Generalmente se visualiza como más legible
* Está de acuerdo con convenciones aplicadas dando formato a otros editores y herramientas en Visual Studio
* Similar a otro código en línea

Estas instrucciones se basan en [una guía completa para las convenciones de formato de F #](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) por [Phan Anh estiércol](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Reglas generales para la sangría

F # utiliza espacios en blanco significativos de forma predeterminada. Las instrucciones siguientes están diseñadas para proporcionar una orientación acerca de cómo hacer juegos malabares con algunos de los desafíos que esto puede imponer.

### <a name="using-spaces"></a>Con espacios

Cuando es necesario aplicar sangría, debe usar espacios, no tabulaciones. Se requiere al menos un espacio. Su organización puede crear los estándares de codificación para especificar el número de espacios que se utilizarán para la sangría; dos, tres o cuatro espacios de sangría en cada nivel donde se produce la sangría es normal.

**Se recomienda 4 espacios por sangría.**

Es decir, sangría de programas es una cuestión subjetiva. Variaciones están bien, pero es la primera regla que debería seguir *coherencia de sangría*. Elija un estilo de sangría generalmente aceptado y usarlo de forma sistemática en todo el código base.

## <a name="formatting-blank-lines"></a>Aplicar formato a líneas en blanco

* Independiente nivel superior (función) y la clase de definiciones con dos líneas en blanco.
* Definiciones de método dentro de una clase se separan mediante una sola línea en blanco.
* Líneas en blanco adicionales pueden usarse (con moderación) para separar los grupos de funciones relacionadas. Pueden omitir las líneas en blanco entre una serie de líneas de código relacionados (por ejemplo, un conjunto de implementaciones ficticias).
* Utilice las líneas en blanco en las funciones, con moderación, para indicar secciones lógicas.

## <a name="formatting-comments"></a>Aplicar formato a los comentarios

Por lo general preferir múltiples comentarios de barra diagonal doble comentarios del bloque de estilo de aprendizaje automático.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Comentarios en línea deben poner en mayúscula la primera letra.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Convenciones de nomenclatura

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Usar camelCase para funciones y los valores de límite de clase, expresión enlazados y límite de patrón

Es normal y aceptado estilo de F # que se usará camelCase para todos los nombres enlazados como variables locales o en coincidencias de patrón y las definiciones de función.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Las funciones enlazadas a localmente en clases también deben usar camelCase.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Usar camelCase para funciones públicas de límite de módulo

Cuando una función de módulo enlazada es parte de una API pública, debe utilizar camelCase:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Usar camelCase para las funciones y los valores de límite de módulo privados e internos

Use camelCase para los valores de límite de módulo privados, incluidas las siguientes:

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

### <a name="use-pascalcase-for-modules"></a>Utilizar PascalCase para módulos

Todos los módulos (nivel superior, internos, privados, anidados) deben usar PascalCase.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Usar PascalCase de declaraciones de tipos, miembros y etiquetas

Las clases, interfaces, estructuras, enumeraciones, delegados, registros y uniones discriminadas deben denominarse con PascalCase. Los miembros dentro de los tipos y las etiquetas para los registros y uniones discriminadas también deben usar PascalCase.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Utilizar PascalCase para construcciones intrínsecas de .NET

Espacios de nombres, excepciones, eventos y el proyecto /`.dll` nombres también deben utilizar PascalCase. No sólo hace esto que el consumo de otros lenguajes .NET sentirse más natural a los consumidores, también es coherente con las convenciones de nomenclatura de .NET que es probable que encuentre.

### <a name="avoid-underscores-in-names"></a>Evite los caracteres de subrayado en nombres

Históricamente, algunas bibliotecas de F # usan caracteres de subrayado en nombres. Sin embargo, esto se ampliamente ya no se acepta, en parte porque entra en conflicto con las convenciones de nomenclatura. NET. Es decir, algunos programadores de F # utilizan caracteres de subrayado mucho, en parte por motivos históricos y respeto y la tolerancia es importante. Sin embargo, tenga en cuenta que el estilo a menudo se disliked por otros usuarios que tienen una opción sobre si desea usarlo.

Algunas excepciones incluye interoperar con componentes nativos, donde el carácter de subrayado es muy comunes.

### <a name="use-standard-f-operators"></a>Utilizar operadores estándar de F #

Los operadores siguientes se definen en la biblioteca estándar de F # y deben utilizarse en lugar de definir equivalentes. Uso de estos operadores se recomienda tiende a dificultar el código sea más legible e idiomática. Los desarrolladores con un fondo en OCaml o en otro lenguaje de programación funcional pueden ser acostumbrados a diferentes expresiones. En la lista siguiente se resume los operadores de F # recomendados.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Use la sintaxis de prefijo para los tipos genéricos (`Foo<T>`) con preferencia a sintaxis de postfijo (`T Foo`)

F # hereda tanto el estilo de aprendizaje automático de postfijo de asignación de nombres de tipos genéricos (por ejemplo, `int list`), así como el estilo de .NET de prefijo (por ejemplo, `list<int>`). Prefiere el estilo. NET, excepto los cuatro tipos específicos:

1. Para F # listas, utilice la forma de postfijo: `int list` en lugar de `list<int>`.
2. Para opciones de F #, utilice la forma de postfijo: `int option` en lugar de `option<int>`.
3. Para las matrices de F #, utilice el nombre sintáctico `int[]` en lugar de `int array` o `array<int>`.
4. Para las celdas de referencia, utilice `int ref` en lugar de `ref<int>` o `Ref<int>`.

Para todos los otros tipos, utilice la forma de prefijo.

## <a name="formatting-discriminated-union-declarations"></a>Formato discriminada declaraciones de unión

Aplicar sangría `|` en la definición de tipo por 4 espacios:

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

Uniones discriminadas instancias que se dividen en varias líneas debe proporcionar datos contenidos en un nuevo ámbito con sangría:

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

## <a name="formatting-tuples"></a>Formato tuplas

La creación de instancias de una tupla debe ir entre paréntesis, y las comas dentro de delimitadores deben ir seguidas un único espacio, por ejemplo: `(1, 2)`, `(x, y, z)`.

Una excepción aceptada es omitir los paréntesis en la coincidencia de patrones de tuplas:

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a>Formato de registros

Registros cortos pueden escribirse en una sola línea:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Los registros que tengan más deben usar nuevas líneas para etiquetas:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Colocar el símbolo (token) de apertura en la misma línea y el símbolo (token) de cierre en una nueva línea también está bien:

```fsharp
let rainbow = {
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
```

Se aplican las mismas reglas para los elementos de lista y matriz.

## <a name="formatting-lists-and-arrays"></a>Aplicar formato a las listas y matrices

Escribir `x :: l` con espacios alrededor del `::` operador (`::` es un operador infijo, por lo tanto, rodeado por espacios) y `[1; 2; 3]` (`;` es un delimitador, por lo tanto, seguido por un espacio).

Utilice siempre al menos un espacio entre los dos operadores distintos de llave similar. Por ejemplo, deje un espacio entre un `[` y `{`.

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

Listas y matrices que se dividen en varias líneas siguen una regla similar igual que los registros:

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a>Formato if expresiones

Sangría del condicionales depende de los tamaños de las expresiones que ellos constituyen. Si `cond`, `e1` y `e2` son pequeños, basta con escribirlos en una sola línea:

```fsharp
if cond then e1 else e2
```

Si `e1` y `cond` son pequeñas, pero `e2` es grande:

```fsharp
if cond then e1
else
    e2
```

Si `e1` y `cond` son grandes y `e2` es pequeño:

```fsharp
if cond then
    e1
else e2
```

Si todas las expresiones son grandes:

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

### <a name="pattern-matching-constructs"></a>Construcciones de búsqueda de coincidencias de patrón

Use un `|` para cada cláusula de una coincidencia con ninguna sangría. Si la expresión es corta, puede utilizar una sola línea si cada subexpresión también es sencilla.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Si la expresión situada a la derecha de la flecha de coincidencia es demasiado grande, muévalo a la siguiente línea, con sangría un paso de la `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Coincidencia de funciones anónimas, comenzando por `function`, por lo general debe no aplicar sangría demasiado lejos. Por ejemplo, está bien aplicar sangría a un ámbito como se indica a continuación:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Patrón de búsqueda de coincidencias en las funciones definidas por `let` o `let rec` debe ser con sangría 4 espacios después de iniciar de `let`, incluso si `function` se utiliza la palabra clave:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

No se recomienda alinear flechas.

## <a name="formatting-trywith-expressions"></a>Formato try / con expresiones

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

## <a name="formatting-function-parameter-application"></a>Aplicación de parámetro de función de formato

En general, la mayoría de los aplicaciones de parámetro de función se realiza en la misma línea.

Si desea aplicar parámetros a una función en una nueva línea, hágalo con un ámbito.

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

Se aplican las mismas directrices para las expresiones lambda como argumentos de función. Si el cuerpo de una expresión lambda, el cuerpo puede tener otra línea, aplica sangría a un ámbito

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

Sin embargo, si el cuerpo de una expresión lambda más de una línea, considere la posibilidad de factorización horizontal a una función diferente en lugar de tener una construcción de varias líneas aplicar como un solo argumento a una función.

### <a name="formatting-infix-operators"></a>Aplicar formato a los operadores de infijo

Operadores separados por espacios. Obvias excepciones a esta regla son las `!` y `.` operadores.

Expresiones de infijo resulta adecuado para la línea en la misma columna:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Aplicar formato a los operadores de canalización

Canalización `|>` operadores deberían ir debajo de las expresiones que operan en.

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

Código en un módulo local se debe aplicar la sangría en relación con el módulo, pero no debe aplicarse sangría a código en un módulo de nivel superior. Elementos de Namespace no es necesario que tenga la sangría.

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

Expresiones de objeto y las interfaces se deben alinear en la misma manera con `member` que se aplica una sangría después de 4 espacios.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a>Espacio en blanco en las expresiones de formato

Evite el espacio en blanco extraño en expresiones de F #.

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
