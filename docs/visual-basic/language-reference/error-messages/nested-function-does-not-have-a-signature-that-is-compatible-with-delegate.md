---
title: Función anidada no tiene una firma que es compatible con el delegado &#39; &lt;nombredelegado&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: abfda4ee6064ec9ea54b8a3c383d10f8263a1458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506412"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a><span data-ttu-id="e1c38-102">Función anidada no tiene una firma que es compatible con el delegado &#39; &lt;nombredelegado&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="e1c38-102">Nested function does not have a signature that is compatible with delegate &#39;&lt;delegatename&gt;&#39;</span></span>
<span data-ttu-id="e1c38-103">Una expresión lambda se asignó a un delegado que tiene una firma incompatible.</span><span class="sxs-lookup"><span data-stu-id="e1c38-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="e1c38-104">Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.</span><span class="sxs-lookup"><span data-stu-id="e1c38-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="e1c38-105">Se produce el error si una expresión lambda con un argumento se declara como tipo `Del`:</span><span class="sxs-lookup"><span data-stu-id="e1c38-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="e1c38-106">**Identificador de error:** BC36532</span><span class="sxs-lookup"><span data-stu-id="e1c38-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e1c38-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e1c38-107">To correct this error</span></span>  
  
-   <span data-ttu-id="e1c38-108">Ajuste la definición del delegado o la expresión lambda asignada para que las firmas son compatibles.</span><span class="sxs-lookup"><span data-stu-id="e1c38-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c38-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1c38-109">See also</span></span>
- [<span data-ttu-id="e1c38-110">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="e1c38-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="e1c38-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="e1c38-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
