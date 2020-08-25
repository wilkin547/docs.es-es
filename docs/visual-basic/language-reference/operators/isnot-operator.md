---
title: IsNot (operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811046"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="3dd8f-102">IsNot (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dd8f-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="3dd8f-103">Compara dos variables de referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="3dd8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3dd8f-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="3dd8f-105">Partes</span><span class="sxs-lookup"><span data-stu-id="3dd8f-105">Parts</span></span>

- `result`

  <span data-ttu-id="3dd8f-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-106">Required.</span></span> <span data-ttu-id="3dd8f-107">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-107">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="3dd8f-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-108">Required.</span></span> <span data-ttu-id="3dd8f-109">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-109">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="3dd8f-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-110">Required.</span></span> <span data-ttu-id="3dd8f-111">Cualquier `Object` variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="3dd8f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3dd8f-112">Remarks</span></span>

<span data-ttu-id="3dd8f-113">El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="3dd8f-114">Sin embargo, no realiza comparaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-114">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="3dd8f-115">Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `False` ; si no, `result` es `True` .</span><span class="sxs-lookup"><span data-stu-id="3dd8f-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="3dd8f-116">`IsNot` es lo contrario del `Is` operador.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="3dd8f-117">La ventaja de `IsNot` es que puede evitar una sintaxis complicada con `Not` y `Is` , que puede ser difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="3dd8f-118">Puede usar los `Is` operadores y `IsNot` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="3dd8f-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dd8f-119">Example</span></span>

<span data-ttu-id="3dd8f-120">En el ejemplo de código siguiente se usa el `Is` operador y el `IsNot` operador para realizar la misma comparación.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="3dd8f-121">Usar el operador typeof con el Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="3dd8f-121">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="3dd8f-122">A partir de Visual Basic 14, puede usar el `TypeOf` operador con el `IsNot` operador para comprobar si un objeto *no* es compatible con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3dd8f-122">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="3dd8f-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3dd8f-123">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="3dd8f-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dd8f-124">See also</span></span>

- [<span data-ttu-id="3dd8f-125">Operador is</span><span class="sxs-lookup"><span data-stu-id="3dd8f-125">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="3dd8f-126">Typeof (operador)</span><span class="sxs-lookup"><span data-stu-id="3dd8f-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="3dd8f-127">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3dd8f-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="3dd8f-128">Procedimiento para comprobar si dos objetos son iguales</span><span class="sxs-lookup"><span data-stu-id="3dd8f-128">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
