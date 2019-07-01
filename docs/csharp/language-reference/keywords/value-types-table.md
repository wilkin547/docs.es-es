---
title: 'Tabla de tipos de valor: Referencia de C#'
ms.custom: seodec18
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: 98829f30c2c25c0710cf3fe044359d3c7538fe76
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424050"
---
# <a name="value-types-table-c-reference"></a>Tabla de tipos de valor (referencia de C#)

En la tabla siguiente se muestran los tipos de valor de C#:

|Tipo de valor|Categoría|Sufijo de tipo|
|----------------|--------------|-----------------|
|[bool](bool.md)|Booleano||
|[byte](../builtin-types/integral-numeric-types.md)|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|[char](char.md)|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)
)||
|[decimal](decimal.md)|Numérico, [punto flotante](floating-point-types-table.md)|M o m|
|[double](double.md)|Numérico, [punto flotante](floating-point-types-table.md)|D o d|
|[enum](enum.md)|Enumeración||
|[float](float.md)|Numérico, [punto flotante](floating-point-types-table.md)|F o f|
|[int](../builtin-types/integral-numeric-types.md)|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|[long](../builtin-types/integral-numeric-types.md)|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)|L o l|
|[sbyte](../builtin-types/integral-numeric-types.md)|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|[short](../builtin-types/integral-numeric-types.md)|Con signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||
|[struct](struct.md)|Estructura definida por el usuario||
|[uint](../builtin-types/integral-numeric-types.md)|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)|U o u|
|[ulong](../builtin-types/integral-numeric-types.md)|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)|UL, Ul, uL, ul, LU, Lu, lU o lu|
|[ushort](../builtin-types/integral-numeric-types.md)|Sin signo, numérico, [entero](../builtin-types/integral-numeric-types.md)||

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
