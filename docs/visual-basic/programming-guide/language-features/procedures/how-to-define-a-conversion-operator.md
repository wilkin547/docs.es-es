---
description: 'Más información sobre: Cómo: definir un operador de conversión (Visual Basic)'
title: Procedimiento para definir un operador de conversión
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: c090e183e809974163625c4bfcf33536b1082b66
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481992"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="707ec-103">Cómo: Definir un operador de conversión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="707ec-103">How to: Define a Conversion Operator (Visual Basic)</span></span>

<span data-ttu-id="707ec-104">Si ha definido una clase o estructura, puede definir un operador de conversión de tipos entre el tipo de la clase o estructura y otro tipo de datos (como `Integer` , `Double` o `String` ).</span><span class="sxs-lookup"><span data-stu-id="707ec-104">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="707ec-105">Defina la conversión de tipos como un procedimiento de [función ctype](../../../language-reference/functions/ctype-function.md) dentro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="707ec-105">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="707ec-106">Todos los procedimientos de conversión deben ser `Public Shared` , y cada uno de ellos debe especificar la [ampliación](../../../language-reference/modifiers/widening.md) o la [restricción](../../../language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="707ec-106">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="707ec-107">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="707ec-107">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="707ec-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="707ec-108">Example</span></span>  

 <span data-ttu-id="707ec-109">En el ejemplo siguiente se definen operadores de conversión entre una estructura denominada `digit` y una `Byte` .</span><span class="sxs-lookup"><span data-stu-id="707ec-109">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="707ec-110">Puede probar la estructura `digit` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="707ec-110">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="707ec-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="707ec-111">See also</span></span>

- [<span data-ttu-id="707ec-112">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="707ec-112">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="707ec-113">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="707ec-113">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="707ec-114">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="707ec-114">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="707ec-115">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="707ec-115">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="707ec-116">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="707ec-116">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="707ec-117">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="707ec-117">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="707ec-118">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="707ec-118">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="707ec-119">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="707ec-119">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="707ec-120">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="707ec-120">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
