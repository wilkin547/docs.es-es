---
description: "Más información sobre: BC30020: ' is ' requiere operandos que tengan tipos de referencia, pero este operando tiene el tipo de valor ' <typename> '"
title: "'Is' requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor '<typename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: f05040c6174f4b1edd006d1302f0d94b871d1cd9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427549"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="426a9-103">BC30020: ' is ' requiere operandos que tengan tipos de referencia, pero este operando tiene el tipo de valor ' \<typename> '</span><span class="sxs-lookup"><span data-stu-id="426a9-103">BC30020: 'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>

<span data-ttu-id="426a9-104">El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="426a9-104">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="426a9-105">Esta comparación no está definida para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="426a9-105">This comparison is not defined for value types.</span></span>

 <span data-ttu-id="426a9-106">**Identificador de error:** BC30020</span><span class="sxs-lookup"><span data-stu-id="426a9-106">**Error ID:** BC30020</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="426a9-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="426a9-107">To correct this error</span></span>

- <span data-ttu-id="426a9-108">Utilice el operador de comparación aritmética adecuado o el `Like` operador para comparar dos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="426a9-108">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>

## <a name="see-also"></a><span data-ttu-id="426a9-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="426a9-109">See also</span></span>

- [<span data-ttu-id="426a9-110">Operador Is</span><span class="sxs-lookup"><span data-stu-id="426a9-110">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="426a9-111">Like (Operador)</span><span class="sxs-lookup"><span data-stu-id="426a9-111">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="426a9-112">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="426a9-112">Comparison Operators</span></span>](../operators/comparison-operators.md)
