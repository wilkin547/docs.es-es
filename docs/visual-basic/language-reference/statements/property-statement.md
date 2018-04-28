---
title: Property Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 558b62dd8c676532355ef12134ad8cb803b70796
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="property-statement"></a><span data-ttu-id="1c8d6-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1c8d6-102">Property Statement</span></span>
<span data-ttu-id="1c8d6-103">Declara el nombre de una propiedad y los procedimientos de propiedad que se utiliza para almacenar y recuperar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c8d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c8d6-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="1c8d6-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1c8d6-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="1c8d6-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-106">Optional.</span></span> <span data-ttu-id="1c8d6-107">Lista de atributos que se aplican a esta propiedad o `Get` o `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="1c8d6-108">Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="1c8d6-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-109">Optional.</span></span> <span data-ttu-id="1c8d6-110">Especifica que esta propiedad es la propiedad predeterminada para la clase o estructura en el que está definido.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="1c8d6-111">Propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="1c8d6-112">Si se declara la propiedad como `Default`, no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="1c8d6-113">Opcional en la `Property` instrucción y en al menos uno de los `Get` y `Set` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="1c8d6-114">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c8d6-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="1c8d6-115">Public</span><span class="sxs-lookup"><span data-stu-id="1c8d6-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="1c8d6-116">Protected</span><span class="sxs-lookup"><span data-stu-id="1c8d6-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="1c8d6-117">Friend</span><span class="sxs-lookup"><span data-stu-id="1c8d6-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="1c8d6-118">Private</span><span class="sxs-lookup"><span data-stu-id="1c8d6-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="1c8d6-119">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="1c8d6-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-120">Optional.</span></span> <span data-ttu-id="1c8d6-121">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c8d6-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="1c8d6-122">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="1c8d6-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="1c8d6-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="1c8d6-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="1c8d6-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="1c8d6-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="1c8d6-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="1c8d6-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="1c8d6-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="1c8d6-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="1c8d6-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-127">Optional.</span></span> <span data-ttu-id="1c8d6-128">Vea [compartido](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="1c8d6-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-129">Optional.</span></span> <span data-ttu-id="1c8d6-130">Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="1c8d6-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-131">Optional.</span></span> <span data-ttu-id="1c8d6-132">Vea [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="1c8d6-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-133">Optional.</span></span> <span data-ttu-id="1c8d6-134">Vea [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="1c8d6-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-135">Optional.</span></span> <span data-ttu-id="1c8d6-136">Vea [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="1c8d6-137">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-137">Required.</span></span> <span data-ttu-id="1c8d6-138">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-138">Name of the property.</span></span> <span data-ttu-id="1c8d6-139">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="1c8d6-140">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-140">Optional.</span></span> <span data-ttu-id="1c8d6-141">Lista de nombres de variable locales que representa los parámetros de esta propiedad y posibles parámetros adicionales de la `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="1c8d6-142">Vea [lista de parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="1c8d6-143">Obligatorio si `Option``Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="1c8d6-144">Tipo de datos del valor devuelto por esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="1c8d6-145">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-145">Optional.</span></span> <span data-ttu-id="1c8d6-146">Indica que esta propiedad implementa una o varias propiedades, cada uno definido en una interfaz implementada por la clase o estructura contenedora de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="1c8d6-147">Vea [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="1c8d6-148">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="1c8d6-149">Lista de propiedades que se están implementando.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="1c8d6-150">Cada `implementedproperty` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c8d6-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="1c8d6-151">Parte</span><span class="sxs-lookup"><span data-stu-id="1c8d6-151">Part</span></span>|<span data-ttu-id="1c8d6-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c8d6-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="1c8d6-153">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-153">Required.</span></span> <span data-ttu-id="1c8d6-154">Nombre de una interfaz implementada por esta propiedad contenedora de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="1c8d6-155">Requerido.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-155">Required.</span></span> <span data-ttu-id="1c8d6-156">Nombre por el que se define la propiedad en `interface`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="1c8d6-157">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-157">Optional.</span></span> <span data-ttu-id="1c8d6-158">Necesario si la propiedad está marcada `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="1c8d6-159">Inicia un `Get` procedimiento de propiedad que se usa para devolver el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="1c8d6-160">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-160">Optional.</span></span> <span data-ttu-id="1c8d6-161">Bloque de instrucciones que se ejecutan dentro de la `Get` o `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="1c8d6-162">Finaliza el `Get` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="1c8d6-163">Opcional.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-163">Optional.</span></span> <span data-ttu-id="1c8d6-164">Necesario si la propiedad está marcada `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="1c8d6-165">Inicia un `Set` procedimiento de propiedad que se utiliza para almacenar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="1c8d6-166">Finaliza el `Set` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="1c8d6-167">Termina la definición de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c8d6-168">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c8d6-168">Remarks</span></span>  
 <span data-ttu-id="1c8d6-169">El `Property` instrucción introduce la declaración de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="1c8d6-170">Una propiedad puede tener un `Get` procedimiento (solo lectura), un `Set` procedimiento (de solo escritura) o ambas (de lectura y escritura).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="1c8d6-171">Puede omitir el `Get` y `Set` procedimiento cuando se usa una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="1c8d6-172">Para obtener más información, vea [Propiedades implementadas automáticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="1c8d6-173">Puede usar `Property` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="1c8d6-174">Esto significa que la *contexto de la declaración* para una propiedad debe ser una clase, estructura, módulo o interfaz y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="1c8d6-175">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="1c8d6-176">De forma predeterminada, propiedades usan acceso público.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-176">By default, properties use public access.</span></span> <span data-ttu-id="1c8d6-177">Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en la `Property` instrucción y, opcionalmente, puede ajustar uno de los procedimientos de propiedad para un nivel de acceso más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="1c8d6-178">Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="1c8d6-179">Si no especifica ningún parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="1c8d6-180">Este parámetro contiene el valor que se asignará a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="1c8d6-181">Normalmente almacena este valor en una variable local privada y devolverlo cada vez que la `Get` se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1c8d6-182">Reglas</span><span class="sxs-lookup"><span data-stu-id="1c8d6-182">Rules</span></span>  
  
-   <span data-ttu-id="1c8d6-183">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="1c8d6-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="1c8d6-184">Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="1c8d6-185">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="1c8d6-186">Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="1c8d6-187">Si va a definir un `ReadOnly` o `WriteOnly` propiedad, el procedimiento de propiedad único (`Get` o `Set`, respectivamente) representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="1c8d6-188">No se puede declarar un nivel de acceso diferente para este tipo de procedimiento, porque se establecerían dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="1c8d6-189">**Tipo de valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="1c8d6-189">**Return Type.**</span></span> <span data-ttu-id="1c8d6-190">El `Property` instrucción puede declarar el tipo de datos del valor que devuelve.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="1c8d6-191">Puede especificar cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="1c8d6-192">Si no se especifica `returntype`, la propiedad devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="1c8d6-193">**Implementación de.**</span><span class="sxs-lookup"><span data-stu-id="1c8d6-193">**Implementation.**</span></span> <span data-ttu-id="1c8d6-194">Si esta propiedad utiliza la `Implements` (palabra clave), la clase o estructura contenedora debe tener un `Implements` instrucción inmediatamente posterior a su `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="1c8d6-195">El `Implements` instrucción debe incluir cada interfaz especificada en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="1c8d6-196">Sin embargo, el nombre por el que una interfaz que define el `Property` (en `definedname`) no tiene que ser el mismo que el nombre de esta propiedad (en `name`).</span><span class="sxs-lookup"><span data-stu-id="1c8d6-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="1c8d6-197">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="1c8d6-197">Behavior</span></span>  
  
-   <span data-ttu-id="1c8d6-198">**Devolver desde un procedimiento de propiedad.**</span><span class="sxs-lookup"><span data-stu-id="1c8d6-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="1c8d6-199">Cuando el `Get` o `Set` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="1c8d6-200">El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="1c8d6-201">Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento y se pueden mezclar `Exit Property` y `Return` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="1c8d6-202">**Valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="1c8d6-202">**Return Value.**</span></span> <span data-ttu-id="1c8d6-203">Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de propiedad o incluirlo en una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="1c8d6-204">En el ejemplo siguiente se asigna el valor devuelto al nombre de propiedad `quoteForTheDay` y, a continuación, usa el `Exit Property` instrucción que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="1c8d6-205">Si usa `Exit Property` sin asignar un valor a `name`, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-205">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="1c8d6-206">El `Return` instrucción al mismo tiempo asigna el `Get` procedimiento devolver valor y sale del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-206">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="1c8d6-207">En el ejemplo siguiente se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-207">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="1c8d6-208">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c8d6-208">Example</span></span>  
 <span data-ttu-id="1c8d6-209">En el ejemplo siguiente se declara una propiedad en una clase.</span><span class="sxs-lookup"><span data-stu-id="1c8d6-209">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1c8d6-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c8d6-210">See Also</span></span>  
 [<span data-ttu-id="1c8d6-211">Propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="1c8d6-211">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="1c8d6-212">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="1c8d6-212">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="1c8d6-213">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1c8d6-213">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="1c8d6-214">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1c8d6-214">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="1c8d6-215">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="1c8d6-215">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="1c8d6-216">Predetermiado</span><span class="sxs-lookup"><span data-stu-id="1c8d6-216">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
