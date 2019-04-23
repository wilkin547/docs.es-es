---
title: Procedimiento Crear un procedimiento que devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 115c1df4bd49d5848d72c4cbd0242a49a12740c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335503"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="bd7d8-102">Procedimiento Crear un procedimiento que devuelve un valor (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd7d8-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="bd7d8-103">Usa un `Function` procedimiento devuelva un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="bd7d8-104">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="bd7d8-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="bd7d8-105">Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="bd7d8-106">En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, a continuación, en la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="bd7d8-107">Siga los paréntesis con un `As` cláusula para especificar el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="bd7d8-108">Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="bd7d8-109">Use un `Return` instrucción para devolver el valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="bd7d8-110">La siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los dos lados.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="bd7d8-111">El ejemplo siguiente muestra una llamada típica al `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="bd7d8-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="bd7d8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd7d8-112">See also</span></span>

- [<span data-ttu-id="bd7d8-113">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="bd7d8-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bd7d8-114">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="bd7d8-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="bd7d8-115">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="bd7d8-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="bd7d8-116">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="bd7d8-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="bd7d8-117">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="bd7d8-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="bd7d8-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="bd7d8-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="bd7d8-119">Cómo: Devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="bd7d8-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="bd7d8-120">Cómo: Llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="bd7d8-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
