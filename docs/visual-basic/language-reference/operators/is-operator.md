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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917215"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="e40f1-102">Is (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e40f1-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="e40f1-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="e40f1-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e40f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e40f1-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="e40f1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e40f1-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="e40f1-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e40f1-106">Required.</span></span> <span data-ttu-id="e40f1-107">Cualquier `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="e40f1-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="e40f1-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e40f1-108">Required.</span></span> <span data-ttu-id="e40f1-109">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="e40f1-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="e40f1-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="e40f1-110">Required.</span></span> <span data-ttu-id="e40f1-111">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="e40f1-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e40f1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e40f1-112">Remarks</span></span>  
 <span data-ttu-id="e40f1-113">El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="e40f1-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="e40f1-114">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="e40f1-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="e40f1-115">Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto `result` exacta `True`, es; si no es `result` así `False`, es.</span><span class="sxs-lookup"><span data-stu-id="e40f1-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="e40f1-116">`Is`también se puede usar con la `TypeOf` palabra clave para `TypeOf`crear... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="e40f1-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e40f1-117">La `Is` palabra clave también se usa en la [selección... Instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e40f1-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e40f1-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e40f1-118">Example</span></span>  
 <span data-ttu-id="e40f1-119">En el ejemplo siguiente se `Is` usa el operador para comparar pares de referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="e40f1-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="e40f1-120">Los resultados se asignan a `Boolean` un valor que representa si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="e40f1-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="e40f1-121">Como se muestra en el ejemplo anterior, puede utilizar `Is` el operador para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e40f1-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40f1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e40f1-122">See also</span></span>

- [<span data-ttu-id="e40f1-123">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="e40f1-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="e40f1-124">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="e40f1-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="e40f1-125">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e40f1-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="e40f1-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e40f1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e40f1-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e40f1-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e40f1-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="e40f1-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
