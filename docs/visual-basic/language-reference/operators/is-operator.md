---
title: Is (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601955"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="92864-102">Is (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92864-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="92864-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="92864-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92864-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92864-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="92864-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="92864-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="92864-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="92864-106">Required.</span></span> <span data-ttu-id="92864-107">Cualquier `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="92864-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="92864-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="92864-108">Required.</span></span> <span data-ttu-id="92864-109">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="92864-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="92864-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="92864-110">Required.</span></span> <span data-ttu-id="92864-111">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="92864-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92864-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92864-112">Remarks</span></span>  
 <span data-ttu-id="92864-113">El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="92864-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="92864-114">Sin embargo, no realiza las comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="92864-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="92864-115">Si `object1` y `object2` ambos hacen referencia a la misma instancia objeto exacta, `result` es `True`; si no lo hacen, `result` es `False`.</span><span class="sxs-lookup"><span data-stu-id="92864-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="92864-116">`Is` También puede utilizarse con el `TypeOf` palabra clave que se va a realizar un `TypeOf`... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="92864-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92864-117">El `Is` también se utiliza la palabra clave en el [seleccione... Caso instrucción](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="92864-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92864-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92864-118">Example</span></span>  
 <span data-ttu-id="92864-119">En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="92864-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="92864-120">El resultado se asigna a un `Boolean` valor que indica si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="92864-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="92864-121">Como se muestra en el ejemplo anterior, puede usar el `Is` operador que se va a probar ambos enlazadas tempranamente y enlazada tempranamente objetos.</span><span class="sxs-lookup"><span data-stu-id="92864-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92864-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="92864-122">See Also</span></span>  
 [<span data-ttu-id="92864-123">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="92864-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="92864-124">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="92864-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="92864-125">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="92864-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="92864-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="92864-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="92864-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="92864-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="92864-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="92864-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
