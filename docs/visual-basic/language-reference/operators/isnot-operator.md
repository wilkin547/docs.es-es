---
title: IsNot (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336072"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="955ca-102">IsNot (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="955ca-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="955ca-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="955ca-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="955ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="955ca-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="955ca-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="955ca-105">Parts</span></span>
 <span data-ttu-id="955ca-106">`result` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="955ca-106">`result` Required.</span></span> <span data-ttu-id="955ca-107">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="955ca-107">A `Boolean` value.</span></span>

 <span data-ttu-id="955ca-108">`object1` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="955ca-108">`object1` Required.</span></span> <span data-ttu-id="955ca-109">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="955ca-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="955ca-110">`object2` Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="955ca-110">`object2` Required.</span></span> <span data-ttu-id="955ca-111">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="955ca-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="955ca-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="955ca-112">Remarks</span></span>
 <span data-ttu-id="955ca-113">El operador `IsNot` determina si dos referencias de objeto hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="955ca-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="955ca-114">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="955ca-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="955ca-115">Si `object1` y `object2` hacen referencia a la misma instancia de objeto exacta, se `False``result`. Si no es así, `result` se `True`.</span><span class="sxs-lookup"><span data-stu-id="955ca-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="955ca-116">`IsNot` es lo contrario del operador de `Is`.</span><span class="sxs-lookup"><span data-stu-id="955ca-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="955ca-117">La ventaja de `IsNot` es que puede evitar una sintaxis poco complicada con `Not` y `Is`, lo que puede resultar difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="955ca-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="955ca-118">Puede usar los operadores `Is` y `IsNot` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="955ca-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="955ca-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="955ca-119">Example</span></span>
 <span data-ttu-id="955ca-120">En el ejemplo de código siguiente se usa el operador `Is` y el operador `IsNot` para realizar la misma comparación.</span><span class="sxs-lookup"><span data-stu-id="955ca-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="955ca-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="955ca-121">See also</span></span>

- [<span data-ttu-id="955ca-122">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="955ca-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="955ca-123">TypeOf (operador)</span><span class="sxs-lookup"><span data-stu-id="955ca-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="955ca-124">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="955ca-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="955ca-125">Comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="955ca-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
