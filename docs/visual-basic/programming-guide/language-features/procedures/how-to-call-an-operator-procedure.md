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
ms.openlocfilehash: d68781aa12ab7c1c717031ca252c5f3120649edc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335490"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="4fc7e-102">Filtrar Llamar a un procedimiento de operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc7e-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="4fc7e-103">Llame a un procedimiento de operador mediante el símbolo de operador en una expresión.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="4fc7e-104">En el caso de un operador de conversión, llame a la [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="4fc7e-105">No llame explícitamente procedimientos de operador.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="4fc7e-106">Utilizaremos el operador, o el `CType` función en una instrucción de asignación o una expresión, la misma manera que se usa habitualmente un operador.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="4fc7e-107">Visual Basic realiza la llamada al procedimiento de operador.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="4fc7e-108">Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="4fc7e-109">Para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="4fc7e-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="4fc7e-110">Utilice el símbolo de operador en una expresión de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="4fc7e-111">Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y, en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="4fc7e-112">El operador contribuye al valor de la expresión, según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="4fc7e-113">Llamar a un procedimiento de operador de conversión</span><span class="sxs-lookup"><span data-stu-id="4fc7e-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="4fc7e-114">Use `CType` dentro de una expresión.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="4fc7e-115">Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y, en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. `CType` <span data-ttu-id="4fc7e-116">llama al procedimiento de operador de conversión y devuelve el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-116">calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fc7e-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fc7e-117">Example</span></span>  
 <span data-ttu-id="4fc7e-118">En el ejemplo siguiente se crean dos <xref:System.TimeSpan> estructuras, agrega juntos y almacena el resultado en una tercera <xref:System.TimeSpan> estructura.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="4fc7e-119">El <xref:System.TimeSpan> estructura define procedimientos de operador para sobrecargar varios operadores estándar.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="4fc7e-120">Dado que <xref:System.TimeSpan> sobrecargas estándar `+` operador, en el ejemplo anterior, se llama a un procedimiento de operador cuando calcula el valor de `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="4fc7e-121">Para obtener un ejemplo de una llamada a un procedimiento de operador de conversación, vea [Cómo: Usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="4fc7e-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4fc7e-122">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4fc7e-122">Compiling the Code</span></span>  
 <span data-ttu-id="4fc7e-123">Asegúrese de que la clase o estructura que está utilizando define el operador que desea usar.</span><span class="sxs-lookup"><span data-stu-id="4fc7e-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc7e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fc7e-124">See also</span></span>

- [<span data-ttu-id="4fc7e-125">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="4fc7e-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="4fc7e-126">Filtrar para definir un operador</span><span class="sxs-lookup"><span data-stu-id="4fc7e-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="4fc7e-127">Filtrar para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="4fc7e-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="4fc7e-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="4fc7e-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="4fc7e-129">Widening</span><span class="sxs-lookup"><span data-stu-id="4fc7e-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="4fc7e-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="4fc7e-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="4fc7e-131">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="4fc7e-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="4fc7e-132">Filtrar Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="4fc7e-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="4fc7e-133">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="4fc7e-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="4fc7e-134">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="4fc7e-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
