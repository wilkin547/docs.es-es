---
title: Function (Instrucción)
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
ms.openlocfilehash: 8140c7e6267e66c69c20d413a11d04372400c581
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345917"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="e0e6e-102">Function (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0e6e-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="e0e6e-103">Declara el nombre, los parámetros y el código que definen un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0e6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0e6e-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="e0e6e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="e0e6e-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="e0e6e-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-106">Optional.</span></span> <span data-ttu-id="e0e6e-107">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="e0e6e-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-108">Optional.</span></span> <span data-ttu-id="e0e6e-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0e6e-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="e0e6e-110">Public</span><span class="sxs-lookup"><span data-stu-id="e0e6e-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="e0e6e-111">Protected</span><span class="sxs-lookup"><span data-stu-id="e0e6e-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="e0e6e-112">Friend</span><span class="sxs-lookup"><span data-stu-id="e0e6e-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="e0e6e-113">Private</span><span class="sxs-lookup"><span data-stu-id="e0e6e-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="e0e6e-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="e0e6e-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="e0e6e-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="e0e6e-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="e0e6e-116">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="e0e6e-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-117">Optional.</span></span> <span data-ttu-id="e0e6e-118">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0e6e-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="e0e6e-119">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="e0e6e-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="e0e6e-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="e0e6e-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="e0e6e-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="e0e6e-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="e0e6e-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e0e6e-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="e0e6e-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e0e6e-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="e0e6e-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-124">Optional.</span></span> <span data-ttu-id="e0e6e-125">Vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="e0e6e-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-126">Optional.</span></span> <span data-ttu-id="e0e6e-127">Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="e0e6e-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-128">Optional.</span></span> <span data-ttu-id="e0e6e-129">Vea [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="e0e6e-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-130">Optional.</span></span> <span data-ttu-id="e0e6e-131">Vea [iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="e0e6e-132">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-132">Required.</span></span> <span data-ttu-id="e0e6e-133">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-133">Name of the procedure.</span></span> <span data-ttu-id="e0e6e-134">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="e0e6e-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-135">Optional.</span></span> <span data-ttu-id="e0e6e-136">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="e0e6e-137">Consulte [lista de tipos](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="e0e6e-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-138">Optional.</span></span> <span data-ttu-id="e0e6e-139">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="e0e6e-140">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="e0e6e-141">Es obligatorio si se `On``Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="e0e6e-142">Tipo de datos del valor devuelto por este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="e0e6e-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-143">Optional.</span></span> <span data-ttu-id="e0e6e-144">Indica que este procedimiento implementa uno o varios procedimientos de `Function`, cada uno de los cuales se define en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="e0e6e-145">Vea [Implements (instrucción](implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="e0e6e-146">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="e0e6e-147">Lista de procedimientos `Function` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="e0e6e-148">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0e6e-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="e0e6e-149">Parte</span><span class="sxs-lookup"><span data-stu-id="e0e6e-149">Part</span></span>|<span data-ttu-id="e0e6e-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0e6e-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="e0e6e-151">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-151">Required.</span></span> <span data-ttu-id="e0e6e-152">Nombre de una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="e0e6e-153">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-153">Required.</span></span> <span data-ttu-id="e0e6e-154">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="e0e6e-155">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-155">Optional.</span></span> <span data-ttu-id="e0e6e-156">Indica que este procedimiento puede controlar uno o más eventos concretos.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="e0e6e-157">Vea [identificadores](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="e0e6e-158">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="e0e6e-159">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="e0e6e-160">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0e6e-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="e0e6e-161">Parte</span><span class="sxs-lookup"><span data-stu-id="e0e6e-161">Part</span></span>|<span data-ttu-id="e0e6e-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0e6e-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="e0e6e-163">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-163">Required.</span></span> <span data-ttu-id="e0e6e-164">Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="e0e6e-165">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-165">Required.</span></span> <span data-ttu-id="e0e6e-166">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="e0e6e-167">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-167">Optional.</span></span> <span data-ttu-id="e0e6e-168">Bloque de instrucciones que se ejecutarán en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="e0e6e-169">Finaliza la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0e6e-170">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0e6e-170">Remarks</span></span>

<span data-ttu-id="e0e6e-171">Todo el código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="e0e6e-172">Cada procedimiento, a su vez, se declara dentro de una clase, una estructura o un módulo al que se hace referencia como la clase, estructura o módulo contenedor.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="e0e6e-173">Para devolver un valor al código de llamada, use un procedimiento `Function`; de lo contrario, use un procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="e0e6e-174">Definir una función</span><span class="sxs-lookup"><span data-stu-id="e0e6e-174">Defining a Function</span></span>

<span data-ttu-id="e0e6e-175">Solo puede definir un procedimiento `Function` en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="e0e6e-176">Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="e0e6e-177">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="e0e6e-178">`Function` procedimientos tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="e0e6e-179">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="e0e6e-180">Un procedimiento `Function` puede declarar el tipo de datos del valor que devuelve el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="e0e6e-181">Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="e0e6e-182">Si no especifica el parámetro `returntype`, el procedimiento devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="e0e6e-183">Si este procedimiento usa la palabra clave `Implements`, la clase o estructura contenedora también debe tener una instrucción `Implements` que siga inmediatamente a su instrucción `Class` o `Structure`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="e0e6e-184">La instrucción `Implements` debe incluir cada interfaz que se especifica en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="e0e6e-185">Sin embargo, el nombre por el que una interfaz define el `Function` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="e0e6e-186">Puede usar expresiones lambda para definir expresiones de función alineadas.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="e0e6e-187">Para obtener más información, vea [expresión de función](../../../visual-basic/language-reference/operators/function-expression.md) y [expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="e0e6e-188">Devolver desde una función</span><span class="sxs-lookup"><span data-stu-id="e0e6e-188">Returning from a Function</span></span>

<span data-ttu-id="e0e6e-189">Cuando el procedimiento `Function` devuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="e0e6e-190">Para devolver un valor de una función, puede asignar el valor al nombre de la función o incluirlo en una instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="e0e6e-191">La instrucción `Return` asigna simultáneamente el valor devuelto y sale de la función, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="e0e6e-192">En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction` y, a continuación, se usa la instrucción `Exit Function` para devolver.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="e0e6e-193">Las instrucciones `Exit Function` y `Return` producen una salida inmediata de un procedimiento de `Function`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="e0e6e-194">Cualquier número de instrucciones `Exit Function` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Function` y `Return`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="e0e6e-195">Si usa `Exit Function` sin asignar un valor a `name`, el procedimiento devuelve el valor predeterminado para el tipo de datos especificado en `returntype`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="e0e6e-196">Si no se especifica `returntype`, el procedimiento devuelve `Nothing`, que es el valor predeterminado para `Object`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="e0e6e-197">Llamar a una función</span><span class="sxs-lookup"><span data-stu-id="e0e6e-197">Calling a Function</span></span>

<span data-ttu-id="e0e6e-198">Se llama a un procedimiento de `Function` mediante el nombre del procedimiento, seguido de la lista de argumentos entre paréntesis, en una expresión.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="e0e6e-199">Solo se pueden omitir los paréntesis si no se proporcionan argumentos.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="e0e6e-200">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="e0e6e-201">Se llama a un procedimiento `Function` del mismo modo que se llama a cualquier función de biblioteca como `Sqrt`, `Cos`o `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="e0e6e-202">También puede llamar a una función mediante la palabra clave `Call`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="e0e6e-203">En ese caso, se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="e0e6e-204">No se recomienda el uso de la palabra clave `Call` en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="e0e6e-205">Para obtener más información, consulte [instrucción call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="e0e6e-206">A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="e0e6e-207">Por ese motivo, no debe utilizar un procedimiento `Function` en una expresión aritmética cuando la función cambia el valor de las variables en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="e0e6e-208">Funciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="e0e6e-208">Async Functions</span></span>

<span data-ttu-id="e0e6e-209">La característica *Async* le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="e0e6e-210">Si marca una función con el modificador [Async](../../../visual-basic/language-reference/modifiers/async.md) , puede usar el operador [Await](../../../visual-basic/language-reference/operators/await-operator.md) en la función.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="e0e6e-211">Cuando el control alcanza una expresión `Await` en la función `Async`, el control vuelve al llamador y el progreso de la función se suspende hasta que se completa la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="e0e6e-212">Una vez completada la tarea, la ejecución puede reanudarse en la función.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="e0e6e-213">Un procedimiento `Async` devuelve al autor de la llamada cuando encuentra el primer objeto esperado que aún no se ha completado o hasta el final de la `Async` procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="e0e6e-214">Una función `Async` puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="e0e6e-215">A continuación se proporciona un ejemplo de una función de `Async` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="e0e6e-216">Una función `Async` no puede declarar ningún parámetro [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="e0e6e-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="e0e6e-217">Una [instrucción Sub](sub-statement.md) también se puede marcar con el modificador `Async`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="e0e6e-218">Se utiliza principalmente para los controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="e0e6e-219">No se puede esperar a un procedimiento de `Sub` de `Async`, y el llamador de un procedimiento de `Sub` de `Async` no puede detectar las excepciones producidas por el procedimiento `Sub`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="e0e6e-220">Para obtener más información sobre las funciones de `Async`, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="e0e6e-221">Funciones de iterador</span><span class="sxs-lookup"><span data-stu-id="e0e6e-221">Iterator Functions</span></span>

<span data-ttu-id="e0e6e-222">Una función de *iterador* realiza una iteración personalizada en una colección, como una lista o una matriz.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="e0e6e-223">Una función de iterador utiliza la instrucción [yield](yield-statement.md) para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="e0e6e-224">Cuando se alcanza una instrucción [yield](yield-statement.md) , se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="e0e6e-225">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="e0e6e-226">Se llama a un iterador desde el código de cliente mediante un método [for each... Instrucción siguiente](for-each-next-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="e0e6e-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="e0e6e-227">El tipo de valor devuelto de una función de iterador puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="e0e6e-228">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="e0e6e-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="e0e6e-229">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0e6e-229">Example</span></span>

<span data-ttu-id="e0e6e-230">En el ejemplo siguiente se usa la instrucción `Function` para declarar el nombre, los parámetros y el código que forman el cuerpo de un procedimiento `Function`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="e0e6e-231">El modificador `ParamArray` permite que la función acepte un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="e0e6e-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0e6e-232">Example</span></span>

<span data-ttu-id="e0e6e-233">En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="e0e6e-234">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0e6e-234">Example</span></span>

<span data-ttu-id="e0e6e-235">En el ejemplo siguiente, `DelayAsync` es un `Function` de `Async` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="e0e6e-236">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="e0e6e-237">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="e0e6e-238">Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la expresión de `Await` en `DoSomethingAsync` produce un entero.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="e0e6e-239">Esto se muestra en esta instrucción: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="e0e6e-240">El procedimiento `startButton_Click` es un ejemplo de un procedimiento `Async Sub`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="e0e6e-241">Dado que `DoSomethingAsync` es una función `Async`, se debe esperar la tarea para la llamada a `DoSomethingAsync`, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="e0e6e-242">El procedimiento de `Sub` de `startButton_Click` debe definirse con el modificador `Async` porque tiene una expresión de `Await`.</span><span class="sxs-lookup"><span data-stu-id="e0e6e-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="e0e6e-243">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0e6e-243">See also</span></span>

- [<span data-ttu-id="e0e6e-244">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e0e6e-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="e0e6e-245">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="e0e6e-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="e0e6e-246">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="e0e6e-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="e0e6e-247">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e0e6e-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="e0e6e-248">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e0e6e-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="e0e6e-249">Of</span><span class="sxs-lookup"><span data-stu-id="e0e6e-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="e0e6e-250">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="e0e6e-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="e0e6e-251">Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="e0e6e-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="e0e6e-252">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="e0e6e-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="e0e6e-253">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="e0e6e-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="e0e6e-254">Expresión de función</span><span class="sxs-lookup"><span data-stu-id="e0e6e-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
