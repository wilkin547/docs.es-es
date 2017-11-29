---
title: "Sub (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Sub
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
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02ba9a999db20abce2106269522c9a3221a00cef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="eb955-102">Sub (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb955-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="eb955-103">Declara el nombre, parámetros y código que definen un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb955-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb955-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="eb955-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="eb955-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="eb955-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-106">Optional.</span></span> <span data-ttu-id="eb955-107">Vea [lista de los atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="eb955-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-108">Optional.</span></span> <span data-ttu-id="eb955-109">Indica la definición de un método parcial.</span><span class="sxs-lookup"><span data-stu-id="eb955-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="eb955-110">Vea [métodos parciales](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="eb955-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-111">Optional.</span></span> <span data-ttu-id="eb955-112">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="eb955-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="eb955-113">Public</span><span class="sxs-lookup"><span data-stu-id="eb955-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="eb955-114">Protected</span><span class="sxs-lookup"><span data-stu-id="eb955-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="eb955-115">Friend</span><span class="sxs-lookup"><span data-stu-id="eb955-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="eb955-116">Private</span><span class="sxs-lookup"><span data-stu-id="eb955-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="eb955-117">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-117">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="eb955-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-118">Optional.</span></span> <span data-ttu-id="eb955-119">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="eb955-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="eb955-120">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="eb955-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="eb955-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="eb955-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="eb955-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="eb955-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="eb955-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="eb955-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="eb955-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="eb955-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="eb955-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-125">Optional.</span></span> <span data-ttu-id="eb955-126">Vea [compartido](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="eb955-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-127">Optional.</span></span> <span data-ttu-id="eb955-128">Vea [sombras](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="eb955-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-129">Optional.</span></span> <span data-ttu-id="eb955-130">Vea [Async](../modifiers/async.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="eb955-131">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb955-131">Required.</span></span> <span data-ttu-id="eb955-132">Nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-132">Name of the procedure.</span></span> <span data-ttu-id="eb955-133">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="eb955-134">Para crear un procedimiento de constructor para una clase, establezca el nombre de un `Sub` procedimiento para la `New` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="eb955-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="eb955-135">Para obtener más información, consulte [duración de los objetos: cómo los objetos son crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="eb955-136">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-136">Optional.</span></span> <span data-ttu-id="eb955-137">Lista de parámetros de tipo para un procedimiento genérico.</span><span class="sxs-lookup"><span data-stu-id="eb955-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="eb955-138">Vea [escriba lista](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="eb955-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-139">Optional.</span></span> <span data-ttu-id="eb955-140">Lista de nombres de variables locales que representan los parámetros de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="eb955-141">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="eb955-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-142">Optional.</span></span> <span data-ttu-id="eb955-143">Indica que este procedimiento implementa uno o varios `Sub` procedimientos, cada uno definido en una interfaz implementada por la clase o estructura contenedora de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="eb955-144">Vea [implementa instrucción](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="eb955-145">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="eb955-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="eb955-146">Lista de procedimientos `Sub` que se implementan.</span><span class="sxs-lookup"><span data-stu-id="eb955-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="eb955-147">Cada `implementedprocedure` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="eb955-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="eb955-148">Parte</span><span class="sxs-lookup"><span data-stu-id="eb955-148">Part</span></span>|<span data-ttu-id="eb955-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb955-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="eb955-150">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb955-150">Required.</span></span> <span data-ttu-id="eb955-151">Nombre de una interfaz implementada por este procedimiento contenedora de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="eb955-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="eb955-152">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb955-152">Required.</span></span> <span data-ttu-id="eb955-153">Nombre por el que se define el procedimiento en `interface`.</span><span class="sxs-lookup"><span data-stu-id="eb955-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="eb955-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-154">Optional.</span></span> <span data-ttu-id="eb955-155">Indica que este procedimiento puede controlar uno o más eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="eb955-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="eb955-156">Vea [controla](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="eb955-157">Es necesario si se proporciona `Handles`.</span><span class="sxs-lookup"><span data-stu-id="eb955-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="eb955-158">Lista de eventos que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="eb955-159">Cada `eventspecifier` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="eb955-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="eb955-160">Parte</span><span class="sxs-lookup"><span data-stu-id="eb955-160">Part</span></span>|<span data-ttu-id="eb955-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb955-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="eb955-162">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb955-162">Required.</span></span> <span data-ttu-id="eb955-163">Variable de objeto declarada con el tipo de datos de la clase o estructura que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="eb955-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="eb955-164">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="eb955-164">Required.</span></span> <span data-ttu-id="eb955-165">Nombre del evento que controla este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="eb955-166">Opcional.</span><span class="sxs-lookup"><span data-stu-id="eb955-166">Optional.</span></span> <span data-ttu-id="eb955-167">Bloque de instrucciones que se ejecutan dentro de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="eb955-168">Termina la definición de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb955-169">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb955-169">Remarks</span></span>  
 <span data-ttu-id="eb955-170">Todo el código ejecutable debe estar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="eb955-171">Use un `Sub` procedimiento si no desea devolver un valor para el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="eb955-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="eb955-172">Use un `Function` procedimiento cuando desee devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="eb955-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="eb955-173">Definir un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="eb955-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="eb955-174">Puede definir un `Sub` procedimiento sólo en el nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="eb955-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="eb955-175">El contexto de la declaración de un procedimiento sub por lo tanto, debe ser una clase, una estructura, un módulo o una interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="eb955-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="eb955-176">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="eb955-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="eb955-177">`Sub`procedimientos como valor predeterminado para el acceso público.</span><span class="sxs-lookup"><span data-stu-id="eb955-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="eb955-178">Puede ajustar los niveles de acceso mediante los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="eb955-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="eb955-179">Si el procedimiento utiliza el `Implements` (palabra clave), la clase o estructura contenedora debe tener un `Implements` instrucción que sigue inmediatamente a su `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="eb955-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="eb955-180">El `Implements` instrucción debe incluir cada interfaz que se especifica en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="eb955-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="eb955-181">Sin embargo, el nombre por el que una interfaz que define el `Sub` (en `definedname`) no tiene que coincidir con el nombre de este procedimiento (en `name`).</span><span class="sxs-lookup"><span data-stu-id="eb955-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="eb955-182">Devolver desde un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="eb955-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="eb955-183">Cuando un `Sub` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción después de la instrucción que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="eb955-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="eb955-184">En el ejemplo siguiente se muestra una devolución de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="eb955-185">El `Exit Sub` y `Return` instrucciones provocan una salida inmediata de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="eb955-186">Cualquier número de `Exit Sub` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Sub` y `Return` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="eb955-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="eb955-187">Llamar a un procedimiento Sub</span><span class="sxs-lookup"><span data-stu-id="eb955-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="eb955-188">Se llama a un `Sub` procedimiento mediante el nombre del procedimiento en una instrucción y, a continuación, siga ese nombre con su lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="eb955-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="eb955-189">Puede omitir los paréntesis solo si no facilita ningún argumento.</span><span class="sxs-lookup"><span data-stu-id="eb955-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="eb955-190">Sin embargo, el código es más legible si siempre incluye los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="eb955-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="eb955-191">A `Sub` procedimiento y un `Function` procedimiento puede tener parámetros y llevar a cabo una serie de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="eb955-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="eb955-192">Sin embargo, un `Function` procedimiento devuelve un valor y un `Sub` no de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="eb955-193">Por lo tanto, no puede usar un `Sub` procedimiento en una expresión.</span><span class="sxs-lookup"><span data-stu-id="eb955-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="eb955-194">Puede usar el `Call` palabra clave cuando se llama a un `Sub` procedimiento, pero esa palabra clave no se recomienda para la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="eb955-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="eb955-195">Para obtener más información, consulte [instrucción Call](call-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="eb955-196">Visual Basic reorganiza a veces las expresiones aritméticas para aumentar la eficacia interna.</span><span class="sxs-lookup"><span data-stu-id="eb955-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="eb955-197">Por esta razón, si la lista de argumentos incluye expresiones que llaman a otros procedimientos, no debe asumir que las expresiones se llamará en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="eb955-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="eb955-198">Async Sub (procedimientos)</span><span class="sxs-lookup"><span data-stu-id="eb955-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="eb955-199">Mediante el uso de la característica Async, se pueden invocar funciones asincrónicas sin usar devoluciones de llamada explícitas ni dividir manualmente el código en varias funciones o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="eb955-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="eb955-200">Si marca un procedimiento con el [Async](../modifiers/async.md) modificador, puede usar el [Await](../../../visual-basic/language-reference/operators/await-operator.md) operador en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="eb955-201">Cuando el control alcanza un `Await` expresión en el `Async` procedimiento, el control vuelve al llamador y el progreso en el procedimiento se suspende hasta que se complete la tarea esperada.</span><span class="sxs-lookup"><span data-stu-id="eb955-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="eb955-202">Una vez completada la tarea, la ejecución puede reanudarse en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb955-203">Un `Async` procedimiento vuelve al llamador cuando se encuentra ya sea el primer objeto esperado que aún no se ha completado o el final de la `Async` se alcanza el procedimiento, lo que ocurra primero.</span><span class="sxs-lookup"><span data-stu-id="eb955-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="eb955-204">También puede marcar un [Function (instrucción)](function-statement.md) con el `Async` modificador.</span><span class="sxs-lookup"><span data-stu-id="eb955-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="eb955-205">Un `Async` función puede tener un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601> o <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="eb955-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="eb955-206">Un ejemplo más adelante en este tema se muestra un `Async` función que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="eb955-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="eb955-207">`Async``Sub` procedimientos se utilizan principalmente para controladores de eventos, donde no se puede devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="eb955-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="eb955-208">Un `Async``Sub` procedimiento no se puede esperar y el llamador de un `Async``Sub` procedimiento no puede detectar las excepciones que el `Sub` procedimiento produce.</span><span class="sxs-lookup"><span data-stu-id="eb955-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="eb955-209">Un `Async` procedimiento no puede declarar ningún [ByRef](../modifiers/byref.md) parámetros.</span><span class="sxs-lookup"><span data-stu-id="eb955-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="eb955-210">Para obtener más información acerca de `Async` procedimientos, consulte [programación asincrónica con Async y Await](../../../visual-basic/programming-guide/concepts/async/index.md), [flujo de Control en programas Async](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), y [tipos de valor devueltos de Async](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="eb955-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb955-211">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb955-211">Example</span></span>  
 <span data-ttu-id="eb955-212">En el ejemplo siguiente se usa el `Sub` instrucción para definir el nombre, parámetros y código que forman el cuerpo de un `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="eb955-213">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb955-213">Example</span></span>  
 <span data-ttu-id="eb955-214">En el ejemplo siguiente, `DelayAsync` es un una `Async``Function` que tiene un tipo de valor devuelto de <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="eb955-214">In the following example, `DelayAsync` is an an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="eb955-215">`DelayAsync` tiene una instrucción `Return` que devuelve un entero.</span><span class="sxs-lookup"><span data-stu-id="eb955-215">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="eb955-216">Por lo tanto, la declaración de función de `DelayAsync` debe tener un tipo de valor devuelto de `Task(Of Integer)`.</span><span class="sxs-lookup"><span data-stu-id="eb955-216">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="eb955-217">Dado que el tipo de valor devuelto es `Task(Of Integer)`, la evaluación de la `Await` expresión en `DoSomethingAsync` genera un entero, como se muestra en la siguiente instrucción: `Dim result As Integer = Await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="eb955-217">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="eb955-218">El `startButton_Click` procedimiento es un ejemplo de un `Async Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="eb955-218">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="eb955-219">Dado que `DoSomethingAsync` es un `Async` función, la tarea de la llamada a `DoSomethingAsync` debe esperar, como se muestra en la siguiente instrucción: `Await DoSomethingAsync()`.</span><span class="sxs-lookup"><span data-stu-id="eb955-219">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="eb955-220">El `startButton_Click``Sub` procedimiento debe definirse con el `Async` modificador porque tiene un `Await` expresión.</span><span class="sxs-lookup"><span data-stu-id="eb955-220">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="eb955-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb955-221">See Also</span></span>  
 [<span data-ttu-id="eb955-222">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="eb955-222">Implements Statement</span></span>](implements-statement.md)  
 [<span data-ttu-id="eb955-223">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="eb955-223">Function Statement</span></span>](function-statement.md)  
 [<span data-ttu-id="eb955-224">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="eb955-224">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="eb955-225">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="eb955-225">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="eb955-226">Call (instrucción)</span><span class="sxs-lookup"><span data-stu-id="eb955-226">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="eb955-227">Of</span><span class="sxs-lookup"><span data-stu-id="eb955-227">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="eb955-228">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="eb955-228">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="eb955-229">Utilizar una clase genérica</span><span class="sxs-lookup"><span data-stu-id="eb955-229">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="eb955-230">Solución de problemas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="eb955-230">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="eb955-231">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="eb955-231">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
