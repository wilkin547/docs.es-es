---
description: 'Más información acerca de:  >>= operador (Visual Basic)'
title: '>>= (Operador)'
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
ms.openlocfilehash: 80f614042403ad9179de0025b289bd83c71008b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795318"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="829e9-103">>>= (operador) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="829e9-103">>>= Operator (Visual Basic)</span></span>

<span data-ttu-id="829e9-104">Realiza un desplazamiento aritmético a la derecha en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="829e9-104">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="829e9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="829e9-105">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="829e9-106">Partes</span><span class="sxs-lookup"><span data-stu-id="829e9-106">Parts</span></span>  

 `variableorproperty`  
 <span data-ttu-id="829e9-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="829e9-107">Required.</span></span> <span data-ttu-id="829e9-108">Variable o propiedad de un tipo entero ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` ).</span><span class="sxs-lookup"><span data-stu-id="829e9-108">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="829e9-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="829e9-109">Required.</span></span> <span data-ttu-id="829e9-110">Expresión numérica de un tipo de datos que se amplía a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="829e9-110">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="829e9-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="829e9-111">Remarks</span></span>  

 <span data-ttu-id="829e9-112">El elemento del lado izquierdo del `>>=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="829e9-112">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="829e9-113">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="829e9-113">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="829e9-114">El `>>=` operador realiza primero un desplazamiento aritmético a la derecha en el valor de la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="829e9-114">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="829e9-115">A continuación, el operador asigna el resultado de la operación a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="829e9-115">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="829e9-116">Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="829e9-116">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="829e9-117">En un desplazamiento aritmético a la derecha, se descartan los bits desplazados más allá de la posición de bit situada más a la derecha y el bit del extremo izquierdo se propaga a las posiciones de bits que quedan a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="829e9-117">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="829e9-118">Esto significa que si `variableorproperty` tiene un valor negativo, las posiciones vacías se establecen en una.</span><span class="sxs-lookup"><span data-stu-id="829e9-118">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="829e9-119">Si `variableorproperty` es positivo, o si su tipo de datos es un tipo sin signo, las posiciones vacantes se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="829e9-119">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="829e9-120">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="829e9-120">Overloading</span></span>  

 <span data-ttu-id="829e9-121">El [ operador de>>](right-shift-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="829e9-121">The [>> Operator](right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="829e9-122">La sobrecarga del `>>` operador afecta al comportamiento del `>>=` operador.</span><span class="sxs-lookup"><span data-stu-id="829e9-122">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="829e9-123">Si el código utiliza `>>=` en una clase o estructura que sobrecarga `>>` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="829e9-123">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="829e9-124">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="829e9-124">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="829e9-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="829e9-125">Example</span></span>  

 <span data-ttu-id="829e9-126">En el ejemplo siguiente se usa el `>>=` operador para desplazar el patrón de bits de una `Integer` variable a la derecha la cantidad especificada y asignar el resultado a la variable.</span><span class="sxs-lookup"><span data-stu-id="829e9-126">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="829e9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="829e9-127">See also</span></span>

- [<span data-ttu-id="829e9-128">>> (operador)</span><span class="sxs-lookup"><span data-stu-id="829e9-128">>> Operator</span></span>](right-shift-operator.md)
- [<span data-ttu-id="829e9-129">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="829e9-129">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="829e9-130">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="829e9-130">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="829e9-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="829e9-131">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="829e9-132">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="829e9-132">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="829e9-133">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="829e9-133">Statements</span></span>](../../programming-guide/language-features/statements.md)
