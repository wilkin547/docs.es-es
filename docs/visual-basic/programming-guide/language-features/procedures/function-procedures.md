---
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
ms.openlocfilehash: b0ba96a875fd8785e45eee565beefe4b961ffc9d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388756"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="ab837-102">Procedimientos de función (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab837-102">Function procedures (Visual Basic)</span></span>

<span data-ttu-id="ab837-103">Un `Function` procedimiento es una serie de instrucciones Visual Basic incluidas en las `Function` `End Function` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="ab837-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="ab837-104">El `Function` procedimiento realiza una tarea y, a continuación, devuelve el control al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ab837-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="ab837-105">Cuando devuelve el control, también devuelve un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ab837-105">When it returns control, it also returns a value to the calling code.</span></span>

<span data-ttu-id="ab837-106">Cada vez que se llama al procedimiento, sus instrucciones se ejecutan, empezando por la primera instrucción ejecutable después de la `Function` instrucción y terminando por la primera `End Function` `Exit Function` instrucción, o `Return` encontrada.</span><span class="sxs-lookup"><span data-stu-id="ab837-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>

<span data-ttu-id="ab837-107">Puede definir un `Function` procedimiento en un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="ab837-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="ab837-108">Es de `Public` forma predeterminada, lo que significa que se puede llamar desde cualquier parte de la aplicación que tenga acceso al módulo, clase o estructura en la que se definió.</span><span class="sxs-lookup"><span data-stu-id="ab837-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>

<span data-ttu-id="ab837-109">Un `Function` procedimiento puede aceptar argumentos, como constantes, variables o expresiones, que se le pasan por el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ab837-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="ab837-110">Sintaxis de declaración</span><span class="sxs-lookup"><span data-stu-id="ab837-110">Declaration syntax</span></span>

<span data-ttu-id="ab837-111">La sintaxis para declarar un `Function` procedimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab837-111">The syntax for declaring a `Function` procedure is as follows:</span></span>

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

<span data-ttu-id="ab837-112">Los *Modificadores* pueden especificar el nivel de acceso y la información relacionada con la sobrecarga, el reemplazo, el uso compartido y el sombreado.</span><span class="sxs-lookup"><span data-stu-id="ab837-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="ab837-113">Para obtener más información, vea [function (instrucción](../../../language-reference/statements/function-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="ab837-113">For more information, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

<span data-ttu-id="ab837-114">Los parámetros se declaran de la misma manera que para [los procedimientos sub](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ab837-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="ab837-115">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab837-115">Data type</span></span>

<span data-ttu-id="ab837-116">Cada `Function` procedimiento tiene un tipo de datos, al igual que cada variable.</span><span class="sxs-lookup"><span data-stu-id="ab837-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="ab837-117">Este tipo de datos se especifica mediante la `As` cláusula en la `Function` instrucción y determina el tipo de datos del valor que la función devuelve al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="ab837-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="ab837-118">En las declaraciones de ejemplo siguientes se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="ab837-118">The following sample declarations illustrate this.</span></span>

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

<span data-ttu-id="ab837-119">Para obtener más información, vea "Parts" en la [instrucción function](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ab837-119">For more information, see "Parts" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

### <a name="returning-values"></a><span data-ttu-id="ab837-120">Devolver valores</span><span class="sxs-lookup"><span data-stu-id="ab837-120">Returning values</span></span>

<span data-ttu-id="ab837-121">El valor `Function` que un procedimiento devuelve al código de llamada se denomina su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ab837-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="ab837-122">El procedimiento devuelve este valor de una de estas dos maneras:</span><span class="sxs-lookup"><span data-stu-id="ab837-122">The procedure returns this value in one of two ways:</span></span>

- <span data-ttu-id="ab837-123">Usa la `Return` instrucción para especificar el valor devuelto y devuelve el control inmediatamente al programa que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="ab837-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="ab837-124">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ab837-124">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- <span data-ttu-id="ab837-125">Asigna un valor a su propio nombre de función en una o más instrucciones del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ab837-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="ab837-126">El control no vuelve al programa que realiza la llamada hasta que `Exit Function` `End Function` se ejecuta una instrucción o.</span><span class="sxs-lookup"><span data-stu-id="ab837-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="ab837-127">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ab837-127">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

<span data-ttu-id="ab837-128">La ventaja de asignar el valor devuelto al nombre de la función es que el control no vuelve del procedimiento hasta que encuentra una `Exit Function` `End Function` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="ab837-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="ab837-129">Esto le permite asignar un valor preliminar y ajustarlo más adelante si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ab837-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>

<span data-ttu-id="ab837-130">Para obtener más información sobre cómo devolver valores, vea [function (instrucción](../../../language-reference/statements/function-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="ab837-130">For more information about returning values, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="ab837-131">Para obtener información sobre cómo devolver matrices, vea [matrices](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="ab837-131">For information about returning arrays, see [Arrays](../arrays/index.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="ab837-132">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="ab837-132">Calling syntax</span></span>

<span data-ttu-id="ab837-133">Para invocar un `Function` procedimiento, incluya su nombre y sus argumentos en el lado derecho de una instrucción de asignación o en una expresión.</span><span class="sxs-lookup"><span data-stu-id="ab837-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="ab837-134">Debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="ab837-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="ab837-135">Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="ab837-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="ab837-136">La sintaxis de una llamada a un `Function` procedimiento es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab837-136">The syntax for a call to a `Function` procedure is as follows.</span></span>

<span data-ttu-id="ab837-137">valor *l* `=` *nombrefunción* `[(` *argumentlist*    `)]`</span><span class="sxs-lookup"><span data-stu-id="ab837-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>

<span data-ttu-id="ab837-138">`If ((`*nombrefunción* `[(` *argumentlist* `)] / 3) <=` *expresión* de  `) Then`</span><span class="sxs-lookup"><span data-stu-id="ab837-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>

<span data-ttu-id="ab837-139">Cuando se llama a un `Function` procedimiento, no es necesario usar su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ab837-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="ab837-140">Si no es así, se realizan todas las acciones de la función, pero se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ab837-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="ab837-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>a menudo se llama de esta manera.</span><span class="sxs-lookup"><span data-stu-id="ab837-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="ab837-142">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="ab837-142">Illustration of declaration and call</span></span>

<span data-ttu-id="ab837-143">En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.</span><span class="sxs-lookup"><span data-stu-id="ab837-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

<span data-ttu-id="ab837-144">En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="ab837-144">The following example shows a typical call to `hypotenuse`.</span></span>

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a><span data-ttu-id="ab837-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab837-145">See also</span></span>

- [<span data-ttu-id="ab837-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="ab837-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="ab837-147">Procedimientos Sub</span><span class="sxs-lookup"><span data-stu-id="ab837-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="ab837-148">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="ab837-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="ab837-149">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="ab837-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="ab837-150">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="ab837-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="ab837-151">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="ab837-151">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="ab837-152">Procedimiento para crear un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="ab837-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="ab837-153">Procedimiento para devolver un valor de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="ab837-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="ab837-154">Procedimiento para llamar a un procedimiento que devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="ab837-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
