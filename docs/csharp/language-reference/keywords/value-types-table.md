---
title: 'Tabla de tipos de valor: Referencia de C#'
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 959d4840344ba041ae1b01fd6d202f2b53936afc
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422372"
---
# <a name="value-types-table-c-reference"></a>Tabla de tipos de valor (referencia de C#)

En la tabla siguiente se muestran los tipos de valor de C#:

|Tipo de valor|Categoría|Sufijo de tipo|
|----------------|--------------|-----------------|
|[bool](bool.md)|Booleano||
|[byte](byte.md)|Sin signo, numérico, [entero](integral-types-table.md)||
|[char](char.md)|Sin signo, numérico, [entero](integral-types-table.md)||
|[decimal](decimal.md)|Numérico, [punto flotante](floating-point-types-table.md)|M o m|
|[double](double.md)|Numérico, [punto flotante](floating-point-types-table.md)|D o d|
|[enum](enum.md)|Enumeración||
|[float](float.md)|Numérico, [punto flotante](floating-point-types-table.md)|F o f|
|[int](int.md)|Con signo, numérico, [entero](integral-types-table.md)||
|[long](long.md)|Con signo, numérico, [entero](integral-types-table.md)|L o l|
|[sbyte](sbyte.md)|Con signo, numérico, [entero](integral-types-table.md)||
|[short](short.md)|Con signo, numérico, [entero](integral-types-table.md)||
|[struct](struct.md)|Estructura definida por el usuario||
|[uint](uint.md)|Sin signo, numérico, [entero](integral-types-table.md)|U o u|
|[ulong](ulong.md)|Sin signo, numérico, [entero](integral-types-table.md)|UL, Ul, uL, ul, LU, Lu, lU o lu|
|[ushort](ushort.md)|Sin signo, numérico, [entero](integral-types-table.md)||

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
