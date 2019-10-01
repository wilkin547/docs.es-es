---
title: '>>= (Operador, Visual Basic)'
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
ms.openlocfilehash: 08d4e251a96ca387a709319e752351db6825d9e8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701358"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="5443d-102">> > = operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5443d-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="5443d-103">Realiza un desplazamiento aritmético a la derecha en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="5443d-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5443d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5443d-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="5443d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="5443d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="5443d-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5443d-106">Required.</span></span> <span data-ttu-id="5443d-107">Variable o propiedad de un tipo entero (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` o `ULong`).</span><span class="sxs-lookup"><span data-stu-id="5443d-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="5443d-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5443d-108">Required.</span></span> <span data-ttu-id="5443d-109">Expresión numérica de un tipo de datos que se amplía a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="5443d-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5443d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5443d-110">Remarks</span></span>  
 <span data-ttu-id="5443d-111">El elemento del lado izquierdo del operador `>>=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="5443d-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="5443d-112">La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="5443d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="5443d-113">El operador `>>=` primero realiza un desplazamiento aritmético a la derecha en el valor de la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="5443d-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="5443d-114">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="5443d-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="5443d-115">Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="5443d-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="5443d-116">En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit situada más a la derecha y el bit del extremo izquierdo se propaga a las posiciones de bits que quedan a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="5443d-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="5443d-117">Esto significa que si `variableorproperty` tiene un valor negativo, las posiciones vacantes se establecen en una.</span><span class="sxs-lookup"><span data-stu-id="5443d-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="5443d-118">Si `variableorproperty` es positivo, o si su tipo de datos es un tipo sin signo, las posiciones vacías se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="5443d-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="5443d-119">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="5443d-119">Overloading</span></span>  
 <span data-ttu-id="5443d-120">Se puede *sobrecargar*el [operador > >](../../../visual-basic/language-reference/operators/right-shift-operator.md) , lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="5443d-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="5443d-121">La sobrecarga del operador `>>` afecta al comportamiento del operador `>>=`.</span><span class="sxs-lookup"><span data-stu-id="5443d-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="5443d-122">Si el código usa `>>=` en una clase o estructura que sobrecarga `>>`, asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="5443d-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="5443d-123">Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5443d-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5443d-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5443d-124">Example</span></span>  
 <span data-ttu-id="5443d-125">En el ejemplo siguiente se usa el operador `>>=` para desplazar el patrón de bits de una variable `Integer` a la derecha la cantidad especificada y asignar el resultado a la variable.</span><span class="sxs-lookup"><span data-stu-id="5443d-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="5443d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5443d-126">See also</span></span>

- [<span data-ttu-id="5443d-127">Operador >></span><span class="sxs-lookup"><span data-stu-id="5443d-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="5443d-128">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="5443d-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="5443d-129">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="5443d-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="5443d-130">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5443d-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="5443d-131">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="5443d-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="5443d-132">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5443d-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
