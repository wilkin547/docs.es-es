---
title: 'Tabla de tipos enteros: Referencia de C#'
ms.custom: seodec18
description: Información general sobre los tipos enteros de C#
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 1815f057e5cf26d64e5ff151f161cc56214efc1b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237992"
---
# <a name="integral-types-table-c-reference"></a>Tabla de tipos enteros (Referencia de C#)

En la siguiente tabla, se muestran los tamaños e intervalos de los tipos enteros, que constituyen un subconjunto de tipos simples.  
  
|Tipo|Intervalo|Tamaño|  
|----------|-----------|----------|  
|[sbyte](sbyte.md)|De -128 a 127|Entero de 8 bits con signo|  
|[byte](byte.md)|De 0 a 255|Entero de 8 bits sin signo|  
|[char](char.md)|U+0000 a U+ffff|Carácter Unicode de 16 bits|  
|[short](short.md)|De -32 768 a 32 767|Entero de 16 bits con signo|  
|[ushort](ushort.md)|De 0 a 65.535|Entero de 16 bits sin signo|  
|[int](int.md)|De -2.147.483.648 a 2.147.483.647|Entero de 32 bits con signo|  
|[uint](uint.md)|De 0 a 4.294.967.295|Entero de 32 bits sin signo|  
|[long](long.md)|De -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|Entero de 64 bits con signo|  
|[ulong](ulong.md)|De 0 a 18.446.744.073.709.551.615|Entero de 64 bits sin signo|  

## <a name="remarks"></a>Comentarios
  
Si el valor que representa un literal entero supera <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, se produce un error de compilación [CS1021](../../misc/cs1021.md).

Use la clase <xref:System.Numerics.BigInteger?displayProperty=nameWithType> para representar un entero con signo arbitrariamente grande.
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tablas de referencia para tipos](reference-tables-for-types.md)
- [Tabla de tipos de punto flotante](floating-point-types-table.md)
- [Tabla de valores predeterminados](default-values-table.md)
- [Tabla de formatos de presentación para valores numéricos](formatting-numeric-results-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
