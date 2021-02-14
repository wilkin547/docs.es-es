---
description: 'Más información sobre: procedimientos de función (Visual Basic)'
title: Function (procedimientos)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 4997059fc33fb5d438519356b2c9fdd9e6a27cce
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436154"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="79537-103">Procedimientos de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79537-103">Function procedures (Visual Basic)</span></span>

<span data-ttu-id="79537-104">Un `Function` procedimiento es una serie de instrucciones Visual Basic incluidas en las `Function` `End Function` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="79537-104">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="79537-105">El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="79537-105">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="79537-106">Cuando devuelve el control, también devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="79537-106">When it returns control, it also returns a value to the calling code.</span></span>

<span data-ttu-id="79537-107">Cada vez que se llama al procedimiento, sus instrucciones se ejecutan, empezando por la primera instrucción ejecutable después de la `Function` instrucción y terminando por la primera `End Function` `Exit Function` instrucción, o `Return` encontrada.</span><span class="sxs-lookup"><span data-stu-id="79537-107">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>

<span data-ttu-id="79537-108">Puede definir un `Function` procedimiento en un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="79537-108">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="79537-109">Es de `Public` forma predeterminada, lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, clase o estructura en la que se definió.</span><span class="sxs-lookup"><span data-stu-id="79537-109">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>

<span data-ttu-id="79537-110">Un `Function` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se le pasan por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="79537-110">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="79537-111">Sintaxis de declaración</span><span class="sxs-lookup"><span data-stu-id="79537-111">Declaration syntax</span></span>

<span data-ttu-id="79537-112">La sintaxis para declarar un `Function` procedimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="79537-112">The syntax for declaring a `Function` procedure is as follows:</span></span>

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

<span data-ttu-id="79537-113">Los *Modificadores* pueden especificar el nivel de acceso y la información relacionada con la sobrecarga, el reemplazo, el uso compartido y el sombreado.</span><span class="sxs-lookup"><span data-stu-id="79537-113">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="79537-114">Para obtener más información, vea [function (instrucción](../../../language-reference/statements/function-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="79537-114">For more information, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

<span data-ttu-id="79537-115">Los parámetros se declaran de la misma manera que para [los procedimientos sub](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="79537-115">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="79537-116">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="79537-116">Data type</span></span>

<span data-ttu-id="79537-117">Cada `Function` procedimiento tiene un tipo de datos, al igual que cada variable.</span><span class="sxs-lookup"><span data-stu-id="79537-117">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="79537-118">Este tipo de datos se especifica mediante la `As` cláusula en la `Function` instrucción y determina el tipo de datos del valor que la función devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="79537-118">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="79537-119">En las declaraciones de ejemplo siguientes se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="79537-119">The following sample declarations illustrate this.</span></span>

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

<span data-ttu-id="79537-120">Para obtener más información, vea "Parts" en la [instrucción function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="79537-120">For more information, see "Parts" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

### <a name="returning-values"></a><span data-ttu-id="79537-121">Devolver valores</span><span class="sxs-lookup"><span data-stu-id="79537-121">Returning values</span></span>

<span data-ttu-id="79537-122">El valor `Function` que un procedimiento devuelve al código de llamada se denomina su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="79537-122">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="79537-123">El procedimiento devuelve este valor de una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="79537-123">The procedure returns this value in one of two ways:</span></span>

- <span data-ttu-id="79537-124">Usa la `Return` instrucción para especificar el valor devuelto y devuelve el control inmediatamente al programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="79537-124">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="79537-125">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79537-125">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- <span data-ttu-id="79537-126">Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="79537-126">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="79537-127">El control no vuelve al programa que realiza la llamada hasta que `Exit Function` `End Function` se ejecuta una instrucción o.</span><span class="sxs-lookup"><span data-stu-id="79537-127">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="79537-128">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="79537-128">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

<span data-ttu-id="79537-129">La ventaja de asignar el valor devuelto al nombre de la función es que el control no vuelve del procedimiento hasta que encuentra una `Exit Function` `End Function` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="79537-129">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="79537-130">Esto le permite asignar un valor preliminar y ajustarlo más adelante si es necesario.</span><span class="sxs-lookup"><span data-stu-id="79537-130">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>

<span data-ttu-id="79537-131">Para obtener más información sobre cómo devolver valores, vea [function (instrucción](../../../language-reference/statements/function-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="79537-131">For more information about returning values, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="79537-132">Para obtener información sobre cómo devolver matrices, vea [matrices](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="79537-132">For information about returning arrays, see [Arrays](../arrays/index.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="79537-133">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="79537-133">Calling syntax</span></span>

<span data-ttu-id="79537-134">Para invocar un `Function` procedimiento, incluya su nombre y sus argumentos en el lado derecho de una instrucción de asignación o en una expresión.</span><span class="sxs-lookup"><span data-stu-id="79537-134">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="79537-135">Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="79537-135">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="79537-136">Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="79537-136">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="79537-137">La sintaxis de una llamada a un `Function` procedimiento es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="79537-137">The syntax for a call to a `Function` procedure is as follows.</span></span>

<span data-ttu-id="79537-138">valor *l* `=` *nombrefunción* `[(` *argumentlist*    `)]`</span><span class="sxs-lookup"><span data-stu-id="79537-138">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>

<span data-ttu-id="79537-139">`If ((`*nombrefunción* `[(` *argumentlist* `)] / 3) <=` *expresión* de  `) Then`</span><span class="sxs-lookup"><span data-stu-id="79537-139">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>

<span data-ttu-id="79537-140">Cuando se llama a un `Function` procedimiento, no es necesario usar su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="79537-140">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="79537-141">Si no es así, se realizan todas las acciones de la función, pero se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="79537-141">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="79537-142"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> a menudo se llama de esta manera.</span><span class="sxs-lookup"><span data-stu-id="79537-142"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="79537-143">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="79537-143">Illustration of declaration and call</span></span>

<span data-ttu-id="79537-144">En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="79537-144">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

<span data-ttu-id="79537-145">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="79537-145">The following example shows a typical call to `hypotenuse`.</span></span>

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a><span data-ttu-id="79537-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79537-146">See also</span></span>

- [<span data-ttu-id="79537-147">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="79537-147">Procedures</span></span>](./index.md)
- [<span data-ttu-id="79537-148">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="79537-148">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="79537-149">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="79537-149">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="79537-150">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="79537-150">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="79537-151">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="79537-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="79537-152">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="79537-152">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="79537-153">Procedimiento para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="79537-153">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="79537-154">Procedimiento para devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="79537-154">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="79537-155">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="79537-155">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
