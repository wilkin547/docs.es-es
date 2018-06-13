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
ms.openlocfilehash: fe287794423048e993d953c83fc8590a06b7a5e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604060"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="5ee01-102">TypeOf (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ee01-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="5ee01-103">Compara una variable de referencia de objeto a un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5ee01-103">Compares an object reference variable to a data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ee01-104">Syntax</span></span>  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="5ee01-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5ee01-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="5ee01-106">Devuelto.</span><span class="sxs-lookup"><span data-stu-id="5ee01-106">Returned.</span></span> <span data-ttu-id="5ee01-107">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="5ee01-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="5ee01-108">Required.</span></span> <span data-ttu-id="5ee01-109">Cualquier expresión que se evalúa como un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="5ee01-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="5ee01-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="5ee01-110">Required.</span></span> <span data-ttu-id="5ee01-111">Cualquier nombre de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5ee01-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee01-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ee01-112">Remarks</span></span>  
 <span data-ttu-id="5ee01-113">El operador `TypeOf` determina si el tipo en tiempo de ejecución de `objectexpression` es compatible con `typename`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="5ee01-114">La compatibilidad depende de la categoría del tipo de `typename`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="5ee01-115">En la tabla siguiente se muestra cómo se determina la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="5ee01-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="5ee01-116">Categoría de tipo de `typename`</span><span class="sxs-lookup"><span data-stu-id="5ee01-116">Type category of `typename`</span></span>|<span data-ttu-id="5ee01-117">Criterio de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="5ee01-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="5ee01-118">Clase</span><span class="sxs-lookup"><span data-stu-id="5ee01-118">Class</span></span>|<span data-ttu-id="5ee01-119">`objectexpression` es de tipo `typename` o hereda de `typename`</span><span class="sxs-lookup"><span data-stu-id="5ee01-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="5ee01-120">Estructura</span><span class="sxs-lookup"><span data-stu-id="5ee01-120">Structure</span></span>|<span data-ttu-id="5ee01-121">`objectexpression` es de tipo `typename`</span><span class="sxs-lookup"><span data-stu-id="5ee01-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="5ee01-122">Interfaz</span><span class="sxs-lookup"><span data-stu-id="5ee01-122">Interface</span></span>|<span data-ttu-id="5ee01-123">`objectexpression` implementa `typename` o hereda de una clase que implementa `typename`</span><span class="sxs-lookup"><span data-stu-id="5ee01-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="5ee01-124">Si el tipo en tiempo de ejecución de `objectexpression` satisface el criterio de compatibilidad, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="5ee01-125">En caso contrario, `result` es `False`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="5ee01-126">Si `objectexpression` es null, entonces `TypeOf`...`Is` devuelve `False` y ...`IsNot` devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="5ee01-127">`TypeOf` siempre se usa con la palabra clave `Is` para construir una expresión `TypeOf`...`Is`, o con la palabra clave `IsNot` para construir una expresión `TypeOf`...`IsNot`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ee01-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ee01-128">Example</span></span>  
 <span data-ttu-id="5ee01-129">En el ejemplo siguiente se usan expresiones `TypeOf`...`Is` para probar la compatibilidad de tipo de dos variables de referencia de objeto con diversos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="5ee01-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/typeof-operator_1.vb)]  
  
 <span data-ttu-id="5ee01-130">La variable `refInteger` tiene un tipo en tiempo de ejecución de `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="5ee01-131">Es compatible con `Integer` pero no con `Double`.</span><span class="sxs-lookup"><span data-stu-id="5ee01-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="5ee01-132">La variable `refForm` tiene un tipo en tiempo de ejecución de <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="5ee01-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="5ee01-133">Es compatible con <xref:System.Windows.Forms.Form> porque es su tipo, con <xref:System.Windows.Forms.Control> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.Windows.Forms.Control>, y con <xref:System.ComponentModel.IComponent> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.ComponentModel.Component>, que implementa <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="5ee01-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="5ee01-134">Sin embargo, `refForm` no es compatible con <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="5ee01-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee01-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ee01-135">See Also</span></span>  
 [<span data-ttu-id="5ee01-136">Is (operador)</span><span class="sxs-lookup"><span data-stu-id="5ee01-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="5ee01-137">IsNot (operador)</span><span class="sxs-lookup"><span data-stu-id="5ee01-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="5ee01-138">Operadores de comparación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ee01-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="5ee01-139">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5ee01-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="5ee01-140">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5ee01-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="5ee01-141">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="5ee01-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
