---
title: Modelos activos (F#)
description: 'Obtenga información sobre cómo usar los patrones activos para definir particiones con nombre que subdividen los datos de entrada en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4fb7d3e2b9c7e6f1c1ed9d64a47728c7f40017c8
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46006649"
---
# <a name="active-patterns"></a>Patrones activos

*Modelos activos* le permiten definir particiones con nombre que subdividen los datos de entrada, por lo que puede usar estos nombres en una expresión de coincidencia como haría para una unión discriminada. Se pueden usar patrones activos para descomponer los datos de manera personalizada para cada partición.

## <a name="syntax"></a>Sintaxis

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, los identificadores son los nombres de las particiones de los datos de entrada que se representan mediante *argumentos*, o bien, en otras palabras, los nombres de subconjuntos del conjunto de todos los valores de los argumentos. Puede haber hasta siete particiones en una definición de modelo activo. El *expresión* describe la forma en que se va a descomponer los datos. Puede usar una definición de modelo activo para definir las reglas para determinar cuál de las particiones con nombre de los valores proporcionados como argumentos pertenecen a. La (| y |) se conocen como símbolos *clips plátano* y se llama a la función creada por este tipo de enlace let un *reconocedor active*.

Por ejemplo, considere el siguiente patrón activo con un argumento.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Puede usar el modelo activo en una coincidencia de expresión, como en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

El resultado de este programa es como sigue:

```
7 is odd
11 is odd
32 is even
```

Es otro uso de modelos activos descomponer los tipos de datos de varias formas, por ejemplo, cuando los mismos datos subyacentes tienen varias representaciones posibles. Por ejemplo, un `Color` objeto se puede descomponer en una representación RGB o HSB.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

La salida del programa anterior es como sigue:

```
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

En combinación, estas dos formas de usar los patrones activos permiten a la partición y descomponen los datos en el formulario de adecuado y realizan los cálculos adecuados en los datos apropiados en la forma más conveniente para el cálculo.

Las expresiones de coincidencia de patrón resultante permiten a los datos se escriban en forma cómoda de bifurcación potencialmente complejo muy legible, lo que simplificó en gran medida y el código de análisis de datos.

## <a name="partial-active-patterns"></a>Modelos activos parciales

En ocasiones, necesitará sólo una parte del espacio de entrada de partición. En ese caso, escribe un conjunto de modelos parciales cada que coinciden con algunas entradas pero no coincide con otras entradas. Modelos activos que no generan un valor siempre se denominan *modelos activos parciales*; tienen un valor devuelto que es un tipo de opción. Para definir un modelo activo parcial, se utiliza un carácter comodín (\_) al final de la lista de modelos dentro de lo delimitadores de modelo activo. El código siguiente muestra el uso de un modelo activo parcial.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

La salida del ejemplo anterior es el siguiente:

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Al usar patrones activos parciales, en ocasiones, las opciones individuales pueden ser separados o mutuamente excluyentes, pero no se necesita. En el ejemplo siguiente, el cuadrado de patrón y el modelo del cubo no son separados, porque algunos números son cuadrados y cubos, como los 64. El siguiente programa imprime todos los enteros hasta 1000000 que son cuadrados y cubos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

La salida es la siguiente:

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a>Modelos activos con parámetros

Modelos activos siempre tienen al menos un argumento para el elemento que se coteja, pero es posible que tarden argumentos adicionales, en cuyo caso el nombre *modelo activo parametrizado* se aplica. Argumentos adicionales permiten un patrón general estar especializados. Por ejemplo, los patrones activos que utilizan expresiones regulares para analizar cadenas suelen incluyen la expresión regular como un parámetro adicional, como se muestra en el código siguiente, que también usa el patrón activo parcial `Integer` definido en el ejemplo de código anterior. En este ejemplo, se proporcionan las cadenas que usan expresiones regulares para varios formatos de fecha para personalizar el activo ParseRegex general. El modelo activo de entero se utiliza para convertir las cadenas coincidentes en enteros que se pueden pasar al constructor DateTime.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

La salida del código anterior es el siguiente:

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Modelos activos no se limitan únicamente a las expresiones de coincidencia de patrones, también puede usar en enlaces de let.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

La salida del código anterior es el siguiente:

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Expresiones de coincidencia](match-expressions.md)
