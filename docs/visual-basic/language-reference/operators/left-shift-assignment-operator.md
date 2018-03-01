---
title: '&lt;&lt;= (Operador) (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c5c36e4f91155c09d01b448777483941d018d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="325b2-102">&lt;&lt;= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="325b2-102">&lt;&lt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="325b2-103">Realiza un desplazamiento aritmético a la izquierda en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="325b2-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="325b2-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="325b2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="325b2-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="325b2-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="325b2-106">Required.</span></span> <span data-ttu-id="325b2-107">Variable o propiedad de un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="325b2-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="325b2-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="325b2-108">Required.</span></span> <span data-ttu-id="325b2-109">Expresión numérica de un tipo de datos que se amplíe a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="325b2-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325b2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="325b2-110">Remarks</span></span>  
 <span data-ttu-id="325b2-111">El elemento en el lado izquierdo de la `<<=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="325b2-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="325b2-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="325b2-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="325b2-113">El `<<=` operador primero realiza un desplazamiento aritmético a la izquierda en el valor de la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="325b2-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="325b2-114">El operador, a continuación, asigna el resultado de esa operación a esa variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="325b2-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="325b2-115">Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="325b2-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="325b2-116">En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits vacantes a la derecha se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="325b2-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="325b2-117">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="325b2-117">Overloading</span></span>  
 <span data-ttu-id="325b2-118">El [<< operador](../../../visual-basic/language-reference/operators/left-shift-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="325b2-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="325b2-119">Sobrecarga de la `<<` operador afecta al comportamiento de la `<<=` operador.</span><span class="sxs-lookup"><span data-stu-id="325b2-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="325b2-120">Si el código usa `<<=` en una clase o estructura que sobrecarga `<<`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="325b2-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="325b2-121">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="325b2-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="325b2-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="325b2-122">Example</span></span>  
 <span data-ttu-id="325b2-123">En el ejemplo siguiente se usa el `<<=` operador de desplazamiento del patrón de bits de un `Integer` variable izquierda por la cantidad especificada y asignar el resultado a la variable.</span><span class="sxs-lookup"><span data-stu-id="325b2-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="325b2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="325b2-124">See Also</span></span>  
 [<span data-ttu-id="325b2-125">Operador <<</span><span class="sxs-lookup"><span data-stu-id="325b2-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [<span data-ttu-id="325b2-126">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="325b2-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="325b2-127">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="325b2-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="325b2-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="325b2-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="325b2-129">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="325b2-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="325b2-130">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="325b2-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
