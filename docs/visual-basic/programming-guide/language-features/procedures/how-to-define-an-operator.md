---
title: 'Cómo: Definir un operador (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 1f5a020a710cecdfd8722a9fca0a8b329697eced
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805404"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="0528a-102">Cómo: Definir un operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0528a-102">How to: Define an Operator (Visual Basic)</span></span>
<span data-ttu-id="0528a-103">Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*`, `<>`, o `And`) cuando uno o ambos de los operandos es del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="0528a-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="0528a-104">Definir el operador estándar como un procedimiento de operador dentro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="0528a-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="0528a-105">Todos los procedimientos de operador deben ser `Public` `Shared`.</span><span class="sxs-lookup"><span data-stu-id="0528a-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="0528a-106">Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.</span><span class="sxs-lookup"><span data-stu-id="0528a-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0528a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0528a-107">Example</span></span>  
 <span data-ttu-id="0528a-108">En el ejemplo siguiente se define la `+` operador para una estructura denominada `height`.</span><span class="sxs-lookup"><span data-stu-id="0528a-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="0528a-109">La estructura utiliza altos que se miden en pies y pulgadas.</span><span class="sxs-lookup"><span data-stu-id="0528a-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="0528a-110">Una *pulgadas* es 2,54 centímetros y uno *foot* es de 12 pulgadas.</span><span class="sxs-lookup"><span data-stu-id="0528a-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="0528a-111">Para garantizar que los valores normalizados (pulgadas < 12.0), el constructor realiza *módulo* 12 aritméticos.</span><span class="sxs-lookup"><span data-stu-id="0528a-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="0528a-112">El `+` operador utiliza el constructor para generar valores normalizados.</span><span class="sxs-lookup"><span data-stu-id="0528a-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 <span data-ttu-id="0528a-113">Puede probar la estructura `height` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0528a-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 <span data-ttu-id="0528a-114">Para obtener más información y ejemplos, vea [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx) (Sobrecarga de operadores en Visual Basic 2005).</span><span class="sxs-lookup"><span data-stu-id="0528a-114">For more information and examples, see [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0528a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0528a-115">See Also</span></span>  
 [<span data-ttu-id="0528a-116">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="0528a-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="0528a-117">Definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="0528a-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="0528a-118">Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="0528a-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="0528a-119">Utilizar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="0528a-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="0528a-120">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0528a-120">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="0528a-121">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0528a-121">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="0528a-122">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="0528a-122">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="0528a-123">Mod (operador)</span><span class="sxs-lookup"><span data-stu-id="0528a-123">Mod Operator</span></span>](../../../../visual-basic/language-reference/operators/mod-operator.md)
