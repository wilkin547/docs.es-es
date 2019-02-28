---
title: '*= (Operador, Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: d672ac147a4d7b2c21f4fcb7ee6cdf91b8b4924b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965337"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e4db7-102">\*= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4db7-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="e4db7-103">Multiplica el valor de una propiedad o variable por el valor de una expresión y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4db7-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4db7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4db7-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="e4db7-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e4db7-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="e4db7-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e4db7-106">Required.</span></span> <span data-ttu-id="e4db7-107">Cualquier propiedad o variable numérica.</span><span class="sxs-lookup"><span data-stu-id="e4db7-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="e4db7-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e4db7-108">Required.</span></span> <span data-ttu-id="e4db7-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="e4db7-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4db7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4db7-110">Remarks</span></span>  
 <span data-ttu-id="e4db7-111">El elemento en el lado izquierdo de la `*=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e4db7-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e4db7-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="e4db7-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="e4db7-113">El `*=` operador primero multiplica el valor de la expresión (en el lado derecho del operador) por el valor de la variable o propiedad (en el lado izquierdo del operador).</span><span class="sxs-lookup"><span data-stu-id="e4db7-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="e4db7-114">El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="e4db7-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e4db7-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="e4db7-115">Overloading</span></span>  
 <span data-ttu-id="e4db7-116">El [\* operador](../../../visual-basic/language-reference/operators/multiplication-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="e4db7-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e4db7-117">Sobrecargar el `*` operador afecta al comportamiento de la `*=` operador.</span><span class="sxs-lookup"><span data-stu-id="e4db7-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="e4db7-118">Si el código usa `*=` en una clase o estructura que sobrecarga `*`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="e4db7-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e4db7-119">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e4db7-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4db7-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4db7-120">Example</span></span>  
 <span data-ttu-id="e4db7-121">En el ejemplo siguiente se usa el `*=` operador Multiplicar uno `Integer` variable por un segundo y asigna el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="e4db7-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e4db7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4db7-122">See also</span></span>
- [<span data-ttu-id="e4db7-123">Operador \*</span><span class="sxs-lookup"><span data-stu-id="e4db7-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="e4db7-124">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="e4db7-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="e4db7-125">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="e4db7-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="e4db7-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4db7-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e4db7-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="e4db7-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e4db7-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="e4db7-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
