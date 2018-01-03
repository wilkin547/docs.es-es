---
title: "Function (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Function
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
caps.latest.revision: "62"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52e9210f9e715b6055e6ed199ef1aa4b919c6dd6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="f7134-102">Function (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7134-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="f7134-103">Declara el nombre, parámetros y código que definen un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7134-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7134-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="f7134-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f7134-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="f7134-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-106">Optional.</span></span> <span data-ttu-id="f7134-107">Vea [lista de los atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="f7134-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-108">Optional.</span></span> <span data-ttu-id="f7134-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7134-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="f7134-110">Public</span><span class="sxs-lookup"><span data-stu-id="f7134-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="f7134-111">Protected</span><span class="sxs-lookup"><span data-stu-id="f7134-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="f7134-112">Friend</span><span class="sxs-lookup"><span data-stu-id="f7134-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="f7134-113">Private</span><span class="sxs-lookup"><span data-stu-id="f7134-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="f7134-114">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="f7134-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-115">Optional.</span></span> <span data-ttu-id="f7134-116">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7134-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="f7134-117">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="f7134-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="f7134-118">Overrides</span><span class="sxs-lookup"><span data-stu-id="f7134-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="f7134-119">Overridable</span><span class="sxs-lookup"><span data-stu-id="f7134-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="f7134-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="f7134-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="f7134-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="f7134-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="f7134-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-122">Optional.</span></span> <span data-ttu-id="f7134-123">Vea [compartido](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="f7134-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-124">Optional.</span></span> <span data-ttu-id="f7134-125">Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="f7134-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-126">Optional.</span></span> <span data-ttu-id="f7134-127">Vea [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="f7134-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-128">Optional.</span></span> <span data-ttu-id="f7134-129">Vea [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="f7134-130">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f7134-130">Required.</span></span> <span data-ttu-id="f7134-131">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-131">Name of the procedure.</span></span> <span data-ttu-id="f7134-132">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="f7134-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-133">Optional.</span></span> <span data-ttu-id="f7134-134">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="f7134-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="f7134-135">Vea [escriba lista](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="f7134-136">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-136">Optional.</span></span> <span data-ttu-id="f7134-137">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="f7134-138">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="f7134-139">Obligatorio si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="f7134-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="f7134-140">Tipo de datos del valor devuelto por este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="f7134-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-141">Optional.</span></span> <span data-ttu-id="f7134-142">Indica que este procedimiento implementa uno o varios `Function` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="f7134-143">Vea [implementa instrucción](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="f7134-144">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="f7134-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="f7134-145">Lista de procedimientos `Function` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="f7134-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="f7134-146">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7134-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="f7134-147">Parte</span><span class="sxs-lookup"><span data-stu-id="f7134-147">Part</span></span>|<span data-ttu-id="f7134-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7134-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="f7134-149">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f7134-149">Required.</span></span> <span data-ttu-id="f7134-150">Nombre de una interfaz implementada por este procedimiento contenedora de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="f7134-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="f7134-151">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f7134-151">Required.</span></span> <span data-ttu-id="f7134-152">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="f7134-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="f7134-153">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-153">Optional.</span></span> <span data-ttu-id="f7134-154">Indica que este procedimiento puede controlar uno o más eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="f7134-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="f7134-155">Vea [controla](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="f7134-156">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="f7134-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="f7134-157">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="f7134-158">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7134-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="f7134-159">Parte</span><span class="sxs-lookup"><span data-stu-id="f7134-159">Part</span></span>|<span data-ttu-id="f7134-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7134-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="f7134-161">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f7134-161">Required.</span></span> <span data-ttu-id="f7134-162">Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="f7134-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="f7134-163">Requerido.</span><span class="sxs-lookup"><span data-stu-id="f7134-163">Required.</span></span> <span data-ttu-id="f7134-164">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="f7134-165">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7134-165">Optional.</span></span> <span data-ttu-id="f7134-166">Bloque de instrucciones que se ejecutan dentro de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="f7134-167">Termina la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7134-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7134-168">Remarks</span></span>  
 <span data-ttu-id="f7134-169">Todo el código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="f7134-170">A su vez, cada procedimiento, se declara dentro de una clase, una estructura o un módulo que se conoce como la clase, estructura o módulo que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="f7134-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="f7134-171">Para devolver un valor para el código de llamada, use un `Function` procedimiento; en caso contrario, utilice un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="f7134-172">Define una función</span><span class="sxs-lookup"><span data-stu-id="f7134-172">Defining a Function</span></span>  
 <span data-ttu-id="f7134-173">Puede definir un `Function` procedimiento sólo en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="f7134-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="f7134-174">Por lo tanto, el contexto de la declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="f7134-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="f7134-175">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="f7134-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="f7134-176">`Function`procedimientos como valor predeterminado para el acceso público.</span><span class="sxs-lookup"><span data-stu-id="f7134-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="f7134-177">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="f7134-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="f7134-178">A `Function` procedimiento puede declarar el tipo de datos del valor que devuelve el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="f7134-179">Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="f7134-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="f7134-180">Si no se especifica la `returntype` parámetro, el procedimiento devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="f7134-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="f7134-181">Si este procedimiento utiliza el `Implements` (palabra clave), la clase o estructura contenedora también debe tener un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f7134-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="f7134-182">El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="f7134-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="f7134-183">Sin embargo, el nombre por el que una interfaz que define el `Function` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).</span><span class="sxs-lookup"><span data-stu-id="f7134-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7134-184">Puede usar expresiones lambda para definir alineado de expresiones de función.</span><span class="sxs-lookup"><span data-stu-id="f7134-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="f7134-185">Para obtener más información, consulte [expresión de función](../../../visual-basic/language-reference/operators/function-expression.md) y [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="f7134-186">Devolver desde una función</span><span class="sxs-lookup"><span data-stu-id="f7134-186">Returning from a Function</span></span>  
 <span data-ttu-id="f7134-187">Cuando el `Function` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="f7134-188">Para devolver un valor de una función, puede asignar el valor al nombre de función o incluirlo en una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f7134-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="f7134-189">El `Return` instrucción asigna el valor devuelto y sale de la función, como se muestra en el siguiente ejemplo simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="f7134-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="f7134-190">En el ejemplo siguiente se asigna el valor devuelto al nombre de función `myFunction` y, a continuación, usa el `Exit Function` instrucción que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="f7134-190">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="f7134-191">El `Exit Function` y `Return` instrucciones provocan una salida inmediata de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-191">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="f7134-192">Cualquier número de `Exit Function` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Function` y `Return` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f7134-192">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="f7134-193">Si usa `Exit Function` sin asignar un valor a `name`, el procedimiento devuelve el valor predeterminado para el tipo de datos que se especifica en `returntype`.</span><span class="sxs-lookup"><span data-stu-id="f7134-193">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="f7134-194">Si `returntype` no se especifica, el procedimiento devuelve `Nothing`, que es el valor predeterminado de `Object`.</span><span class="sxs-lookup"><span data-stu-id="f7134-194">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="f7134-195">Llamar a una función</span><span class="sxs-lookup"><span data-stu-id="f7134-195">Calling a Function</span></span>  
 <span data-ttu-id="f7134-196">Se llama a un `Function` procedimiento utilizando el nombre del procedimiento, seguido por la lista de argumentos entre paréntesis, en una expresión.</span><span class="sxs-lookup"><span data-stu-id="f7134-196">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="f7134-197">Puede omitir los paréntesis solo si no se proporciona ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="f7134-197">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="f7134-198">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="f7134-198">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="f7134-199">Se llama a un `Function` procedimiento del mismo modo que se llama a cualquier biblioteca como función `Sqrt`, `Cos`, o `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="f7134-199">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="f7134-200">También puede llamar a una función utilizando la `Call` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="f7134-200">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="f7134-201">En ese caso, se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f7134-201">In that case, the return value is ignored.</span></span> <span data-ttu-id="f7134-202">El uso de la `Call` palabra clave no se recomienda en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="f7134-202">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="f7134-203">Para obtener más información, consulte [instrucción Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-203">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="f7134-204">Visual Basic reorganiza a veces las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="f7134-204">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="f7134-205">Por esta razón, no debe utilizar un `Function` procedimiento en una expresión aritmética cuando la función cambie el valor de las variables en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="f7134-205">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="f7134-206">Funciones de Async</span><span class="sxs-lookup"><span data-stu-id="f7134-206">Async Functions</span></span>  
 <span data-ttu-id="f7134-207">El *Async* característica le permite invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="f7134-207">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="f7134-208">Si marca una función con el [Async](../../../visual-basic/language-reference/modifiers/async.md) modificador, puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en la función.</span><span class="sxs-lookup"><span data-stu-id="f7134-208">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="f7134-209">Cuando el control alcanza un `Await` expresión en el `Async` función, el control vuelve al llamador y el progreso de la función se suspende hasta que se complete la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="f7134-209">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="f7134-210">Una vez completada la tarea, la ejecución puede reanudarse en la función.</span><span class="sxs-lookup"><span data-stu-id="f7134-210">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7134-211">Un `Async` procedimiento vuelve al llamador cuando encuentra el primer objeto esperado que aún no se ha completado o cuando llega al final de la `Async` procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="f7134-211">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="f7134-212">Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="f7134-212">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="f7134-213">Un ejemplo de un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="f7134-213">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="f7134-214">Un `Async` función no puede declarar ningún [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parámetros.</span><span class="sxs-lookup"><span data-stu-id="f7134-214">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="f7134-215">A [Sub (instrucción)](sub-statement.md) también se deben marcar con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="f7134-215">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="f7134-216">Esto se utiliza principalmente para controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="f7134-216">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="f7134-217">Un `Async``Sub` procedimiento no se puede esperar y el llamador de un `Async``Sub` procedimiento no puede detectar las excepciones producidas por el `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-217">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="f7134-218">Para obtener más información acerca de `Async` funciones, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [tipos de valor devueltos de Async](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-218">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="f7134-219">Funciones de iterador</span><span class="sxs-lookup"><span data-stu-id="f7134-219">Iterator Functions</span></span>  
 <span data-ttu-id="f7134-220">Un *iterador* función realiza una iteración personalizada en una colección, como una lista o matriz.</span><span class="sxs-lookup"><span data-stu-id="f7134-220">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="f7134-221">Una función de iterador utiliza la [producen](yield-statement.md) instrucción para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="f7134-221">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="f7134-222">Cuando un [producen](yield-statement.md) se alcanza la instrucción, se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="f7134-222">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="f7134-223">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="f7134-223">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="f7134-224">Llamar a un iterador de código de cliente mediante un [For Each... Siguiente](for-each-next-statement.md) instrucción.</span><span class="sxs-lookup"><span data-stu-id="f7134-224">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="f7134-225">Puede ser el tipo de valor devuelto de una función de iterador <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="f7134-225">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="f7134-226">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="f7134-226">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7134-227">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7134-227">Example</span></span>  
 <span data-ttu-id="f7134-228">En el ejemplo siguiente se usa el `Function` instrucción para declarar el nombre, parámetros y código que forman el cuerpo de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-228">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="f7134-229">El `ParamArray` modificador permite que la función aceptar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f7134-229">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="f7134-230">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7134-230">Example</span></span>  
 <span data-ttu-id="f7134-231">En el ejemplo siguiente se invoca la función declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="f7134-231">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="f7134-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7134-232">Example</span></span>  
 <span data-ttu-id="f7134-233">En el ejemplo siguiente, `DelayAsync` es un `Async``Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="f7134-233">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="f7134-234">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="f7134-234">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="f7134-235">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="f7134-235">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="f7134-236">Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero.</span><span class="sxs-lookup"><span data-stu-id="f7134-236">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="f7134-237">Esto se muestra en esta instrucción: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="f7134-237">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="f7134-238">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f7134-238">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="f7134-239">Dado que `DoSomethingAsync` es un `Async` función, la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="f7134-239">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="f7134-240">El `startButton_Click``Sub` procedimiento debe definirse con el `Async` modificador porque tiene un `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="f7134-240">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f7134-241">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7134-241">See Also</span></span>  
 [<span data-ttu-id="f7134-242">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f7134-242">Sub Statement</span></span>](sub-statement.md)  
 [<span data-ttu-id="f7134-243">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="f7134-243">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="f7134-244">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="f7134-244">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="f7134-245">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f7134-245">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="f7134-246">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f7134-246">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="f7134-247">Of</span><span class="sxs-lookup"><span data-stu-id="f7134-247">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="f7134-248">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="f7134-248">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="f7134-249">Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="f7134-249">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="f7134-250">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="f7134-250">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="f7134-251">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="f7134-251">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="f7134-252">Expresión de función</span><span class="sxs-lookup"><span data-stu-id="f7134-252">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
