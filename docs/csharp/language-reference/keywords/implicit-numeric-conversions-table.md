---
title: 'Tabla de conversiones numéricas implícitas: Referencia de C#'
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 516505ccacfd2a8a5c275b0de033e1316fa06d3a
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661336"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabla de conversiones numéricas implícitas (Referencia de C#)

En la tabla siguiente se muestran las conversiones implícitas predefinidas entre tipos numéricos de .NET.
  
|De|En|  
|----------|--------|  
|[sbyte](../builtin-types/integral-numeric-types.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|  
|[byte](../builtin-types/integral-numeric-types.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[short](../builtin-types/integral-numeric-types.md)|`int`, `long`, `float`, `double` o `decimal`|  
|[ushort](../builtin-types/integral-numeric-types.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[int](../builtin-types/integral-numeric-types.md)|`long`, `float`, `double` o `decimal`|  
|[uint](../builtin-types/integral-numeric-types.md)|`long`, `ulong`, `float`, `double` o `decimal`|  
|[long](../builtin-types/integral-numeric-types.md)|`float`, `double`o `decimal`|  
|[ulong](../builtin-types/integral-numeric-types.md)|`float`, `double`o `decimal`|  
|[float](../builtin-types/floating-point-numeric-types.md)|`double`|  
  
## <a name="remarks"></a>Comentarios  

- Cualquier [tipo entero](../builtin-types/integral-numeric-types.md) es implícitamente convertible en cualquier [tipo de punto flotante](../builtin-types/floating-point-numeric-types.md).

- Es posible que en las conversiones de `int`, `uint`, `long` o `ulong` en `float` y de `long` o `ulong` en `double` se pierda la precisión, pero no la magnitud.  
  
- No hay ninguna conversión implícita a los tipos `char`, `byte` y `sbyte`.  

- No hay ninguna conversión implícita de los tipos `double` y `decimal`.
  
- No hay ninguna conversión implícita entre el tipo `decimal` y el tipo `float` o `double`.  
  
- Un valor de una expresión constante de tipo `int` (por ejemplo, un valor representado por un literal entero) se puede convertir en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que esté dentro del intervalo del tipo de destino:

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

Para obtener más información sobre las conversiones implícitas, vea la sección [Conversiones implícitas](~/_csharplang/spec/conversions.md#implicit-conversions) de la [Especificación del lenguaje C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Tipos enteros](../builtin-types/integral-numeric-types.md)
- [Tabla de tipos de punto flotante](../builtin-types/floating-point-numeric-types.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
