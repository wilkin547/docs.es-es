---
title: '*= (Operador)'
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
ms.openlocfilehash: 4b60fa44a92bff683e13f850da025d7fe753618d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349787"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5258b-102">\*= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5258b-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="5258b-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="5258b-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5258b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5258b-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="5258b-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5258b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5258b-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="5258b-106">Required.</span></span> <span data-ttu-id="5258b-107">Any numeric variable or property.</span><span class="sxs-lookup"><span data-stu-id="5258b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="5258b-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="5258b-108">Required.</span></span> <span data-ttu-id="5258b-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="5258b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5258b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5258b-110">Remarks</span></span>  
 <span data-ttu-id="5258b-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="5258b-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5258b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5258b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5258b-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span><span class="sxs-lookup"><span data-stu-id="5258b-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="5258b-114">The operator then assigns the result of that operation to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="5258b-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5258b-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5258b-115">Overloading</span></span>  
 <span data-ttu-id="5258b-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="5258b-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5258b-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span><span class="sxs-lookup"><span data-stu-id="5258b-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="5258b-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="5258b-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5258b-119">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5258b-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5258b-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5258b-120">Example</span></span>  
 <span data-ttu-id="5258b-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span><span class="sxs-lookup"><span data-stu-id="5258b-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5258b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5258b-122">See also</span></span>

- [<span data-ttu-id="5258b-123">Operador \*</span><span class="sxs-lookup"><span data-stu-id="5258b-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="5258b-124">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="5258b-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="5258b-125">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="5258b-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="5258b-126">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5258b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5258b-127">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5258b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5258b-128">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5258b-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
