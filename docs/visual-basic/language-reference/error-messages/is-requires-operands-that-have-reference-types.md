---
description: "Más información sobre: BC30020: ' is ' requiere operandos que tengan tipos de referencia, pero este operando tiene el tipo de valor '<typename>"
title: "'Is' requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor '<typename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: f12d4bb4787c3d003c9afc6a0367f7f9e9248f15
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796007"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="d3db5-103">BC30020: ' is ' requiere operandos que tengan tipos de referencia, pero este operando tiene el tipo de valor ' \<typename> '</span><span class="sxs-lookup"><span data-stu-id="d3db5-103">BC30020: 'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>

<span data-ttu-id="d3db5-104">El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="d3db5-104">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="d3db5-105">Esta comparación no está definida para los tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="d3db5-105">This comparison is not defined for value types.</span></span>

 <span data-ttu-id="d3db5-106">**Identificador de error:** BC30020</span><span class="sxs-lookup"><span data-stu-id="d3db5-106">**Error ID:** BC30020</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d3db5-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d3db5-107">To correct this error</span></span>

- <span data-ttu-id="d3db5-108">Utilice el operador de comparación aritmética adecuado o el `Like` operador para comparar dos tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="d3db5-108">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3db5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3db5-109">See also</span></span>

- [<span data-ttu-id="d3db5-110">Operador Is</span><span class="sxs-lookup"><span data-stu-id="d3db5-110">Is Operator</span></span>](../operators/is-operator.md)
- [<span data-ttu-id="d3db5-111">Like (Operador)</span><span class="sxs-lookup"><span data-stu-id="d3db5-111">Like Operator</span></span>](../operators/like-operator.md)
- [<span data-ttu-id="d3db5-112">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="d3db5-112">Comparison Operators</span></span>](../operators/comparison-operators.md)
