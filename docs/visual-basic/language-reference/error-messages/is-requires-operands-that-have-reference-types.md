---
title: '&#39;Es&#39; requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 07838e62bd6b180f7dece79355ea7aa1d6c4527a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585585"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="86a59-102">&#39;Es&#39; requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="86a59-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="86a59-103">El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="86a59-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="86a59-104">Esta comparación no está definida para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="86a59-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="86a59-105">**Id. de error:** BC30020</span><span class="sxs-lookup"><span data-stu-id="86a59-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="86a59-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="86a59-106">To correct this error</span></span>  
  
-   <span data-ttu-id="86a59-107">Utilice el operador de comparación aritmética adecuado o `Like` operador para comparar dos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="86a59-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a59-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="86a59-108">See Also</span></span>  
 [<span data-ttu-id="86a59-109">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="86a59-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="86a59-110">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="86a59-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="86a59-111">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="86a59-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
