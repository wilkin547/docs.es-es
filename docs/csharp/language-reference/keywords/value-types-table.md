---
title: 'Tabla de tipos de valor: Referencia de C#'
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 2e2897ff647140b58b3a1812e153a44a6fcdaef7
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859558"
---
# <a name="value-types-table-c-reference"></a>Tabla de tipos de valor (referencia de C#)

En la tabla siguiente se muestran los tipos de valor de C#:

|Tipo de valor|Categoría|Sufijo de tipo|
|----------------|--------------|-----------------|
|[bool](bool.md)|Booleano||
|`byte`|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)
|`decimal`|Numérico, [punto flotante](../builtin-types/floating-point-numeric-types.md)|M o m|
|`double`|Numérico, [punto flotante](../builtin-types/floating-point-numeric-types.md)|D o d|
|[enum](enum.md)|Enumeración||
|`float`|Numérico, [punto flotante](../builtin-types/floating-point-numeric-types.md)|F o f|
|`int`|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|`long`|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)|L o l|
|`sbyte`|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|`short`|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Estructura definida por el usuario||
|`uint`|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)|U o u|
|`ulong`|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU o lu|
|`ushort`|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||

## <a name="remarks"></a>Comentarios

Use un sufijo de tipo para especificar un tipo de un literal numérico. Por ejemplo:

```csharp
decimal a = 0.1M;
```

Si un [literal numérico entero](~/_csharplang/spec/lexical-structure.md#integer-literals) no tiene sufijo, tiene el primero de los siguientes tipos en el que se puede representar su valor: `int`, `uint`, `long`, `ulong`.

Si un [literal numérico real](~/_csharplang/spec/lexical-structure.md#real-literals) no tiene sufijo, es de tipo `double`.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Tabla de valores predeterminados](default-values-table.md)
- [Tipos de valor](value-types.md)
- [Tabla de formatos de presentación para valores numéricos](formatting-numeric-results-table.md)
