---
description: 'Más información sobre: function (instrucción) (Visual Basic)'
title: Instrucción Function
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: e8a05b02c3a214f0572e85c1fc973cb9f03118ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769070"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="547b1-103">Function (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="547b1-103">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="547b1-104">Declara el nombre, los parámetros y el código que definen un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-104">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="547b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="547b1-105">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="547b1-106">Partes</span><span class="sxs-lookup"><span data-stu-id="547b1-106">Parts</span></span>

- `attributelist`

  <span data-ttu-id="547b1-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-107">Optional.</span></span> <span data-ttu-id="547b1-108">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-108">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="547b1-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-109">Optional.</span></span> <span data-ttu-id="547b1-110">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="547b1-110">Can be one of the following:</span></span>

  - [<span data-ttu-id="547b1-111">Público</span><span class="sxs-lookup"><span data-stu-id="547b1-111">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="547b1-112">Protegido</span><span class="sxs-lookup"><span data-stu-id="547b1-112">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="547b1-113">Friend</span><span class="sxs-lookup"><span data-stu-id="547b1-113">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="547b1-114">Privado</span><span class="sxs-lookup"><span data-stu-id="547b1-114">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="547b1-115">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="547b1-115">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="547b1-116">Private Protected</span><span class="sxs-lookup"><span data-stu-id="547b1-116">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="547b1-117">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-117">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="547b1-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-118">Optional.</span></span> <span data-ttu-id="547b1-119">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="547b1-119">Can be one of the following:</span></span>

  - [<span data-ttu-id="547b1-120">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="547b1-120">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="547b1-121">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="547b1-121">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="547b1-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="547b1-122">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="547b1-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="547b1-123">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="547b1-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="547b1-124">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="547b1-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-125">Optional.</span></span> <span data-ttu-id="547b1-126">Vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-126">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="547b1-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-127">Optional.</span></span> <span data-ttu-id="547b1-128">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-128">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="547b1-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-129">Optional.</span></span> <span data-ttu-id="547b1-130">Vea [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-130">See [Async](../modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="547b1-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-131">Optional.</span></span> <span data-ttu-id="547b1-132">Vea [iterator](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-132">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="547b1-133">Necesario.</span><span class="sxs-lookup"><span data-stu-id="547b1-133">Required.</span></span> <span data-ttu-id="547b1-134">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-134">Name of the procedure.</span></span> <span data-ttu-id="547b1-135">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-135">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="547b1-136">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-136">Optional.</span></span> <span data-ttu-id="547b1-137">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="547b1-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="547b1-138">Consulte [lista de tipos](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-138">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="547b1-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-139">Optional.</span></span> <span data-ttu-id="547b1-140">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="547b1-141">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-141">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="547b1-142">Obligatorio si `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="547b1-142">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="547b1-143">Tipo de datos del valor devuelto por este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-143">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="547b1-144">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-144">Optional.</span></span> <span data-ttu-id="547b1-145">Indica que este procedimiento implementa uno o más `Function` procedimientos, cada uno de ellos definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-145">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="547b1-146">Vea [Implements (instrucción](implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="547b1-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="547b1-147">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="547b1-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="547b1-148">Lista de procedimientos `Function` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="547b1-148">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="547b1-149">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="547b1-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="547b1-150">Parte</span><span class="sxs-lookup"><span data-stu-id="547b1-150">Part</span></span>|<span data-ttu-id="547b1-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="547b1-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="547b1-152">Necesario.</span><span class="sxs-lookup"><span data-stu-id="547b1-152">Required.</span></span> <span data-ttu-id="547b1-153">Nombre de una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="547b1-154">Necesario.</span><span class="sxs-lookup"><span data-stu-id="547b1-154">Required.</span></span> <span data-ttu-id="547b1-155">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="547b1-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="547b1-156">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-156">Optional.</span></span> <span data-ttu-id="547b1-157">Indica que este procedimiento puede controlar uno o más eventos concretos.</span><span class="sxs-lookup"><span data-stu-id="547b1-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="547b1-158">Vea [identificadores](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="547b1-159">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="547b1-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="547b1-160">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="547b1-161">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="547b1-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="547b1-162">Parte</span><span class="sxs-lookup"><span data-stu-id="547b1-162">Part</span></span>|<span data-ttu-id="547b1-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="547b1-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="547b1-164">Necesario.</span><span class="sxs-lookup"><span data-stu-id="547b1-164">Required.</span></span> <span data-ttu-id="547b1-165">Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="547b1-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="547b1-166">Necesario.</span><span class="sxs-lookup"><span data-stu-id="547b1-166">Required.</span></span> <span data-ttu-id="547b1-167">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="547b1-168">Opcional.</span><span class="sxs-lookup"><span data-stu-id="547b1-168">Optional.</span></span> <span data-ttu-id="547b1-169">Bloque de instrucciones que se ejecutarán en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-169">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="547b1-170">Finaliza la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="547b1-171">Observaciones</span><span class="sxs-lookup"><span data-stu-id="547b1-171">Remarks</span></span>

<span data-ttu-id="547b1-172">Todo el código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="547b1-173">Cada procedimiento, a su vez, se declara dentro de una clase, una estructura o un módulo al que se hace referencia como la clase, estructura o módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="547b1-173">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="547b1-174">Para devolver un valor al código de llamada, use un `Function` procedimiento; de lo contrario, use un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-174">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="547b1-175">Definir una función</span><span class="sxs-lookup"><span data-stu-id="547b1-175">Defining a Function</span></span>

<span data-ttu-id="547b1-176">Solo puede definir un `Function` procedimiento en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="547b1-176">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="547b1-177">Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="547b1-177">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="547b1-178">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="547b1-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="547b1-179">`Function` los procedimientos tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="547b1-179">`Function` procedures default to public access.</span></span> <span data-ttu-id="547b1-180">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="547b1-180">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="547b1-181">Un `Function` procedimiento puede declarar el tipo de datos del valor que devuelve el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-181">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="547b1-182">Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="547b1-182">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="547b1-183">Si no especifica el `returntype` parámetro, el procedimiento devuelve `Object` .</span><span class="sxs-lookup"><span data-stu-id="547b1-183">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="547b1-184">Si este procedimiento usa la `Implements` palabra clave, la clase o estructura contenedora también debe tener una `Implements` instrucción que siga inmediatamente a su `Class` `Structure` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="547b1-184">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="547b1-185">La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="547b1-185">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="547b1-186">Sin embargo, el nombre por el que una interfaz define `Function` (en `definedname` ) no tiene que coincidir con el nombre de este procedimiento (en `name` ).</span><span class="sxs-lookup"><span data-stu-id="547b1-186">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="547b1-187">Puede usar expresiones lambda para definir expresiones de función alineadas.</span><span class="sxs-lookup"><span data-stu-id="547b1-187">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="547b1-188">Para obtener más información, vea [expresión de función](../operators/function-expression.md) y [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-188">For more information, see [Function Expression](../operators/function-expression.md) and [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="547b1-189">Devolver desde una función</span><span class="sxs-lookup"><span data-stu-id="547b1-189">Returning from a Function</span></span>

<span data-ttu-id="547b1-190">Cuando el `Function` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-190">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="547b1-191">Para devolver un valor de una función, puede asignar el valor al nombre de la función o incluirlo en una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="547b1-191">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="547b1-192">La `Return` instrucción asigna simultáneamente el valor devuelto y sale de la función, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="547b1-192">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="547b1-193">En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, se usa la `Exit Function` instrucción para devolver.</span><span class="sxs-lookup"><span data-stu-id="547b1-193">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="547b1-194">Las `Exit Function` `Return` instrucciones y producen una salida inmediata de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-194">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="547b1-195">Cualquier número de `Exit Function` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Function` e `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="547b1-195">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="547b1-196">Si utiliza `Exit Function` sin asignar un valor a `name` , el procedimiento devuelve el valor predeterminado para el tipo de datos especificado en `returntype` .</span><span class="sxs-lookup"><span data-stu-id="547b1-196">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="547b1-197">Si `returntype` no se especifica, el procedimiento devuelve `Nothing` , que es el valor predeterminado de `Object` .</span><span class="sxs-lookup"><span data-stu-id="547b1-197">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="547b1-198">Llamar a una función</span><span class="sxs-lookup"><span data-stu-id="547b1-198">Calling a Function</span></span>

<span data-ttu-id="547b1-199">Se llama a un `Function` procedimiento mediante el nombre del procedimiento, seguido de la lista de argumentos entre paréntesis, en una expresión.</span><span class="sxs-lookup"><span data-stu-id="547b1-199">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="547b1-200">Solo se pueden omitir los paréntesis si no se proporcionan argumentos.</span><span class="sxs-lookup"><span data-stu-id="547b1-200">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="547b1-201">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="547b1-201">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="547b1-202">Puede llamar a un `Function` procedimiento de la misma manera que llama a cualquier función de biblioteca como `Sqrt` , `Cos` o `ChrW` .</span><span class="sxs-lookup"><span data-stu-id="547b1-202">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="547b1-203">También puede llamar a una función mediante la `Call` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="547b1-203">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="547b1-204">En ese caso, se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="547b1-204">In that case, the return value is ignored.</span></span> <span data-ttu-id="547b1-205">No se recomienda el uso de la `Call` palabra clave en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="547b1-205">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="547b1-206">Para obtener más información, consulte [instrucción call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-206">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="547b1-207">A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="547b1-207">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="547b1-208">Por ese motivo, no debe utilizar un `Function` procedimiento en una expresión aritmética cuando la función cambia el valor de las variables en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="547b1-208">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="547b1-209">Funciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="547b1-209">Async Functions</span></span>

<span data-ttu-id="547b1-210">La característica *Async* le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="547b1-210">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="547b1-211">Si marca una función con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en la función.</span><span class="sxs-lookup"><span data-stu-id="547b1-211">If you mark a function with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="547b1-212">Cuando el control alcanza una `Await` expresión de la `Async` función, el control vuelve al autor de la llamada y el progreso de la función se suspende hasta que se completa la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="547b1-212">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="547b1-213">Una vez completada la tarea, la ejecución puede reanudarse en la función.</span><span class="sxs-lookup"><span data-stu-id="547b1-213">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="547b1-214">Un `Async` procedimiento vuelve al autor de la llamada cuando encuentra el primer objeto esperado que aún no se ha completado o se llega al final del `Async` procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="547b1-214">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="547b1-215">Una `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="547b1-215">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="547b1-216">A continuación se proporciona un ejemplo de una `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="547b1-216">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="547b1-217">Una `Async` función no puede declarar ningún parámetro [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="547b1-217">An `Async` function cannot declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="547b1-218">Una [instrucción Sub](sub-statement.md) también se puede marcar con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="547b1-218">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="547b1-219">Se utiliza principalmente para los controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="547b1-219">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="547b1-220">`Async` `Sub` No se puede esperar un procedimiento y el autor de la llamada de un `Async` `Sub` procedimiento no puede detectar las excepciones producidas por el `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-220">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="547b1-221">Para obtener más información sobre `Async` las funciones, vea [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-221">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="547b1-222">Funciones de iterador</span><span class="sxs-lookup"><span data-stu-id="547b1-222">Iterator Functions</span></span>

<span data-ttu-id="547b1-223">Una función de *iterador* realiza una iteración personalizada en una colección, como una lista o una matriz.</span><span class="sxs-lookup"><span data-stu-id="547b1-223">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="547b1-224">Una función de iterador utiliza la instrucción [yield](yield-statement.md) para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="547b1-224">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="547b1-225">Cuando se alcanza una instrucción [yield](yield-statement.md) , se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="547b1-225">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="547b1-226">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="547b1-226">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="547b1-227">Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](for-each-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="547b1-227">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="547b1-228">El tipo de valor devuelto de una función de iterador puede ser <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="547b1-228">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="547b1-229">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="547b1-229">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="547b1-230">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="547b1-230">Example</span></span>

<span data-ttu-id="547b1-231">En el ejemplo siguiente se usa la `Function` instrucción para declarar el nombre, los parámetros y el código que forman el cuerpo de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-231">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="547b1-232">El `ParamArray` modificador permite que la función acepte un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="547b1-232">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="547b1-233">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="547b1-233">Example</span></span>

<span data-ttu-id="547b1-234">En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="547b1-234">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="547b1-235">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="547b1-235">Example</span></span>

<span data-ttu-id="547b1-236">En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="547b1-236">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="547b1-237">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="547b1-237">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="547b1-238">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="547b1-238">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="547b1-239">Dado que el tipo de valor devuelto es `Task(Of Integer)` , la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero.</span><span class="sxs-lookup"><span data-stu-id="547b1-239">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="547b1-240">Esto se muestra en esta declaración: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="547b1-240">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="547b1-241">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="547b1-241">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="547b1-242">Dado `DoSomethingAsync` que es una `Async` función, se debe esperar a la tarea de la llamada a `DoSomethingAsync` , como se muestra en la siguiente instrucción: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="547b1-242">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="547b1-243">El `startButton_Click` `Sub` procedimiento debe definirse con el `Async` modificador porque tiene una `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="547b1-243">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="547b1-244">Vea también</span><span class="sxs-lookup"><span data-stu-id="547b1-244">See also</span></span>

- [<span data-ttu-id="547b1-245">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="547b1-245">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="547b1-246">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="547b1-246">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="547b1-247">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="547b1-247">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="547b1-248">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="547b1-248">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="547b1-249">Instrucción Call</span><span class="sxs-lookup"><span data-stu-id="547b1-249">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="547b1-250">De</span><span class="sxs-lookup"><span data-stu-id="547b1-250">Of</span></span>](of-clause.md)
- [<span data-ttu-id="547b1-251">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="547b1-251">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="547b1-252">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="547b1-252">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="547b1-253">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="547b1-253">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="547b1-254">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="547b1-254">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="547b1-255">Expresión Function</span><span class="sxs-lookup"><span data-stu-id="547b1-255">Function Expression</span></span>](../operators/function-expression.md)
