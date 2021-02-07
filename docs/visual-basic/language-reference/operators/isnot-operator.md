---
description: 'Más información acerca de: Operador IsNot (Visual Basic)'
title: IsNot (operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ac3e127676dfa57d14e07838152022de62fc336b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665671"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="c71f7-103">IsNot (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c71f7-103">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="c71f7-104">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="c71f7-104">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="c71f7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c71f7-105">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="c71f7-106">Partes</span><span class="sxs-lookup"><span data-stu-id="c71f7-106">Parts</span></span>

- `result`

  <span data-ttu-id="c71f7-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c71f7-107">Required.</span></span> <span data-ttu-id="c71f7-108">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c71f7-108">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="c71f7-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c71f7-109">Required.</span></span> <span data-ttu-id="c71f7-110">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="c71f7-110">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="c71f7-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c71f7-111">Required.</span></span> <span data-ttu-id="c71f7-112">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="c71f7-112">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="c71f7-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c71f7-113">Remarks</span></span>

<span data-ttu-id="c71f7-114">El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="c71f7-114">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="c71f7-115">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="c71f7-115">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="c71f7-116">Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `False` ; si no, `result` es `True` .</span><span class="sxs-lookup"><span data-stu-id="c71f7-116">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="c71f7-117">`IsNot` es lo contrario del `Is` operador.</span><span class="sxs-lookup"><span data-stu-id="c71f7-117">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="c71f7-118">La ventaja de `IsNot` es que puede evitar una sintaxis complicada con `Not` y `Is` , que puede ser difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="c71f7-118">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="c71f7-119">Puede usar los `Is` operadores y `IsNot` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c71f7-119">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="c71f7-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c71f7-120">Example</span></span>

<span data-ttu-id="c71f7-121">En el ejemplo de código siguiente se usa el `Is` operador y el `IsNot` operador para realizar la misma comparación.</span><span class="sxs-lookup"><span data-stu-id="c71f7-121">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="c71f7-122">Usar el operador typeof con el Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="c71f7-122">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="c71f7-123">A partir de Visual Basic 14, puede usar el `TypeOf` operador con el `IsNot` operador para comprobar si un objeto *no* es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c71f7-123">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="c71f7-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c71f7-124">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="c71f7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c71f7-125">See also</span></span>

- [<span data-ttu-id="c71f7-126">Operador Is</span><span class="sxs-lookup"><span data-stu-id="c71f7-126">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="c71f7-127">Operador TypeOf</span><span class="sxs-lookup"><span data-stu-id="c71f7-127">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="c71f7-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c71f7-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c71f7-129">Procedimiento para comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="c71f7-129">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
