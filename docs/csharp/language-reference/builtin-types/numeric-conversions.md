---
title: 'Conversiones numéricas integradas: referencia de C#'
ms.date: 10/22/2019
helpviewer_keywords:
- implicit numeric conversions [C#]
- explicit numeric conversion [C#]
- numeric conversions [C#], implicit
- numeric conversions [C#], explicit
- conversions [C#], implicit numeric
- conversions [C#], explicit numeric
ms.openlocfilehash: 5380e8480c39d1940df13b2ecb50a0f394367388
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398290"
---
# <a name="built-in-numeric-conversions-c-reference"></a>Conversiones numéricas integradas (referencia de C#)

C# proporciona un conjunto de tipos numéricos [enteros](integral-numeric-types.md) y de [punto flotante](floating-point-numeric-types.md). Existe una conversión entre dos tipos numéricos, ya sea implícita o explícita. Debe usar el [operador de conversión `()`](../operators/type-testing-and-cast.md#cast-operator-) para invocar una conversión explícita.

## <a name="implicit-numeric-conversions"></a>Conversiones numéricas implícitas

En la tabla siguiente se muestran las conversiones implícitas predefinidas entre los tipos numéricos integrados:

|De|Para|
|----------|--------|
|[sbyte](integral-numeric-types.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|
|[byte](integral-numeric-types.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|
|[short](integral-numeric-types.md)|`int`, `long`, `float`, `double` o `decimal`|
|[ushort](integral-numeric-types.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|
|[int](integral-numeric-types.md)|`long`, `float`, `double` o `decimal`|
|[uint](integral-numeric-types.md)|`long`, `ulong`, `float`, `double` o `decimal`|
|[long](integral-numeric-types.md)|`float`, `double` o `decimal`|
|[ulong](integral-numeric-types.md)|`float`, `double` o `decimal`|
|[float](floating-point-numeric-types.md)|`double`|

> [!NOTE]
> Las conversiones implícitas de `int`, `uint`, `long` o `ulong` a `float` y de `long` o `ulong` a `double` pueden provocar una pérdida de precisión, pero nunca una pérdida de un orden de magnitud. El resto de conversiones numéricas implícitas nunca pierden información.

Tenga en cuenta también lo siguiente:

- Cualquier [tipo numérico entero](integral-numeric-types.md) es implícitamente convertible en cualquier [tipo numérico de punto flotante](floating-point-numeric-types.md).

- No hay ninguna conversión implícita a los tipos `byte` y `sbyte`. No hay ninguna conversión implícita de los tipos `double` y `decimal`.

- No hay ninguna conversión implícita entre el tipo `decimal` y el tipo `float` o `double`.

- Un valor de una expresión constante de tipo `int` (por ejemplo, un valor representado por un literal entero) se puede convertir implícitamente en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que esté dentro del rango del tipo de destino:

  ```csharp
  byte a = 13;
  byte b = 300;  // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

  Como se muestra en el ejemplo anterior, si el valor constante no está dentro del rango del tipo de destino, se produce el error del compilador [CS0031](../../misc/cs0031.md).

## <a name="explicit-numeric-conversions"></a>Conversiones numéricas explícitas

La siguiente tabla muestra las conversiones explícitas predefinidas entre tipos numéricos integrados para los que no hay ninguna [conversión implícita](#implicit-numeric-conversions):

|De|Para|
|----------|--------|
|[sbyte](integral-numeric-types.md)|`byte`, `ushort`, `uint` o `ulong`|
|[byte](integral-numeric-types.md)|`sbyte`|
|[short](integral-numeric-types.md)|`sbyte`, `byte`, `ushort`, `uint` o `ulong`|
|[ushort](integral-numeric-types.md)|`sbyte`, `byte` o `short`|
|[int](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`|
|[uint](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort` o `int`|
|[long](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint` o `ulong`|
|[ulong](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint` o `long`|
|[float](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong` o `decimal`|
|[double](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float` o `decimal`|
|[decimal](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float` o `double`|

> [!NOTE]
> Una conversión numérica explícita podría provocar la pérdida de datos o producir una excepción, normalmente una de tipo <xref:System.OverflowException>.

Tenga en cuenta también lo siguiente:

- Al convertir un valor de tipo entero en otro tipo entero, el resultado depende del [contexto de comprobación](../keywords/checked-and-unchecked.md) de desbordamiento. En un contexto comprobado, la conversión se realiza correctamente si el valor de origen está dentro del intervalo del tipo de destino. De lo contrario, se produce una excepción <xref:System.OverflowException>. En un contexto no comprobado, la conversión siempre se realiza correctamente y continúa así:

  - Si el tipo de origen es mayor que el tipo de destino, el valor de origen se trunca al descartar sus bits "extra" más significativos. El resultado se trata como un valor del tipo de destino.

  - Si el tipo de origen es menor que el tipo de destino, el valor de origen se amplía mediante signos o ceros para que tenga el mismo tamaño que el tipo de destino. La ampliación mediante signos se usa si el tipo de origen tiene signo; se emplea ampliación mediante ceros si el tipo de origen no tiene signo. El resultado se trata como un valor del tipo de destino.

  - Si el tipo de origen es del mismo tamaño que el tipo de destino, el valor de origen se trata como un valor del tipo de destino.

- Cuando convierte un valor `decimal` en un tipo entero, este valor se redondea hacia cero al valor entero más cercano. Si el valor entero resultante está fuera del rango del tipo de destino, se genera una excepción <xref:System.OverflowException>.

- Al convertir un valor `double` o `float` en un tipo entero, este valor se redondea hacia cero al valor entero más cercano. Si el valor entero resultante está fuera del intervalo del tipo de destino, el resultado depende del [contexto de comprobación](../keywords/checked-and-unchecked.md) de desbordamiento. En un contexto comprobado, se genera una excepción <xref:System.OverflowException>, mientras que en un contexto no comprobado, el resultado es un valor no especificado del tipo de destino.

- Cuando convierte `double` en `float`, el valor `double` se redondea al valor `float` más cercano. Si el valor `double` es demasiado pequeño o demasiado grande para adaptarse al tipo `float`, el resultado será cero o infinito.

- Cuando convierte `float` o `double` en `decimal`, el valor de origen se convierte en la representación `decimal` y se redondea al número más cercano después de la posición decimal 28 si es necesario. Dependiendo del valor que tenga el valor de origen, puede producirse uno de los siguientes resultados:

  - Si el valor de origen es demasiado pequeño para representarse como `decimal`, el resultado se convierte en cero.

  - Si el valor de origen es NaN (no es un número), infinito o demasiado grande para representarse como un `decimal`, se genera <xref:System.OverflowException>.

- Cuando se convierte `decimal` en `float` o `double`, el valor de origen se redondea al valor `float` o `double` más cercano, respectivamente.

## <a name="c-language-specification"></a>especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Conversiones numéricas implícitas](~/_csharplang/spec/conversions.md#implicit-numeric-conversions)
- [Conversiones numéricas explícitas](~/_csharplang/spec/conversions.md#explicit-numeric-conversions)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
