---
title: 'Cómo: Llamar a un procedimiento de operador'
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
ms.openlocfilehash: a977b17d4b2c797bbe38d289a57f3d9d31fa64fa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345966"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="28c4c-102">Cómo: Llamar a un procedimiento de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28c4c-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="28c4c-103">Se llama a un procedimiento de operador mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="28c4c-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="28c4c-104">En el caso de un operador de conversión, se llama a la [función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="28c4c-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="28c4c-105">No llame a los procedimientos de operador explícitamente.</span><span class="sxs-lookup"><span data-stu-id="28c4c-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="28c4c-106">Solo se usa el operador, o la función `CType`, en una instrucción de asignación o una expresión, del mismo modo que normalmente se usa un operador.</span><span class="sxs-lookup"><span data-stu-id="28c4c-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="28c4c-107">Visual Basic realiza la llamada al procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="28c4c-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="28c4c-108">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="28c4c-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="28c4c-109">Para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="28c4c-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="28c4c-110">Use el símbolo del operador en una expresión de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="28c4c-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="28c4c-111">Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="28c4c-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="28c4c-112">El operador contribuye al valor de la expresión según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="28c4c-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="28c4c-113">Para llamar a un procedimiento de operador de conversión</span><span class="sxs-lookup"><span data-stu-id="28c4c-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="28c4c-114">Use `CType` dentro de una expresión.</span><span class="sxs-lookup"><span data-stu-id="28c4c-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="28c4c-115">Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="28c4c-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="28c4c-116">`CType` llama al procedimiento del operador de conversión y devuelve el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="28c4c-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28c4c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28c4c-117">Example</span></span>  
 <span data-ttu-id="28c4c-118">En el ejemplo siguiente se crean dos estructuras <xref:System.TimeSpan>, se agregan juntas y se almacena el resultado en una tercera <xref:System.TimeSpan> estructura.</span><span class="sxs-lookup"><span data-stu-id="28c4c-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="28c4c-119">La estructura <xref:System.TimeSpan> define los procedimientos de operador para sobrecargar varios operadores estándar.</span><span class="sxs-lookup"><span data-stu-id="28c4c-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="28c4c-120">Dado que <xref:System.TimeSpan> sobrecarga el operador de `+` estándar, en el ejemplo anterior se llama a un procedimiento de operador al calcular el valor de `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="28c4c-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="28c4c-121">Para obtener un ejemplo de cómo llamar a un procedimiento de operador de conversación, consulte [Cómo: utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="28c4c-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="28c4c-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="28c4c-122">Compile the code</span></span>  
 <span data-ttu-id="28c4c-123">Asegúrese de que la clase o estructura que está usando define el operador que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="28c4c-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c4c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="28c4c-124">See also</span></span>

- [<span data-ttu-id="28c4c-125">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="28c4c-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="28c4c-126">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="28c4c-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="28c4c-127">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="28c4c-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="28c4c-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="28c4c-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="28c4c-129">Widening</span><span class="sxs-lookup"><span data-stu-id="28c4c-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="28c4c-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="28c4c-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="28c4c-131">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28c4c-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="28c4c-132">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="28c4c-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="28c4c-133">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="28c4c-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="28c4c-134">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="28c4c-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
