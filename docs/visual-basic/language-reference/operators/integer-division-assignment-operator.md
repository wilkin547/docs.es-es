---
description: 'Más información acerca de: = (operador)'
title: Operador \=
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: a05e136cbf17eaf7102fb2213993adf9cf0e06be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665814"
---
# <a name="-operator"></a><span data-ttu-id="12b94-103">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="12b94-103">\\= Operator</span></span>

<span data-ttu-id="12b94-104">Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado entero a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="12b94-104">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b94-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12b94-105">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="12b94-106">Partes</span><span class="sxs-lookup"><span data-stu-id="12b94-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="12b94-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="12b94-107">Required.</span></span> <span data-ttu-id="12b94-108">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="12b94-108">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="12b94-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="12b94-109">Required.</span></span> <span data-ttu-id="12b94-110">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="12b94-110">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12b94-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="12b94-111">Remarks</span></span>  

 <span data-ttu-id="12b94-112">El elemento del lado izquierdo del `\=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="12b94-112">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="12b94-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="12b94-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="12b94-114">El `\=` operador divide el valor de una variable o propiedad a su izquierda por el valor de su derecha, y asigna el resultado entero a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="12b94-114">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="12b94-115">Para obtener más información sobre la división de enteros, vea [\ (operador Visual Basic)](integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="12b94-115">For further information on integer division, see [\ Operator (Visual Basic)](integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="12b94-116">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="12b94-116">Overloading</span></span>  

 <span data-ttu-id="12b94-117">El `\` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="12b94-117">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="12b94-118">La sobrecarga del `\` operador afecta al comportamiento del `\=` operador.</span><span class="sxs-lookup"><span data-stu-id="12b94-118">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="12b94-119">Si el código utiliza `\=` en una clase o estructura que sobrecarga `\` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="12b94-119">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="12b94-120">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="12b94-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12b94-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12b94-121">Example</span></span>  

 <span data-ttu-id="12b94-122">En el ejemplo siguiente se usa el `\=` operador para dividir una `Integer` variable por un segundo y asignar el resultado entero a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="12b94-122">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="12b94-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="12b94-123">See also</span></span>

- [<span data-ttu-id="12b94-124">Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12b94-124">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="12b94-125">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12b94-125">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="12b94-126">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="12b94-126">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="12b94-127">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="12b94-127">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="12b94-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="12b94-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="12b94-129">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="12b94-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="12b94-130">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="12b94-130">Statements</span></span>](../../programming-guide/language-features/statements.md)
