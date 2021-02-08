---
description: 'Más información sobre: operador typeof (Visual Basic)'
title: Operador TypeOf
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
ms.openlocfilehash: 59a03095b2abbaa304221b30402b9a058954db63
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795240"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="c584d-103">TypeOf (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c584d-103">TypeOf Operator (Visual Basic)</span></span>

<span data-ttu-id="c584d-104">Comprueba si el tipo en tiempo de ejecución del resultado de una expresión es compatible con el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="c584d-104">Checks whether the runtime type of an expression's result is type-compatible with the specified type.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c584d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c584d-105">Syntax</span></span>  
  
```vb  
result = TypeOf objectexpression Is typename  
```  
  
```vb  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="c584d-106">Partes</span><span class="sxs-lookup"><span data-stu-id="c584d-106">Parts</span></span>  

 `result`  
 <span data-ttu-id="c584d-107">Devuelto.</span><span class="sxs-lookup"><span data-stu-id="c584d-107">Returned.</span></span> <span data-ttu-id="c584d-108">Valor `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="c584d-108">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="c584d-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c584d-109">Required.</span></span> <span data-ttu-id="c584d-110">Cualquier expresión que se evalúa como un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="c584d-110">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="c584d-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c584d-111">Required.</span></span> <span data-ttu-id="c584d-112">Cualquier nombre de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c584d-112">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c584d-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c584d-113">Remarks</span></span>  

 <span data-ttu-id="c584d-114">El operador `TypeOf` determina si el tipo en tiempo de ejecución de `objectexpression` es compatible con `typename`.</span><span class="sxs-lookup"><span data-stu-id="c584d-114">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="c584d-115">La compatibilidad depende de la categoría del tipo de `typename`.</span><span class="sxs-lookup"><span data-stu-id="c584d-115">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="c584d-116">En la tabla siguiente se muestra cómo se determina la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c584d-116">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="c584d-117">Categoría de tipo de `typename`</span><span class="sxs-lookup"><span data-stu-id="c584d-117">Type category of `typename`</span></span>|<span data-ttu-id="c584d-118">Criterio de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="c584d-118">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="c584d-119">Class</span><span class="sxs-lookup"><span data-stu-id="c584d-119">Class</span></span>|<span data-ttu-id="c584d-120">`objectexpression` es de tipo `typename` o hereda de `typename`</span><span class="sxs-lookup"><span data-stu-id="c584d-120">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="c584d-121">Estructura</span><span class="sxs-lookup"><span data-stu-id="c584d-121">Structure</span></span>|<span data-ttu-id="c584d-122">`objectexpression` es de tipo `typename`</span><span class="sxs-lookup"><span data-stu-id="c584d-122">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="c584d-123">Interfaz</span><span class="sxs-lookup"><span data-stu-id="c584d-123">Interface</span></span>|<span data-ttu-id="c584d-124">`objectexpression` implementa `typename` o hereda de una clase que implementa `typename`</span><span class="sxs-lookup"><span data-stu-id="c584d-124">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="c584d-125">Si el tipo en tiempo de ejecución de `objectexpression` satisface el criterio de compatibilidad, `result` es `True`.</span><span class="sxs-lookup"><span data-stu-id="c584d-125">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="c584d-126">En caso contrario, `result` es `False`.</span><span class="sxs-lookup"><span data-stu-id="c584d-126">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="c584d-127">Si `objectexpression` es null, entonces `TypeOf`...`Is` devuelve `False` y ...`IsNot` devuelve `True`.</span><span class="sxs-lookup"><span data-stu-id="c584d-127">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="c584d-128">`TypeOf` siempre se usa con la palabra clave `Is` para construir una expresión `TypeOf`...`Is`, o con la palabra clave `IsNot` para construir una expresión `TypeOf`...`IsNot`.</span><span class="sxs-lookup"><span data-stu-id="c584d-128">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c584d-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c584d-129">Example</span></span>  

 <span data-ttu-id="c584d-130">En el ejemplo siguiente se usan expresiones `TypeOf`...`Is` para probar la compatibilidad de tipo de dos variables de referencia de objeto con diversos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="c584d-130">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="c584d-131">La variable `refInteger` tiene un tipo en tiempo de ejecución de `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c584d-131">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="c584d-132">Es compatible con `Integer` pero no con `Double`.</span><span class="sxs-lookup"><span data-stu-id="c584d-132">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="c584d-133">La variable `refForm` tiene un tipo en tiempo de ejecución de <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="c584d-133">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="c584d-134">Es compatible con <xref:System.Windows.Forms.Form> porque es su tipo, con <xref:System.Windows.Forms.Control> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.Windows.Forms.Control>, y con <xref:System.ComponentModel.IComponent> porque <xref:System.Windows.Forms.Form> hereda de <xref:System.ComponentModel.Component>, que implementa <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="c584d-134">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="c584d-135">Sin embargo, `refForm` no es compatible con <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="c584d-135">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c584d-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c584d-136">See also</span></span>

- [<span data-ttu-id="c584d-137">Operador Is</span><span class="sxs-lookup"><span data-stu-id="c584d-137">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="c584d-138">Operador IsNot</span><span class="sxs-lookup"><span data-stu-id="c584d-138">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="c584d-139">Comparison Operators in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c584d-139">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="c584d-140">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c584d-140">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c584d-141">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="c584d-141">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="c584d-142">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="c584d-142">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
