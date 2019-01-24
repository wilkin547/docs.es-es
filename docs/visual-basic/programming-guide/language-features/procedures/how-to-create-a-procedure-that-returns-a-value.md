---
title: Procedimiento Crear un procedimiento que devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 18becfe05da27e538c5c294b26e0bb7aa19cad2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506425"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="08cbc-102">Procedimiento Crear un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="08cbc-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="08cbc-103">Usa un `Function` procedimiento devuelva un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08cbc-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="08cbc-104">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="08cbc-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="08cbc-105">Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="08cbc-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="08cbc-106">En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, a continuación, en la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="08cbc-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="08cbc-107">Siga los paréntesis con un `As` cláusula para especificar el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="08cbc-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="08cbc-108">Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="08cbc-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="08cbc-109">Use un `Return` instrucción para devolver el valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="08cbc-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="08cbc-110">La siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los dos lados.</span><span class="sxs-lookup"><span data-stu-id="08cbc-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="08cbc-111">El ejemplo siguiente muestra una llamada típica al `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="08cbc-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="08cbc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="08cbc-112">See also</span></span>
- [<span data-ttu-id="08cbc-113">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="08cbc-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="08cbc-114">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="08cbc-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="08cbc-115">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="08cbc-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="08cbc-116">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="08cbc-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="08cbc-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="08cbc-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="08cbc-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="08cbc-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="08cbc-119">Cómo: Devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="08cbc-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="08cbc-120">Cómo: Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="08cbc-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
