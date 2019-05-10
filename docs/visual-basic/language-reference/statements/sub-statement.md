---
title: Sub (Instrucción, Visual Basic)
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
ms.openlocfilehash: 00e2f313e283259ea44dd6da71530bed4bff31c5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751178"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="6e5f2-102">Sub (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e5f2-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="6e5f2-103">Declara el nombre, parámetros y código que definen un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e5f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e5f2-104">Syntax</span></span>

```
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="6e5f2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="6e5f2-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="6e5f2-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-106">Optional.</span></span> <span data-ttu-id="6e5f2-107">Consulte [lista de los atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="6e5f2-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-108">Optional.</span></span> <span data-ttu-id="6e5f2-109">Indica la definición de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="6e5f2-110">Consulte [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="6e5f2-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-111">Optional.</span></span> <span data-ttu-id="6e5f2-112">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e5f2-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="6e5f2-113">Public</span><span class="sxs-lookup"><span data-stu-id="6e5f2-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="6e5f2-114">Protected</span><span class="sxs-lookup"><span data-stu-id="6e5f2-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="6e5f2-115">Friend</span><span class="sxs-lookup"><span data-stu-id="6e5f2-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="6e5f2-116">Private</span><span class="sxs-lookup"><span data-stu-id="6e5f2-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="6e5f2-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="6e5f2-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="6e5f2-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="6e5f2-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="6e5f2-119">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="6e5f2-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-120">Optional.</span></span> <span data-ttu-id="6e5f2-121">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e5f2-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="6e5f2-122">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="6e5f2-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="6e5f2-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="6e5f2-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="6e5f2-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="6e5f2-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="6e5f2-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="6e5f2-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="6e5f2-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="6e5f2-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="6e5f2-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-127">Optional.</span></span> <span data-ttu-id="6e5f2-128">Consulte [compartido](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="6e5f2-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-129">Optional.</span></span> <span data-ttu-id="6e5f2-130">Consulte [sombras](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="6e5f2-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-131">Optional.</span></span> <span data-ttu-id="6e5f2-132">Consulte [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="6e5f2-133">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-133">Required.</span></span> <span data-ttu-id="6e5f2-134">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-134">Name of the procedure.</span></span> <span data-ttu-id="6e5f2-135">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="6e5f2-136">Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento a la `New` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="6e5f2-137">Para obtener más información, consulte [duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="6e5f2-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-138">Optional.</span></span> <span data-ttu-id="6e5f2-139">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="6e5f2-140">Consulte [escriba lista](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="6e5f2-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-141">Optional.</span></span> <span data-ttu-id="6e5f2-142">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="6e5f2-143">Consulte [Lista_de_parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="6e5f2-144">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-144">Optional.</span></span> <span data-ttu-id="6e5f2-145">Indica que este procedimiento implementa uno o varios `Sub` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="6e5f2-146">Consulte [implementa instrucción](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="6e5f2-147">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="6e5f2-148">Lista de procedimientos `Sub` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="6e5f2-149">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e5f2-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="6e5f2-150">Parte</span><span class="sxs-lookup"><span data-stu-id="6e5f2-150">Part</span></span>|<span data-ttu-id="6e5f2-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e5f2-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="6e5f2-152">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-152">Required.</span></span> <span data-ttu-id="6e5f2-153">Nombre de una interfaz implementada por este procedimiento contenedora de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="6e5f2-154">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-154">Required.</span></span> <span data-ttu-id="6e5f2-155">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="6e5f2-156">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-156">Optional.</span></span> <span data-ttu-id="6e5f2-157">Indica que este procedimiento puede controlar uno o más eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="6e5f2-158">Consulte [controla](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="6e5f2-159">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="6e5f2-160">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="6e5f2-161">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="6e5f2-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="6e5f2-162">Parte</span><span class="sxs-lookup"><span data-stu-id="6e5f2-162">Part</span></span>|<span data-ttu-id="6e5f2-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e5f2-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="6e5f2-164">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-164">Required.</span></span> <span data-ttu-id="6e5f2-165">Variable de objeto declarada con el tipo de datos de la clase o estructura que provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="6e5f2-166">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-166">Required.</span></span> <span data-ttu-id="6e5f2-167">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="6e5f2-168">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-168">Optional.</span></span> <span data-ttu-id="6e5f2-169">Bloque de instrucciones que se ejecutan dentro de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="6e5f2-170">Termina la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e5f2-171">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e5f2-171">Remarks</span></span>

<span data-ttu-id="6e5f2-172">El código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="6e5f2-173">Use un `Sub` cuando no desee devolver un valor al código de llamada de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="6e5f2-174">Use un `Function` procedimiento cuando desee devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="6e5f2-175">Definir un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="6e5f2-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="6e5f2-176">Puede definir un `Sub` procedimiento sólo en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="6e5f2-177">El contexto de declaración de un procedimiento sub por lo tanto, debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="6e5f2-178">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="6e5f2-179">`Sub` valor predeterminado de los procedimientos para acceso público.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="6e5f2-180">Puede ajustar sus niveles de acceso mediante los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="6e5f2-181">Si el procedimiento utiliza el `Implements` debe tener la palabra clave, la clase o estructura que contiene un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="6e5f2-182">El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="6e5f2-183">Sin embargo, el nombre por el que una interfaz define el `Sub` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="6e5f2-184">Devolución desde un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="6e5f2-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="6e5f2-185">Cuando un `Sub` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="6e5f2-186">El ejemplo siguiente muestra una devolución de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="6e5f2-187">El `Exit Sub` y `Return` instrucciones provocan una inmediata salida desde un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="6e5f2-188">Cualquier número de `Exit Sub` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento, y puede mezclar `Exit Sub` y `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="6e5f2-189">Llamar a un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="6e5f2-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="6e5f2-190">Se llama a un `Sub` procedimiento con el nombre del procedimiento en una instrucción y, a continuación, siguiendo ese nombre con su lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="6e5f2-191">Puede omitir los paréntesis solo si no se proporciona ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="6e5f2-192">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="6e5f2-193">Un `Sub` procedimiento y un `Function` procedimiento puede tener parámetros y realizar una serie de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="6e5f2-194">Sin embargo, un `Function` procedimiento devuelve un valor y un `Sub` procedimiento no.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="6e5f2-195">Por lo tanto, no puede usar un `Sub` procedimiento en una expresión.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="6e5f2-196">Puede usar el `Call` palabra clave cuando se llama a un `Sub` procedimiento, pero esa palabra clave no se recomienda para la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="6e5f2-197">Para obtener más información, consulte [instrucción Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="6e5f2-198">Visual Basic a veces se reorganiza las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="6e5f2-199">Por ese motivo, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que las expresiones se llamará en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="6e5f2-200">Procedimientos Sub en asincrónico</span><span class="sxs-lookup"><span data-stu-id="6e5f2-200">Async Sub Procedures</span></span>

<span data-ttu-id="6e5f2-201">Mediante el uso de la característica Async, puede invocar las funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="6e5f2-202">Si marca un procedimiento con el [Async](../modifiers/async.md) modificador, puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="6e5f2-203">Cuando el control alcanza un `Await` expresión en el `Async` procedimiento, el control vuelve al llamador y el progreso en el procedimiento se suspende hasta que se complete la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="6e5f2-204">Cuando se completa la tarea, puede reanudar la ejecución del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="6e5f2-205">Un `Async` procedimiento devuelve al llamador cuando se encuentra en el primer objeto esperado que aún no se ha completado o el final de la `Async` se alcanza el procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="6e5f2-206">También puede marcar un [instrucción Function](function-statement.md) con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="6e5f2-207">Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="6e5f2-208">Un ejemplo más adelante en este tema se muestra un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="6e5f2-209">`Async` `Sub` los procedimientos se utilizan principalmente para controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="6e5f2-210">Un `Async` `Sub` procedimiento no se espera y el llamador de un `Async` `Sub` procedimiento no puede detectar las excepciones que el `Sub` procedimiento inicia.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="6e5f2-211">Un `Async` procedimiento no puede declarar ningún [ByRef](../modifiers/byref.md) parámetros.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="6e5f2-212">Para obtener más información acerca de `Async` procedimientos, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [tipos de valor devueltos de Async](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e5f2-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="6e5f2-213">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e5f2-213">Example</span></span>

<span data-ttu-id="6e5f2-214">En el ejemplo siguiente se usa el `Sub` instrucción para definir el nombre, parámetros y código que forman el cuerpo de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="6e5f2-215">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e5f2-215">Example</span></span>

<span data-ttu-id="6e5f2-216">En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="6e5f2-217">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="6e5f2-218">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="6e5f2-219">Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="6e5f2-220">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="6e5f2-221">Dado que `DoSomethingAsync` es un `Async` (función), la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="6e5f2-222">El `startButton_Click` `Sub` procedimiento debe definirse con la `Async` modificador porque tiene un `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="6e5f2-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="6e5f2-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e5f2-223">See also</span></span>

- [<span data-ttu-id="6e5f2-224">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6e5f2-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="6e5f2-225">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6e5f2-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="6e5f2-226">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="6e5f2-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="6e5f2-227">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6e5f2-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="6e5f2-228">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6e5f2-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="6e5f2-229">Of</span><span class="sxs-lookup"><span data-stu-id="6e5f2-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="6e5f2-230">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="6e5f2-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="6e5f2-231">Cómo: Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="6e5f2-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="6e5f2-232">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="6e5f2-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="6e5f2-233">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="6e5f2-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
