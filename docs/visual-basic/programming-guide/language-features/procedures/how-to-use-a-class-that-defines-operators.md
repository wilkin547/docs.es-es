---
title: Procedimiento para usar una clase que define operadores
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
ms.openlocfilehash: fe15e976e6a5469f2a9d1b3521a70a3e1860fdd3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414355"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="15f7f-102">Cómo: Utilizar una clase que define operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15f7f-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="15f7f-103">Si usa una clase o estructura que define sus propios operadores, puede tener acceso a esos operadores desde Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15f7f-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="15f7f-104">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="15f7f-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15f7f-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15f7f-105">Example</span></span>  
 <span data-ttu-id="15f7f-106">En el ejemplo siguiente se tiene acceso a la estructura SQL <xref:System.Data.SqlTypes.SqlString> , que define los operadores de conversión ([función ctype](../../../language-reference/functions/ctype-function.md)) en ambas direcciones entre una cadena SQL y una cadena de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="15f7f-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="15f7f-107">Use `CType(` la *expresión de cadena de SQL*para `String)` convertir una cadena de SQL en una cadena de Visual Basic y `CType(` *Visual Basic expresión de cadena*, <xref:System.Data.SqlTypes.SqlString> `)` para convertirla en la otra dirección.</span><span class="sxs-lookup"><span data-stu-id="15f7f-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="15f7f-108">La <xref:System.Data.SqlTypes.SqlString> estructura define un operador de conversión ([función ctype](../../../language-reference/functions/ctype-function.md)) de `String` a <xref:System.Data.SqlTypes.SqlString> y otro de <xref:System.Data.SqlTypes.SqlString> a `String` .</span><span class="sxs-lookup"><span data-stu-id="15f7f-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="15f7f-109">La instrucción que asigna `title` a `jobTitle` hace uso del primer operador y la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada de función utiliza el segundo.</span><span class="sxs-lookup"><span data-stu-id="15f7f-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="15f7f-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="15f7f-110">Compile the code</span></span>  
 <span data-ttu-id="15f7f-111">Asegúrese de que la clase o estructura que está usando define el operador que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="15f7f-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="15f7f-112">No suponga que la clase o la estructura ha definido todos los operadores disponibles para la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="15f7f-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="15f7f-113">Para obtener una lista de operadores disponibles, vea [Operator (instrucción](../../../language-reference/statements/operator-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="15f7f-113">For a list of available operators, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="15f7f-114">Incluya la `Imports` instrucción adecuada para la cadena SQL al principio del archivo de código fuente (en este caso <xref:System.Data.SqlTypes> ).</span><span class="sxs-lookup"><span data-stu-id="15f7f-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="15f7f-115">El proyecto debe tener referencias a System. Data y System. XML.</span><span class="sxs-lookup"><span data-stu-id="15f7f-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f7f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15f7f-116">See also</span></span>

- [<span data-ttu-id="15f7f-117">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="15f7f-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="15f7f-118">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="15f7f-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="15f7f-119">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="15f7f-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="15f7f-120">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="15f7f-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="15f7f-121">Widening</span><span class="sxs-lookup"><span data-stu-id="15f7f-121">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="15f7f-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="15f7f-122">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="15f7f-123">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="15f7f-123">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="15f7f-124">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="15f7f-124">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="15f7f-125">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="15f7f-125">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="15f7f-126">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="15f7f-126">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
