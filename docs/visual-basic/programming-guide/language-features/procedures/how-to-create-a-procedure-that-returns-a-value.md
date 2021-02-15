---
description: 'Más información sobre: Cómo: crear un procedimiento que devuelve un valor (Visual Basic)'
title: Procedimiento para crear un procedimiento que devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: fa2ea50febd1cc4e7aecf1e6f5cca671789b36fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100467061"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="acffb-103">Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acffb-103">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>

<span data-ttu-id="acffb-104">Use un `Function` procedimiento para devolver un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="acffb-104">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="acffb-105">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="acffb-105">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="acffb-106">Fuera de cualquier otro procedimiento, use una `Function` instrucción seguida de una `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="acffb-106">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="acffb-107">En la `Function` instrucción, siga la `Function` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="acffb-107">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="acffb-108">Siga los paréntesis con una `As` cláusula para especificar el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="acffb-108">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="acffb-109">Coloque las instrucciones de código del procedimiento entre `Function` las `End Function` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="acffb-109">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="acffb-110">Use una `Return` instrucción para devolver el valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="acffb-110">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="acffb-111">En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="acffb-111">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="acffb-112">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="acffb-112">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="acffb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acffb-113">See also</span></span>

- [<span data-ttu-id="acffb-114">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="acffb-114">Procedures</span></span>](./index.md)
- [<span data-ttu-id="acffb-115">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="acffb-115">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="acffb-116">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="acffb-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="acffb-117">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="acffb-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="acffb-118">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="acffb-118">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="acffb-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="acffb-119">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="acffb-120">Procedimiento para devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="acffb-120">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="acffb-121">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="acffb-121">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
