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
ms.openlocfilehash: c4b23bb2d81d1f5272a5813123681da7406c3368
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980348"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="7f517-102">Is (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f517-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="7f517-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="7f517-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f517-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f517-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="7f517-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="7f517-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="7f517-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f517-106">Required.</span></span> <span data-ttu-id="7f517-107">Cualquier `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="7f517-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="7f517-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f517-108">Required.</span></span> <span data-ttu-id="7f517-109">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="7f517-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="7f517-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7f517-110">Required.</span></span> <span data-ttu-id="7f517-111">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="7f517-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f517-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f517-112">Remarks</span></span>  
 <span data-ttu-id="7f517-113">El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="7f517-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="7f517-114">Sin embargo, no realiza las comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="7f517-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="7f517-115">Si `object1` y `object2` ambos hacen referencia a la instancia exacta del objeto mismo, `result` es `True`; si no, es `result` es `False`.</span><span class="sxs-lookup"><span data-stu-id="7f517-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="7f517-116">`Is` También puede utilizarse con el `TypeOf` palabra clave para realizar un `TypeOf`... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="7f517-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f517-117">El `Is` también se utiliza la palabra clave en el [seleccione... Instrucción de caso](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7f517-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f517-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f517-118">Example</span></span>  
 <span data-ttu-id="7f517-119">En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="7f517-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="7f517-120">Los resultados se asignan a un `Boolean` valor que indica si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="7f517-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="7f517-121">Como se muestra en el ejemplo anterior, puede usar el `Is` operador para probar ambas enlaza de manera anticipada y los objetos enlazados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f517-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f517-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f517-122">See also</span></span>
- [<span data-ttu-id="7f517-123">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="7f517-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="7f517-124">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="7f517-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="7f517-125">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f517-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="7f517-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f517-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7f517-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="7f517-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7f517-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="7f517-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
