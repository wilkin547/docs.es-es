---
title: Patrones activos
description: 'Obtenga información sobre cómo usar patrones activos para definir particiones con nombre que subdividen los datos de entrada en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 7b6da38baa35f30ae6de8a930be60a4e4fc0fc0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493898"
---
# <a name="active-patterns"></a>Patrones activos

Los *modelos activos* permiten definir particiones con nombre que subdividen los datos de entrada, de modo que puede usar estos nombres en una expresión de coincidencia de patrones de la misma forma que lo haría para una Unión discriminada. Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.

## <a name="syntax"></a>Sintaxis

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch = expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, los identificadores son nombres para las particiones de los datos de entrada que se representan mediante *argumentos*o, en otras palabras, nombres para subconjuntos del conjunto de todos los valores de los argumentos. Puede haber hasta siete particiones en una definición de modelo activo. La *expresión* describe el formulario en el que se descomponen los datos. Puede usar una definición de modelo activa para definir las reglas para determinar a qué particiones con nombre se encuentran los valores especificados como argumentos. Los símbolos (| y |) se conocen como *clips de banana* y la función creada por este tipo de enlace Let se denomina *reconocedor activo*.

Como ejemplo, considere el siguiente patrón activo con un argumento.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Puede usar el modelo activo en una expresión de coincidencia de patrones, como en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

La salida de este programa es la siguiente:

```console
7 is odd
11 is odd
32 is even
```

Otro uso de los patrones activos es descomponer los tipos de datos de varias maneras, por ejemplo, cuando los mismos datos subyacentes tienen varias representaciones posibles. Por ejemplo, un `Color` objeto se puede descomponer en una representación RGB o en una representación HSB.

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

En combinación, estas dos maneras de utilizar los modelos activos permiten particionar y descomponer los datos en el formulario adecuado y realizar los cálculos adecuados en los datos adecuados en el formulario más conveniente para el cálculo.

Las expresiones de coincidencia de patrones resultantes permiten escribir datos de una manera cómoda que sea muy legible, lo que simplifica considerablemente la bifurcación y el código de análisis de datos potencialmente complejos.

## <a name="partial-active-patterns"></a>Modelos activos parciales

A veces, solo necesita crear particiones de parte del espacio de entrada. En ese caso, se escribe un conjunto de patrones parciales cada uno de los cuales coinciden con algunas entradas pero no coinciden con otras entradas. Los modelos activos que no siempre generan un valor se denominan *modelos activos parciales*. tienen un valor devuelto que es un tipo de opción. Para definir un modelo activo parcial, se usa un carácter comodín ( \_ ) al final de la lista de patrones dentro de los clips de banana. En el código siguiente se muestra el uso de un modelo activo parcial.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

La salida del ejemplo anterior es la siguiente:

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Cuando se usan modelos activos parciales, algunas veces las opciones individuales pueden ser disjuntas o excluidas mutuamente, pero no es necesario. En el ejemplo siguiente, el cuadrado de patrón y el cubo de patrón no están separados, porque algunos números son cuadrados y cubos, como 64. En el siguiente programa se usa el patrón y para combinar los patrones de cuadrados y de cubo. Imprime todos los enteros hasta 1000 que son cuadrados y cubos, así como aquellos que son solo cubos.

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

## <a name="parameterized-active-patterns"></a>Modelos activos con parámetros

Los modelos activos siempre toman al menos un argumento para el elemento que se está coincidentendo, pero también pueden tomar argumentos adicionales, en cuyo caso se aplica el nombre del *modelo activo parametrizado* . Los argumentos adicionales permiten que un patrón general esté especializado. Por ejemplo, los patrones activos que usan expresiones regulares para analizar cadenas suelen incluir la expresión regular como parámetro adicional, como en el código siguiente, que también usa el modelo activo parcial `Integer` definido en el ejemplo de código anterior. En este ejemplo, se proporcionan cadenas que usan expresiones regulares para varios formatos de fecha para personalizar el modelo activo ParseRegex general. El modelo activo entero se usa para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor DateTime.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

La salida del código anterior es la siguiente:

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Los modelos activos no se limitan solo a las expresiones de coincidencia de patrones, sino que también se pueden usar en los enlaces Let.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

La salida del código anterior es la siguiente:

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Consulte también:

- [Referencia del lenguaje F#](index.md)
- [Expresiones de coincidencia](match-expressions.md)
