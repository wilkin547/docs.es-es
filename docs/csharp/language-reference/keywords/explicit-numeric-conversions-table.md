---
title: 'Tabla de conversiones numéricas explícitas: Referencia de C#'
ms.custom: seodec18
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 90691ae0d9de35831b7b3119493e4e9cd81720e6
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236319"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a>Tabla de conversiones numéricas explícitas (Referencia de C#)

La siguiente tabla muestra las conversiones explícitas predefinidas entre tipos numéricos de .NET para los que no hay ninguna [conversión implícita](implicit-numeric-conversions-table.md).

|De|En|  
|----------|--------|  
|[sbyte](sbyte.md)|`byte`, `ushort`, `uint`, `ulong` o `char`|  
|[byte](byte.md)|`sbyte` o `char`|  
|[short](short.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` o `char`|  
|[ushort](ushort.md)|`sbyte`, `byte`, `short` o `char`|  
|[int](int.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` o `char`|  
|[uint](uint.md)|`sbyte`, `byte`, `short`, `ushort`, `int` o `char`|  
|[long](long.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` o `char`|  
|[ulong](ulong.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` o `char`|  
|[char](char.md)|`sbyte`, `byte`o `short`|  
|[float](float.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` o `decimal`|  
|[double](double.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `decimal`|  
|[decimal](decimal.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` o `double`|  
  
## <a name="remarks"></a>Comentarios  
  
- La conversión numérica explícita puede provocar una pérdida de precisión o dar lugar a que se produzca una excepción, normalmente <xref:System.OverflowException>.  

- Al convertir un valor de tipo entero en otro tipo entero, el resultado depende del [contexto de comprobación](checked-and-unchecked.md) de desbordamiento. En un contexto comprobado, la conversión se realiza correctamente si el valor de origen está dentro del intervalo del tipo de destino. De lo contrario, se produce una excepción <xref:System.OverflowException>. En un contexto no comprobado, la conversión siempre se realiza correctamente y continúa así:

  - Si el tipo de origen es mayor que el tipo de destino, el valor de origen se trunca al descartar sus bits "extra" más significativos. El resultado se trata como un valor del tipo de destino.

  - Si el tipo de origen es menor que el tipo de destino, el valor de origen se amplía mediante signos o ceros para que tenga el mismo tamaño que el tipo de destino. La ampliación mediante signos se usa si el tipo de origen tiene signo; se emplea ampliación mediante ceros si el tipo de origen no tiene signo. El resultado se trata como un valor del tipo de destino.

  - Si el tipo de origen es del mismo tamaño que el tipo de destino, el valor de origen se trata como un valor del tipo de destino.
  
- Cuando convierte un valor `decimal` en un tipo entero, este valor se redondea hacia cero al valor entero más cercano. Si el valor entero resultante está fuera del rango del tipo de destino, se genera una excepción <xref:System.OverflowException>.  
  
- Al convertir un valor `double` o `float` en un tipo entero, este valor se redondea hacia cero al valor entero más cercano. Si el valor entero resultante está fuera del intervalo del tipo de destino, el resultado depende del [contexto de comprobación](checked-and-unchecked.md) de desbordamiento. En un contexto comprobado, se genera una excepción <xref:System.OverflowException>, mientras que en un contexto no comprobado, el resultado es un valor no especificado del tipo de destino.  
  
- Cuando convierte `double` en `float`, el valor `double` se redondea al valor `float` más cercano. Si el valor `double` es demasiado pequeño o demasiado grande para adaptarse al tipo de destino, el resultado será cero o infinito.  
  
- Cuando convierte `float` o `double` en `decimal`, el valor de origen se convierte en la representación `decimal` y se redondea al número más cercano después de la posición decimal 28 si es necesario. Dependiendo del valor que tenga el valor de origen, puede producirse uno de los siguientes resultados:  

  - Si el valor de origen es demasiado pequeño para representarse como `decimal`, el resultado se convierte en cero.  

  - Si el valor de origen es NaN (no es un número), infinito o demasiado grande para representarse como un `decimal`, se genera <xref:System.OverflowException>.  
  
- Cuando convierte `decimal` en `float` o `double`, el valor `decimal` se redondea al valor `double` o `float` más cercano.  
  
 Para obtener más información sobre las conversiones explícitas, vea la sección [Conversiones explícitas](~/_csharplang/spec/conversions.md#explicit-conversions) de la [Especificación del lenguaje C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
- [Operator ()](../operators/invocation-operator.md)
- [Tabla de tipos enteros](integral-types-table.md)
- [Tabla de tipos de punto flotante](floating-point-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md)
