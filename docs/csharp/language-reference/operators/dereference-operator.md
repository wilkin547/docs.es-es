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
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45609534"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="6c92e-102">Operador -&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6c92e-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="6c92e-103">El operador `->` combina la desreferenciación del puntero y el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="6c92e-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c92e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c92e-104">Remarks</span></span>  
 <span data-ttu-id="6c92e-105">Una expresión con el formato,</span><span class="sxs-lookup"><span data-stu-id="6c92e-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="6c92e-106">(donde `x` es un puntero de tipo `T*` y `y` es un miembro de `T`) es equivalente a,</span><span class="sxs-lookup"><span data-stu-id="6c92e-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="6c92e-107">El operador `->` solo puede usarse en código que esté marcado como [no seguro](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6c92e-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="6c92e-108">El operador `->` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="6c92e-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c92e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c92e-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6c92e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c92e-110">See Also</span></span>

- [<span data-ttu-id="6c92e-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6c92e-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6c92e-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6c92e-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6c92e-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6c92e-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
