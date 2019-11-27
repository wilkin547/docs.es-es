---
title: Is (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 52fbb39ab0a36c8b947b78f464fad26be05ce204
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349531"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="fe2be-102">Is (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe2be-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="fe2be-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="fe2be-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe2be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe2be-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="fe2be-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="fe2be-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="fe2be-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe2be-106">Required.</span></span> <span data-ttu-id="fe2be-107">Cualquier valor de `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fe2be-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="fe2be-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe2be-108">Required.</span></span> <span data-ttu-id="fe2be-109">Cualquier nombre de `Object`.</span><span class="sxs-lookup"><span data-stu-id="fe2be-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="fe2be-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe2be-110">Required.</span></span> <span data-ttu-id="fe2be-111">Cualquier nombre de `Object`.</span><span class="sxs-lookup"><span data-stu-id="fe2be-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe2be-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe2be-112">Remarks</span></span>  
 <span data-ttu-id="fe2be-113">El operador `Is` determina si dos referencias de objeto hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="fe2be-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="fe2be-114">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="fe2be-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="fe2be-115">Si `object1` y `object2` hacen referencia a la misma instancia de objeto exacta, se `True``result`. Si no es así, `result` se `False`.</span><span class="sxs-lookup"><span data-stu-id="fe2be-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="fe2be-116">también se puede usar `Is` con la palabra clave `TypeOf` para crear una expresión `TypeOf`...`Is`, que comprueba si una variable de objeto es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="fe2be-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe2be-117">La palabra clave `Is` también se usa en [la Instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fe2be-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe2be-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fe2be-118">Example</span></span>  
 <span data-ttu-id="fe2be-119">En el ejemplo siguiente se usa el operador `Is` para comparar pares de referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="fe2be-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="fe2be-120">Los resultados se asignan a un valor `Boolean` que representa si los dos objetos son idénticos.</span><span class="sxs-lookup"><span data-stu-id="fe2be-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="fe2be-121">Como se muestra en el ejemplo anterior, puede utilizar el operador `Is` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe2be-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe2be-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe2be-122">See also</span></span>

- [<span data-ttu-id="fe2be-123">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="fe2be-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="fe2be-124">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="fe2be-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="fe2be-125">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe2be-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="fe2be-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe2be-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="fe2be-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="fe2be-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="fe2be-128">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="fe2be-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
