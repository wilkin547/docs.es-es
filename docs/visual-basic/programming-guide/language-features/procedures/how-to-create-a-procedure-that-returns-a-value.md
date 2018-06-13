---
title: 'Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 472f55173a4897a23a82812a2b24bf1646c1a6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648442"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="3b1a3-102">Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b1a3-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="3b1a3-103">Usa un `Function` procedimiento devuelva un valor para el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="3b1a3-104">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="3b1a3-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="3b1a3-105">Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="3b1a3-106">En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, a continuación, en la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="3b1a3-107">Siga los paréntesis con un `As` cláusula para especificar el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="3b1a3-108">Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="3b1a3-109">Use un `Return` instrucción para devolver el valor para el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="3b1a3-110">El siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="3b1a3-111">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="3b1a3-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3b1a3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b1a3-112">See Also</span></span>  
 [<span data-ttu-id="3b1a3-113">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="3b1a3-113">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3b1a3-114">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="3b1a3-114">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3b1a3-115">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="3b1a3-115">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3b1a3-116">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="3b1a3-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="3b1a3-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="3b1a3-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3b1a3-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3b1a3-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="3b1a3-119">Devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="3b1a3-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="3b1a3-120">Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="3b1a3-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
