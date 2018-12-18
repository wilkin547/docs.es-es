---
title: 'short: Referencia de C#'
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: 8c38a4158f627f41d1667eb96478cd499de78772
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238904"
---
# <a name="short-c-reference"></a>short (Referencia de C#)

`short` denota un tipo de datos integral que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.

|Tipo|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------------------|
|`short`|De -32 768 a 32 767|Entero de 16 bits con signo|<xref:System.Int16?displayProperty=nameWithType>|

## <a name="literals"></a>Literales

Puede declarar e inicializar una variable `short` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.  Si el literal entero está fuera del intervalo de `short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.

En el ejemplo siguiente, los enteros que equivalen a 1034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](int.md) a valores `short`.

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]

> [!NOTE]
> Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario. Los literales decimales no tienen prefijo.

A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad.

- C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.
- C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo. Un literal decimal no puede tener un carácter de subrayado inicial.

A continuación se muestran algunos ejemplos.

[!code-csharp[Short](~/samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]

## <a name="compiler-overload-resolution"></a>Resolución de sobrecarga del compilador

Debe usarse una conversión de tipos al llamar a métodos sobrecargados. Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `short` e [int](int.md):

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(short s) {}
```

El uso de la conversión `short` garantiza que se llama al tipo correcto, por ejemplo:

```csharp
SampleMethod(5);         // Calling the method with the int parameter
SampleMethod((short)5);  // Calling the method with the short parameter
```

## <a name="conversions"></a>Conversiones

Existe una conversión implícita predefinida de `short` a [int](int.md), [long](long.md), [float](float.md), [double](double.md) o [decimal](decimal.md).

No se pueden convertir implícitamente tipos numéricos no literales cuyo tamaño de almacenamiento sea superior a `short` (vea [Tabla de tipos enteros](integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros). Considere, por ejemplo, las dos siguientes variables de `short`, `x` e `y`:

```csharp
short x = 5, y = 12;
```

La instrucción de asignación siguiente produce un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa como [int](int.md) de manera predeterminada.

```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

Para corregir este problema, use una conversión:

```csharp
short z  = (short)(x + y);   // Explicit conversion
```

También es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:

```csharp
int m = x + y;
long n = x + y;
```

No existe conversión implícita de tipos de punto flotante a `short`. Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:

```csharp
short x = 3.0;          // Error: no implicit conversion from double
short y = (short)3.0;   // OK: explicit conversion
```

Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](float.md) y [double](double.md).

Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Tipos enteros](~/_csharplang/spec/types.md#integral-types) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.

## <a name="see-also"></a>Vea también

- <xref:System.Int16>
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tabla de tipos enteros](integral-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)