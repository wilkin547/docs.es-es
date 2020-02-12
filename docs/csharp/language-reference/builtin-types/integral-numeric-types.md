---
title: Tipos numéricos enteros - Referencia de C#
description: Obtenga información sobre el intervalo, el tamaño de almacenamiento y el uso de cada uno de los tipos numéricos enteros.
ms.date: 10/22/2019
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
ms.openlocfilehash: 394a809a9a2f45f4aee652d0eca892f62f0f2e54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093206"
---
# <a name="integral-numeric-types--c-reference"></a>Tipos numéricos enteros (referencia de C#)

Los *tipos numéricos integrales* representan números enteros. Todos los tipos numéricos integrales son [tipos de valor](value-types.md). También son [tipos simples](value-types.md#built-in-value-types) y se pueden inicializar con [literales](#integer-literals). Todos los tipos numéricos enteros admiten operadores [aritméticos](../operators/arithmetic-operators.md), [lógicos bit a bit](../operators/bitwise-and-shift-operators.md), de [comparación](../operators/comparison-operators.md) y de [igualdad](../operators/equality-operators.md).

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

Si el tipo determinado de un literal entero es `int` y el valor que representa el literal está dentro del rango del tipo de destino, el valor se puede convertir de forma implícita en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`:

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

Puede convertir un tipo numérico entero en cualquier otro tipo numérico entero. Si el tipo de destino puede almacenar todos los valores del tipo de origen, la conversión es implícita. De lo contrario, se necesita usar el [operador de conversión `()`](../operators/type-testing-and-cast.md#cast-operator-) para invocar una conversión explícita. Para obtener más información, consulte [Conversiones numéricas integradas](numeric-conversions.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):

- [Tipos enteros](~/_csharplang/spec/types.md#integral-types)
- [Literales enteros](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de valor](value-types.md)
- [Tipos de punto flotante](floating-point-numeric-types.md)
- [Cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md)
- [Valores numéricos en .NET](../../../standard/numerics.md)
