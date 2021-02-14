---
description: 'Más información sobre: Cómo: definir un operador (Visual Basic)'
title: Procedimiento para definir un operador
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
ms.openlocfilehash: ead96a302426c6f5b1667bb030aab56afe3284c8
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462716"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="7949e-103">Cómo: Definir un operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7949e-103">How to: Define an Operator (Visual Basic)</span></span>

<span data-ttu-id="7949e-104">Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*` , `<>` o `And` ) cuando uno o los dos operandos son del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7949e-104">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="7949e-105">Defina el operador estándar como procedimiento de operador dentro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7949e-105">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="7949e-106">Todos los procedimientos de operador deben ser `Public` `Shared` .</span><span class="sxs-lookup"><span data-stu-id="7949e-106">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="7949e-107">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="7949e-107">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7949e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7949e-108">Example</span></span>  

 <span data-ttu-id="7949e-109">En el ejemplo siguiente se define el `+` operador para una estructura denominada `height` .</span><span class="sxs-lookup"><span data-stu-id="7949e-109">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="7949e-110">La estructura utiliza altos medidos en pies y pulgadas.</span><span class="sxs-lookup"><span data-stu-id="7949e-110">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="7949e-111">Una *pulgada* es 2,54 centímetros y un *pie* es 12 pulgadas.</span><span class="sxs-lookup"><span data-stu-id="7949e-111">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="7949e-112">Para garantizar valores normalizados (pulgadas < 12,0), el constructor realiza la aritmética de *módulo* 12.</span><span class="sxs-lookup"><span data-stu-id="7949e-112">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="7949e-113">El `+` operador usa el constructor para generar valores normalizados.</span><span class="sxs-lookup"><span data-stu-id="7949e-113">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="7949e-114">Puede probar la estructura `height` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7949e-114">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="7949e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7949e-115">See also</span></span>

- [<span data-ttu-id="7949e-116">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="7949e-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="7949e-117">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="7949e-117">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="7949e-118">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="7949e-118">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="7949e-119">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="7949e-119">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="7949e-120">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="7949e-120">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="7949e-121">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="7949e-121">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7949e-122">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="7949e-122">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="7949e-123">Mod (Operador)</span><span class="sxs-lookup"><span data-stu-id="7949e-123">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)
