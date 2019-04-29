---
title: Subprocedimientos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: b70594e002bbf08f0890586e78df901ccb26c7ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791826"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="1b850-102">Subprocedimientos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b850-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="1b850-103">Un `Sub` procedimiento es una serie de instrucciones de Visual Basic está incluido en el `Sub` y `End Sub` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1b850-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="1b850-104">El `Sub` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="1b850-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="1b850-105">Cada vez que se llama al procedimiento, se ejecutan las instrucciones, empezando por la primera instrucción ejecutable tras el `Sub` instrucción y terminando por la primera `End Sub`, `Exit Sub`, o `Return` encontrada una instrucción.</span><span class="sxs-lookup"><span data-stu-id="1b850-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="1b850-106">Puede definir un `Sub` procedimiento en módulos, clases y estructuras.</span><span class="sxs-lookup"><span data-stu-id="1b850-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="1b850-107">De forma predeterminada, es `Public`, lo que significa que puede llamar desde cualquier lugar en la aplicación que tiene acceso al módulo, clase o estructura en el que se define.</span><span class="sxs-lookup"><span data-stu-id="1b850-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="1b850-108">El término, *método*, describe un `Sub` o `Function` procedimiento que se obtiene acceso desde fuera de su definición de módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1b850-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="1b850-109">Para más información, vea [Procedimientos en Visual Basic](./index.md).</span><span class="sxs-lookup"><span data-stu-id="1b850-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="1b850-110">Un `Sub` procedimiento puede tomar argumentos, como constantes, variables o expresiones, que se pasan a él por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="1b850-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="1b850-111">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="1b850-111">Declaration Syntax</span></span>  
 <span data-ttu-id="1b850-112">La sintaxis para declarar un `Sub` es el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b850-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="1b850-113">`[` *modificadores* `] Sub` *subname* `[(` *parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="1b850-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="1b850-114">El `modifiers` puede especificar el nivel de acceso e información sobre la sobrecarga, invalidación, uso compartido y sombreado.</span><span class="sxs-lookup"><span data-stu-id="1b850-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="1b850-115">Para obtener más información, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1b850-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="1b850-116">Declaración de parámetros</span><span class="sxs-lookup"><span data-stu-id="1b850-116">Parameter Declaration</span></span>  
 <span data-ttu-id="1b850-117">Declarar cada parámetro de procedimiento de forma similar a cómo declarar una variable, especificando el tipo de datos y el nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b850-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="1b850-118">También puede especificar el mecanismo de paso y si el parámetro es opcional o una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="1b850-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="1b850-119">La sintaxis para cada parámetro en la lista de parámetros es como sigue:</span><span class="sxs-lookup"><span data-stu-id="1b850-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="1b850-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *ParameterName*`As`*datatype*</span><span class="sxs-lookup"><span data-stu-id="1b850-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="1b850-121">Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="1b850-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="1b850-122">La sintaxis para especificar un valor predeterminado es como sigue:</span><span class="sxs-lookup"><span data-stu-id="1b850-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="1b850-123">`Optional [ByVal | ByRef]`  *ParameterName*`As`*datatype*`=`*defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="1b850-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="1b850-124">Parámetros como Variables locales</span><span class="sxs-lookup"><span data-stu-id="1b850-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="1b850-125">Cuando el control pasa al procedimiento, cada parámetro se tratan como una variable local.</span><span class="sxs-lookup"><span data-stu-id="1b850-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="1b850-126">Esto significa que su duración es igual que el del procedimiento y su ámbito es el procedimiento completo.</span><span class="sxs-lookup"><span data-stu-id="1b850-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="1b850-127">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="1b850-127">Calling Syntax</span></span>  
 <span data-ttu-id="1b850-128">Se invoca un `Sub` procedimiento explícitamente con una instrucción de llamada independiente.</span><span class="sxs-lookup"><span data-stu-id="1b850-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="1b850-129">No se puede llamar a utilizando su nombre en una expresión.</span><span class="sxs-lookup"><span data-stu-id="1b850-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="1b850-130">Debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1b850-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="1b850-131">Si se proporciona ningún argumento, opcionalmente, puede omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1b850-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1b850-132">El uso de la `Call` palabra clave es opcional, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="1b850-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="1b850-133">La sintaxis para llamar a un `Sub` es el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b850-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="1b850-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="1b850-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="1b850-135">Puede llamar a un `Sub` método desde fuera de la clase que lo define.</span><span class="sxs-lookup"><span data-stu-id="1b850-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="1b850-136">En primer lugar, tiene que usar el `New` palabra clave para crear una instancia de la clase o llamar a un método que devuelve una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="1b850-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="1b850-137">Para obtener más información, consulte [nuevo operador](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1b850-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="1b850-138">A continuación, puede usar la siguiente sintaxis para llamar a la `Sub` método en el objeto de instancia:</span><span class="sxs-lookup"><span data-stu-id="1b850-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="1b850-139">*Objeto*. *MethodName*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="1b850-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="1b850-140">Ilustración de la declaración y llamada</span><span class="sxs-lookup"><span data-stu-id="1b850-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="1b850-141">La siguiente `Sub` procedimiento le indica al usuario del equipo tarea que la aplicación está a punto de llevar a cabo y también muestra una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="1b850-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="1b850-142">En lugar de duplicar este código al principio de cada tarea, la aplicación simplemente llama a `tellOperator` desde varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1b850-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="1b850-143">Cada llamada pasa una cadena en el `task` argumento que identifica la tarea que se está iniciando.</span><span class="sxs-lookup"><span data-stu-id="1b850-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="1b850-144">El ejemplo siguiente muestra una llamada típica al `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="1b850-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1b850-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b850-145">See also</span></span>

- [<span data-ttu-id="1b850-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="1b850-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1b850-147">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="1b850-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="1b850-148">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="1b850-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="1b850-149">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="1b850-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="1b850-150">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="1b850-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1b850-151">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1b850-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1b850-152">Cómo: Llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="1b850-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="1b850-153">Cómo: Llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b850-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
