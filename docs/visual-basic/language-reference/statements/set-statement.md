---
title: "Instrucción Set (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b18e6c858e64e78d7ab85fdaafd70e510f7a02f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="a0b16-102">Instrucción Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0b16-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="a0b16-103">Declara un `Set` procedimiento de propiedad que se usa para asignar un valor a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0b16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0b16-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="a0b16-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="a0b16-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="a0b16-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a0b16-106">Optional.</span></span> <span data-ttu-id="a0b16-107">Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="a0b16-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="a0b16-108">Opcional en al menos uno de los `Get` y `Set` las instrucciones de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="a0b16-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0b16-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="a0b16-110">Protected</span><span class="sxs-lookup"><span data-stu-id="a0b16-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [<span data-ttu-id="a0b16-111">Friend</span><span class="sxs-lookup"><span data-stu-id="a0b16-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [<span data-ttu-id="a0b16-112">Private</span><span class="sxs-lookup"><span data-stu-id="a0b16-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 <span data-ttu-id="a0b16-113">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a0b16-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="a0b16-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a0b16-114">Required.</span></span> <span data-ttu-id="a0b16-115">Parámetro que contiene el nuevo valor para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="a0b16-116">Obligatorio si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="a0b16-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="a0b16-117">Tipo de datos de la `value` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a0b16-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="a0b16-118">El tipo de datos especificado debe ser el mismo que el tipo de datos de la propiedad donde esto `Set` instrucción se declara.</span><span class="sxs-lookup"><span data-stu-id="a0b16-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="a0b16-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a0b16-119">Optional.</span></span> <span data-ttu-id="a0b16-120">Una o más instrucciones que se ejecutan cuando el `Set` se llama al procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="a0b16-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a0b16-121">Required.</span></span> <span data-ttu-id="a0b16-122">Termina la definición de la `Set` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0b16-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0b16-123">Remarks</span></span>  
 <span data-ttu-id="a0b16-124">Cada propiedad debe tener un `Set` procedimiento de propiedad, a menos que la propiedad está marcada como `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="a0b16-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="a0b16-125">El `Set` procedimiento se utiliza para establecer el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="a0b16-126">Visual Basic llama automáticamente a una propiedad `Set` procedimiento cuando una instrucción de asignación proporciona un valor que se almacenará en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="a0b16-127">Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="a0b16-128">Si no especifica ningún parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`.</span><span class="sxs-lookup"><span data-stu-id="a0b16-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="a0b16-129">El parámetro contiene el valor que se asignará a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="a0b16-130">Normalmente almacena este valor en una variable local privada y devolverlo cada vez que la `Get` se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a0b16-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="a0b16-131">El cuerpo de la declaración de propiedad puede contener solo la propiedad `Get` y `Set` procedimientos entre el [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a0b16-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="a0b16-132">No puede almacenar nada distinto de esos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="a0b16-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="a0b16-133">En concreto, no puede almacenar el valor la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="a0b16-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="a0b16-134">Debe almacenar este valor fuera de la propiedad, porque si almacena dentro de cualquiera de los procedimientos de propiedad, el procedimiento de la propiedad no puede acceder a él.</span><span class="sxs-lookup"><span data-stu-id="a0b16-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="a0b16-135">El enfoque habitual consiste en almacenar el valor en un [privada](../../../visual-basic/language-reference/modifiers/private.md) variable declarada en el mismo nivel que la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="a0b16-136">Debe definir un `Set` procedimiento dentro de la propiedad a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="a0b16-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="a0b16-137">El `Set` procedimiento tiene como valor predeterminado para el nivel de acceso de su propiedad que contiene a menos que use `accessmodifier` en el `Set` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a0b16-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a0b16-138">Reglas</span><span class="sxs-lookup"><span data-stu-id="a0b16-138">Rules</span></span>  
  
-   <span data-ttu-id="a0b16-139">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="a0b16-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="a0b16-140">Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="a0b16-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="a0b16-141">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="a0b16-142">Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.</span><span class="sxs-lookup"><span data-stu-id="a0b16-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="a0b16-143">Si va a definir un `WriteOnly` propiedad, el `Set` procedimiento representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="a0b16-144">No se puede declarar un acceso diferente nivel para `Set`, porque se establecerían dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="a0b16-145">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="a0b16-145">Behavior</span></span>  
  
-   <span data-ttu-id="a0b16-146">**Devolver desde un procedimiento de propiedad.**</span><span class="sxs-lookup"><span data-stu-id="a0b16-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="a0b16-147">Cuando el `Set` procedimiento vuelve al código de llamada, la ejecución continúa después de la instrucción que proporciona el valor que se almacenará.</span><span class="sxs-lookup"><span data-stu-id="a0b16-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="a0b16-148">`Set`los procedimientos de propiedad pueden devolver mediante el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) o [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a0b16-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="a0b16-149">El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="a0b16-150">Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Property` y `Return` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="a0b16-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0b16-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0b16-151">Example</span></span>  
 <span data-ttu-id="a0b16-152">En el ejemplo siguiente se usa el `Set` instrucción que se va a establecer el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0b16-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a0b16-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0b16-153">See Also</span></span>  
 [<span data-ttu-id="a0b16-154">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a0b16-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="a0b16-155">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a0b16-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="a0b16-156">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a0b16-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="a0b16-157">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="a0b16-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
