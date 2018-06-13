---
title: '&gt;&gt;= (Operador) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: d0c0ea819741f80e30e55a960b1187699898a3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604112"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="02780-102">&gt;&gt;= (Operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02780-102">&gt;&gt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="02780-103">Realiza un desplazamiento aritmético a la derecha en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="02780-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02780-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02780-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="02780-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="02780-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="02780-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="02780-106">Required.</span></span> <span data-ttu-id="02780-107">Variable o propiedad de un tipo integral (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="02780-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="02780-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="02780-108">Required.</span></span> <span data-ttu-id="02780-109">Expresión numérica de un tipo de datos que se amplíe a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="02780-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02780-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02780-110">Remarks</span></span>  
 <span data-ttu-id="02780-111">El elemento en el lado izquierdo de la `>>=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="02780-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="02780-112">La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="02780-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="02780-113">El `>>=` operador primero realiza un desplazamiento aritmético a la derecha en el valor de la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="02780-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="02780-114">El operador, a continuación, asigna el resultado de esa operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="02780-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="02780-115">Los desplazamientos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se vuelven a introducir en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="02780-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="02780-116">En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit de la derecha y el bit de la izquierda se propaga a las posiciones de bits vacantes a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="02780-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="02780-117">Esto significa que si `variableorproperty` tiene un valor negativo, las posiciones vacantes se establecen en uno.</span><span class="sxs-lookup"><span data-stu-id="02780-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="02780-118">Si `variableorproperty` es positivo, o si su tipo de datos es un tipo sin signo, las posiciones vacantes se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="02780-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="02780-119">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="02780-119">Overloading</span></span>  
 <span data-ttu-id="02780-120">El [>> operador](../../../visual-basic/language-reference/operators/right-shift-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="02780-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="02780-121">Sobrecarga de la `>>` operador afecta al comportamiento de la `>>=` operador.</span><span class="sxs-lookup"><span data-stu-id="02780-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="02780-122">Si el código usa `>>=` en una clase o estructura que sobrecarga `>>`, asegúrese de conocer su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="02780-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="02780-123">Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="02780-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02780-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02780-124">Example</span></span>  
 <span data-ttu-id="02780-125">En el ejemplo siguiente se usa el `>>=` operador de desplazamiento del patrón de bits de un `Integer` variable derecha por la cantidad especificada y asignar el resultado a la variable.</span><span class="sxs-lookup"><span data-stu-id="02780-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="02780-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="02780-126">See Also</span></span>  
 [<span data-ttu-id="02780-127">Operador >></span><span class="sxs-lookup"><span data-stu-id="02780-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [<span data-ttu-id="02780-128">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="02780-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="02780-129">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="02780-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="02780-130">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02780-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="02780-131">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="02780-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="02780-132">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="02780-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
