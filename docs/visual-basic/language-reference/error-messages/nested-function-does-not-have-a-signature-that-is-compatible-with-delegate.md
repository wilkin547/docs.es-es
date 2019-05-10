---
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 912962e2ab39c4811294ccc225814b230100e12a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592016"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="14826-102">Función anidada no tiene una firma que es compatible con el delegado '\<delegatename >'</span><span class="sxs-lookup"><span data-stu-id="14826-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>
<span data-ttu-id="14826-103">Una expresión lambda se asignó a un delegado que tiene una firma incompatible.</span><span class="sxs-lookup"><span data-stu-id="14826-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="14826-104">Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.</span><span class="sxs-lookup"><span data-stu-id="14826-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 <span data-ttu-id="14826-105">Se produce el error si una expresión lambda con un argumento se declara como tipo `Del`:</span><span class="sxs-lookup"><span data-stu-id="14826-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 <span data-ttu-id="14826-106">**Identificador de error:** BC36532</span><span class="sxs-lookup"><span data-stu-id="14826-106">**Error ID:** BC36532</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14826-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="14826-107">To correct this error</span></span>  
  
- <span data-ttu-id="14826-108">Ajuste la definición del delegado o la expresión lambda asignada para que las firmas son compatibles.</span><span class="sxs-lookup"><span data-stu-id="14826-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14826-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="14826-109">See also</span></span>

- [<span data-ttu-id="14826-110">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="14826-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="14826-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="14826-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
