---
title: 'Cómo: Crear un procedimiento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: da4cc299fbe35702990a62b5bf824e3ac71d5902
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649268"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="04267-102">Cómo: Crear un procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04267-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="04267-103">Incluir un procedimiento entre una instrucción de declaración inicial (`Sub` o `Function`) y una instrucción de declaración final (`End Sub` o `End Function`).</span><span class="sxs-lookup"><span data-stu-id="04267-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="04267-104">Todo el código de procedimiento está comprendida entre estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="04267-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="04267-105">Un procedimiento no puede contener otro procedimiento, por lo que sus instrucciones inicial y finales deben estar fuera de cualquier otro procedimiento.</span><span class="sxs-lookup"><span data-stu-id="04267-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="04267-106">Si tiene código que realiza la misma tarea en distintos lugares, puede escribir la tarea una vez que un procedimiento y, a continuación, llamarlo desde distintos lugares del código.</span><span class="sxs-lookup"><span data-stu-id="04267-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="04267-107">Para crear un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="04267-107">To create a procedure that does not return a value</span></span>  
  
1.  <span data-ttu-id="04267-108">Fuera de cualquier otro procedimiento, utilice un `Sub` instrucción, seguida de un `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="04267-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="04267-109">En el `Sub` (instrucción), siga el `Sub` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="04267-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="04267-110">Coloque las instrucciones de código del procedimiento entre el `Sub` y `End Sub` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="04267-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="04267-111">Para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="04267-111">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="04267-112">Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="04267-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="04267-113">En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis y, a continuación, un `As` cláusula que especifica el tipo de datos del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="04267-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3.  <span data-ttu-id="04267-114">Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="04267-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4.  <span data-ttu-id="04267-115">Use un `Return` instrucción para devolver el valor para el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="04267-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="04267-116">Para conectar el nuevo procedimiento con los bloques anteriores y repetitivos de código</span><span class="sxs-lookup"><span data-stu-id="04267-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1.  <span data-ttu-id="04267-117">Asegúrese de que define el nuevo procedimiento en un lugar donde el código anterior tiene acceso a él.</span><span class="sxs-lookup"><span data-stu-id="04267-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2.  <span data-ttu-id="04267-118">En el bloque de código anterior, repetitivos, reemplace las instrucciones que realizan la tarea repetitiva con una sola instrucción que llama el `Sub` o `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="04267-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3.  <span data-ttu-id="04267-119">Si el procedimiento es un `Function` que devuelve un valor, asegúrese de que la instrucción de llamada realiza una acción con el valor devuelto, como el almacenamiento en una variable, o bien el valor se perderá.</span><span class="sxs-lookup"><span data-stu-id="04267-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04267-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04267-120">Example</span></span>  
 <span data-ttu-id="04267-121">El siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="04267-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04267-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="04267-122">See also</span></span>

 [<span data-ttu-id="04267-123">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="04267-123">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="04267-124">Subprocedimientos</span><span class="sxs-lookup"><span data-stu-id="04267-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="04267-125">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="04267-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="04267-126">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="04267-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="04267-127">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="04267-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="04267-128">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="04267-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="04267-129">Procedimientos recursivos</span><span class="sxs-lookup"><span data-stu-id="04267-129">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="04267-130">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="04267-130">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="04267-131">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="04267-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="04267-132">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04267-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
