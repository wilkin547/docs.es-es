---
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
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163818"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="21b5f-102">Procedimientos sub (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21b5f-102">Sub procedures (Visual Basic)</span></span>

<span data-ttu-id="21b5f-103">Un procedimiento `Sub` es una serie de instrucciones de Visual Basic incluidas en las instrucciones `Sub` y `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="21b5f-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="21b5f-104">El procedimiento `Sub` realiza una tarea y, a continuación, devuelve el control al código de llamada, pero no devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="21b5f-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>

<span data-ttu-id="21b5f-105">Cada vez que se llama al procedimiento, se ejecutan sus instrucciones, comenzando por la primera instrucción ejecutable después de la instrucción `Sub` y finalizando con la primera instrucción `End Sub`, `Exit Sub`o `Return` encontrada.</span><span class="sxs-lookup"><span data-stu-id="21b5f-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>

<span data-ttu-id="21b5f-106">Puede definir una `Sub` procedimiento en módulos, clases y estructuras.</span><span class="sxs-lookup"><span data-stu-id="21b5f-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="21b5f-107">De forma predeterminada, es `Public`, lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, clase o estructura en la que se definió.</span><span class="sxs-lookup"><span data-stu-id="21b5f-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="21b5f-108">El término *método* describe un procedimiento `Sub` o `Function` al que se tiene acceso desde fuera de su módulo de definición, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="21b5f-108">The term *method* describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="21b5f-109">Para más información, vea [Procedimientos en Visual Basic](./index.md).</span><span class="sxs-lookup"><span data-stu-id="21b5f-109">For more information, see [Procedures](./index.md).</span></span>

<span data-ttu-id="21b5f-110">Un procedimiento `Sub` puede tomar argumentos, como constantes, variables o expresiones, que se le pasan mediante el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="21b5f-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="21b5f-111">Sintaxis de declaración</span><span class="sxs-lookup"><span data-stu-id="21b5f-111">Declaration syntax</span></span>

<span data-ttu-id="21b5f-112">La sintaxis para declarar un procedimiento `Sub` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="21b5f-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

<span data-ttu-id="21b5f-113">El `modifiers` puede especificar el nivel de acceso e información sobre la sobrecarga, el reemplazo, el uso compartido y el sombreado.</span><span class="sxs-lookup"><span data-stu-id="21b5f-113">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="21b5f-114">Para obtener más información, vea [Sub Statement](../../../language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="21b5f-114">For more information, see [Sub Statement](../../../language-reference/statements/sub-statement.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="21b5f-115">Declaración de parámetros</span><span class="sxs-lookup"><span data-stu-id="21b5f-115">Parameter declaration</span></span>

<span data-ttu-id="21b5f-116">Cada parámetro de procedimiento se declara de forma similar a como se declara una variable, especificando el nombre del parámetro y el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="21b5f-116">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="21b5f-117">También puede especificar el mecanismo de paso y si el parámetro es opcional o una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="21b5f-117">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>

<span data-ttu-id="21b5f-118">La sintaxis de cada parámetro de la lista de parámetros es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="21b5f-118">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

<span data-ttu-id="21b5f-119">Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="21b5f-119">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="21b5f-120">La sintaxis para especificar un valor predeterminado es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="21b5f-120">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a><span data-ttu-id="21b5f-121">Parámetros como variables locales</span><span class="sxs-lookup"><span data-stu-id="21b5f-121">Parameters as local variables</span></span>

<span data-ttu-id="21b5f-122">Cuando el control pasa al procedimiento, cada parámetro se trata como una variable local.</span><span class="sxs-lookup"><span data-stu-id="21b5f-122">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="21b5f-123">Esto significa que su duración es la misma que la del procedimiento y su ámbito es todo el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="21b5f-123">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="21b5f-124">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="21b5f-124">Calling syntax</span></span>

<span data-ttu-id="21b5f-125">Invoca un procedimiento `Sub` explícitamente con una instrucción de llamada independiente.</span><span class="sxs-lookup"><span data-stu-id="21b5f-125">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="21b5f-126">No se puede llamar mediante su nombre en una expresión.</span><span class="sxs-lookup"><span data-stu-id="21b5f-126">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="21b5f-127">Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="21b5f-127">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="21b5f-128">Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="21b5f-128">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="21b5f-129">El uso de la palabra clave `Call` es opcional, pero no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="21b5f-129">The use of the `Call` keyword is optional but not recommended.</span></span>

<span data-ttu-id="21b5f-130">La sintaxis de una llamada a un procedimiento `Sub` es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="21b5f-130">The syntax for a call to a `Sub` procedure is as follows:</span></span>

```vb
[Call] SubName[(argumentlist)]
```

<span data-ttu-id="21b5f-131">Puede llamar a un método `Sub` desde fuera de la clase que lo define.</span><span class="sxs-lookup"><span data-stu-id="21b5f-131">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="21b5f-132">En primer lugar, debe usar la palabra clave `New` para crear una instancia de la clase o llamar a un método que devuelva una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="21b5f-132">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="21b5f-133">Para obtener más información, vea [New (operador](../../../language-reference/operators/new-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="21b5f-133">For more information, see [New Operator](../../../language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="21b5f-134">A continuación, puede usar la siguiente sintaxis para llamar al método `Sub` en el objeto de instancia:</span><span class="sxs-lookup"><span data-stu-id="21b5f-134">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="21b5f-135">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="21b5f-135">Illustration of declaration and call</span></span>

<span data-ttu-id="21b5f-136">En el siguiente procedimiento de `Sub` se indica al operador de equipo qué tarea está a punto de realizar la aplicación y también se muestra una marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="21b5f-136">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="21b5f-137">En lugar de duplicar este código al inicio de cada tarea, la aplicación simplemente llama a `tellOperator` desde varias ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="21b5f-137">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="21b5f-138">Cada llamada pasa una cadena en el argumento `task` que identifica la tarea que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="21b5f-138">Each call passes a string in the `task` argument that identifies the task being started.</span></span>

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

<span data-ttu-id="21b5f-139">En el ejemplo siguiente se muestra una llamada típica a `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="21b5f-139">The following example shows a typical call to `tellOperator`.</span></span>

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a><span data-ttu-id="21b5f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="21b5f-140">See also</span></span>

- [<span data-ttu-id="21b5f-141">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="21b5f-141">Procedures</span></span>](./index.md)
- [<span data-ttu-id="21b5f-142">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="21b5f-142">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="21b5f-143">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="21b5f-143">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="21b5f-144">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="21b5f-144">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="21b5f-145">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="21b5f-145">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="21b5f-146">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="21b5f-146">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="21b5f-147">Llamar a un procedimiento que no devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="21b5f-147">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="21b5f-148">Cómo: llamar a un controlador de eventos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21b5f-148">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
