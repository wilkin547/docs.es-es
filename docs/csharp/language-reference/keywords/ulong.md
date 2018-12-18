---
title: ulong (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
ms.openlocfilehash: 97db22612e900658746f40cd117ff941135027a1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235025"
---
# <a name="ulong-c-reference"></a>ulong (Referencia de C#)

La palabra clave `ulong` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.

|Tipo|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------------------|
|`ulong`|De 0 a 18.446.744.073.709.551.615|Entero de 64 bits sin signo|<xref:System.UInt64?displayProperty=nameWithType>|

## <a name="literals"></a>Literales

Puede declarar e inicializar una variable `ulong` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.  Si el literal entero está fuera del intervalo de `ulong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ulong`.

[!code-csharp[ulong](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]

> [!NOTE]
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo.

A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad:

- C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.
- C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo. Un literal decimal no puede tener un carácter de subrayado inicial.

A continuación se muestran algunos ejemplos.

[!code-csharp[long](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]

Los literales enteros también pueden incluir un sufijo que denote el tipo. El sufijo `UL` o `ul` identifica de manera inequívoca un literal numérico como un valor `ulong`. El sufijo `L` denota un `ulong` si el valor literal supera <xref:System.Int64.MaxValue?displayProperty=nameWithType>. Y el sufijo `U` o `u` denota un `ulong` si el valor literal supera <xref:System.UInt32.MaxValue?displayProperty=nameWithType>. En el ejemplo siguiente se usa el sufijo `ul` para denotar un entero largo:

[!code-csharp[ulsuffix](~/samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:

1. [int](int.md)
2. [uint](uint.md)
3. [long](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a>Resolución de sobrecarga del compilador

El sufijo se usa habitualmente en las llamadas a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ulong` e [int](int.md):

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(ulong l) {}
```

Si se usa un sufijo con el parámetro `ulong`, se garantiza la llamada al tipo correcto, por ejemplo:

```csharp
SampleMethod(5);    // Calling the method with the int parameter
SampleMethod(5UL);  // Calling the method with the ulong parameter
```

## <a name="conversions"></a>Conversiones

Existe una conversión implícita predefinida de `ulong` a [float](float.md), [double](double.md) o [decimal](decimal.md).

No existe conversión implícita de `ulong` a cualquier tipo entero. Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:

```csharp
long long1 = 8UL;   // Error: no implicit conversion from ulong
```

Existe una conversión implícita predefinida de [byte](byte.md), [ushort](ushort.md), [uint](uint.md) o [char](char.md) a `ulong`.

Además, no hay ninguna conversión implícita de tipos de punto flotante a `ulong`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:

```csharp
// Error -- no implicit conversion from double:
ulong x = 3.0;
// OK -- explicit conversion:
ulong y = (ulong)3.0;
```

Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](float.md) y [double](double.md).

Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- <xref:System.UInt64>
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tabla de tipos enteros](integral-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)
