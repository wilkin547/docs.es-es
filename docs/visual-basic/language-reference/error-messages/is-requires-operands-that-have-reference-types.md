---
title: '&#39; es &#39; requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28d017a566fdc1e55cb53ce907641d6bccfb354c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="35538-102">&#39; es &#39; requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="35538-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="35538-103">El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="35538-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="35538-104">Esta comparación no está definida para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="35538-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="35538-105">**Id. de error:** BC30020</span><span class="sxs-lookup"><span data-stu-id="35538-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="35538-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="35538-106">To correct this error</span></span>  
  
-   <span data-ttu-id="35538-107">Utilice el operador de comparación aritmética adecuado o `Like` operador para comparar dos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="35538-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35538-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="35538-108">See Also</span></span>  
 [<span data-ttu-id="35538-109">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="35538-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="35538-110">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="35538-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="35538-111">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="35538-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
