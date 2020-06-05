---
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
ms.openlocfilehash: a546d8b0c9b3852386970f80d3da96794da2351c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370952"
---
# <a name="-operator"></a><span data-ttu-id="bc5ca-102">\\= (Operador)</span><span class="sxs-lookup"><span data-stu-id="bc5ca-102">\\= Operator</span></span>
<span data-ttu-id="bc5ca-103">Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado entero a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc5ca-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="bc5ca-105">Partes</span><span class="sxs-lookup"><span data-stu-id="bc5ca-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="bc5ca-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-106">Required.</span></span> <span data-ttu-id="bc5ca-107">Cualquier variable o propiedad numérica.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="bc5ca-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-108">Required.</span></span> <span data-ttu-id="bc5ca-109">Cualquier expresión numérica.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc5ca-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc5ca-110">Remarks</span></span>  
 <span data-ttu-id="bc5ca-111">El elemento del lado izquierdo del `\=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="bc5ca-112">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="bc5ca-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="bc5ca-113">El `\=` operador divide el valor de una variable o propiedad a su izquierda por el valor de su derecha, y asigna el resultado entero a la variable o propiedad de su izquierda.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="bc5ca-114">Para obtener más información sobre la división de enteros, vea [\ (operador Visual Basic)](integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="bc5ca-114">For further information on integer division, see [\ Operator (Visual Basic)](integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="bc5ca-115">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="bc5ca-115">Overloading</span></span>  
 <span data-ttu-id="bc5ca-116">El `\` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bc5ca-117">La sobrecarga del `\` operador afecta al comportamiento del `\=` operador.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="bc5ca-118">Si el código utiliza `\=` en una clase o estructura que sobrecarga `\` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bc5ca-119">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="bc5ca-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc5ca-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc5ca-120">Example</span></span>  
 <span data-ttu-id="bc5ca-121">En el ejemplo siguiente se usa el `\=` operador para dividir una `Integer` variable por un segundo y asignar el resultado entero a la primera variable.</span><span class="sxs-lookup"><span data-stu-id="bc5ca-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="bc5ca-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc5ca-122">See also</span></span>

- [<span data-ttu-id="bc5ca-123">Operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc5ca-123">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="bc5ca-124">/= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc5ca-124">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="bc5ca-125">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="bc5ca-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="bc5ca-126">Operadores aritméticos</span><span class="sxs-lookup"><span data-stu-id="bc5ca-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="bc5ca-127">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc5ca-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="bc5ca-128">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="bc5ca-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="bc5ca-129">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="bc5ca-129">Statements</span></span>](../../programming-guide/language-features/statements.md)
