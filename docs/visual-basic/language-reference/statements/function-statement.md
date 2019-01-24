---
title: Function (Instrucción, Visual Basic)
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
ms.openlocfilehash: 5018aebb0401ce5a1c46ecf04a7c65ca676271e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565909"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="db16d-102">Function (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db16d-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="db16d-103">Declara el nombre, parámetros y código que definen un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db16d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db16d-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="db16d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="db16d-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="db16d-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-106">Optional.</span></span> <span data-ttu-id="db16d-107">Consulte [lista de los atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="db16d-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-108">Optional.</span></span> <span data-ttu-id="db16d-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="db16d-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="db16d-110">Public</span><span class="sxs-lookup"><span data-stu-id="db16d-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="db16d-111">Protected</span><span class="sxs-lookup"><span data-stu-id="db16d-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="db16d-112">Friend</span><span class="sxs-lookup"><span data-stu-id="db16d-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="db16d-113">Private</span><span class="sxs-lookup"><span data-stu-id="db16d-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="db16d-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="db16d-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="db16d-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="db16d-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)  
  
     <span data-ttu-id="db16d-116">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="db16d-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-117">Optional.</span></span> <span data-ttu-id="db16d-118">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="db16d-118">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="db16d-119">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="db16d-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="db16d-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="db16d-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="db16d-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="db16d-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="db16d-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="db16d-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="db16d-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="db16d-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="db16d-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-124">Optional.</span></span> <span data-ttu-id="db16d-125">Consulte [compartido](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="db16d-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-126">Optional.</span></span> <span data-ttu-id="db16d-127">Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="db16d-128">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-128">Optional.</span></span> <span data-ttu-id="db16d-129">Consulte [Async](../../../visual-basic/language-reference/modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="db16d-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-130">Optional.</span></span> <span data-ttu-id="db16d-131">Consulte [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="db16d-132">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db16d-132">Required.</span></span> <span data-ttu-id="db16d-133">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-133">Name of the procedure.</span></span> <span data-ttu-id="db16d-134">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="db16d-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-135">Optional.</span></span> <span data-ttu-id="db16d-136">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="db16d-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="db16d-137">Consulte [escriba lista](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-137">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="db16d-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-138">Optional.</span></span> <span data-ttu-id="db16d-139">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="db16d-140">Consulte [Lista_de_parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-140">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="db16d-141">Es necesario si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="db16d-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="db16d-142">Tipo de datos del valor devuelto por este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-142">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="db16d-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-143">Optional.</span></span> <span data-ttu-id="db16d-144">Indica que este procedimiento implementa uno o varios `Function` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="db16d-145">Consulte [implementa instrucción](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-145">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="db16d-146">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="db16d-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="db16d-147">Lista de procedimientos `Function` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="db16d-147">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="db16d-148">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="db16d-148">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="db16d-149">Parte</span><span class="sxs-lookup"><span data-stu-id="db16d-149">Part</span></span>|<span data-ttu-id="db16d-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="db16d-150">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="db16d-151">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db16d-151">Required.</span></span> <span data-ttu-id="db16d-152">Nombre de una interfaz implementada por este procedimiento contenedora de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="db16d-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="db16d-153">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db16d-153">Required.</span></span> <span data-ttu-id="db16d-154">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="db16d-154">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="db16d-155">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-155">Optional.</span></span> <span data-ttu-id="db16d-156">Indica que este procedimiento puede controlar uno o más eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="db16d-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="db16d-157">Consulte [controla](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-157">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="db16d-158">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="db16d-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="db16d-159">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-159">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="db16d-160">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="db16d-160">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="db16d-161">Parte</span><span class="sxs-lookup"><span data-stu-id="db16d-161">Part</span></span>|<span data-ttu-id="db16d-162">Descripción</span><span class="sxs-lookup"><span data-stu-id="db16d-162">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="db16d-163">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db16d-163">Required.</span></span> <span data-ttu-id="db16d-164">Variable de objeto declarada con el tipo de datos de la clase o estructura que provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="db16d-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="db16d-165">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db16d-165">Required.</span></span> <span data-ttu-id="db16d-166">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-166">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="db16d-167">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db16d-167">Optional.</span></span> <span data-ttu-id="db16d-168">Bloque de instrucciones que se ejecutan dentro de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-168">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="db16d-169">Termina la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-169">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db16d-170">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db16d-170">Remarks</span></span>  
 <span data-ttu-id="db16d-171">El código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="db16d-172">A su vez, cada procedimiento, se declara dentro de una clase, una estructura o un módulo que se conoce como la clase, estructura o módulo que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="db16d-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="db16d-173">Para devolver un valor al código de llamada, use un `Function` procedimiento; en caso contrario, use un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="db16d-174">Definir una función</span><span class="sxs-lookup"><span data-stu-id="db16d-174">Defining a Function</span></span>  
 <span data-ttu-id="db16d-175">Puede definir un `Function` procedimiento sólo en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="db16d-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="db16d-176">Por lo tanto, el contexto de declaración de una función debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="db16d-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="db16d-177">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="db16d-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="db16d-178">`Function` valor predeterminado de los procedimientos para acceso público.</span><span class="sxs-lookup"><span data-stu-id="db16d-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="db16d-179">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="db16d-179">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="db16d-180">Un `Function` procedimiento puede declarar el tipo de datos del valor que devuelve el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="db16d-181">Puede especificar cualquier tipo de datos o el nombre de una enumeración, una estructura, una clase o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="db16d-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="db16d-182">Si no se especifica la `returntype` parámetro, el procedimiento devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="db16d-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="db16d-183">Si este procedimiento utiliza el `Implements` también debe tener la palabra clave, la clase o estructura que contiene un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="db16d-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="db16d-184">El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="db16d-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="db16d-185">Sin embargo, el nombre por el que una interfaz define el `Function` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).</span><span class="sxs-lookup"><span data-stu-id="db16d-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db16d-186">Puede usar expresiones lambda para definir expresiones de función en línea.</span><span class="sxs-lookup"><span data-stu-id="db16d-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="db16d-187">Para obtener más información, consulte [expresión de función](../../../visual-basic/language-reference/operators/function-expression.md) y [expresiones Lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="db16d-188">Devolver desde una función</span><span class="sxs-lookup"><span data-stu-id="db16d-188">Returning from a Function</span></span>  
 <span data-ttu-id="db16d-189">Cuando el `Function` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que llamó al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="db16d-190">Para devolver un valor de una función, puede asignar el valor al nombre de función o incluirlo en un `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="db16d-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="db16d-191">El `Return` instrucción asigna el valor devuelto al mismo tiempo y sale de la función, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="db16d-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="db16d-192">En el ejemplo siguiente se asigna el valor devuelto para el nombre de función `myFunction` y, a continuación, usa el `Exit Function` instrucción para devolver.</span><span class="sxs-lookup"><span data-stu-id="db16d-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="db16d-193">El `Exit Function` y `Return` instrucciones provocan una inmediata salida desde un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="db16d-194">Cualquier número de `Exit Function` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento, y puede mezclar `Exit Function` y `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="db16d-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="db16d-195">Si usas `Exit Function` sin asignar un valor a `name`, el procedimiento devuelve el valor predeterminado para el tipo de datos que se especifica en `returntype`.</span><span class="sxs-lookup"><span data-stu-id="db16d-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="db16d-196">Si `returntype` no se especifica, el procedimiento devuelve `Nothing`, que es el valor predeterminado de `Object`.</span><span class="sxs-lookup"><span data-stu-id="db16d-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="db16d-197">Llamar a una función</span><span class="sxs-lookup"><span data-stu-id="db16d-197">Calling a Function</span></span>  
 <span data-ttu-id="db16d-198">Se llama a un `Function` procedimiento utilizando el nombre del procedimiento, seguido de la lista de argumentos entre paréntesis en una expresión.</span><span class="sxs-lookup"><span data-stu-id="db16d-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="db16d-199">Puede omitir los paréntesis solo si no se proporciona ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="db16d-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="db16d-200">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="db16d-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="db16d-201">Se llama a un `Function` procedimiento del mismo modo que llamar a cualquier biblioteca de función como `Sqrt`, `Cos`, o `ChrW`.</span><span class="sxs-lookup"><span data-stu-id="db16d-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="db16d-202">También puede llamar a una función mediante el `Call` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="db16d-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="db16d-203">En ese caso, se omite el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="db16d-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="db16d-204">El uso de la `Call` palabra clave no se recomienda en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="db16d-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="db16d-205">Para obtener más información, consulte [instrucción Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="db16d-206">Visual Basic a veces se reorganiza las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="db16d-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="db16d-207">Por ese motivo, no debe usar un `Function` procedimiento en una expresión aritmética cuando la función cambia el valor de variables en la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="db16d-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="db16d-208">Funciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="db16d-208">Async Functions</span></span>  
 <span data-ttu-id="db16d-209">El *Async* característica permite invocar las funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="db16d-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="db16d-210">Si marca una función con el [Async](../../../visual-basic/language-reference/modifiers/async.md) modificador, puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en la función.</span><span class="sxs-lookup"><span data-stu-id="db16d-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="db16d-211">Cuando el control alcanza un `Await` expresión en el `Async` función, el control vuelve al llamador y progreso de la función se suspende hasta que se complete la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="db16d-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="db16d-212">Cuando se completa la tarea, puede reanudar la ejecución de la función.</span><span class="sxs-lookup"><span data-stu-id="db16d-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db16d-213">Un `Async` procedimiento vuelve al llamador cuando encuentra el primer objeto esperado que aún no se ha completado, o cuando llega al final de la `Async` procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="db16d-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="db16d-214">Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="db16d-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="db16d-215">Un ejemplo de un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> se proporciona a continuación.</span><span class="sxs-lookup"><span data-stu-id="db16d-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="db16d-216">Un `Async` función no puede declarar ningún [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parámetros.</span><span class="sxs-lookup"><span data-stu-id="db16d-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="db16d-217">Un [Sub (instrucción)](sub-statement.md) también se pueden marcar con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="db16d-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="db16d-218">Se utiliza principalmente para controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="db16d-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="db16d-219">Un `Async` `Sub` procedimiento no se espera y el llamador de un `Async` `Sub` procedimiento no puede detectar las excepciones producidas por la `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="db16d-220">Para obtener más información acerca de `Async` funciones, vea [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [tipos de valor devueltos de Async](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="db16d-221">Funciones de iterador</span><span class="sxs-lookup"><span data-stu-id="db16d-221">Iterator Functions</span></span>  
 <span data-ttu-id="db16d-222">Un *iterador* función realiza una iteración personalizada en una colección, como una lista o matriz.</span><span class="sxs-lookup"><span data-stu-id="db16d-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="db16d-223">Una función de iterador usa la [Yield](yield-statement.md) instrucción para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="db16d-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="db16d-224">Cuando un [Yield](yield-statement.md) se alcanza la instrucción, se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="db16d-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="db16d-225">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="db16d-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="db16d-226">Llamar a un iterador desde código de cliente mediante un [For Each... Siguiente](for-each-next-statement.md) instrucción.</span><span class="sxs-lookup"><span data-stu-id="db16d-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="db16d-227">Puede ser el tipo de valor devuelto de una función de iterador <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="db16d-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="db16d-228">Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="db16d-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="db16d-229">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db16d-229">Example</span></span>  
 <span data-ttu-id="db16d-230">En el ejemplo siguiente se usa el `Function` instrucción para declarar el nombre, parámetros y código que forman el cuerpo de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="db16d-231">El `ParamArray` modificador permite que la función que acepte un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="db16d-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="db16d-232">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db16d-232">Example</span></span>  
 <span data-ttu-id="db16d-233">El ejemplo siguiente invoca la función declarada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="db16d-233">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="db16d-234">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db16d-234">Example</span></span>  
 <span data-ttu-id="db16d-235">En el ejemplo siguiente, `DelayAsync` es un `Async` `Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="db16d-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="db16d-236">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="db16d-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="db16d-237">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="db16d-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="db16d-238">Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero.</span><span class="sxs-lookup"><span data-stu-id="db16d-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="db16d-239">Esto se muestra en esta instrucción: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="db16d-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="db16d-240">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db16d-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="db16d-241">Dado que `DoSomethingAsync` es un `Async` (función), la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="db16d-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="db16d-242">El `startButton_Click` `Sub` procedimiento debe definirse con la `Async` modificador porque tiene un `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="db16d-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="db16d-243">Vea también</span><span class="sxs-lookup"><span data-stu-id="db16d-243">See also</span></span>
- [<span data-ttu-id="db16d-244">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db16d-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="db16d-245">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="db16d-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="db16d-246">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="db16d-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="db16d-247">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db16d-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="db16d-248">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="db16d-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="db16d-249">Of</span><span class="sxs-lookup"><span data-stu-id="db16d-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="db16d-250">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="db16d-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="db16d-251">Cómo: Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="db16d-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="db16d-252">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="db16d-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="db16d-253">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="db16d-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="db16d-254">Expresión de función</span><span class="sxs-lookup"><span data-stu-id="db16d-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
