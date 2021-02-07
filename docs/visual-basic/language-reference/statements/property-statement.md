---
description: 'Más información acerca de: Property (instrucción)'
title: Property Statement
ms.date: 05/12/2018
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
ms.openlocfilehash: 95f2ac1f993fc8698d2033dfe50d925cd55a7dc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741398"
---
# <a name="property-statement"></a><span data-ttu-id="69cc1-103">Property Statement</span><span class="sxs-lookup"><span data-stu-id="69cc1-103">Property Statement</span></span>

<span data-ttu-id="69cc1-104">Declara el nombre de una propiedad y los procedimientos de propiedad que se usan para almacenar y recuperar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-104">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="69cc1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69cc1-105">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="69cc1-106">Partes</span><span class="sxs-lookup"><span data-stu-id="69cc1-106">Parts</span></span>

- `attributelist`

  <span data-ttu-id="69cc1-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-107">Optional.</span></span> <span data-ttu-id="69cc1-108">Lista de atributos que se aplican a esta propiedad o `Get` `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="69cc1-108">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="69cc1-109">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-109">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="69cc1-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-110">Optional.</span></span> <span data-ttu-id="69cc1-111">Especifica que esta propiedad es la propiedad predeterminada de la clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="69cc1-111">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="69cc1-112">Las propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-112">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="69cc1-113">Si declara la propiedad como `Default` , no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-113">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="69cc1-114">Opcional en la `Property` instrucción y en, como máximo, una de las `Get` `Set` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="69cc1-114">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="69cc1-115">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="69cc1-115">Can be one of the following:</span></span>

  - [<span data-ttu-id="69cc1-116">Público</span><span class="sxs-lookup"><span data-stu-id="69cc1-116">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="69cc1-117">Protegido</span><span class="sxs-lookup"><span data-stu-id="69cc1-117">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="69cc1-118">Friend</span><span class="sxs-lookup"><span data-stu-id="69cc1-118">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="69cc1-119">Privado</span><span class="sxs-lookup"><span data-stu-id="69cc1-119">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="69cc1-120">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="69cc1-120">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="69cc1-121">Private Protected</span><span class="sxs-lookup"><span data-stu-id="69cc1-121">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="69cc1-122">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-122">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="69cc1-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-123">Optional.</span></span> <span data-ttu-id="69cc1-124">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="69cc1-124">Can be one of the following:</span></span>

  - [<span data-ttu-id="69cc1-125">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="69cc1-125">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="69cc1-126">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="69cc1-126">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="69cc1-127">Overridable</span><span class="sxs-lookup"><span data-stu-id="69cc1-127">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="69cc1-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="69cc1-128">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="69cc1-129">MustOverride</span><span class="sxs-lookup"><span data-stu-id="69cc1-129">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="69cc1-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-130">Optional.</span></span> <span data-ttu-id="69cc1-131">Vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-131">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="69cc1-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-132">Optional.</span></span> <span data-ttu-id="69cc1-133">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-133">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="69cc1-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-134">Optional.</span></span> <span data-ttu-id="69cc1-135">Vea [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-135">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="69cc1-136">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-136">Optional.</span></span> <span data-ttu-id="69cc1-137">Vea [WriteOnly](../modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-137">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="69cc1-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-138">Optional.</span></span> <span data-ttu-id="69cc1-139">Vea [iterator](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-139">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="69cc1-140">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69cc1-140">Required.</span></span> <span data-ttu-id="69cc1-141">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-141">Name of the property.</span></span> <span data-ttu-id="69cc1-142">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-142">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="69cc1-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-143">Optional.</span></span> <span data-ttu-id="69cc1-144">Lista de nombres de variables locales que representan los parámetros de esta propiedad y posibles parámetros adicionales del `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="69cc1-144">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="69cc1-145">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-145">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="69cc1-146">Obligatorio si `Option Strict` es `On` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-146">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="69cc1-147">Tipo de datos del valor devuelto por esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-147">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="69cc1-148">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-148">Optional.</span></span> <span data-ttu-id="69cc1-149">Indica que esta propiedad implementa una o más propiedades, cada una de las cuales se define en una interfaz implementada por la clase o estructura que contiene esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-149">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="69cc1-150">Vea [Implements (instrucción](implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="69cc1-150">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="69cc1-151">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="69cc1-151">Required if `Implements` is supplied.</span></span> <span data-ttu-id="69cc1-152">Lista de propiedades que se implementan.</span><span class="sxs-lookup"><span data-stu-id="69cc1-152">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="69cc1-153">Cada `implementedproperty` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="69cc1-153">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="69cc1-154">Parte</span><span class="sxs-lookup"><span data-stu-id="69cc1-154">Part</span></span>|<span data-ttu-id="69cc1-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="69cc1-155">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="69cc1-156">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69cc1-156">Required.</span></span> <span data-ttu-id="69cc1-157">Nombre de una interfaz implementada por la clase o estructura que contiene esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-157">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="69cc1-158">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69cc1-158">Required.</span></span> <span data-ttu-id="69cc1-159">Nombre por el que se define la propiedad en `interface` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-159">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="69cc1-160">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-160">Optional.</span></span> <span data-ttu-id="69cc1-161">Es obligatorio si la propiedad está marcada `ReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-161">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="69cc1-162">Inicia un `Get` procedimiento de propiedad que se usa para devolver el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-162">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="69cc1-163">La `Get` instrucción no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-163">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="69cc1-164">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-164">Optional.</span></span> <span data-ttu-id="69cc1-165">Bloque de instrucciones que se ejecutarán dentro del `Get` `Set` procedimiento o.</span><span class="sxs-lookup"><span data-stu-id="69cc1-165">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="69cc1-166">Finaliza el `Get` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-166">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="69cc1-167">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69cc1-167">Optional.</span></span> <span data-ttu-id="69cc1-168">Es obligatorio si la propiedad está marcada `WriteOnly` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-168">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="69cc1-169">Inicia un `Set` procedimiento de propiedad que se usa para almacenar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-169">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="69cc1-170">La `Set` instrucción no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-170">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="69cc1-171">Finaliza el `Set` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-171">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="69cc1-172">Finaliza la definición de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-172">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="69cc1-173">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69cc1-173">Remarks</span></span>

<span data-ttu-id="69cc1-174">La `Property` instrucción presenta la declaración de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-174">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="69cc1-175">Una propiedad puede tener un `Get` procedimiento (solo lectura), un `Set` procedimiento (solo escritura) o ambos (lectura y escritura).</span><span class="sxs-lookup"><span data-stu-id="69cc1-175">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="69cc1-176">Puede omitir el `Get` `Set` procedimiento y cuando use una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="69cc1-176">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="69cc1-177">Para obtener más información, vea [Propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="69cc1-177">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="69cc1-178">Solo se puede usar `Property` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="69cc1-178">You can use `Property` only at class level.</span></span> <span data-ttu-id="69cc1-179">Esto significa que el contexto de la *declaración* de una propiedad debe ser una clase, una estructura, un módulo o una interfaz, y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="69cc1-179">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="69cc1-180">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="69cc1-180">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="69cc1-181">De forma predeterminada, las propiedades usan el acceso público.</span><span class="sxs-lookup"><span data-stu-id="69cc1-181">By default, properties use public access.</span></span> <span data-ttu-id="69cc1-182">Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en la `Property` instrucción y, opcionalmente, puede ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="69cc1-182">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="69cc1-183">Visual Basic pasa un parámetro al `Set` procedimiento durante las asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="69cc1-183">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="69cc1-184">Si no proporciona un parámetro para `Set` , el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-184">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="69cc1-185">Este parámetro contiene el valor que se va a asignar a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-185">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="69cc1-186">Normalmente, este valor se almacena en una variable local privada y se devuelve cada vez que `Get` se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="69cc1-186">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="69cc1-187">Reglas</span><span class="sxs-lookup"><span data-stu-id="69cc1-187">Rules</span></span>

- <span data-ttu-id="69cc1-188">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="69cc1-188">**Mixed Access Levels.**</span></span> <span data-ttu-id="69cc1-189">Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` procedimiento o `Set` , pero no para ambos.</span><span class="sxs-lookup"><span data-stu-id="69cc1-189">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="69cc1-190">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-190">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="69cc1-191">Por ejemplo, si se declara la propiedad `Friend` , puede declarar el `Set` procedimiento `Private` , pero no `Public` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-191">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="69cc1-192">Si está definiendo una `ReadOnly` `WriteOnly` propiedad o, el procedimiento de propiedad única ( `Get` o `Set` , respectivamente) representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-192">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="69cc1-193">No se puede declarar un nivel de acceso diferente para este procedimiento, ya que esto establecería dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-193">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="69cc1-194">**Tipo de valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="69cc1-194">**Return Type.**</span></span> <span data-ttu-id="69cc1-195">La `Property` instrucción puede declarar el tipo de datos del valor que devuelve.</span><span class="sxs-lookup"><span data-stu-id="69cc1-195">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="69cc1-196">Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="69cc1-196">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="69cc1-197">Si no se especifica `returntype` , la propiedad devuelve `Object` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-197">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="69cc1-198">**Aplicación.**</span><span class="sxs-lookup"><span data-stu-id="69cc1-198">**Implementation.**</span></span> <span data-ttu-id="69cc1-199">Si esta propiedad utiliza la `Implements` palabra clave, la clase contenedora o la estructura deben tener una `Implements` instrucción inmediatamente después de su `Class` `Structure` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="69cc1-199">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="69cc1-200">La `Implements` instrucción debe incluir cada interfaz especificada en `implementslist` .</span><span class="sxs-lookup"><span data-stu-id="69cc1-200">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="69cc1-201">Sin embargo, el nombre por el que una interfaz define `Property` (en `definedname` ) no tiene que ser el mismo que el nombre de esta propiedad (en `name` ).</span><span class="sxs-lookup"><span data-stu-id="69cc1-201">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="69cc1-202">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="69cc1-202">Behavior</span></span>

- <span data-ttu-id="69cc1-203">**Devolver desde un procedimiento de propiedad.**</span><span class="sxs-lookup"><span data-stu-id="69cc1-203">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="69cc1-204">Cuando el `Get` `Set` procedimiento o vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.</span><span class="sxs-lookup"><span data-stu-id="69cc1-204">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="69cc1-205">Las `Exit Property` `Return` instrucciones y producen una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-205">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="69cc1-206">Cualquier número de `Exit Property` `Return` instrucciones y puede aparecer en cualquier parte del procedimiento y se pueden mezclar `Exit Property` e `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="69cc1-206">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="69cc1-207">**Valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="69cc1-207">**Return Value.**</span></span> <span data-ttu-id="69cc1-208">Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de la propiedad o incluirlo en una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="69cc1-208">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="69cc1-209">En el ejemplo siguiente se asigna el valor devuelto al nombre de la propiedad `quoteForTheDay` y, a continuación, se usa la `Exit Property` instrucción para devolver.</span><span class="sxs-lookup"><span data-stu-id="69cc1-209">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="69cc1-210">Si usa `Exit Property` sin asignar un valor a `name` , el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="69cc1-210">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="69cc1-211">La `Return` instrucción al mismo tiempo asigna el `Get` valor devuelto del procedimiento y sale del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="69cc1-211">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="69cc1-212">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="69cc1-212">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="69cc1-213">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69cc1-213">Example</span></span>

<span data-ttu-id="69cc1-214">En el ejemplo siguiente se declara una propiedad en una clase.</span><span class="sxs-lookup"><span data-stu-id="69cc1-214">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="69cc1-215">Vea también</span><span class="sxs-lookup"><span data-stu-id="69cc1-215">See also</span></span>

- [<span data-ttu-id="69cc1-216">Propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="69cc1-216">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="69cc1-217">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="69cc1-217">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="69cc1-218">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="69cc1-218">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="69cc1-219">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="69cc1-219">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="69cc1-220">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="69cc1-220">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="69cc1-221">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="69cc1-221">Default</span></span>](../modifiers/default.md)
