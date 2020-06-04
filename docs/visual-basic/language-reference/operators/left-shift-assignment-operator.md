---
title: Operador <<=
ms.date: 07/20/2015
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
ms.openlocfilehash: ff7cbb02a9a10dbe11450491e93fd85fd77b44ba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370666"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="ec583-102">\<\<Operador = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec583-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="ec583-103">Realiza un desplazamiento aritmético a la izquierda en el valor de una variable o propiedad y asigna el resultado a la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec583-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec583-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec583-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="ec583-105">Partes</span><span class="sxs-lookup"><span data-stu-id="ec583-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="ec583-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ec583-106">Required.</span></span> <span data-ttu-id="ec583-107">Variable o propiedad de un tipo entero ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` ).</span><span class="sxs-lookup"><span data-stu-id="ec583-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="ec583-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ec583-108">Required.</span></span> <span data-ttu-id="ec583-109">Expresión numérica de un tipo de datos que se amplía a `Integer` .</span><span class="sxs-lookup"><span data-stu-id="ec583-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec583-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec583-110">Remarks</span></span>  
 <span data-ttu-id="ec583-111">El elemento del lado izquierdo del `<<=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz.</span><span class="sxs-lookup"><span data-stu-id="ec583-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="ec583-112">La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="ec583-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="ec583-113">El `<<=` operador realiza primero un desplazamiento aritmético a la izquierda en el valor de la variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec583-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="ec583-114">A continuación, el operador asigna de nuevo el resultado de la operación a esa variable o propiedad.</span><span class="sxs-lookup"><span data-stu-id="ec583-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="ec583-115">Los turnos aritméticos no son circulares, lo que significa que los bits desplazados fuera de un extremo del resultado no se reintroducen en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="ec583-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="ec583-116">En un desplazamiento aritmético a la izquierda, los bits desplazados más allá del intervalo del tipo de datos del resultado se descartan y las posiciones de bits que quedan a la derecha se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="ec583-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="ec583-117">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ec583-117">Overloading</span></span>  
 <span data-ttu-id="ec583-118">El [operador de<< ](left-shift-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ec583-118">The [<< Operator](left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="ec583-119">La sobrecarga del `<<` operador afecta al comportamiento del `<<=` operador.</span><span class="sxs-lookup"><span data-stu-id="ec583-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="ec583-120">Si el código utiliza `<<=` en una clase o estructura que sobrecarga `<<` , asegúrese de que entiende su comportamiento redefinido.</span><span class="sxs-lookup"><span data-stu-id="ec583-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="ec583-121">Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ec583-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec583-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec583-122">Example</span></span>  
 <span data-ttu-id="ec583-123">En el ejemplo siguiente se usa el `<<=` operador para desplazar el patrón de bits de una `Integer` variable a la izquierda en la cantidad especificada y asignar el resultado a la variable.</span><span class="sxs-lookup"><span data-stu-id="ec583-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="ec583-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec583-124">See also</span></span>

- [<span data-ttu-id="ec583-125"><< (operador)</span><span class="sxs-lookup"><span data-stu-id="ec583-125"><< Operator</span></span>](left-shift-operator.md)
- [<span data-ttu-id="ec583-126">Operadores de asignación</span><span class="sxs-lookup"><span data-stu-id="ec583-126">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="ec583-127">Operadores de desplazamiento de bits</span><span class="sxs-lookup"><span data-stu-id="ec583-127">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="ec583-128">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec583-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="ec583-129">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="ec583-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="ec583-130">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="ec583-130">Statements</span></span>](../../programming-guide/language-features/statements.md)
