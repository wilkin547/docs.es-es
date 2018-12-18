---
title: uint (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- uint
- uint_CSharpKeyword
helpviewer_keywords:
- uint keyword [C#]
ms.openlocfilehash: e22468eea63ce082f2e9842e6ec307aba1888964
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241605"
---
# <a name="uint-c-reference"></a>uint (Referencia de C#)

La palabra clave `uint` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.

|Tipo|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------------------|
|`uint`|De 0 a 4.294.967.295|Entero de 32 bits sin signo|<xref:System.UInt32?displayProperty=nameWithType>|

**Nota**: El tipo `uint` no es conforme a CLS. Use `int` siempre que sea posible.

## <a name="literals"></a>Literales

Puede declarar e inicializar una variable `uint` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario. Si el literal entero está fuera del intervalo de `uint` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt32.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `uint`.

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]

> [!NOTE]
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo.

A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad:

- C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.
- C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo. Un literal decimal no puede tener un carácter de subrayado inicial.

A continuación se muestran algunos ejemplos.

[!code-csharp[uint](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]

Los literales enteros también pueden incluir un sufijo que denote el tipo. El sufijo `U` o "u" denota `uint` o `ulong`, dependiendo del valor numérico del literal. En el ejemplo siguiente se usa el sufijo `u` para denotar un entero sin signo de ambos tipos. Tenga en cuenta que el primer literal es `uint` porque su valor es inferior a <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, mientras que el segundo es `ulong` porque su valor es superior a <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.

[!code-csharp[usuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]

Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:

1. [int](int.md)
2. `uint`
3. [long](long.md)
4. [ulong](ulong.md)

## <a name="conversions"></a>Conversiones

Existe una conversión implícita predefinida de `uint` a [long](long.md), [ulong](ulong.md), [float](float.md), [double](double.md) o [decimal](decimal.md). Por ejemplo:

```csharp
float myFloat = 4294967290;   // OK: implicit conversion to float
```

Existe una conversión implícita predefinida de [byte](byte.md), [ushort](ushort.md) o [char](char.md) a `uint`. De lo contrario, debe usar una conversión. Por ejemplo, la instrucción de asignación siguiente producirá un error de compilación sin una conversión:

```csharp
long aLong = 22;
// Error -- no implicit conversion from long:
uint uInt1 = aLong;
// OK -- explicit conversion:
uint uInt2 = (uint)aLong;
```

Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `uint`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:

```csharp
// Error -- no implicit conversion from double:
uint x = 3.0;
// OK -- explicit conversion:
uint y = (uint)3.0;
```

Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](float.md) y [double](double.md).

Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- <xref:System.UInt32>
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tabla de tipos enteros](integral-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)