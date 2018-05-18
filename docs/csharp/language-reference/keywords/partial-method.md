---
title: Método parcial (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 29b5d442a1aa33babc24aee987e749c93a5ec727
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="partial-method-c-reference"></a>Método parcial (Referencia de C#)
Un método parcial tiene su signatura definida en una parte de un tipo parcial y su implementación definida en otra parte del tipo. Los métodos parciales permiten a los diseñadores de clases proporcionar enlaces de método, similares a los controladores de eventos, que los desarrolladores pueden decidir implementar o no. Si el desarrollador no proporciona una implementación, el compilador quita la signatura en tiempo de compilación. Se aplican las siguientes condiciones a los métodos parciales:  
  
-   Las signaturas de ambas partes del tipo parcial deben coincidir.  
  
-   El método debe devolver el valor void.  
  
-   No se permiten modificadores de acceso. Los métodos parciales son privados implícitamente.  
  
 En el ejemplo siguiente se muestra un método parcial definido en dos partes de una clase parcial:  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Para obtener más información, consulte [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [partial (Tipos)](../../../csharp/language-reference/keywords/partial-type.md)
