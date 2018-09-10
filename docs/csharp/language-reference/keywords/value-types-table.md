---
title: Tabla de tipos de valor (referencia de C#)
ms.date: 08/24/2018
helpviewer_keywords:
- value types [C#], table
- types [C#], value types
- types [C#], suffixes
ms.assetid: 67d8f631-b6e3-4d83-9910-5ec497f8c5f3
ms.openlocfilehash: bc7143b9f006af20b0bb91203d3093410d4ac0bf
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262025"
---
# <a name="value-types-table-c-reference"></a>Tabla de tipos de valor (referencia de C#)

En la tabla siguiente se muestran los tipos de valor de C#.  
  
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

Si un [literal numérico entero](/dotnet/csharp/language-reference/language-specification/lexical-structure#integer-literals) no tiene sufijo, tiene el primero de los siguientes tipos en el que se puede representar su valor: `int`, `uint`, `long`, `ulong`.

Si un [literal numérico real](/dotnet/csharp/language-reference/language-specification/lexical-structure#real-literals) no tiene sufijo, es de tipo `double`.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Tablas de referencia para tipos](reference-tables-for-types.md)
- [Tabla de valores predeterminados](default-values-table.md)
- [Tipos de valor](value-types.md)
- [Tabla de formatos de presentación para valores numéricos](formatting-numeric-results-table.md)
