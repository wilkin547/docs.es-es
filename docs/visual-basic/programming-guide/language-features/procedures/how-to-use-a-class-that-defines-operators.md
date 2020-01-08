---
title: 'Cómo: Utilizar una clase que define operadores'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347892"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="811e4-102">Cómo: Utilizar una clase que define operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="811e4-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="811e4-103">Si usa una clase o estructura que define sus propios operadores, puede tener acceso a esos operadores desde Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="811e4-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="811e4-104">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="811e4-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="811e4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="811e4-105">Example</span></span>  
 <span data-ttu-id="811e4-106">En el ejemplo siguiente se obtiene acceso a la estructura de SQL <xref:System.Data.SqlTypes.SqlString>, que define los operadores de conversión ([función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una cadena Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="811e4-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="811e4-107">Use `CType(`*expresión de cadena SQL*, `String)` para convertir una cadena SQL en una cadena Visual Basic y `CType(`*Visual Basic expresión de cadena*, <xref:System.Data.SqlTypes.SqlString>`)` para convertirla en la otra dirección.</span><span class="sxs-lookup"><span data-stu-id="811e4-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="811e4-108">La estructura <xref:System.Data.SqlTypes.SqlString> define un operador de conversión ([función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md)) de `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String`.</span><span class="sxs-lookup"><span data-stu-id="811e4-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="811e4-109">La instrucción que asigna `title` a `jobTitle` usa el primer operador y la llamada a la función <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> usa el segundo.</span><span class="sxs-lookup"><span data-stu-id="811e4-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="811e4-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="811e4-110">Compile the code</span></span>  
 <span data-ttu-id="811e4-111">Asegúrese de que la clase o estructura que está usando define el operador que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="811e4-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="811e4-112">No suponga que la clase o la estructura ha definido todos los operadores disponibles para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="811e4-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="811e4-113">Para obtener una lista de operadores disponibles, vea [Operator (instrucción](../../../../visual-basic/language-reference/statements/operator-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="811e4-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="811e4-114">Incluya la instrucción `Imports` adecuada para la cadena SQL al principio del archivo de código fuente (en este caso <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="811e4-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="811e4-115">El proyecto debe tener referencias a System. Data y System. XML.</span><span class="sxs-lookup"><span data-stu-id="811e4-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811e4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="811e4-116">See also</span></span>

- [<span data-ttu-id="811e4-117">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="811e4-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="811e4-118">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="811e4-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="811e4-119">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="811e4-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="811e4-120">Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="811e4-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="811e4-121">Widening</span><span class="sxs-lookup"><span data-stu-id="811e4-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="811e4-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="811e4-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="811e4-123">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="811e4-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="811e4-124">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="811e4-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="811e4-125">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="811e4-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="811e4-126">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="811e4-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
