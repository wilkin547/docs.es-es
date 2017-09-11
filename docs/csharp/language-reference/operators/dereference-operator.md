---
title: Operador -&gt; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ->_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f42135e43bdfc58ee64fd3465074b3f8791f8ada
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="68a77-102">Operador -&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="68a77-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="68a77-103">El operador `->` combina la desreferenciación del puntero y el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="68a77-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68a77-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68a77-104">Remarks</span></span>  
 <span data-ttu-id="68a77-105">Una expresión con el formato,</span><span class="sxs-lookup"><span data-stu-id="68a77-105">An expression of the form,</span></span>  
  
```  
x->y  
```  
  
 <span data-ttu-id="68a77-106">(donde `x` es un puntero de tipo `T*` y `y` es un miembro de `T`) es equivalente a,</span><span class="sxs-lookup"><span data-stu-id="68a77-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```  
(*x).y  
```  
  
 <span data-ttu-id="68a77-107">El operador `->` solo puede usarse en código que esté marcado como [no seguro](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="68a77-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="68a77-108">El operador `->` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="68a77-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a77-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68a77-109">Example</span></span>  
 <span data-ttu-id="68a77-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="68a77-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a77-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="68a77-111">See Also</span></span>  
 <span data-ttu-id="68a77-112">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="68a77-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="68a77-113">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="68a77-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="68a77-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="68a77-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

