---
title: TypeOf (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 7162fcc24595bbb16d268d5d9e1ea4d82f6e67fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920541"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="b22d2-102">TypeOf (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b22d2-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="b22d2-103">Compara una variable de referencia de objeto a un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b22d2-103">Compares an object reference variable to a data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b22d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b22d2-104">Syntax</span></span>  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="b22d2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b22d2-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b22d2-106">Devuelto.</span><span class="sxs-lookup"><span data-stu-id="b22d2-106">Returned.</span></span> <span data-ttu-id="b22d2-107">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="b22d2-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b22d2-108">Required.</span></span> <span data-ttu-id="b22d2-109">Cualquier expresión que se evalúa como un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="b22d2-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="b22d2-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b22d2-110">Required.</span></span> <span data-ttu-id="b22d2-111">Cualquier nombre de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b22d2-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b22d2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b22d2-112">Remarks</span></span>  
 <span data-ttu-id="b22d2-113">El operador `TypeOf` determina si el tipo en tiempo de ejecución de `objectexpression` es compatible con `typename`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="b22d2-114">La compatibilidad depende de la categoría del tipo de `typename`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="b22d2-115">En la tabla siguiente se muestra cómo se determina la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b22d2-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="b22d2-116">Categoría de tipo de `typename`</span><span class="sxs-lookup"><span data-stu-id="b22d2-116">Type category of `typename`</span></span>|<span data-ttu-id="b22d2-117">Criterio de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="b22d2-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="b22d2-118">Clase</span><span class="sxs-lookup"><span data-stu-id="b22d2-118">Class</span></span>|<span data-ttu-id="b22d2-119">`objectexpression` es de tipo `typename` o hereda de `typename`</span><span class="sxs-lookup"><span data-stu-id="b22d2-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="b22d2-120">Estructura</span><span class="sxs-lookup"><span data-stu-id="b22d2-120">Structure</span></span>|<span data-ttu-id="b22d2-121">`objectexpression` es de tipo `typename`</span><span class="sxs-lookup"><span data-stu-id="b22d2-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="b22d2-122">Interfaz</span><span class="sxs-lookup"><span data-stu-id="b22d2-122">Interface</span></span>|<span data-ttu-id="b22d2-123">`objectexpression` implementa `typename` o hereda de una clase que implementa `typename`</span><span class="sxs-lookup"><span data-stu-id="b22d2-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="b22d2-124">Si el tipo en tiempo de ejecución de `objectexpression` satisface el criterio de compatibilidad, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="b22d2-125">En caso contrario, `result` es `False`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="b22d2-126">Si `objectexpression` es null, entonces `TypeOf`...`Is` devuelve `False` y ...`IsNot` devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="b22d2-127">`TypeOf` siempre se usa con la palabra clave `Is` para construir una expresión `TypeOf`...`Is`, o con la palabra clave `IsNot` para construir una expresión `TypeOf`...`IsNot`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b22d2-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b22d2-128">Example</span></span>  
 <span data-ttu-id="b22d2-129">En el ejemplo siguiente se usan expresiones `TypeOf`...`Is` para probar la compatibilidad de tipo de dos variables de referencia de objeto con diversos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="b22d2-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="b22d2-130">La variable `refInteger` tiene un tipo en tiempo de ejecución de `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="b22d2-131">Es compatible con `Integer` pero no con `Double`.</span><span class="sxs-lookup"><span data-stu-id="b22d2-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="b22d2-132">La variable `refForm` tiene un tipo en tiempo de ejecución de <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="b22d2-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="b22d2-133">Es compatible con <xref:System.Windows.Forms.Form> porque es su tipo, con <xref:System.Windows.Forms.Control> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.Windows.Forms.Control>, y con <xref:System.ComponentModel.IComponent> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.ComponentModel.Component>, que implementa <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="b22d2-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="b22d2-134">Sin embargo, `refForm` no es compatible con <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="b22d2-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b22d2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b22d2-135">See also</span></span>

- [<span data-ttu-id="b22d2-136">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="b22d2-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="b22d2-137">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="b22d2-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="b22d2-138">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b22d2-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="b22d2-139">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b22d2-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="b22d2-140">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="b22d2-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="b22d2-141">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="b22d2-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
