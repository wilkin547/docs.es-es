---
title: Tipos numéricos enteros - Referencia de C#
description: Obtenga información sobre el intervalo, el tamaño de almacenamiento y el uso de cada uno de los tipos numéricos enteros.
ms.date: 06/25/2019
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
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236076"
---
# <a name="integral-numeric-types--c-reference"></a>Tipos numéricos enteros (referencia de C#)

Los **tipos numéricos enteros** son un subconjunto de **tipos simples** y se pueden inicializar con [*literales*](#integral-literals). Todos los tipos enteros también son tipos de valor. Todos los tipos numéricos enteros admiten operadores [aritméticos](../operators/arithmetic-operators.md), [lógicos bit a bit](../operators/bitwise-and-shift-operators.md), de [comparación e igualdad](../operators/equality-operators.md).

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

## <a name="integral-literals"></a>Literales enteros

Los literales enteros pueden especificarse como *literales decimales*, *literales hexadecimales* o *literales binarios*. A continuación se muestra un ejemplo de cada uno:

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

Los literales decimales no requieren ningún prefijo. El prefijo `x` o `X` significa un *literal hexadecimal*. El prefijo `b` o `B` significa un *literal binario*. La declaración de `binaryLiteral` muestra el uso de `_` como un *separador de dígitos*. El separador de dígitos también se puede usar con todos los literales numéricos. Los literales binarios y el separador de dígitos `_` se admiten a partir de C# 7.0.

### <a name="literal-suffixes"></a>Sufijos literales

El sufijo `l` o `L` especifica que el literal entero debe ser del tipo `long`. El sufijo `ul` o `UL` especifica el tipo `ulong`. Si el sufijo `L` se usa en un literal que es mayor de 9 223 372 036 854 775 807 (el valor máximo de `long`), el valor se convierte en el tipo `ulong`. Si el valor que representa un literal integral supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación [CS1021](../../misc/cs1021.md). 

> [!NOTE]
> Puede usar la letra minúscula "l" como sufijo, aunque esto genera una advertencia del compilador porque la letra "l" se confunde fácilmente con el dígito "1". Use "L" para mayor claridad.

### <a name="type-of-an-integral-literal"></a>Tipo de un literal entero

Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:

1. `int`
1. `uint`
1. `long`
1. `ulong`

Puede convertir un literal entero en un tipo con un rango menor que el valor predeterminado mediante una asignación o una conversión:

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

Puede convertir un literal entero en un tipo con un rango mayor que el valor predeterminado mediante una asignación, una conversión o un sufijo en el literal:

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a>Conversiones

Hay una conversión implícita (llamada *conversión de ampliación*) entre los dos tipos enteros donde el tipo de destino puede almacenar todos los valores del tipo de origen. Por ejemplo, hay una conversión implícita de `int` a `long` porque el rango de valores de `int` es un subconjunto apropiado de `long`. Hay conversiones implícitas de un tipo entero sin signo más pequeño en un tipo entero con signo de mayor tamaño. También hay una conversión implícita de cualquier tipo entero en cualquier tipo de punto flotante.  No hay ninguna conversión implícita de ningún tipo entero con signo en ningún tipo entero sin signo.

Debe usar una conversión explícita para convertir un tipo entero en otro tipo entero cuando no se define una conversión implícita del tipo de origen en el tipo de destino. Esto se denomina *conversión de restricción*. El caso explícito es necesario porque la conversión puede producir pérdida de datos.

## <a name="see-also"></a>Vea también

- [Especificación del lenguaje C# - Tipos enteros](~/_csharplang/spec/types.md#integral-types)
- [Referencia de C#](../index.md)
- [Tipos de punto flotante](floating-point-numeric-types.md)
- [Tabla de valores predeterminados](../keywords/default-values-table.md)
- [Tabla de formatos de presentación para valores numéricos](../keywords/formatting-numeric-results-table.md)
- [Tabla de tipos integrados](../keywords/built-in-types-table.md)
- [Valores numéricos en .NET](../../../standard/numerics.md)
