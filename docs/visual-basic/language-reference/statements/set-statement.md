---
title: Instrucción Set (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: fb51dfbae4d9c4ef205e67ac15c5027e62a9a938
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663195"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="ad3a6-102">Instrucción Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad3a6-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="ad3a6-103">Declara un `Set` procedimiento de propiedad que se utiliza para asignar un valor a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad3a6-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="ad3a6-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ad3a6-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="ad3a6-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-106">Optional.</span></span> <span data-ttu-id="ad3a6-107">Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="ad3a6-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="ad3a6-108">Opcional en al menos uno de los `Get` y `Set` instrucciones de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="ad3a6-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad3a6-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="ad3a6-110">Protected</span><span class="sxs-lookup"><span data-stu-id="ad3a6-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="ad3a6-111">Friend</span><span class="sxs-lookup"><span data-stu-id="ad3a6-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="ad3a6-112">Private</span><span class="sxs-lookup"><span data-stu-id="ad3a6-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="ad3a6-113">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ad3a6-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="ad3a6-114">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-114">Required.</span></span> <span data-ttu-id="ad3a6-115">Parámetro que contiene el nuevo valor para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="ad3a6-116">Es necesario si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="ad3a6-117">Tipo de datos de la `value` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="ad3a6-118">El tipo de datos especificado debe ser el mismo que el tipo de datos de la propiedad donde esto `Set` se declara la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="ad3a6-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-119">Optional.</span></span> <span data-ttu-id="ad3a6-120">Una o varias instrucciones que se ejecutan cuando el `Set` se llama al procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="ad3a6-121">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-121">Required.</span></span> <span data-ttu-id="ad3a6-122">Termina la definición de la `Set` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad3a6-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad3a6-123">Remarks</span></span>  
 <span data-ttu-id="ad3a6-124">Cada propiedad debe tener un `Set` procedimiento de propiedad, a menos que la propiedad se marca `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="ad3a6-125">El `Set` procedimiento se usa para establecer el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="ad3a6-126">Visual Basic llama automáticamente una propiedad `Set` procedimiento cuando una instrucción de asignación proporciona un valor que se almacenará en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="ad3a6-127">Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="ad3a6-128">Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="ad3a6-129">El parámetro contiene el valor que se asignará a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="ad3a6-130">Se suele almacenar este valor en una variable local privada y devolverlo cada vez que el `Get` se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="ad3a6-131">El cuerpo de la declaración de propiedad puede contener sólo la propiedad `Get` y `Set` procedimientos entre el [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="ad3a6-132">No puede almacenar algo distinto de esos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="ad3a6-133">En concreto, no puede almacenar el valor actual de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="ad3a6-134">Debe almacenar este valor fuera de la propiedad, porque si lo guarda dentro de cualquiera de los procedimientos de propiedad, el procedimiento de la propiedad no puede acceder a él.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="ad3a6-135">El enfoque habitual consiste en almacenar el valor en un [privada](../../../visual-basic/language-reference/modifiers/private.md) variable declarada en el mismo nivel que la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="ad3a6-136">Debe definir un `Set` procedimiento dentro de la propiedad a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="ad3a6-137">El `Set` procedimiento tiene como valor predeterminado para el nivel de acceso de su propiedad contenedora a menos que use `accessmodifier` en el `Set` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ad3a6-138">Reglas</span><span class="sxs-lookup"><span data-stu-id="ad3a6-138">Rules</span></span>  
  
- <span data-ttu-id="ad3a6-139">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="ad3a6-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="ad3a6-140">Si va a definir una propiedad de lectura y escritura, opcionalmente, puede especificar un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="ad3a6-141">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="ad3a6-142">Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="ad3a6-143">Si está definiendo un `WriteOnly` propiedad, el `Set` procedimiento representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="ad3a6-144">No se puede declarar un acceso diferente nivel `Set`, ya que establecería dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="ad3a6-145">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="ad3a6-145">Behavior</span></span>  
  
- <span data-ttu-id="ad3a6-146">**Devolución desde un procedimiento de propiedad.**</span><span class="sxs-lookup"><span data-stu-id="ad3a6-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="ad3a6-147">Cuando el `Set` procedimiento vuelve al código de llamada, la ejecución continúa después de la instrucción que proporciona el valor que se almacenará.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="ad3a6-148">`Set` procedimientos de propiedad pueden devolver mediante el [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md) o [instrucción Exit](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ad3a6-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="ad3a6-149">El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="ad3a6-150">Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento, y puede mezclar `Exit Property` y `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad3a6-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad3a6-151">Example</span></span>  
 <span data-ttu-id="ad3a6-152">En el ejemplo siguiente se usa el `Set` instrucción para establecer el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ad3a6-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="ad3a6-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad3a6-153">See also</span></span>

- [<span data-ttu-id="ad3a6-154">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ad3a6-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="ad3a6-155">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ad3a6-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="ad3a6-156">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ad3a6-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="ad3a6-157">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="ad3a6-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
