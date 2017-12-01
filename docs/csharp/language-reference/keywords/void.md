---
title: void (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords: void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a71cac30132417abce60cdde54322b5f2067d39d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="void-c-reference"></a>void (Referencia de C#)
Cuando se usa como tipo de valor devuelto para un método, `void` especifica que el método no devuelve un valor.

`void` no se permite en la lista de parámetros de un método. Un método que no usa parámetros y que no devuelve ningún valor se declara del siguiente modo:

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

`void` también se usa en un contexto no seguro para declarar un puntero a un tipo desconocido. Para obtener más información, vea [Tipos de puntero](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).

`void` es un alias del tipo <xref:System.Void?displayProperty=nameWithType> de .NET Framework.

## <a name="c-language-specification"></a>Especificación del lenguaje C#
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)  
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)  
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
