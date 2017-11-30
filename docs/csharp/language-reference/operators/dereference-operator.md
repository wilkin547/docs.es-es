---
title: Operador -&gt; (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c5918f56257feb29d2624ba29b8cebaaa4f4ebe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-gt-operator-c-reference"></a>Operador -&gt; (Referencia de C#)
El operador `->` combina la desreferenciación del puntero y el acceso a miembros.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato,  
  
```  
x->y  
```  
  
 (donde `x` es un puntero de tipo `T*` y `y` es un miembro de `T`) es equivalente a,  
  
```  
(*x).y  
```  
  
 El operador `->` solo puede usarse en código que esté marcado como [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  
  
 El operador `->` no se puede sobrecargar.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)
