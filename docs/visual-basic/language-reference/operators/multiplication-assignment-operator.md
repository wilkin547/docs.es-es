---
description: 'Más información acerca de: * = (operador) (Visual Basic)'
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
ms.openlocfilehash: d5a88dc71a05c6375a09fe3f4b55eff704c13910
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665424"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="d9c38-103">\*= (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9c38-103">\*= Operator (Visual Basic)</span></span>

<span data-ttu-id="d9c38-104">Multiplica el valor de una variable o propiedad por el valor de una expresión y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9c38-104">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c38-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9c38-105">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d9c38-106">Partes</span><span class="sxs-lookup"><span data-stu-id="d9c38-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="d9c38-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="d9c38-107">Required.</span></span> <span data-ttu-id="d9c38-108">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="d9c38-108">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="d9c38-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d9c38-109">Required.</span></span> <span data-ttu-id="d9c38-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="d9c38-110">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9c38-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d9c38-111">Remarks</span></span>  

 <span data-ttu-id="d9c38-112">El elemento del lado izquierdo del `*=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="d9c38-112">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="d9c38-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="d9c38-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="d9c38-114">El `*=` operador multiplica primero el valor de la expresión (en el lado derecho del operador) por el valor de la variable o propiedad (en el lado izquierdo del operador).</span><span class="sxs-lookup"><span data-stu-id="d9c38-114">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="d9c38-115">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9c38-115">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="d9c38-116">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="d9c38-116">Overloading</span></span>  

 <span data-ttu-id="d9c38-117">El [operador \*](multiplication-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="d9c38-117">The [\* Operator](multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d9c38-118">La sobrecarga del `*` operador afecta al comportamiento del `*=` operador.</span><span class="sxs-lookup"><span data-stu-id="d9c38-118">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="d9c38-119">Si el código utiliza `*=` en una clase o estructura que sobrecarga `*` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="d9c38-119">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="d9c38-120">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d9c38-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9c38-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9c38-121">Example</span></span>  

 <span data-ttu-id="d9c38-122">En el ejemplo siguiente se usa el `*=` operador para multiplicar una `Integer` variable por un segundo y asignar el resultado a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="d9c38-122">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="d9c38-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9c38-123">See also</span></span>

- [<span data-ttu-id="d9c38-124">\* (Operador)</span><span class="sxs-lookup"><span data-stu-id="d9c38-124">\* Operator</span></span>](multiplication-operator.md)
- [<span data-ttu-id="d9c38-125">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="d9c38-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="d9c38-126">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="d9c38-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="d9c38-127">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9c38-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="d9c38-128">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="d9c38-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="d9c38-129">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="d9c38-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
