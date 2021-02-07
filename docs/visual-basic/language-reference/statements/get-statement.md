---
description: 'Más información sobre: get (instrucción)'
title: Get (Instrucción)
ms.date: 07/20/2015
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
ms.openlocfilehash: 1cda485867a941129ab2453d4c0900d1403f4e8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769044"
---
# <a name="get-statement"></a><span data-ttu-id="4baf0-103">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="4baf0-103">Get Statement</span></span>

<span data-ttu-id="4baf0-104">Declara un `Get` procedimiento de propiedad que se usa para recuperar el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-104">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4baf0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4baf0-105">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="4baf0-106">Partes</span><span class="sxs-lookup"><span data-stu-id="4baf0-106">Parts</span></span>  
  
|<span data-ttu-id="4baf0-107">Término</span><span class="sxs-lookup"><span data-stu-id="4baf0-107">Term</span></span>|<span data-ttu-id="4baf0-108">Definición</span><span class="sxs-lookup"><span data-stu-id="4baf0-108">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="4baf0-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4baf0-109">Optional.</span></span> <span data-ttu-id="4baf0-110">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4baf0-110">See [Attribute List](attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="4baf0-111">Opcional en, como máximo, una de las `Get` `Set` instrucciones y de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-111">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="4baf0-112">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4baf0-112">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="4baf0-113">-   [Contra](../modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="4baf0-113">-   [Protected](../modifiers/protected.md)</span></span><br /><span data-ttu-id="4baf0-114">-   [Respecto](../modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="4baf0-114">-   [Friend](../modifiers/friend.md)</span></span><br /><span data-ttu-id="4baf0-115">-   [Privada](../modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="4baf0-115">-   [Private](../modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="4baf0-116">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4baf0-116">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="4baf0-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4baf0-117">Optional.</span></span> <span data-ttu-id="4baf0-118">Una o varias instrucciones que se ejecutan cuando `Get` se llama al procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-118">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="4baf0-119">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4baf0-119">Required.</span></span> <span data-ttu-id="4baf0-120">Finaliza la definición del procedimiento de `Get` propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-120">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4baf0-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4baf0-121">Remarks</span></span>  

 <span data-ttu-id="4baf0-122">Cada propiedad debe tener un `Get` procedimiento de propiedad a menos que se marque la propiedad `WriteOnly` .</span><span class="sxs-lookup"><span data-stu-id="4baf0-122">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="4baf0-123">El `Get` procedimiento se utiliza para devolver el valor actual de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-123">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="4baf0-124">Visual Basic llama automáticamente al procedimiento de una propiedad `Get` cuando una expresión solicita el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-124">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="4baf0-125">El cuerpo de la declaración de propiedad solo puede contener los procedimientos y de la propiedad `Get` `Set` entre la [instrucción Property](property-statement.md) y la `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="4baf0-125">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="4baf0-126">No puede almacenar nada que no sea esos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="4baf0-126">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="4baf0-127">En concreto, no puede almacenar el valor actual de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-127">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="4baf0-128">Debe almacenar este valor fuera de la propiedad, porque si lo almacena dentro de cualquiera de los procedimientos de propiedad, el otro procedimiento de propiedad no podrá tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="4baf0-128">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="4baf0-129">El enfoque habitual es almacenar el valor en una variable [privada](../modifiers/private.md) declarada en el mismo nivel que la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-129">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="4baf0-130">Debe definir un `Get` procedimiento dentro de la propiedad a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="4baf0-130">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="4baf0-131">El `Get` procedimiento tiene como valor predeterminado el nivel de acceso de la propiedad que lo contiene a menos que use `accessmodifier` en la `Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="4baf0-131">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4baf0-132">Reglas</span><span class="sxs-lookup"><span data-stu-id="4baf0-132">Rules</span></span>  
  
- <span data-ttu-id="4baf0-133">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="4baf0-133">**Mixed Access Levels.**</span></span> <span data-ttu-id="4baf0-134">Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` procedimiento o `Set` , pero no para ambos.</span><span class="sxs-lookup"><span data-stu-id="4baf0-134">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="4baf0-135">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-135">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="4baf0-136">Por ejemplo, si se declara la propiedad `Friend` , puede declarar el `Get` procedimiento `Private` , pero no `Public` .</span><span class="sxs-lookup"><span data-stu-id="4baf0-136">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="4baf0-137">Si está definiendo una `ReadOnly` propiedad, el `Get` procedimiento representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-137">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="4baf0-138">No se puede declarar un nivel de acceso diferente para `Get` , ya que esto establecería dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-138">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="4baf0-139">**Tipo de valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="4baf0-139">**Return Type.**</span></span> <span data-ttu-id="4baf0-140">La [instrucción Property](property-statement.md) puede declarar el tipo de datos del valor que devuelve.</span><span class="sxs-lookup"><span data-stu-id="4baf0-140">The [Property Statement](property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="4baf0-141">El `Get` procedimiento devuelve automáticamente ese tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="4baf0-141">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="4baf0-142">Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="4baf0-142">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="4baf0-143">Si la `Property` instrucción no especifica `returntype` , el procedimiento devuelve `Object` .</span><span class="sxs-lookup"><span data-stu-id="4baf0-143">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4baf0-144">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="4baf0-144">Behavior</span></span>  
  
- <span data-ttu-id="4baf0-145">**Devolver de un procedimiento.**</span><span class="sxs-lookup"><span data-stu-id="4baf0-145">**Returning from a Procedure.**</span></span> <span data-ttu-id="4baf0-146">Cuando el `Get` procedimiento vuelve al código de llamada, la ejecución continúa dentro de la instrucción que solicitó el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-146">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="4baf0-147">`Get` los procedimientos de propiedad pueden devolver un valor mediante la [instrucción return](return-statement.md) o asignando el valor devuelto al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-147">`Get` property procedures can return a value using either the [Return Statement](return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="4baf0-148">Para obtener más información, vea el tema sobre el valor devuelto en la [instrucción function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4baf0-148">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="4baf0-149">Las `Exit Property` `Return` instrucciones y producen una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="4baf0-150">Cualquier número de `Exit Property` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Property` e `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="4baf0-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="4baf0-151">**Valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="4baf0-151">**Return Value.**</span></span> <span data-ttu-id="4baf0-152">Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de la propiedad o incluirlo en una [instrucción return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4baf0-152">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](return-statement.md).</span></span> <span data-ttu-id="4baf0-153">La `Return` instrucción asigna simultáneamente el `Get` valor devuelto del procedimiento y sale del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4baf0-153">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="4baf0-154">Si utiliza `Exit Property` sin asignar un valor al nombre de la propiedad, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-154">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="4baf0-155">Para obtener más información, vea el tema sobre el valor devuelto en la [instrucción function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4baf0-155">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="4baf0-156">En el ejemplo siguiente se muestran dos maneras en que la propiedad de solo lectura `quoteForTheDay` puede devolver el valor contenido en la variable privada `quoteValue` .</span><span class="sxs-lookup"><span data-stu-id="4baf0-156">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="4baf0-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4baf0-157">Example</span></span>  

 <span data-ttu-id="4baf0-158">En el ejemplo siguiente se usa la `Get` instrucción para devolver el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="4baf0-158">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="4baf0-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="4baf0-159">See also</span></span>

- [<span data-ttu-id="4baf0-160">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4baf0-160">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="4baf0-161">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4baf0-161">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="4baf0-162">Instrucción Exit</span><span class="sxs-lookup"><span data-stu-id="4baf0-162">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="4baf0-163">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="4baf0-163">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="4baf0-164">Tutorial: Definir clases</span><span class="sxs-lookup"><span data-stu-id="4baf0-164">Walkthrough: Defining Classes</span></span>](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
