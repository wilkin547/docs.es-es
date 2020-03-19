---
title: Patrones activos
description: Aprenda a utilizar patrones activos para definir particiones con nombre que subdividen los datos de entrada en el lenguaje de programación de F .
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187059"
---
# <a name="active-patterns"></a>Patrones activos

*Los patrones activos* le permiten definir particiones con nombre que subdividen los datos de entrada, de modo que pueda usar estos nombres en una expresión de coincidencia de patrones tal como lo haría para una unión discriminada. Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.

## <a name="syntax"></a>Sintaxis

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>Observaciones

En la sintaxis anterior, los identificadores son nombres para las particiones de los datos de entrada representados por argumentos o, en otras *palabras,* nombres para subconjuntos del conjunto de todos los valores de los argumentos. Puede haber hasta siete particiones en una definición de patrón activo. La *expresión* describe el formulario en el que se descomponen los datos. Puede utilizar una definición de patrón activa para definir las reglas para determinar a cuál de las particiones con nombre pertenecen los valores dados como argumentos. Los símbolos (a) se conocen como clips de *plátano* y la función creada por este tipo de enlace let se denomina *reconocedor activo.*

Por ejemplo, considere el siguiente patrón activo con un argumento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Puede utilizar el patrón activo en una expresión de coincidencia de patrones, como en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

La salida de este programa es la siguiente:

```console
7 is odd
11 is odd
32 is even
```

Otro uso de patrones activos es descomponer los tipos de datos de varias maneras, como cuando los mismos datos subyacentes tienen varias representaciones posibles. Por ejemplo, `Color` un objeto podría descomponerse en una representación RGB o una representación HSB.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

La salida del programa anterior es la siguiente:

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

En combinación, estas dos formas de usar patrones activos le permiten particionar y descomponer datos en solo el formulario adecuado y realizar los cálculos adecuados en los datos adecuados en la forma más conveniente para el cálculo.

Las expresiones de coincidencia de patrones resultantes permiten que los datos se escriban de una manera conveniente que sea muy legible, lo que simplifica en gran medida el código de bifurcación y análisis de datos potencialmente complejo.

## <a name="partial-active-patterns"></a>Patrones activos parciales

A veces, solo necesita particionar una parte del espacio de entrada. En ese caso, se escribe un conjunto de patrones parciales cada uno de los cuales coincide con algunas entradas, pero no coinciden con otras entradas. Los patrones activos que no siempre producen un valor se denominan *patrones activos parciales;* tienen un valor devuelto que es un tipo de opción. Para definir un patrón activo parcial,\_utilice un carácter comodín ( ) al final de la lista de patrones dentro de los clips de plátano. El código siguiente ilustra el uso de un patrón activo parcial.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

La salida del ejemplo anterior es la siguiente:

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Cuando se utilizan patrones activos parciales, a veces las opciones individuales pueden ser desarticuladas o mutuamente excluyentes, pero no es necesario que lo sean. En el ejemplo siguiente, el patrón Square y el patrón Cube no están desarticulados, porque algunos números son cuadrados y cubos, como 64. El siguiente programa utiliza el patrón AND para combinar los patrones Square y Cube. Imprime todos los enteros de hasta 1000 que son cuadrados y cubos, así como los que son solo cubos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

La salida es como sigue:

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a>Patrones activos parametrizados

Los patrones activos siempre toman al menos un argumento para el elemento que se va a coincidir, pero también pueden tomar argumentos adicionales, en cuyo caso se aplica el *patrón activo con parámetros* de nombre. Los argumentos adicionales permiten especializar un patrón general. Por ejemplo, los patrones activos que usan expresiones regulares para analizar cadenas a menudo incluyen la `Integer` expresión regular como un parámetro adicional, como en el código siguiente, que también usa el patrón activo parcial definido en el ejemplo de código anterior. En este ejemplo, se proporcionan cadenas que utilizan expresiones regulares para varios formatos de fecha para personalizar el patrón activo general de ParseRegex. El patrón activo entero se utiliza para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor DateTime.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

La salida del código anterior es la siguiente:

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Los patrones activos no están restringidos solo a las expresiones de coincidencia de patrones, también puede usarlos en enlaces let.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

La salida del código anterior es la siguiente:

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje f](index.md)
- [Expresiones de coincidencia](match-expressions.md)
