---
title: Operador -&gt; (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: fb95e508ce1339868723bcc3178851e8c1355c1f
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271252"
---
# <a name="-gt-operator-c-reference"></a>Operador -&gt; (Referencia de C#)
El operador `->` combina la desreferenciación del puntero y el acceso a miembros.  
  
## <a name="remarks"></a>Comentarios  
 Una expresión con el formato,  
  
```csharp  
x->y  
```  
  
 (donde `x` es un puntero de tipo `T*` y `y` es un miembro de `T`) es equivalente a,  
  
```csharp  
(*x).y  
```  
  
 El operador `->` solo puede usarse en código que esté marcado como [no seguro](../../../csharp/language-reference/keywords/unsafe.md).  
  
 El operador `->` no se puede sobrecargar.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)
