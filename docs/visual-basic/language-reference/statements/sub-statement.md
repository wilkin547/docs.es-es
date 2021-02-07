---
description: 'Más información acerca de: sub Statement (Visual Basic)'
title: Instrucción Sub
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 9be40c8284c677a151e4b1665f0b49e5f852bf00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740995"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="9d996-103">Sub (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d996-103">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="9d996-104">Declara el nombre, los parámetros y el código que definen un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-104">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d996-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d996-105">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="9d996-106">Partes</span><span class="sxs-lookup"><span data-stu-id="9d996-106">Parts</span></span>

- `attributelist`

  <span data-ttu-id="9d996-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-107">Optional.</span></span> <span data-ttu-id="9d996-108">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-108">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="9d996-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-109">Optional.</span></span> <span data-ttu-id="9d996-110">Indica la definición de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="9d996-110">Indicates definition of a partial method.</span></span> <span data-ttu-id="9d996-111">Vea [métodos parciales](../../programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-111">See [Partial Methods](../../programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="9d996-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-112">Optional.</span></span> <span data-ttu-id="9d996-113">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d996-113">Can be one of the following:</span></span>

  - [<span data-ttu-id="9d996-114">Público</span><span class="sxs-lookup"><span data-stu-id="9d996-114">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="9d996-115">Protegido</span><span class="sxs-lookup"><span data-stu-id="9d996-115">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="9d996-116">Friend</span><span class="sxs-lookup"><span data-stu-id="9d996-116">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="9d996-117">Privado</span><span class="sxs-lookup"><span data-stu-id="9d996-117">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="9d996-118">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="9d996-118">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="9d996-119">Private Protected</span><span class="sxs-lookup"><span data-stu-id="9d996-119">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="9d996-120">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-120">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="9d996-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-121">Optional.</span></span> <span data-ttu-id="9d996-122">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d996-122">Can be one of the following:</span></span>

  - [<span data-ttu-id="9d996-123">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="9d996-123">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="9d996-124">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="9d996-124">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="9d996-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="9d996-125">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="9d996-126">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="9d996-126">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="9d996-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="9d996-127">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="9d996-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-128">Optional.</span></span> <span data-ttu-id="9d996-129">Vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-129">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="9d996-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-130">Optional.</span></span> <span data-ttu-id="9d996-131">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-131">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="9d996-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-132">Optional.</span></span> <span data-ttu-id="9d996-133">Vea [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-133">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="9d996-134">Necesario.</span><span class="sxs-lookup"><span data-stu-id="9d996-134">Required.</span></span> <span data-ttu-id="9d996-135">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-135">Name of the procedure.</span></span> <span data-ttu-id="9d996-136">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-136">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="9d996-137">Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento en la `New` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="9d996-137">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="9d996-138">Para obtener más información, vea [duración del objeto: cómo se crean y destruyen los objetos](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-138">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="9d996-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-139">Optional.</span></span> <span data-ttu-id="9d996-140">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="9d996-140">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="9d996-141">Consulte [lista de tipos](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-141">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="9d996-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-142">Optional.</span></span> <span data-ttu-id="9d996-143">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-143">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="9d996-144">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-144">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="9d996-145">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-145">Optional.</span></span> <span data-ttu-id="9d996-146">Indica que este procedimiento implementa uno o más `Sub` procedimientos, cada uno de ellos definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-146">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="9d996-147">Vea [Implements (instrucción](implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="9d996-147">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="9d996-148">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="9d996-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="9d996-149">Lista de procedimientos `Sub` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="9d996-149">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="9d996-150">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d996-150">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="9d996-151">Parte</span><span class="sxs-lookup"><span data-stu-id="9d996-151">Part</span></span>|<span data-ttu-id="9d996-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d996-152">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="9d996-153">Necesario.</span><span class="sxs-lookup"><span data-stu-id="9d996-153">Required.</span></span> <span data-ttu-id="9d996-154">Nombre de una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-154">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="9d996-155">Necesario.</span><span class="sxs-lookup"><span data-stu-id="9d996-155">Required.</span></span> <span data-ttu-id="9d996-156">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="9d996-156">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="9d996-157">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-157">Optional.</span></span> <span data-ttu-id="9d996-158">Indica que este procedimiento puede controlar uno o más eventos concretos.</span><span class="sxs-lookup"><span data-stu-id="9d996-158">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="9d996-159">Vea [identificadores](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-159">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="9d996-160">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="9d996-160">Required if `Handles` is supplied.</span></span> <span data-ttu-id="9d996-161">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-161">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="9d996-162">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d996-162">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="9d996-163">Parte</span><span class="sxs-lookup"><span data-stu-id="9d996-163">Part</span></span>|<span data-ttu-id="9d996-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d996-164">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="9d996-165">Necesario.</span><span class="sxs-lookup"><span data-stu-id="9d996-165">Required.</span></span> <span data-ttu-id="9d996-166">Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="9d996-166">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="9d996-167">Necesario.</span><span class="sxs-lookup"><span data-stu-id="9d996-167">Required.</span></span> <span data-ttu-id="9d996-168">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-168">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="9d996-169">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9d996-169">Optional.</span></span> <span data-ttu-id="9d996-170">Bloque de instrucciones que se ejecutarán dentro de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-170">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="9d996-171">Finaliza la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-171">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d996-172">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9d996-172">Remarks</span></span>

<span data-ttu-id="9d996-173">Todo el código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-173">All executable code must be inside a procedure.</span></span> <span data-ttu-id="9d996-174">Use un `Sub` procedimiento cuando no desee devolver un valor al código de llamada.</span><span class="sxs-lookup"><span data-stu-id="9d996-174">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="9d996-175">Use un `Function` procedimiento cuando desee devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="9d996-175">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="9d996-176">Definir un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="9d996-176">Defining a Sub Procedure</span></span>

<span data-ttu-id="9d996-177">Solo puede definir un `Sub` procedimiento en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="9d996-177">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="9d996-178">El contexto de la declaración para un procedimiento Sub debe, por tanto, ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="9d996-178">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="9d996-179">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="9d996-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="9d996-180">`Sub` los procedimientos tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="9d996-180">`Sub` procedures default to public access.</span></span> <span data-ttu-id="9d996-181">Puede ajustar sus niveles de acceso mediante los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="9d996-181">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="9d996-182">Si el procedimiento usa la `Implements` palabra clave, la clase contenedora o la estructura deben tener una `Implements` instrucción que siga inmediatamente a su `Class` `Structure` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="9d996-182">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="9d996-183">La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="9d996-183">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="9d996-184">Sin embargo, el nombre por el que una interfaz define `Sub` (en `definedname` ) no tiene que coincidir con el nombre de este procedimiento (en `name` ).</span><span class="sxs-lookup"><span data-stu-id="9d996-184">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="9d996-185">Devolver desde un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="9d996-185">Returning from a Sub Procedure</span></span>

<span data-ttu-id="9d996-186">Cuando un `Sub` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="9d996-186">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="9d996-187">En el ejemplo siguiente se muestra un valor devuelto de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-187">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="9d996-188">Las `Exit Sub` `Return` instrucciones y producen una salida inmediata de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-188">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="9d996-189">Cualquier número de `Exit Sub` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Sub` e `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9d996-189">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="9d996-190">Llamar a un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="9d996-190">Calling a Sub Procedure</span></span>

<span data-ttu-id="9d996-191">Llame a un `Sub` procedimiento mediante el nombre del procedimiento en una instrucción y, a continuación, siga ese nombre con su lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9d996-191">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="9d996-192">Solo se pueden omitir los paréntesis si no se proporcionan argumentos.</span><span class="sxs-lookup"><span data-stu-id="9d996-192">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="9d996-193">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="9d996-193">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="9d996-194">Un `Sub` procedimiento y un `Function` procedimiento pueden tener parámetros y realizar una serie de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9d996-194">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="9d996-195">Sin embargo, un `Function` procedimiento devuelve un valor y un `Sub` procedimiento no.</span><span class="sxs-lookup"><span data-stu-id="9d996-195">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="9d996-196">Por lo tanto, no se puede usar un `Sub` procedimiento en una expresión.</span><span class="sxs-lookup"><span data-stu-id="9d996-196">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="9d996-197">Puede usar la `Call` palabra clave al llamar a un `Sub` procedimiento, pero esa palabra clave no se recomienda para la mayoría de los usos.</span><span class="sxs-lookup"><span data-stu-id="9d996-197">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="9d996-198">Para obtener más información, consulte [instrucción call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-198">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="9d996-199">A veces Visual Basic reorganiza las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="9d996-199">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="9d996-200">Por ese motivo, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que se llamará a esas expresiones en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="9d996-200">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="9d996-201">Procedimientos sub asincrónicos</span><span class="sxs-lookup"><span data-stu-id="9d996-201">Async Sub Procedures</span></span>

<span data-ttu-id="9d996-202">Mediante el uso de la característica Async, puede invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="9d996-202">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="9d996-203">Si marca un procedimiento con el modificador [Async](../modifiers/async.md) , puede usar el operador [Await](../operators/await-operator.md) en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-203">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="9d996-204">Cuando el control alcanza una `Await` expresión en el `Async` procedimiento, el control vuelve al autor de la llamada y el progreso en el procedimiento se suspende hasta que se completa la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="9d996-204">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="9d996-205">Una vez completada la tarea, la ejecución puede reanudarse en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-205">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="9d996-206">Un `Async` procedimiento vuelve al llamador cuando se encuentra el primer objeto esperado que aún no se ha completado o hasta que se alcanza el final del `Async` procedimiento, lo que suceda primero.</span><span class="sxs-lookup"><span data-stu-id="9d996-206">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="9d996-207">También puede marcar una [instrucción function](function-statement.md) con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="9d996-207">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="9d996-208">Una `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task> .</span><span class="sxs-lookup"><span data-stu-id="9d996-208">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="9d996-209">Un ejemplo más adelante en este tema muestra una `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="9d996-209">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="9d996-210">`Async``Sub`los procedimientos se utilizan principalmente para los controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="9d996-210">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="9d996-211">`Async` `Sub` No se puede esperar a un procedimiento y el autor de la llamada de un `Async` `Sub` procedimiento no puede detectar las excepciones que `Sub` inicia el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-211">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="9d996-212">Un `Async` procedimiento no puede declarar ningún parámetro [ByRef](../modifiers/byref.md) .</span><span class="sxs-lookup"><span data-stu-id="9d996-212">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="9d996-213">Para obtener más información sobre `Async` los procedimientos, consulte [programación asincrónica con Async y Await](../../programming-guide/concepts/async/index.md), [flujo de control en programas asincrónicos](../../programming-guide/concepts/async/control-flow-in-async-programs.md)y [tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="9d996-213">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="9d996-214">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d996-214">Example</span></span>

<span data-ttu-id="9d996-215">En el ejemplo siguiente se usa la `Sub` instrucción para definir el nombre, los parámetros y el código que forman el cuerpo de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-215">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="9d996-216">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d996-216">Example</span></span>

<span data-ttu-id="9d996-217">En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> .</span><span class="sxs-lookup"><span data-stu-id="9d996-217">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9d996-218">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="9d996-218">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="9d996-219">Por consiguiente, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)` .</span><span class="sxs-lookup"><span data-stu-id="9d996-219">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="9d996-220">Dado que el tipo de valor devuelto es `Task(Of Integer)` , la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask` .</span><span class="sxs-lookup"><span data-stu-id="9d996-220">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="9d996-221">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9d996-221">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="9d996-222">Dado `DoSomethingAsync` que es una `Async` función, se debe esperar a la tarea de la llamada a `DoSomethingAsync` , como se muestra en la siguiente instrucción: `Await DoSomethingAsync()` .</span><span class="sxs-lookup"><span data-stu-id="9d996-222">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="9d996-223">El `startButton_Click` `Sub` procedimiento debe definirse con el `Async` modificador porque tiene una `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="9d996-223">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9d996-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d996-224">See also</span></span>

- [<span data-ttu-id="9d996-225">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="9d996-225">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="9d996-226">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="9d996-226">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="9d996-227">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="9d996-227">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="9d996-228">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="9d996-228">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="9d996-229">Instrucción Call</span><span class="sxs-lookup"><span data-stu-id="9d996-229">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="9d996-230">De</span><span class="sxs-lookup"><span data-stu-id="9d996-230">Of</span></span>](of-clause.md)
- [<span data-ttu-id="9d996-231">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="9d996-231">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="9d996-232">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="9d996-232">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="9d996-233">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="9d996-233">Troubleshooting Procedures</span></span>](../../programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="9d996-234">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="9d996-234">Partial Methods</span></span>](../../programming-guide/language-features/procedures/partial-methods.md)
