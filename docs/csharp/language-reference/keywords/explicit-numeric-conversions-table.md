---
title: Tabla de conversiones numéricas explícitas (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 7363df3e4b2449924222745de409fd68349b93de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218389"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Tabla de conversiones numéricas explícitas (Referencia de C#)
La conversión numérica explícita se usa para convertir cualquier tipo numérico en cualquier otro tipo numérico, para el que no existe ninguna conversión implícita, mediante una expresión de conversión. En la siguiente tabla se muestran estas conversiones.  
  
 Para obtener más información sobre las conversiones, vea [Conversiones de tipos (Guía de programación de C#)](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
|De|En|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`byte`, `ushort`, `uint`, `ulong` o `char`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`Sbyte` o `char`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` o `char`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`sbyte`, `byte`, `short` o `char`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` o `char`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` o `char`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` o `char`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` o `char`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`sbyte`, `byte`o `short`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` o `decimal`|  
|[double](../../../csharp/language-reference/keywords/double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `decimal`|  
|[decimal](../../../csharp/language-reference/keywords/decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`|  
  
## <a name="remarks"></a>Comentarios  
  
-   La conversión numérica explícita puede provocar la pérdida de precisión o que se generen excepciones.  
  
-   Cuando convierte un valor `decimal` en un tipo entero, este valor se redondea hacia cero al valor entero más cercano. Si el valor entero resultante está fuera del rango del tipo de destino, se genera una excepción <xref:System.OverflowException>.  
  
-   Cuando convierte de un valor `double` o `float` a un tipo entero, el valor se trunca. Si el valor entero resultante está fuera del rango del valor de destino, el resultado depende del contexto de comprobación de desbordamiento. En un contexto comprobado, se genera una excepción `OverflowException`, mientras que en un contexto no comprobado, el resultado es un valor no especificado del tipo de destino.  
  
-   Cuando convierte `double` en `float`, el valor `double` se redondea al valor `float` más cercano. Si el valor `double` es demasiado pequeño o demasiado grande para adaptarse al tipo de destino, el resultado será cero o infinito.  
  
-   Cuando convierte `float` o `double` en `decimal`, el valor de origen se convierte en la representación `decimal` y se redondea al número más cercano después de la posición decimal 28 si es necesario. Dependiendo del valor que tenga el valor de origen, puede producirse uno de los siguientes resultados:  
  
    -   Si el valor de origen es demasiado pequeño para representarse como `decimal`, el resultado se convierte en cero.  
  
    -   Si el valor de origen es NaN (no es un número), infinito o demasiado grande para representarse como un `decimal`, se genera `OverflowException`.  
  
-   Cuando convierte `decimal` en `float` o `double`, el valor `decimal` se redondea al valor `double` o `float` más cercano.  
  
 Para obtener más información sobre la conversión explícita, vea Explícita en la especificación del lenguaje C#. Para obtener más información sobre cómo tener acceso a la especificación, vea [Especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [Operator ()](../../../csharp/language-reference/operators/invocation-operator.md)  
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
