---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: a7a0952ebe13b732ce706c3dad97a6da3b5cb85d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966559"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="c510d-102">IsNot (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c510d-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="c510d-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="c510d-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c510d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c510d-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="c510d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c510d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="c510d-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c510d-106">Required.</span></span> <span data-ttu-id="c510d-107">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c510d-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="c510d-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c510d-108">Required.</span></span> <span data-ttu-id="c510d-109">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="c510d-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="c510d-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c510d-110">Required.</span></span> <span data-ttu-id="c510d-111">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="c510d-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c510d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c510d-112">Remarks</span></span>  
 <span data-ttu-id="c510d-113">El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c510d-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="c510d-114">Sin embargo, no realiza las comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="c510d-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="c510d-115">Si `object1` y `object2` ambos hacen referencia a la instancia exacta del objeto mismo, `result` es `False`; si no, es `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="c510d-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="c510d-116">`IsNot` es el opuesto de la `Is` operador.</span><span class="sxs-lookup"><span data-stu-id="c510d-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="c510d-117">La ventaja de `IsNot` es que puede evitar sintaxis extraña con `Not` y `Is`, que puede ser difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="c510d-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="c510d-118">Puede usar el `Is` y `IsNot` operadores a los objetos con enlace anticipado y en tiempo de ejecución de prueba.</span><span class="sxs-lookup"><span data-stu-id="c510d-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c510d-119">El `IsNot` operador no puede utilizarse para comparar expresiones devueltas desde el `TypeOf` operador.</span><span class="sxs-lookup"><span data-stu-id="c510d-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="c510d-120">En su lugar, debe usar el `Not` y `Is` operadores.</span><span class="sxs-lookup"><span data-stu-id="c510d-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c510d-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c510d-121">Example</span></span>  
 <span data-ttu-id="c510d-122">En el ejemplo de código siguiente se usa tanto el `Is` operador y el `IsNot` operador para realizar la comparación de la misma.</span><span class="sxs-lookup"><span data-stu-id="c510d-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="c510d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c510d-123">See also</span></span>
- [<span data-ttu-id="c510d-124">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="c510d-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="c510d-125">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="c510d-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="c510d-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c510d-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c510d-127">Cómo: Probar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="c510d-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
