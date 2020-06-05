---
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
ms.openlocfilehash: 49cf4fead2c5594b7ac6815f82fea0dc995ea436
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404633"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="c5b71-102">Function (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5b71-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="c5b71-103">Declara el nombre, los parámetros y el código que definen un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5b71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5b71-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="c5b71-105">Partes</span><span class="sxs-lookup"><span data-stu-id="c5b71-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="c5b71-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-106">Optional.</span></span> <span data-ttu-id="c5b71-107">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="c5b71-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-108">Optional.</span></span> <span data-ttu-id="c5b71-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5b71-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="c5b71-110">Público</span><span class="sxs-lookup"><span data-stu-id="c5b71-110">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="c5b71-111">Contra</span><span class="sxs-lookup"><span data-stu-id="c5b71-111">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="c5b71-112">Respecto</span><span class="sxs-lookup"><span data-stu-id="c5b71-112">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="c5b71-113">Privado</span><span class="sxs-lookup"><span data-stu-id="c5b71-113">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="c5b71-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="c5b71-114">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="c5b71-115">Privado protegido</span><span class="sxs-lookup"><span data-stu-id="c5b71-115">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="c5b71-116">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="c5b71-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-117">Optional.</span></span> <span data-ttu-id="c5b71-118">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5b71-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="c5b71-119">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="c5b71-119">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="c5b71-120">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="c5b71-120">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="c5b71-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="c5b71-121">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="c5b71-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="c5b71-122">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="c5b71-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="c5b71-123">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="c5b71-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-124">Optional.</span></span> <span data-ttu-id="c5b71-125">Vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-125">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="c5b71-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-126">Optional.</span></span> <span data-ttu-id="c5b71-127">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-127">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="c5b71-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-128">Optional.</span></span> <span data-ttu-id="c5b71-129">Vea [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-129">See [Async](../modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="c5b71-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-130">Optional.</span></span> <span data-ttu-id="c5b71-131">Vea [iterator](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-131">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="c5b71-132">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c5b71-132">Required.</span></span> <span data-ttu-id="c5b71-133">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-133">Name of the procedure.</span></span> <span data-ttu-id="c5b71-134">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-134">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="c5b71-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-135">Optional.</span></span> <span data-ttu-id="c5b71-136">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="c5b71-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="c5b71-137">Consulte [lista de tipos](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="c5b71-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-138">Optional.</span></span> <span data-ttu-id="c5b71-139">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="c5b71-140">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="c5b71-141">Obligatorio si `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="c5b71-142">Tipo de datos del valor devuelto por este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="c5b71-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-143">Optional.</span></span> <span data-ttu-id="c5b71-144">Indica que este procedimiento implementa uno o más `Function` procedimientos, cada uno de ellos definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="c5b71-145">Vea [Implements (instrucción](implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="c5b71-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="c5b71-146">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="c5b71-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="c5b71-147">Lista de procedimientos `Function` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="c5b71-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="c5b71-148">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5b71-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="c5b71-149">Parte</span><span class="sxs-lookup"><span data-stu-id="c5b71-149">Part</span></span>|<span data-ttu-id="c5b71-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5b71-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="c5b71-151">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c5b71-151">Required.</span></span> <span data-ttu-id="c5b71-152">Nombre de una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="c5b71-153">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c5b71-153">Required.</span></span> <span data-ttu-id="c5b71-154">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="c5b71-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="c5b71-155">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-155">Optional.</span></span> <span data-ttu-id="c5b71-156">Indica que este procedimiento puede controlar uno o más eventos concretos.</span><span class="sxs-lookup"><span data-stu-id="c5b71-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="c5b71-157">Vea [identificadores](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="c5b71-158">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="c5b71-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="c5b71-159">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="c5b71-160">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5b71-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="c5b71-161">Parte</span><span class="sxs-lookup"><span data-stu-id="c5b71-161">Part</span></span>|<span data-ttu-id="c5b71-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5b71-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="c5b71-163">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c5b71-163">Required.</span></span> <span data-ttu-id="c5b71-164">Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="c5b71-165">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c5b71-165">Required.</span></span> <span data-ttu-id="c5b71-166">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="c5b71-167">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c5b71-167">Optional.</span></span> <span data-ttu-id="c5b71-168">Bloque de instrucciones que se ejecutarán en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="c5b71-169">Finaliza la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5b71-170">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5b71-170">Remarks</span></span>

<span data-ttu-id="c5b71-171">Todo el código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="c5b71-172">Cada procedimiento, a su vez, se declara dentro de una clase, una estructura o un módulo al que se hace referencia como la clase, estructura o módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="c5b71-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="c5b71-173">Para devolver un valor al código de llamada, use un `Function` procedimiento; de lo contrario, use un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="c5b71-174">Definir una función</span><span class="sxs-lookup"><span data-stu-id="c5b71-174">Defining a Function</span></span>

<span data-ttu-id="c5b71-175">Solo puede definir un `Function` procedimiento en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="c5b71-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="c5b71-176">Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="c5b71-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="c5b71-177">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="c5b71-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="c5b71-178">`Function`los procedimientos tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="c5b71-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="c5b71-179">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="c5b71-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="c5b71-180">Un `Function` procedimiento puede declarar el tipo de datos del valor que devuelve el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="c5b71-181">Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c5b71-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="c5b71-182">Si no especifica el `returntype` parámetro, el procedimiento devuelve `Object` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="c5b71-183">Si este procedimiento usa la `Implements` palabra clave, la clase o estructura contenedora también debe tener una `Implements` instrucción que siga inmediatamente a su `Class` `Structure` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="c5b71-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="c5b71-184">La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="c5b71-185">Sin embargo, el nombre por el que una interfaz define `Function` (en `definedname` ) no tiene que coincidir con el nombre de este procedimiento (en `name` ).</span><span class="sxs-lookup"><span data-stu-id="c5b71-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="c5b71-186">Puede usar expresiones lambda para definir expresiones de función alineadas.</span><span class="sxs-lookup"><span data-stu-id="c5b71-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="c5b71-187">Para obtener más información, vea [expresión de función](../operators/function-expression.md) y [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-187">For more information, see [Function Expression](../operators/function-expression.md) and [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="c5b71-188">Devolver desde una función</span><span class="sxs-lookup"><span data-stu-id="c5b71-188">Returning from a Function</span></span>

<span data-ttu-id="c5b71-189">Cuando el `Function` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="c5b71-190">Para devolver un valor de una función, puede asignar el valor al nombre de la función o incluirlo en una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c5b71-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="c5b71-191">La `Return` instrucción asigna simultáneamente el valor devuelto y sale de la función, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c5b71-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="c5b71-192">En el ejemplo siguiente se asigna el valor devuelto al nombre de la función `myFunction` y, a continuación, se usa la `Exit Function` instrucción para devolver.</span><span class="sxs-lookup"><span data-stu-id="c5b71-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="c5b71-193">Las `Exit Function` `Return` instrucciones y producen una salida inmediata de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="c5b71-194">Cualquier número de `Exit Function` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Function` e `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c5b71-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="c5b71-195">Si utiliza `Exit Function` sin asignar un valor a `name` , el procedimiento devuelve el valor predeterminado para el tipo de datos especificado en `returntype` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="c5b71-196">Si `returntype` no se especifica, el procedimiento devuelve `Nothing` , que es el valor predeterminado de `Object` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="c5b71-197">Llamar a una función</span><span class="sxs-lookup"><span data-stu-id="c5b71-197">Calling a Function</span></span>

<span data-ttu-id="c5b71-198">Se llama a un `Function` procedimiento mediante el nombre del procedimiento, seguido de la lista de argumentos entre paréntesis, en una expresión.</span><span class="sxs-lookup"><span data-stu-id="c5b71-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="c5b71-199">Solo se pueden omitir los paréntesis si no se proporcionan argumentos.</span><span class="sxs-lookup"><span data-stu-id="c5b71-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="c5b71-200">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="c5b71-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="c5b71-201">Puede llamar a un `Function` procedimiento de la misma manera que llama a cualquier función de biblioteca como `Sqrt` , `Cos` o `ChrW` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="c5b71-202">También puede llamar a una función mediante la `Call` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="c5b71-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="c5b71-203">En ese caso, se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c5b71-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="c5b71-204">No se recomienda el uso de la `Call` palabra clave en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="c5b71-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="c5b71-205">Para obtener más información, consulte [instrucción call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="c5b71-206">A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="c5b71-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="c5b71-207">Por ese motivo, no debe utilizar un `Function` procedimiento en una expresión aritmética cuando la función cambia el valor de las variables en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="c5b71-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="c5b71-208">Funciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="c5b71-208">Async Functions</span></span>

<span data-ttu-id="c5b71-209">La característica *Async* le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="c5b71-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="c5b71-210">Si marca una función con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en la función.</span><span class="sxs-lookup"><span data-stu-id="c5b71-210">If you mark a function with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="c5b71-211">Cuando el control alcanza una `Await` expresión de la `Async` función, el control vuelve al autor de la llamada y el progreso de la función se suspende hasta que se completa la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="c5b71-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="c5b71-212">Una vez completada la tarea, la ejecución puede reanudarse en la función.</span><span class="sxs-lookup"><span data-stu-id="c5b71-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="c5b71-213">Un `Async` procedimiento vuelve al autor de la llamada cuando encuentra el primer objeto esperado que aún no se ha completado o se llega al final del `Async` procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="c5b71-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="c5b71-214">Una `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="c5b71-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="c5b71-215">A continuación se proporciona un ejemplo de una `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="c5b71-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="c5b71-216">Una `Async` función no puede declarar ningún parámetro [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="c5b71-216">An `Async` function cannot declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="c5b71-217">Una [instrucción Sub](sub-statement.md) también se puede marcar con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="c5b71-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="c5b71-218">Se utiliza principalmente para los controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="c5b71-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="c5b71-219">`Async` `Sub` No se puede esperar un procedimiento y el autor de la llamada de un `Async` `Sub` procedimiento no puede detectar las excepciones producidas por el `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="c5b71-220">Para obtener más información sobre `Async` las funciones, vea [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="c5b71-221">Funciones de iterador</span><span class="sxs-lookup"><span data-stu-id="c5b71-221">Iterator Functions</span></span>

<span data-ttu-id="c5b71-222">Una función de *iterador* realiza una iteración personalizada en una colección, como una lista o una matriz.</span><span class="sxs-lookup"><span data-stu-id="c5b71-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="c5b71-223">Una función de iterador utiliza la instrucción [yield](yield-statement.md) para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="c5b71-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="c5b71-224">Cuando se alcanza una instrucción [yield](yield-statement.md) , se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="c5b71-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="c5b71-225">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="c5b71-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="c5b71-226">Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](for-each-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="c5b71-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="c5b71-227">El tipo de valor devuelto de una función de iterador puede ser <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> .</span><span class="sxs-lookup"><span data-stu-id="c5b71-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="c5b71-228">Para obtener más información, vea [iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="c5b71-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="c5b71-229">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5b71-229">Example</span></span>

<span data-ttu-id="c5b71-230">En el ejemplo siguiente se usa la `Function` instrucción para declarar el nombre, los parámetros y el código que forman el cuerpo de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="c5b71-231">El `ParamArray` modificador permite que la función acepte un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="c5b71-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="c5b71-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5b71-232">Example</span></span>

<span data-ttu-id="c5b71-233">En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c5b71-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="c5b71-234">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5b71-234">Example</span></span>

<span data-ttu-id="c5b71-235">En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="c5b71-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="c5b71-236">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="c5b71-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="c5b71-237">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="c5b71-238">Dado que el tipo de valor devuelto es `Task(Of Integer)` , la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero.</span><span class="sxs-lookup"><span data-stu-id="c5b71-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="c5b71-239">Esto se muestra en esta declaración: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="c5b71-240">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c5b71-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="c5b71-241">Dado `DoSomethingAsync` que es una `Async` función, se debe esperar a la tarea de la llamada a `DoSomethingAsync` , como se muestra en la siguiente instrucción: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="c5b71-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="c5b71-242">El `startButton_Click` `Sub` procedimiento debe definirse con el `Async` modificador porque tiene una `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="c5b71-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="c5b71-243">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5b71-243">See also</span></span>

- [<span data-ttu-id="c5b71-244">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="c5b71-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="c5b71-245">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="c5b71-245">Function Procedures</span></span>](../../programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="c5b71-246">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="c5b71-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="c5b71-247">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="c5b71-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="c5b71-248">Instrucción Call</span><span class="sxs-lookup"><span data-stu-id="c5b71-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="c5b71-249">De</span><span class="sxs-lookup"><span data-stu-id="c5b71-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="c5b71-250">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="c5b71-250">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="c5b71-251">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="c5b71-251">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="c5b71-252">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="c5b71-252">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="c5b71-253">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="c5b71-253">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="c5b71-254">Expresión de función</span><span class="sxs-lookup"><span data-stu-id="c5b71-254">Function Expression</span></span>](../operators/function-expression.md)
