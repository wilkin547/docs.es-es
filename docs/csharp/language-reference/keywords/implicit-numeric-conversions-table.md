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
ms.openlocfilehash: 98774a0f7ad86e43178c6d0216e29e7b4767f3f2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235259"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabla de conversiones numéricas implícitas (Referencia de C#)

En la tabla siguiente se muestran las conversiones implícitas predefinidas entre tipos numéricos de .NET.
  
|De|En|  
|----------|--------|  
|[sbyte](sbyte.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|  
|[byte](byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[short](short.md)|`int`, `long`, `float`, `double` o `decimal`|  
|[ushort](ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[int](int.md)|`long`, `float`, `double` o `decimal`|  
|[uint](uint.md)|`long`, `ulong`, `float`, `double` o `decimal`|  
|[long](long.md)|`float`, `double`o `decimal`|  
|[char](char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[float](float.md)|`double`|  
|[ulong](ulong.md)|`float`, `double`o `decimal`|  
  
## <a name="remarks"></a>Comentarios  

- Cualquier [tipo entero](integral-types-table.md) es implícitamente convertible en cualquier [tipo de punto flotante](floating-point-types-table.md).

- Es posible que en las conversiones de `int`, `uint`, `long` o `ulong` en `float` y de `long` o `ulong` en `double` se pierda la precisión, pero no la magnitud.  
  
- No hay ninguna conversión implícita al tipo `char`.  
  
- No hay ninguna conversión implícita entre los tipos `float` y `double` y el tipo `decimal`.  
  
- Un valor de una expresión constante de tipo `int` (por ejemplo, un valor representado por un literal entero) se puede convertir en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que esté dentro del intervalo del tipo de destino:

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

Para obtener más información sobre las conversiones implícitas, vea la sección [Conversiones implícitas](~/_csharplang/spec/conversions.md#implicit-conversions) de la [Especificación del lenguaje C#](../language-specification/index.md).
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Tabla de tipos enteros](integral-types-table.md)
- [Tabla de tipos de punto flotante](floating-point-types-table.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)
- [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md)
