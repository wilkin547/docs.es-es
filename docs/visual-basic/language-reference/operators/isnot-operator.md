---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isnot
helpviewer_keywords: IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="306d1-102">IsNot (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="306d1-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="306d1-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="306d1-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="306d1-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="306d1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="306d1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="306d1-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="306d1-106">Required.</span></span> <span data-ttu-id="306d1-107">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="306d1-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="306d1-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="306d1-108">Required.</span></span> <span data-ttu-id="306d1-109">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="306d1-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="306d1-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="306d1-110">Required.</span></span> <span data-ttu-id="306d1-111">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="306d1-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="306d1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="306d1-112">Remarks</span></span>  
 <span data-ttu-id="306d1-113">El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="306d1-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="306d1-114">Sin embargo, no realiza las comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="306d1-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="306d1-115">Si `object1` y `object2` ambos hacen referencia a la misma instancia objeto exacta, `result` es `False`; si no lo hacen, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="306d1-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="306d1-116">`IsNot`es el opuesto de la `Is` operador.</span><span class="sxs-lookup"><span data-stu-id="306d1-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="306d1-117">La ventaja de `IsNot` es que puede evitar sintaxis extraña con `Not` y `Is`, que puede ser difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="306d1-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="306d1-118">Puede usar el `Is` y `IsNot` operadores a los objetos de tiempo de compilación y en tiempo de ejecución de prueba.</span><span class="sxs-lookup"><span data-stu-id="306d1-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="306d1-119">El `IsNot` no se puede usar el operador para comparar expresiones devueltas desde el `TypeOf` operador.</span><span class="sxs-lookup"><span data-stu-id="306d1-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="306d1-120">En su lugar, debe utilizar el `Not` y `Is` operadores.</span><span class="sxs-lookup"><span data-stu-id="306d1-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="306d1-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="306d1-121">Example</span></span>  
 <span data-ttu-id="306d1-122">En el ejemplo de código siguiente se utiliza la `Is` operador y el `IsNot` operador que se va a realizar la comparación de la misma.</span><span class="sxs-lookup"><span data-stu-id="306d1-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="306d1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="306d1-123">See Also</span></span>  
 [<span data-ttu-id="306d1-124">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="306d1-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="306d1-125">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="306d1-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="306d1-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="306d1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="306d1-127">Comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="306d1-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
