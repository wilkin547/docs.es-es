---
title: Filtrar Definir un operador de conversión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: cf7bfdd09c7f3429f9c730a7aec34b24af3f2e9f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829231"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="7c9e5-102">Filtrar Definir un operador de conversión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c9e5-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="7c9e5-103">Si ha definido una clase o estructura, puede definir un operador de conversión de tipos entre el tipo de la clase o estructura y otro tipo de datos (como `Integer`, `Double`, o `String`).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="7c9e5-104">Definir la conversión de tipos como un [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedimiento dentro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="7c9e5-105">Todos los procedimientos de conversión deben ser `Public Shared`, y cada uno debe especificar [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) o [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="7c9e5-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="7c9e5-106">Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c9e5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c9e5-107">Example</span></span>  
 <span data-ttu-id="7c9e5-108">En el ejemplo siguiente se define los operadores de conversión entre una estructura denominada `digit` y un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="7c9e5-109">Puede probar la estructura `digit` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c9e5-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="7c9e5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c9e5-110">See also</span></span>

- [<span data-ttu-id="7c9e5-111">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="7c9e5-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="7c9e5-112">Cómo: Definir un operador</span><span class="sxs-lookup"><span data-stu-id="7c9e5-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="7c9e5-113">Cómo: Llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="7c9e5-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="7c9e5-114">Cómo: Usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="7c9e5-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="7c9e5-115">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7c9e5-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="7c9e5-116">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7c9e5-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="7c9e5-117">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="7c9e5-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="7c9e5-118">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="7c9e5-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="7c9e5-119">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="7c9e5-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
