---
title: 'Novedades de C# 8.0: Guía de C#'
description: Obtenga información general sobre las nuevas características disponibles en C# 8.0. Este artículo está actualizado con la versión preliminar 2.
ms.date: 02/12/2019
ms.openlocfilehash: 874420775215502ebdacb8420b3fe0e027d6660f
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747627"
---
# <a name="whats-new-in-c-80"></a>Novedades de C# 8.0

Hay muchas mejoras en el lenguaje C# que ya se pueden probar en la versión preliminar 2. Las nuevas características agregadas en la versión preliminar 2 son:

- [Mejoras de coincidencia de patrones](#more-patterns-in-more-places):
  * [Expresiones switch](#switch-expressions)
  * [Patrones de propiedades](#property-patterns)
  * [Patrones de tupla](#tuple-patterns)
  * [Patrones posicionales](#positional-patterns)
- [Declaraciones using](#using-declarations)
- [Funciones locales estáticas](#static-local-functions)
- [Estructuras ref descartables](#disposable-ref-structs)

Las siguientes características del lenguaje aparecieron primero en la versión preliminar 1 de C# 8.0:

- [Tipos de referencia que aceptan valores null](#nullable-reference-types)
- [Secuencias asincrónicas](#asynchronous-streams)
- [Índices y rangos](#indices-and-ranges)

> [!NOTE]
> Este artículo se actualizó por última vez para la versión preliminar 2 de C# 8.0.

En el resto de este artículo se describen brevemente estas características. Cuando hay disponibles artículos detallados, se proporcionan vínculos a esos tutoriales e introducciones.

## <a name="more-patterns-in-more-places"></a>Más patrones en más lugares

La **coincidencia de patrones** ofrece herramientas que proporcionan funcionalidad dependiente de la forma entre tipos de datos relacionados pero diferentes. C# 7.0 introdujo la sintaxis de patrones de tipos y patrones de constantes mediante la expresión [`is`](../language-reference/keywords/is.md) y la instrucción [`switch`](../language-reference/keywords/switch.md). Estas características representaban los primeros pasos hacia el uso de paradigmas de programación donde los datos y la funcionalidad están separados. A medida que el sector se mueve hacia más microservicios y otras arquitecturas basadas en la nube, se necesitan otras herramientas de lenguaje.

C# 8.0 amplía este vocabulario para que pueda usar más expresiones de patrones en más lugares del código. Cuando los datos y la funcionalidad estén separados, tenga en cuenta estas características. Cuando los algoritmos dependan de un hecho distinto del tipo de entorno de ejecución de un objeto, tenga en cuenta la coincidencia de patrones. Estas técnicas ofrecen otra forma de expresar los diseños.

Además de nuevos patrones en nuevos lugares C# 8.0 agrega **patrones recursivos**. El resultado de cualquier expresión de patrón es una expresión. Un patrón recursivo es simplemente una expresión de patrón aplicada a la salida de otra expresión de patrón.

### <a name="switch-expressions"></a>Expresiones switch

Con frecuencia, una instrucción [ `switch`](../language-reference/keywords/switch.md) genera un valor en cada uno de sus bloques `case`. Las **expresiones switch** le permiten usar una sintaxis de expresiones más concisa. Hay menos palabras clave `case` y `break` repetitivas y menos llaves.  Por ejemplo, considere la siguiente enumeración que muestra los colores del arco iris:

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Blue,
    Indigo,
    Violet
}
```

Puede convertir un valor `Rainbow` a sus valores RGB mediante el método siguiente que contiene una expresión switch:

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

Aquí hay varias mejoras en la sintaxis:

- La variable precede a la palabra clave `switch`. El orden diferente permite distinguir fácilmente la expresión switch de la instrucción switch.
- Los elementos `case` y `:` se reemplazan por `=>`. Es más concisa e intuitiva.
- El caso `default` se reemplaza por un descarte `_`.
- Los cuerpos son expresiones, no instrucciones.

Compárelo con el código equivalente mediante la instrucción clásica `switch`:

```csharp
public static RGBColor fromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a>Patrones de propiedades

El **patrón de propiedades** permite hallar la coincidencia con las propiedades del objeto examinado. Considere un sitio de comercio electrónico que debe calcular los impuestos de ventas según la dirección del comprador. Ese cálculo no es una responsabilidad fundamental de una clase `Address`. Cambiará con el tiempo, probablemente con más frecuencia que el formato de dirección. El importe de los impuestos de ventas depende de la propiedad `State` de la dirección. El método siguiente usa el patrón de propiedades para calcular los impuestos de ventas a partir de la dirección y el precio:

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
    ```

Pattern matching creates a concise syntax for expressing this algorithm.

### Tuple patterns

Some algorithms depend on multiple inputs. **Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).  The following code shows a switch expression for the game *rock, paper, scissors*:

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
    ```

The messages indicate the winner. The discard case represents the three combinations for ties, or other text inputs.

### Positional patterns

Some types include a `Deconstruct` method that deconstructs its properties into discrete variables. When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.  Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

El método siguiente usa el **patrón posicional** para extraer los valores de `x` y `y`. A continuación, usa una cláusula `when` para determinar el cuadrante del punto:

```csharp
static string Quadrant(Point p) => p switch
{
    (0, 0) => "origin",
    (var x, var y) when x > 0 && y > 0 => "Quadrant 1",
    (var x, var y) when x < 0 && y > 0 => "Quadrant 2",
    (var x, var y) when x < 0 && y < 0 => "Quadrant 3",
    (var x, var y) when x > 0 && y < 0 => "Quadrant 4",
    (var x, var y) => "on a border",
    _ => "unknown"
};
```

El patrón de descarte del modificador anterior coincide cuando `x` o `y`, pero no ambos, es 0. Una expresión switch debe generar un valor o producir una excepción. Si ninguno de los casos coincide, la expresión switch produce una excepción. El compilador genera una advertencia si no cubre todos los posibles casos en la expresión switch.

## <a name="using-declarations"></a>Declaraciones using

Una **declaración using** es una declaración de variable precedida por la palabra clave `using`. Indica al compilador que la variable que se declara debe eliminarse al final del ámbito de inclusión. Por ejemplo, considere el siguiente código que escribe un archivo de texto:

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

En el ejemplo anterior, el archivo se elimina cuando se alcanza la llave de cierre del método. Ese es el final del ámbito en el que se declara `file`. El código anterior es equivalente al siguiente código que usa las [instrucciones using](../language-reference/keywords/using-statement.md) clásicas:


```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

En el ejemplo anterior, el archivo se elimina cuando se alcanza la llave de cierre asociada con la instrucción `using`.

En ambos casos, el compilador genera la llamada a `Dispose()`. El compilador genera un error si la expresión de la instrucción using no se puede eliminar.

## <a name="static-local-functions"></a>Funciones locales estáticas

Ahora puede agregar el modificador `static` a funciones locales para asegurarse de que la función local no captura (hace referencia a) las variables del ámbito de inclusión. Si lo hace, se genera un error que dice que `CS8421`una función local estática no puede contener una referencia a <variable>. 

Observe el código siguiente. La función local `LocalFunction` accede a la variable `y`, declarada en el ámbito de inclusión (el método `M`). Por lo tanto, `LocalFunction` no se puede declarar con el modificador `static`:

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

El código siguiente contiene una función local estática. Puede ser estática porque no accede a las variables del ámbito de inclusión:

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a>Estructuras ref descartables

Un elemento `struct` declarado con el modificador `ref` no puede implementar ninguna interfaz y, por tanto, no puede implementar <xref:System.IDisposable>. Por lo tanto, para permitir que se elimine un elemento `ref struct`, debe tener un método `void Dispose()` accesible. Esto también se aplica a las declaraciones `readonly ref struct`.

## <a name="nullable-reference-types"></a>Tipos de referencia que aceptan valores NULL

Dentro de un contexto de anotación que acepta valores NULL, cualquier variable de un tipo de referencia se considera un **tipo de referencia que no acepta valores NULL**. Si quiere indicar que una variable puede ser NULL, debe anexar `?` al nombre del tipo para declarar la variable como un **tipo de referencia que acepta valores NULL**.

En los tipos de referencia que no aceptan valores NULL, el compilador usa el análisis de flujo para garantizar que las variables locales se inicializan en un valor no NULL cuando se declaran. Los campos se deben inicializar durante la construcción. Si la variable no se establece mediante una llamada a alguno de los constructores disponibles o por medio de un inicializador, el compilador genera una advertencia. Además, los tipos de referencia que no aceptan valores NULL no pueden tener asignado un valor que podría ser NULL.

Los tipos de referencia que aceptan valores NULL no se comprueban para garantizar que se asignan o inicializan como NULL. Sin embargo, el compilador usa el análisis de flujo para garantizar que cualquier variable de un tipo de referencia que acepta valores NULL se compara con NULL antes de acceder a ella o de asignarse a un tipo de referencia que no los acepta.

Puede aprender más sobre la característica en la introducción a los [tipos de referencia que aceptan valores NULL](../nullable-references.md). Pruébela por su cuenta en una nueva aplicación en este [tutorial de tipos de referencia que aceptan valores NULL](../tutorials/nullable-reference-types.md). Puede encontrar más información sobre los pasos para migrar una base de código existente para hacer uso de los tipos de referencia que aceptan valores NULL en el [tutorial sobre la migración de una aplicación para usar tipos de referencia que aceptan valores NULL](../tutorials/upgrade-to-nullable-references.md).

## <a name="asynchronous-streams"></a>Secuencias asincrónicas

A partir de C# 8.0, puede crear y consumir secuencias de forma asincrónica. Un método que devuelve una secuencia asincrónica tiene tres propiedades:

1. Se ha declarado con el modificador `async`.
1. Devuelve <xref:System.Collections.Generic.IAsyncEnumerable%601>.
1. El método contiene instrucciones `yield return` que devuelven elementos sucesivos de la secuencia asincrónica.

Para consumir una secuencia asincrónica es necesario agregar la palabra clave `await` delante de la palabra clave `foreach` al enumerar los elementos de la secuencia. Para agregar la palabra clave `await` es necesario declarar el método que enumera la secuencia asincrónica con el modificador `async` y devolver un tipo permitido para un método `async`. Normalmente, esto significa devolver <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. También puede ser <xref:System.Threading.Tasks.ValueTask> o <xref:System.Threading.Tasks.ValueTask%601>. Un método puede consumir y producir una secuencia asincrónica, lo que significa que devolvería <xref:System.Collections.Generic.IAsyncEnumerable%601>. El siguiente código genera una secuencia de 1 a 20, con una espera de 100 ms entre la generación de cada número:

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

Se enumeraría la secuencia mediante la instrucción `await foreach`:

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

Puede probar secuencias asincrónicas por su cuenta en nuestro tutorial sobre la [creación y consumo de secuencias asincrónicas](../tutorials/generate-consume-asynchronous-stream.md).

## <a name="indices-and-ranges"></a>Índices y rangos

Los rangos e índices proporcionan una sintaxis concisa para especificar subrangos en una matriz, <xref:System.Span%601>, o <xref:System.ReadOnlySpan%601>.

Puede especificar un índice **desde el final**. Para especificar **desde el final**, puede usar el operador `^`. Está familiarizado con `array[2]` lo que significa el elemento "2 desde el principio". Ahora, `array[^2]` significa el elemento "2 desde el final". El índice `^0` significa "el final" o el índice que sigue al último elemento.

Puede especificar un **rango** con el **operador de rango**: `..`. Por ejemplo, `0..^0` especifica el rango completo de la matriz: 0 desde el principio hasta, pero sin incluir 0 desde el final. Cualquier operando puede usar "desde el principio" o "desde el final". Además, se puede omitir cualquier operando. Los valores predeterminados son `0` para el índice de inicio y `^0` para el índice de final.

Veamos algunos ejemplos. Tenga en cuenta la siguiente matriz, anotada con su índice desde el principio y desde el final:

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};
```

El índice de cada elemento refuerza el concepto de "desde el inicio" y "desde el final", y que los rangos son exclusivos del final del rango. El "inicio" de toda la matriz es el primer elemento. El "final" de toda la matriz es *pasado* el último elemento.

Puede recuperar la última palabra con el índice `^1`:

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

El siguiente código crea un subrango con las palabras "quick", "brown" y "fox". Va de `words[1]` a `words[3]`. El elemento `words[4]` no está en el rango.

```csharp
var brownFox = words[1..4];
```

El siguiente código crea un subrango con "lazy" y "dog". Incluye `words[^2]` y `words[^1]`. El índice del final `words[^0]` no se incluye:

```csharp
var lazyDog = words[^2..^0];
```

En los ejemplos siguientes se crean rangos con final abierto para el inicio, el final o ambos:

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

También puede declarar rangos como variables:

```csharp
Range phrase = 1..4;
```

El rango se puede usar luego dentro de los caracteres `[` y `]`:

```csharp
var text = words[phrase];
```
