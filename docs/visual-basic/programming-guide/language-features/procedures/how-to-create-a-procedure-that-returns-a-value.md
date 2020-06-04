---
title: Procedimiento para crear un procedimiento que devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 2655aba6ce37be831d8dd4202ffd484cfd3fd5ef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388354"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="6f393-102">Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f393-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="6f393-103">Use un `Function` procedimiento para devolver un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="6f393-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="6f393-104">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="6f393-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="6f393-105">Fuera de cualquier otro procedimiento, use una `Function` instrucción seguida de una `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6f393-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="6f393-106">En la `Function` instrucción, siga la `Function` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6f393-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="6f393-107">Siga los paréntesis con una `As` cláusula para especificar el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="6f393-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="6f393-108">Coloque las instrucciones de código del procedimiento entre `Function` las `End Function` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="6f393-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="6f393-109">Use una `Return` instrucción para devolver el valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="6f393-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="6f393-110">En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="6f393-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="6f393-111">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="6f393-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6f393-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f393-112">See also</span></span>

- [<span data-ttu-id="6f393-113">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6f393-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6f393-114">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="6f393-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="6f393-115">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="6f393-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6f393-116">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="6f393-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="6f393-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="6f393-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6f393-118">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="6f393-118">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="6f393-119">Procedimiento para devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="6f393-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="6f393-120">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="6f393-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
