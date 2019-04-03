---
title: Filtrar Llamar a un procedimiento de operador (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: 46614ad43e7be72c8396f47ba7f5d02185f62827
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837096"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="5e5ff-102">Filtrar Llamar a un procedimiento de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e5ff-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="5e5ff-103">Llame a un procedimiento de operador mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="5e5ff-104">En el caso de un operador de conversión, llame a la [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="5e5ff-105">No llame explícitamente procedimientos de operador.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="5e5ff-106">Utilizaremos el operador, o el `CType` función en una instrucción de asignación o una expresión, la misma manera que se usa habitualmente un operador.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="5e5ff-107">Visual Basic realiza la llamada al procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="5e5ff-108">Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="5e5ff-109">Para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="5e5ff-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="5e5ff-110">Utilice el símbolo de operador en una expresión de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="5e5ff-111">Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y, en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="5e5ff-112">El operador contribuye al valor de la expresión, según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="5e5ff-113">Llamar a un procedimiento de operador de conversión</span><span class="sxs-lookup"><span data-stu-id="5e5ff-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="5e5ff-114">Use `CType` dentro de una expresión.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="5e5ff-115">Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y, en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="5e5ff-116">`CType` llama al procedimiento de operador de conversión y devuelve el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e5ff-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e5ff-117">Example</span></span>  
 <span data-ttu-id="5e5ff-118">En el ejemplo siguiente se crean dos <xref:System.TimeSpan> estructuras, agrega juntos y almacena el resultado en una tercera <xref:System.TimeSpan> estructura.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="5e5ff-119">El <xref:System.TimeSpan> estructura define procedimientos de operador para sobrecargar varios operadores estándar.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="5e5ff-120">Dado que <xref:System.TimeSpan> sobrecargas estándar `+` operador, en el ejemplo anterior, se llama a un procedimiento de operador cuando calcula el valor de `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="5e5ff-121">Para obtener un ejemplo de una llamada a un procedimiento de operador de conversación, vea [Cómo: Usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5e5ff-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e5ff-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5e5ff-122">Compiling the Code</span></span>  
 <span data-ttu-id="5e5ff-123">Asegúrese de que la clase o estructura que está utilizando define el operador que desea usar.</span><span class="sxs-lookup"><span data-stu-id="5e5ff-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5ff-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e5ff-124">See also</span></span>

- [<span data-ttu-id="5e5ff-125">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="5e5ff-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="5e5ff-126">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="5e5ff-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="5e5ff-127">Cómo: Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="5e5ff-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="5e5ff-128">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5e5ff-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="5e5ff-129">Widening</span><span class="sxs-lookup"><span data-stu-id="5e5ff-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="5e5ff-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="5e5ff-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="5e5ff-131">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5e5ff-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="5e5ff-132">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="5e5ff-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="5e5ff-133">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="5e5ff-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="5e5ff-134">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="5e5ff-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
