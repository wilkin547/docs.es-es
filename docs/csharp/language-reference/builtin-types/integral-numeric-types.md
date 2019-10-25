---
title: Tipos numéricos enteros - Referencia de C#
description: Obtenga información sobre el intervalo, el tamaño de almacenamiento y el uso de cada uno de los tipos numéricos enteros.
ms.date: 10/18/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579194"
---
# <a name="integral-numeric-types--c-reference"></a>Tipos numéricos enteros (referencia de C#)

Los **tipos numéricos enteros** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#integer-literals). Todos los tipos enteros también son tipos de valor. Todos los tipos numéricos enteros admiten operadores [aritméticos](../operators/arithmetic-operators.md), [lógicos bit a bit](../operators/bitwise-and-shift-operators.md), de [comparación](../operators/comparison-operators.md) y de [igualdad](../operators/equality-operators.md).

## <a name="characteristics-of-the-integral-types"></a>Características de los tipos enteros

C# admite los siguientes tipos enteros predefinidos:

|Palabra clave/tipo de C#|Intervalo|Tamaño|Tipo de .NET|
|----------|-----------|----------|-------------|
|`sbyte`|De -128 a 127|Entero de 8 bits con signo|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|De 0 a 255|Entero de 8 bits sin signo|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|De -32 768 a 32 767|Entero de 16 bits con signo|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|De 0 a 65.535|Entero de 16 bits sin signo|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|De -2.147.483.648 a 2.147.483.647|Entero de 32 bits con signo|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|De 0 a 4.294.967.295|Entero de 32 bits sin signo|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|Entero de 64 bits con signo|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|De 0 a 18.446.744.073.709.551.615|Entero de 64 bits sin signo|<xref:System.UInt64?displayProperty=nameWithType>|

En la tabla anterior, cada palabra clave de tipo de C# de la columna ubicada más a la izquierda es un alias del tipo de .NET correspondiente. Son intercambiables. Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:

```csharp
int a = 123;
System.Int32 b = 123;
```

El valor predeterminado de cada tipo entero es cero, `0`. Cada uno de los tipos enteros tiene las constantes `MinValue` y `MaxValue` que proporcionan el valor mínimo y máximo de ese tipo.

Use la estructura <xref:System.Numerics.BigInteger?displayProperty=nameWithType> para representar un entero con signo sin límite superior ni inferior.

## <a name="integer-literals"></a>Literales enteros

Los literales enteros pueden ser

- *decimales*: sin ningún prefijo
- *hexadecimales*: con el prefijo de `0x` o `0X`
- *binarios*: con el prefijo `0b` o `0B` (disponible en C# 7.0 y versiones posteriores)

En el código siguiente se muestra un ejemplo de cada uno de ellos:

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

En el ejemplo anterior también se muestra el uso de `_` como un *separador de dígitos*, que se admite a partir de C# 7.0. Puede usar el separador de dígitos con todos los tipos de literales numéricos.

El tipo de un literal entero viene determinado por su sufijo, como se indica a continuación:

- Si el literal no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: `int`, `uint`, `long`, `ulong`.
- Si un literal entero tiene el sufijo `U` o `u`, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: `uint`, `ulong`.
- Si un literal entero tiene el sufijo `L` o `l`, su tipo es el primero de los siguientes tipos en el que se puede representar su valor: `long`, `ulong`.

  > [!NOTE]
  > Puede usar la letra minúscula `l` como sufijo. Sin embargo, esto genera una advertencia del compilador porque la letra `l` se confunde fácilmente con el dígito `1`. Use `L` para mayor claridad.

- Si el literal tiene como sufijo `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` o `lu`, su tipo es `ulong`.

Si el valor que representa un literal entero supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación [CS1021](../../misc/cs1021.md).

El valor representado por un literal entero puede convertirse implícitamente en un tipo con un intervalo más pequeño que el tipo determinado del literal. Es posible cuando el valor está dentro del intervalo del tipo de destino:

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

Como se muestra en el ejemplo anterior, si el valor del literal no está dentro del intervalo del tipo de destino, se produce el error [CS0031](../../misc/cs0031.md) del compilador.

También puede usar una conversión para convertir el valor representado por un literal entero al tipo que no sea el tipo determinado del literal:

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a>Conversiones

Hay una conversión implícita (llamada *conversión de ampliación*) entre los dos tipos enteros donde el tipo de destino puede almacenar todos los valores del tipo de origen. Por ejemplo, hay una conversión implícita de `int` a `long` porque el rango de valores de `int` es un subconjunto apropiado de `long`. Hay conversiones implícitas de un tipo entero sin signo más pequeño en un tipo entero con signo de mayor tamaño. También hay una conversión implícita de cualquier tipo entero en cualquier tipo de punto flotante.  No hay ninguna conversión implícita de ningún tipo entero con signo en ningún tipo entero sin signo.

Debe usar una conversión explícita para convertir un tipo entero en otro tipo entero cuando no se define una conversión implícita del tipo de origen en el tipo de destino. Esto se denomina *conversión de restricción*. El caso explícito es necesario porque la conversión puede producir pérdida de datos.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Tipos enteros](~/_csharplang/spec/types.md#integral-types)
- [Literales enteros](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de punto flotante](floating-point-numeric-types.md)
- [Tabla de valores predeterminados](../keywords/default-values-table.md)
- [Tabla de formatos de presentación para valores numéricos](../keywords/formatting-numeric-results-table.md)
- [Tabla de tipos integrados](../keywords/built-in-types-table.md)
- [Valores numéricos en .NET](../../../standard/numerics.md)
