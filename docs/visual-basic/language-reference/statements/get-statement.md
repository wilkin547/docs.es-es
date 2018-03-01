---
title: "Get (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1ff062a5e3bf41794bd5b4c90f1e188d6d97480
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="get-statement"></a><span data-ttu-id="3cbd3-102">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-102">Get Statement</span></span>
<span data-ttu-id="3cbd3-103">Declara un `Get` procedimiento de propiedad que se usa para recuperar el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbd3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cbd3-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="3cbd3-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="3cbd3-105">Parts</span></span>  
  
|<span data-ttu-id="3cbd3-106">Término</span><span class="sxs-lookup"><span data-stu-id="3cbd3-106">Term</span></span>|<span data-ttu-id="3cbd3-107">Definición</span><span class="sxs-lookup"><span data-stu-id="3cbd3-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="3cbd3-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-108">Optional.</span></span> <span data-ttu-id="3cbd3-109">Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd3-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="3cbd3-110">Opcional en al menos uno de los `Get` y `Set` las instrucciones de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="3cbd3-111">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cbd3-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="3cbd3-112">-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-112">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="3cbd3-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="3cbd3-114">-   [Privada](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-114">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="3cbd3-115">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd3-115">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="3cbd3-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-116">Optional.</span></span> <span data-ttu-id="3cbd3-117">Una o más instrucciones que se ejecutan cuando el `Get` se llama al procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="3cbd3-118">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-118">Required.</span></span> <span data-ttu-id="3cbd3-119">Termina la definición de la `Get` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cbd3-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cbd3-120">Remarks</span></span>  
 <span data-ttu-id="3cbd3-121">Cada propiedad debe tener un `Get` procedimiento de propiedad, a menos que la propiedad está marcada como `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="3cbd3-122">El `Get` procedimiento se utiliza para devolver el valor actual de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="3cbd3-123">Visual Basic llama automáticamente a una propiedad `Get` procedimiento cuando una expresión solicita el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="3cbd3-124">El cuerpo de la declaración de propiedad puede contener solo la propiedad `Get` y `Set` procedimientos entre el [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="3cbd3-125">No puede almacenar nada distinto de esos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="3cbd3-126">En concreto, no puede almacenar el valor la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="3cbd3-127">Debe almacenar este valor fuera de la propiedad, porque si almacena dentro de cualquiera de los procedimientos de propiedad, el procedimiento de la propiedad no puede acceder a él.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="3cbd3-128">El enfoque habitual consiste en almacenar el valor en un [privada](../../../visual-basic/language-reference/modifiers/private.md) variable declarada en el mismo nivel que la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-128">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="3cbd3-129">Debe definir un `Get` procedimiento dentro de la propiedad a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="3cbd3-130">El `Get` procedimiento tiene como valor predeterminado para el nivel de acceso de su propiedad que contiene a menos que use `accessmodifier` en el `Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="3cbd3-131">Reglas</span><span class="sxs-lookup"><span data-stu-id="3cbd3-131">Rules</span></span>  
  
-   <span data-ttu-id="3cbd3-132">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="3cbd3-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="3cbd3-133">Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="3cbd3-134">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="3cbd3-135">Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Get` procedimiento `Private`, pero no `Public`.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="3cbd3-136">Si va a definir un `ReadOnly` propiedad, el `Get` procedimiento representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="3cbd3-137">No se puede declarar un acceso diferente nivel para `Get`, porque se establecerían dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="3cbd3-138">**Tipo de valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="3cbd3-138">**Return Type.**</span></span> <span data-ttu-id="3cbd3-139">El [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md) puede declarar el tipo de datos del valor que devuelve.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-139">The [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="3cbd3-140">El `Get` procedimiento devuelve automáticamente ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="3cbd3-141">Puede especificar cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="3cbd3-142">Si el `Property` instrucción no especifica `returntype`, el procedimiento devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3cbd3-143">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="3cbd3-143">Behavior</span></span>  
  
-   <span data-ttu-id="3cbd3-144">**Devolver desde un procedimiento.**</span><span class="sxs-lookup"><span data-stu-id="3cbd3-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="3cbd3-145">Cuando el `Get` procedimiento vuelve al código de llamada, la ejecución continúa en la instrucción que solicita el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="3cbd3-146">`Get`procedimientos de propiedad pueden devolver un valor mediante la [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) o asignando el valor devuelto al nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-146">`Get` property procedures can return a value using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="3cbd3-147">Para obtener más información, vea "Valor devuelto" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd3-147">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="3cbd3-148">El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="3cbd3-149">Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Property` y `Return` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="3cbd3-150">**Valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="3cbd3-150">**Return Value.**</span></span> <span data-ttu-id="3cbd3-151">Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de propiedad o incluirlo en una [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd3-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span> <span data-ttu-id="3cbd3-152">El `Return` instrucción asigna simultáneamente el `Get` procedimiento devolver valor y sale del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="3cbd3-153">Si usa `Exit Property` sin asignar un valor al nombre de propiedad, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="3cbd3-154">Para obtener más información, vea "Valor devuelto" en [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd3-154">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="3cbd3-155">El ejemplo siguiente muestra dos formas de la propiedad de solo lectura `quoteForTheDay` puede devolver el valor contenido en la variable privada `quoteValue`.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="3cbd3-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cbd3-156">Example</span></span>  
 <span data-ttu-id="3cbd3-157">En el ejemplo siguiente se usa el `Get` instrucción para devolver el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="3cbd3-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3cbd3-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cbd3-158">See Also</span></span>  
 [<span data-ttu-id="3cbd3-159">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-159">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="3cbd3-160">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-160">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="3cbd3-161">Exit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3cbd3-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="3cbd3-162">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="3cbd3-162">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="3cbd3-163">Tutorial: Definir clases</span><span class="sxs-lookup"><span data-stu-id="3cbd3-163">Walkthrough: Defining Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
