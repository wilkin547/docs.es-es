---
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
ms.openlocfilehash: 53b0211c6304625edd7ac24fa52ff0c051d8f0a0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388094"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="0d3d2-102">Cómo: Definir un operador de conversión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d3d2-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="0d3d2-103">Si ha definido una clase o estructura, puede definir un operador de conversión de tipos entre el tipo de la clase o estructura y otro tipo de datos (como `Integer` , `Double` o `String` ).</span><span class="sxs-lookup"><span data-stu-id="0d3d2-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="0d3d2-104">Defina la conversión de tipos como un procedimiento de [función ctype](../../../language-reference/functions/ctype-function.md) dentro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="0d3d2-104">Define the type conversion as a [CType Function](../../../language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="0d3d2-105">Todos los procedimientos de conversión deben ser `Public Shared` , y cada uno de ellos debe especificar la [ampliación](../../../language-reference/modifiers/widening.md) o la [restricción](../../../language-reference/modifiers/narrowing.md).</span><span class="sxs-lookup"><span data-stu-id="0d3d2-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../language-reference/modifiers/widening.md) or [Narrowing](../../../language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="0d3d2-106">La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.</span><span class="sxs-lookup"><span data-stu-id="0d3d2-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d3d2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d3d2-107">Example</span></span>  
 <span data-ttu-id="0d3d2-108">En el ejemplo siguiente se definen operadores de conversión entre una estructura denominada `digit` y una `Byte` .</span><span class="sxs-lookup"><span data-stu-id="0d3d2-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 <span data-ttu-id="0d3d2-109">Puede probar la estructura `digit` con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0d3d2-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="0d3d2-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d3d2-110">See also</span></span>

- [<span data-ttu-id="0d3d2-111">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="0d3d2-111">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0d3d2-112">Procedimiento para definir un operador</span><span class="sxs-lookup"><span data-stu-id="0d3d2-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="0d3d2-113">Procedimiento para llamar a un procedimiento de operador</span><span class="sxs-lookup"><span data-stu-id="0d3d2-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="0d3d2-114">Procedimiento para usar una clase que define operadores</span><span class="sxs-lookup"><span data-stu-id="0d3d2-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)
- [<span data-ttu-id="0d3d2-115">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0d3d2-115">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="0d3d2-116">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0d3d2-116">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0d3d2-117">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="0d3d2-117">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="0d3d2-118">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="0d3d2-118">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="0d3d2-119">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="0d3d2-119">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
