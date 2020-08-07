---
title: Formato de texto sin formato
description: 'Aprenda a usar printf y otro formato de texto sin formato en aplicaciones y scripts de F #.'
ms.date: 07/22/2020
ms.openlocfilehash: 6b14633e074961757d0f0cd258d1b1667f5fd8ee
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854924"
---
# <a name="plain-text-formatting"></a>Formato de texto sin formato

F # admite el formato de texto sin formato con comprobación de tipos mediante `printf` ,, `printfn` `sprintf` y las funciones relacionadas.
Por ejemplo,

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

proporciona la salida

```fsharp
Hello world, 2 + 2 is 4
```

F # también permite dar formato de texto sin formato a los valores estructurados.
Por ejemplo, considere el siguiente ejemplo en el que se da formato a la salida como una presentación de tuplas de tipo matriz.

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

El formato de texto sin formato estructurado se activa cuando se usa el `%A` formato en `printf` cadenas de formato.
También se activa al dar formato a la salida de valores de F # Interactive, donde la salida incluye información adicional y también se puede personalizar.
El formato de texto sin formato también se puede observar a través de cualquier llamada a `x.ToString()` en valores de registro y Unión de F #, incluidos los que se producen implícitamente en la depuración, el registro y otras herramientas.

## <a name="checking-of-printf-format-strings"></a>Comprobando `printf` cadenas de formato

Se informará de un error en tiempo de compilación si `printf` se usa una función de formato con un argumento que no coincida con los especificadores de formato printf en la cadena de formato.  Por ejemplo,

```fsharp
sprintf "Hello %s" (2+2)
```

proporciona la salida

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

Técnicamente hablando, al usar `printf` y otras funciones relacionadas, una regla especial en el compilador de F # comprueba el literal de cadena pasado como la cadena de formato, asegurándose de que los argumentos subsiguientes aplicados son del tipo correcto para que coincidan con los especificadores de formato usados.

## <a name="format-specifiers-for-printf"></a>Especificadores de formato para`printf`

Las especificaciones de formato de los `printf` formatos son cadenas con `%` marcadores que indican el formato. Los marcadores de posición de formato se componen de `%[flags][width][.precision][type]` que el tipo se interpreta de la siguiente manera:

| Especificador de formato   | Tipos (s)        | Observaciones                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | bool      | Con formato `true` o`false`                |
| `%s`               | string    | Con formato de contenido sin escape         |
| `%c`               | char      | Con formato del literal de carácter  |
| `%d`, `%i`         | un tipo entero básico | Con formato de entero decimal, con signo si el tipo entero básico está firmado |
| `%u`               | un tipo entero básico | Con formato de entero decimal sin signo   |
| `%x`, `%X`         | un tipo entero básico | Con formato de número hexadecimal sin signo (a-f o A-F para dígitos hexadecimales, respectivamente)  |
|  `%o`              | un tipo entero básico | Con formato de número octal sin signo |
| `%e`, `%E`         | un tipo de punto flotante básico | Con formato como un valor con signo que tiene el formato `[-]d.dddde[sign]ddd` donde d es un solo dígito decimal, dddd es uno o más dígitos decimales, DDD tiene exactamente tres dígitos decimales y sign es `+` o`-` |
| `%f`               | un tipo de punto flotante básico | Con formato como un valor con signo que tiene el formato `[-]dddd.dddd` , donde `dddd` es uno o más dígitos decimales. El número de dígitos que hay delante del separador decimal depende de la magnitud del número y el número de dígitos que hay detrás del separador decimal depende de la precisión solicitada. |
| `%g`, `%G` | un tipo de punto flotante básico |  Con formato con como valor con signo impreso en `%f` o en `%e` formato, lo que sea más compacto para el valor y la precisión especificados. |
| `%M` | un `System.Decimal` valor  |    Con formato mediante el `"G"` especificador de formato para`System.Decimal.ToString(format)` |
| `%O` | cualquier valor  |   Formateado mediante la conversión boxing del objeto y la llamada a su `System.Object.ToString()` método |
| `%A` | cualquier valor  |   Con formato de [texto sin formato estructurado](plaintext-formatting.md) con la configuración de diseño predeterminada |
| `%a` | cualquier valor  |   Requiere dos argumentos: una función de formato que acepte un parámetro de contexto y el valor, y el valor concreto que se va a imprimir. |
| `%t` | cualquier valor  |   Requiere un argumento: una función de formato que acepte un parámetro de contexto que genere o devuelva el texto adecuado |

Los tipos enteros básicos son `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), `int16` ( `System.Int16` ), `uint16` ( `System.UInt16` ), `int32` ( `System.Int32` ), `uint32` ( `System.UInt32` ), `int64` ( `System.Int64` ), `uint64` ( `System.UInt64` ), `nativeint` ( `System.IntPtr` ) y `unativeint` ( `System.UIntPtr` ).
Los tipos de punto flotante básicos son `float` ( `System.Double` ) y `float32` ( `System.Single` ).

El ancho opcional es un entero que indica el ancho mínimo del resultado. Por ejemplo, `%6d` imprime un entero, prefijando espacios en blanco para rellenar al menos seis caracteres. Si el ancho es `*` , se toma un argumento entero adicional para especificar el ancho correspondiente.

Las marcas válidas son:

| Marca   | Efecto        | Observaciones                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | Agregue ceros en lugar de espacios para crear el ancho necesario |    |
| `-` |  Justificar a la izquierda el resultado dentro del ancho especificado |   |
| `+`  | Agregue un `+` carácter si el número es positivo (para que coincida con un `-` signo para los negativos) |   |
| carácter de espacio | Agregue un espacio adicional si el número es positivo (para que coincida con un signo "-" para los negativos) |

La `#` marca printf no es válida y se indicará un error en tiempo de compilación si se usa.

Se da formato a los valores mediante una referencia cultural invariable. La configuración de la referencia cultural es irrelevante para `printf` dar formato, excepto cuando afecta a los resultados de `%O` y el `%A` formato. Para obtener más información, vea [formato de texto sin formato estructurado](plaintext-formatting.md).

## <a name="a-formatting"></a>`%A`formato

El `%A` especificador de formato se usa para dar formato a los valores de una manera legible y también puede ser útil para notificar información de diagnóstico.

### <a name="primitive-values"></a>Valores primitivos

Al dar formato a texto sin formato mediante el `%A` especificador, se da formato a los valores numéricos de F # con su sufijo y referencia cultural de todos los idiomas. Los valores de punto flotante se formatean con 10 lugares de precisión de punto flotante. Por ejemplo,

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

Obtiene

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

Al usar el `%A` especificador, se da formato a las cadenas con comillas. Los códigos de escape no se agregan y, en su lugar, se imprimen los caracteres sin formato. Por ejemplo,

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

Obtiene

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a>Valores de .NET

Al dar formato a texto sin formato mediante el `%A` especificador, se da formato a los objetos de .net que no son de F # mediante `x.ToString()` el uso de la configuración predeterminada de .net especificada por `System.Globalization.CultureInfo.CurrentCulture` y `System.Globalization.CultureInfo.CurrentUICulture` .  Por ejemplo,

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

Obtiene

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a>Valores estructurados

Al dar formato a texto sin formato mediante el `%A` especificador, la sangría de bloque se usa para las listas y tuplas de F #. Esto se muestra en el ejemplo anterior.
También se utiliza la estructura de matrices, incluidas las matrices multidimensionales.  Las matrices unidimensionales se muestran con `[| ... |]` Sintaxis. Por ejemplo,

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

Obtiene

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

El ancho de impresión predeterminado es 80.  Este ancho se puede personalizar mediante el uso de un ancho de impresión en el especificador de formato. Por ejemplo,

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

Obtiene

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

Si se especifica un ancho de impresión de 0, no se utilizará ningún ancho de impresión. Se producirá una sola línea de texto, excepto donde las cadenas incrustadas en la salida contengan saltos de línea.  Por ejemplo

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

Obtiene

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

Se usa un límite de profundidad de 4 para los valores de secuencia ( `IEnumerable` ), que se muestran como `seq { ...}` . Se usa un límite de profundidad de 100 para los valores de lista y matriz.
Por ejemplo,

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

Obtiene

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

La sangría de bloque también se usa para la estructura de los valores de registro y Unión públicos. Por ejemplo,

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

Obtiene

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

Si `%+A` se utiliza, la estructura privada de los registros y las uniones también se revela mediante la reflexión. Por ejemplo

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

Obtiene

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a>Valores grandes, cíclicos o profundamente anidados

Los valores estructurados grandes tienen el formato de un número máximo de nodos de objetos globales de 10000.
Los valores profundamente anidados tienen el formato de una profundidad de 100.  En ambos casos, `...` se usa para Elide parte de la salida.  Por ejemplo,

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

genera una salida grande con algunas partes eliden:

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

Los ciclos se detectan en los gráficos de objetos y `...` se utilizan en los lugares donde se detectan los ciclos. Por ejemplo

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

Obtiene

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a>Valores de función Lazy, NULL y

Los valores diferidos se imprimen como `Value is not created` o texto equivalente cuando el valor aún no se ha evaluado.

Los valores NULL se imprimen como `null` a menos que el tipo estático del valor se determine como un tipo de Unión donde `null` es una representación permitida.

Los valores de función de F # se imprimen como su nombre de cierre generado internamente, por ejemplo, `<fun:it@43-7>` .

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a>Personalizar el formato de texto sin formato con`StructuredFormatDisplay`

Cuando se usa el `%A` especificador, se respeta la presencia del `StructuredFormatDisplay` atributo en las declaraciones de tipo.  Se puede usar para especificar texto suplente y la propiedad para mostrar un valor. Por ejemplo:

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

Obtiene

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a>Personalizar el formato de texto sin formato invalidando`ToString`

La implementación predeterminada de `ToString` es observable en programación en F #. A menudo, los resultados predeterminados no son adecuados para su uso en la presentación de información orientada al programador o en el resultado del usuario y, como resultado, es habitual reemplazar la implementación predeterminada.  

De forma predeterminada, los tipos de registro y Unión de F # invalidan la implementación de `ToString` con una implementación de que usa `sprintf "%+A"` .  Por ejemplo,

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

Obtiene

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

En el caso de los tipos de clase, no se proporciona ninguna implementación predeterminada de `ToString` y se usa el valor predeterminado de .net, que indica el nombre del tipo. Por ejemplo,

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

Obtiene

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

Agregar una invalidación para `ToString` puede dar un mejor formato.

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

Obtiene

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a>F# interactivo impresión estructurada

F# interactivo ( `dotnet fsi` ) utiliza una versión extendida de formato de texto sin formato estructurado para informar de los valores y permite la personalización adicional. Para obtener más información, vea [F# interactivo](fsharp-interactive-options.md).

## <a name="customize-debug-displays"></a>Personalizar las visualizaciones de depuración

Los depuradores para .NET respetan el uso de atributos como `DebuggerDisplay` y `DebuggerTypeProxy` , y afectan a la presentación estructurada de objetos en las ventanas de inspección del depurador.
El compilador de F # generaba automáticamente estos atributos para los tipos de Unión y de registro discriminados, pero no los tipos de clase, interfaz o estructura.

Estos atributos se omiten en el formato de texto sin formato de F #, pero puede ser útil implementar estos métodos para mejorar las visualizaciones al depurar tipos de F #.

## <a name="see-also"></a>Vea también

- [Cadenas](strings.md)
- [Informes](records.md)
- [Uniones discriminadas](discriminated-unions.md)
- [F# interactivo](fsharp-interactive-options.md)
