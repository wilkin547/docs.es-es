---
title: '&#39;Es&#39; requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor &#39; &lt;typename&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 0b3f80e98087e455ec730dea8c57478528e9259c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722925"
---
# <a name="39is39-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-39lttypenamegt39"></a><span data-ttu-id="599a1-102">&#39;Es&#39; requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor &#39; &lt;typename&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="599a1-102">&#39;Is&#39; requires operands that have reference types, but this operand has the value type &#39;&lt;typename&gt;&#39;</span></span>
<span data-ttu-id="599a1-103">El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="599a1-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="599a1-104">Esta comparación no está definida para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="599a1-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="599a1-105">**Identificador de error:** BC30020</span><span class="sxs-lookup"><span data-stu-id="599a1-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="599a1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="599a1-106">To correct this error</span></span>  
  
-   <span data-ttu-id="599a1-107">Utilice el operador de comparación aritmética adecuado o `Like` operador para comparar dos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="599a1-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599a1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="599a1-108">See also</span></span>
- [<span data-ttu-id="599a1-109">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="599a1-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="599a1-110">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="599a1-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="599a1-111">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="599a1-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
