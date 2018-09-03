---
title: Tabla de conversiones numéricas implícitas (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 4bbc6086dc5fd3838ef9361762c3068ca44efd0e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43417601"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a>Tabla de conversiones numéricas implícitas (Referencia de C#)
En la tabla siguiente se muestran las conversiones numéricas implícitas predefinidas. Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.  
  
|De|En|  
|----------|--------|  
|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|`short`, `int`, `long`, `float`, `double` o `decimal`|  
|[byte](../../../csharp/language-reference/keywords/byte.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[short](../../../csharp/language-reference/keywords/short.md)|`int`, `long`, `float`, `double` o `decimal`|  
|[ushort](../../../csharp/language-reference/keywords/ushort.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[int](../../../csharp/language-reference/keywords/int.md)|`long`, `float`, `double` o `decimal`|  
|[uint](../../../csharp/language-reference/keywords/uint.md)|`long`, `ulong`, `float`, `double` o `decimal`|  
|[long](../../../csharp/language-reference/keywords/long.md)|`float`, `double`o `decimal`|  
|[char](../../../csharp/language-reference/keywords/char.md)|`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`|  
|[float](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|`float`, `double`o `decimal`|  
  
## <a name="remarks"></a>Comentarios  
  
-   Es posible que en las conversiones de `int`, `uint`, `long` o `ulong` a `float` y de `long` o `ulong` a `double` se pierda la precisión pero no la magnitud.  
  
-   No hay ninguna conversión implícita al tipo `char`.  
  
-   No hay ninguna conversión implícita entre tipos de punto flotante y el tipo `decimal`.  
  
-   Una expresión constante de tipo `int` se puede convertir a `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que el valor de la expresión constante esté dentro del intervalo del tipo de destino.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
- [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
