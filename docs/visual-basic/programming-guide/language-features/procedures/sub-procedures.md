---
description: 'Más información sobre: procedimientos sub (Visual Basic)'
title: Sub (procedimientos)
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
ms.openlocfilehash: fe9d26fb2d18fbd29820af7aca96b826d7b45d0b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466515"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="0c5b7-103">Procedimientos sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c5b7-103">Sub procedures (Visual Basic)</span></span>

<span data-ttu-id="0c5b7-104">Un `Sub` procedimiento es una serie de instrucciones Visual Basic incluidas en las `Sub` `End Sub` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-104">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="0c5b7-105">El `Sub` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-105">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>

<span data-ttu-id="0c5b7-106">Cada vez que se llama al procedimiento, se ejecutan sus instrucciones, comenzando por la primera instrucción ejecutable después de la `Sub` instrucción y terminando por la primera `End Sub` `Exit Sub` instrucción, o `Return` encontrada.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-106">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>

<span data-ttu-id="0c5b7-107">Puede definir un `Sub` procedimiento en módulos, clases y estructuras.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-107">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="0c5b7-108">De forma predeterminada, es `Public` , lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, la clase o la estructura en la que se definió.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-108">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="0c5b7-109">El término *método* describe un `Sub` `Function` procedimiento o al que se tiene acceso desde fuera de su módulo de definición, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-109">The term *method* describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="0c5b7-110">Para más información, vea [Procedimientos en Visual Basic](./index.md).</span><span class="sxs-lookup"><span data-stu-id="0c5b7-110">For more information, see [Procedures](./index.md).</span></span>

<span data-ttu-id="0c5b7-111">Un `Sub` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se le pasan por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-111">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="0c5b7-112">Sintaxis de declaración</span><span class="sxs-lookup"><span data-stu-id="0c5b7-112">Declaration syntax</span></span>

<span data-ttu-id="0c5b7-113">La sintaxis para declarar un `Sub` procedimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5b7-113">The syntax for declaring a `Sub` procedure is as follows:</span></span>

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

<span data-ttu-id="0c5b7-114">`modifiers`Puede especificar el nivel de acceso e información sobre la sobrecarga, el reemplazo, el uso compartido y el sombreado.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="0c5b7-115">Para obtener más información, vea [Sub Statement](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0c5b7-115">For more information, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="0c5b7-116">Declaración de parámetros</span><span class="sxs-lookup"><span data-stu-id="0c5b7-116">Parameter declaration</span></span>

<span data-ttu-id="0c5b7-117">Cada parámetro de procedimiento se declara de forma similar a como se declara una variable, especificando el nombre del parámetro y el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="0c5b7-118">También puede especificar el mecanismo de paso y si el parámetro es opcional o una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>

<span data-ttu-id="0c5b7-119">La sintaxis de cada parámetro de la lista de parámetros es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5b7-119">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

<span data-ttu-id="0c5b7-120">Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-120">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="0c5b7-121">La sintaxis para especificar un valor predeterminado es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5b7-121">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a><span data-ttu-id="0c5b7-122">Parámetros como variables locales</span><span class="sxs-lookup"><span data-stu-id="0c5b7-122">Parameters as local variables</span></span>

<span data-ttu-id="0c5b7-123">Cuando el control pasa al procedimiento, cada parámetro se trata como una variable local.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-123">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="0c5b7-124">Esto significa que su duración es la misma que la del procedimiento y su ámbito es todo el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-124">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="0c5b7-125">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="0c5b7-125">Calling syntax</span></span>

<span data-ttu-id="0c5b7-126">Un procedimiento se invoca `Sub` explícitamente con una instrucción de llamada independiente.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-126">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="0c5b7-127">No se puede llamar mediante su nombre en una expresión.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-127">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="0c5b7-128">Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-128">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="0c5b7-129">Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-129">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="0c5b7-130">El uso de la `Call` palabra clave es opcional, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-130">The use of the `Call` keyword is optional but not recommended.</span></span>

<span data-ttu-id="0c5b7-131">La sintaxis de una llamada a un `Sub` procedimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c5b7-131">The syntax for a call to a `Sub` procedure is as follows:</span></span>

```vb
[Call] SubName[(argumentlist)]
```

<span data-ttu-id="0c5b7-132">Puede llamar a un `Sub` método desde fuera de la clase que lo define.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-132">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="0c5b7-133">En primer lugar, debe usar la `New` palabra clave para crear una instancia de la clase o llamar a un método que devuelva una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-133">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="0c5b7-134">Para obtener más información, vea [New (operador](../../../language-reference/operators/new-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0c5b7-134">For more information, see [New Operator](../../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="0c5b7-135">A continuación, puede usar la siguiente sintaxis para llamar al `Sub` método en el objeto de instancia:</span><span class="sxs-lookup"><span data-stu-id="0c5b7-135">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="0c5b7-136">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="0c5b7-136">Illustration of declaration and call</span></span>

<span data-ttu-id="0c5b7-137">El siguiente `Sub` procedimiento indica al operador de equipo qué tarea está a punto de realizar la aplicación y también muestra una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-137">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="0c5b7-138">En lugar de duplicar este código al inicio de cada tarea, la aplicación simplemente llama `tellOperator` desde varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-138">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="0c5b7-139">Cada llamada pasa una cadena en el `task` argumento que identifica la tarea que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="0c5b7-139">Each call passes a string in the `task` argument that identifies the task being started.</span></span>

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

<span data-ttu-id="0c5b7-140">En el ejemplo siguiente se muestra una llamada típica a `tellOperator` .</span><span class="sxs-lookup"><span data-stu-id="0c5b7-140">The following example shows a typical call to `tellOperator`.</span></span>

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="0c5b7-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c5b7-141">See also</span></span>

- [<span data-ttu-id="0c5b7-142">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="0c5b7-142">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0c5b7-143">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="0c5b7-143">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="0c5b7-144">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="0c5b7-144">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0c5b7-145">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="0c5b7-145">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0c5b7-146">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="0c5b7-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0c5b7-147">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="0c5b7-147">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="0c5b7-148">Procedimiento apara llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="0c5b7-148">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="0c5b7-149">Cómo: Llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c5b7-149">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
