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
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054972"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="aec45-102">Is (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aec45-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="aec45-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="aec45-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec45-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aec45-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="aec45-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="aec45-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="aec45-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="aec45-106">Required.</span></span> <span data-ttu-id="aec45-107">Cualquier `Boolean` valor.</span><span class="sxs-lookup"><span data-stu-id="aec45-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="aec45-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="aec45-108">Required.</span></span> <span data-ttu-id="aec45-109">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="aec45-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="aec45-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="aec45-110">Required.</span></span> <span data-ttu-id="aec45-111">Cualquier `Object` nombre.</span><span class="sxs-lookup"><span data-stu-id="aec45-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aec45-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aec45-112">Remarks</span></span>  
 <span data-ttu-id="aec45-113">El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="aec45-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="aec45-114">Sin embargo, no realiza las comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="aec45-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="aec45-115">Si `object1` y `object2` ambos hacen referencia a la instancia exacta del objeto mismo, `result` es `True`; si no, es `result` es `False`.</span><span class="sxs-lookup"><span data-stu-id="aec45-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="aec45-116">`Is` También puede utilizarse con el `TypeOf` palabra clave para realizar un `TypeOf`... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="aec45-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aec45-117">El `Is` también se utiliza la palabra clave en el [seleccione... Instrucción de caso](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aec45-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aec45-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aec45-118">Example</span></span>  
 <span data-ttu-id="aec45-119">En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="aec45-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="aec45-120">Los resultados se asignan a un `Boolean` valor que indica si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="aec45-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="aec45-121">Como se muestra en el ejemplo anterior, puede usar el `Is` operador para probar ambas enlaza de manera anticipada y los objetos enlazados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="aec45-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec45-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec45-122">See also</span></span>

- [<span data-ttu-id="aec45-123">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="aec45-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="aec45-124">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="aec45-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="aec45-125">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aec45-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="aec45-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aec45-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="aec45-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="aec45-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="aec45-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="aec45-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
