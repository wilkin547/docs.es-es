---
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
ms.openlocfilehash: 5acbd0439ddbb956b80d56e23d11cd5e152f37ff
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087406"
---
# <a name="how-to-define-an-operator-visual-basic"></a><span data-ttu-id="f37f7-102">Cómo: Definir un operador (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f37f7-102">How to: Define an Operator (Visual Basic)</span></span>

<span data-ttu-id="f37f7-103">Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*` , `<>` o `And` ) cuando uno o los dos operandos son del tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f37f7-103">If you have defined a class or structure, you can define the behavior of a standard operator (such as `*`, `<>`, or `And`) when one or both of the operands is of the type of your class or structure.</span></span>  
  
 <span data-ttu-id="f37f7-104">Defina el operador estándar como procedimiento de operador dentro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f37f7-104">Define the standard operator as an operator procedure within the class or structure.</span></span> <span data-ttu-id="f37f7-105">Todos los procedimientos de operador deben ser `Public` `Shared` .</span><span class="sxs-lookup"><span data-stu-id="f37f7-105">All operator procedures must be `Public` `Shared`.</span></span>  
  
 <span data-ttu-id="f37f7-106">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="f37f7-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f37f7-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f37f7-107">Example</span></span>  

 <span data-ttu-id="f37f7-108">En el ejemplo siguiente se define el `+` operador para una estructura denominada `height` .</span><span class="sxs-lookup"><span data-stu-id="f37f7-108">The following example defines the `+` operator for a structure called `height`.</span></span> <span data-ttu-id="f37f7-109">La estructura utiliza altos medidos en pies y pulgadas.</span><span class="sxs-lookup"><span data-stu-id="f37f7-109">The structure uses heights measured in feet and inches.</span></span> <span data-ttu-id="f37f7-110">Una *pulgada* es 2,54 centímetros y un *pie* es 12 pulgadas.</span><span class="sxs-lookup"><span data-stu-id="f37f7-110">One *inch* is 2.54 centimeters, and one *foot* is 12 inches.</span></span> <span data-ttu-id="f37f7-111">Para garantizar valores normalizados (pulgadas < 12,0), el constructor realiza la aritmética de *módulo* 12.</span><span class="sxs-lookup"><span data-stu-id="f37f7-111">To ensure normalized values (inches < 12.0), the constructor performs *modulo* 12 arithmetic.</span></span> <span data-ttu-id="f37f7-112">El `+` operador usa el constructor para generar valores normalizados.</span><span class="sxs-lookup"><span data-stu-id="f37f7-112">The `+` operator uses the constructor to generate normalized values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 <span data-ttu-id="f37f7-113">Puede probar la estructura `height` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f37f7-113">You can test the structure `height` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a><span data-ttu-id="f37f7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f37f7-114">See also</span></span>

- [<span data-ttu-id="f37f7-115">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="f37f7-115">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f37f7-116">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="f37f7-116">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="f37f7-117">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="f37f7-117">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="f37f7-118">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="f37f7-118">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="f37f7-119">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="f37f7-119">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="f37f7-120">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f37f7-120">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f37f7-121">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="f37f7-121">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f37f7-122">Mod (Operador)</span><span class="sxs-lookup"><span data-stu-id="f37f7-122">Mod Operator</span></span>](../../../language-reference/operators/mod-operator.md)
