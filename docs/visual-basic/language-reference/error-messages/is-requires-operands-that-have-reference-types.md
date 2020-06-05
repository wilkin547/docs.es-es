---
title: "'Is' requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor '<typename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: e5acc94a3738fca3a43740bdba727fc843132aa1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402816"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="ee1c1-102">'Is' requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor '\<typename>'</span><span class="sxs-lookup"><span data-stu-id="ee1c1-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="ee1c1-103">El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="ee1c1-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="ee1c1-104">Esta comparación no está definida para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="ee1c1-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="ee1c1-105">**Identificador de error:** BC30020</span><span class="sxs-lookup"><span data-stu-id="ee1c1-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee1c1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ee1c1-106">To correct this error</span></span>  
  
- <span data-ttu-id="ee1c1-107">Utilice el operador de comparación aritmética adecuado o el `Like` operador para comparar dos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="ee1c1-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1c1-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee1c1-108">See also</span></span>

- [<span data-ttu-id="ee1c1-109">Operador is</span><span class="sxs-lookup"><span data-stu-id="ee1c1-109">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="ee1c1-110">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="ee1c1-110">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="ee1c1-111">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="ee1c1-111">Comparison Operators</span></span>](../operators/comparison-operators.md)
