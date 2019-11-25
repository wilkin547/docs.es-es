---
title: 'Cómo: Definir un operador de conversión'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344900"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="f080f-102">Cómo: Definir un operador de conversión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f080f-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="f080f-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span><span class="sxs-lookup"><span data-stu-id="f080f-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="f080f-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span><span class="sxs-lookup"><span data-stu-id="f080f-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="f080f-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="f080f-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="f080f-106">Defining an operator on a class or structure is also called *overloading* the operator.</span><span class="sxs-lookup"><span data-stu-id="f080f-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f080f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f080f-107">Example</span></span>  
 <span data-ttu-id="f080f-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span><span class="sxs-lookup"><span data-stu-id="f080f-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="f080f-109">You can test the structure `digit` with the following code.</span><span class="sxs-lookup"><span data-stu-id="f080f-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="f080f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f080f-110">See also</span></span>

- [<span data-ttu-id="f080f-111">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="f080f-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f080f-112">Definir un operador</span><span class="sxs-lookup"><span data-stu-id="f080f-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="f080f-113">Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="f080f-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="f080f-114">Utilizar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="f080f-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="f080f-115">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f080f-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="f080f-116">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f080f-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="f080f-117">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="f080f-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="f080f-118">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="f080f-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="f080f-119">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="f080f-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
