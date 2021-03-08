---
title: 'Procedimiento Convertir una cadena en un número: Guía de programación de C#'
description: Aprenda a convertir una cadena en un número en C# mediante la llamada a los métodos de clase Parse, TryParse o Convert.
ms.date: 02/16/2021
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.topic: how-to
ms.custom: contperf-fy21q3
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 0fffd080f502646b6541ad7b2236359e9d85b884
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103223"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Procedimiento Convertir una cadena en un número (Guía de programación de C#)

Puede convertir `string` en un número si llama al método `Parse` o `TryParse` que se encuentra en tipos numéricos (`int`, `long`, `double`, etc.), o bien mediante los métodos de la clase <xref:System.Convert?displayProperty=nameWithType>.
  
Resulta algo más eficaz y sencillo llamar a un método `TryParse` (por ejemplo, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) o un método `Parse` (por ejemplo, [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)). El uso de un método <xref:System.Convert> resulta más práctico para objetos generales que implementan <xref:System.IConvertible>.
  
Puede usar los métodos `Parse` o `TryParse` sobre el tipo numérico que espera que contenga la cadena, como el tipo <xref:System.Int32?displayProperty=nameWithType>.  El método <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> utiliza <xref:System.Int32.Parse%2A> internamente.  El método `Parse` devuelve el número convertido; el método `TryParse` devuelve un valor booleano que indica si la conversión se realizó correctamente, y devuelve el número convertido en un parámetro `out`. Si el formato de la cadena no es válido, `Parse` inicia una excepción, pero `TryParse` devuelve `false`. Cuando se llama a un método `Parse`, siempre debe usar control de excepciones para detectar un <xref:System.FormatException> cuando se produzca un error en la operación de análisis.
  
## <a name="call-parse-or-tryparse-methods"></a>Llamada a métodos Parse o TryParse

Los métodos `Parse` y `TryParse` no tienen en cuenta los espacios en blanco al principio ni al final de la cadena, pero todos los demás caracteres deben ser caracteres que formen el tipo numérico adecuado (`int`, `long`, `ulong`, `float`, `decimal`, etc.).  Si hay un espacio en blanco dentro de la cadena que forma el número, se producirá un error.  Por ejemplo, puede usar `decimal.TryParse` para analizar "10", "10,3" o "  10  ", pero no para analizar 10 en "10X", "1 0" (observe el espacio insertado), "10 ,3" (observe el espacio insertado) o "10e1" (`float.TryParse` funciona aquí), y así sucesivamente. Una cadena cuyo valor es `null` o <xref:System.String.Empty?displayProperty=nameWithType> no se puede analizar correctamente. Puede buscar una cadena nula o vacía antes de intentar analizarla mediante una llamada al método <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>.

En el siguiente ejemplo se muestran llamadas correctas e incorrectas a `Parse` y `TryParse`.

[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]

En el ejemplo siguiente se muestra un enfoque para analizar una cadena que se espera que incluya caracteres numéricos iniciales (incluidos caracteres hexadecimales) y caracteres no numéricos finales. Asigna caracteres válidos desde el principio de una cadena a una nueva cadena antes de llamar al método <xref:System.Int32.TryParse%2A>. Dado que las cadenas que va a analizar contiene pocos caracteres, el ejemplo llama al método <xref:System.String.Concat%2A?displayProperty=nameWithType> para asignar caracteres válidos a una nueva cadena. Para una cadena más larga, se puede usar la clase <xref:System.Text.StringBuilder> en su lugar.

[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]

## <a name="call-convert-methods"></a>Llamada a métodos Convert

En la siguiente tabla se muestran algunos de los métodos de la clase <xref:System.Convert> que se pueden usar para convertir una cadena en un número.

| Tipo numérico | Método                                             |
|--------------|----------------------------------------------------|
| `decimal`    | <xref:System.Convert.ToDecimal%28System.String%29> |
| `float`      | <xref:System.Convert.ToSingle%28System.String%29>  |
| `double`     | <xref:System.Convert.ToDouble%28System.String%29>  |
| `short`      | <xref:System.Convert.ToInt16%28System.String%29>   |
| `int`        | <xref:System.Convert.ToInt32%28System.String%29>   |
| `long`       | <xref:System.Convert.ToInt64%28System.String%29>   |
| `ushort`     | <xref:System.Convert.ToUInt16%28System.String%29>  |
| `uint`       | <xref:System.Convert.ToUInt32%28System.String%29>  |
| `ulong`      | <xref:System.Convert.ToUInt64%28System.String%29>  |

En este ejemplo, se llama al método <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> para convertir una cadena de entrada en un valor [int](../../language-reference/builtin-types/integral-numeric-types.md). El ejemplo detecta las dos excepciones más comunes que este método puede generar, <xref:System.FormatException> y <xref:System.OverflowException>. Si se puede incrementar el número resultante sin exceder <xref:System.Int32.MaxValue?displayProperty=nameWithType>, el ejemplo suma 1 al resultado y muestra la salida.

[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]
