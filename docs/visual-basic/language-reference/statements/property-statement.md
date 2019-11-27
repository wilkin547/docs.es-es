---
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
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346756"
---
# <a name="property-statement"></a><span data-ttu-id="4489e-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4489e-102">Property Statement</span></span>

<span data-ttu-id="4489e-103">Declara el nombre de una propiedad y los procedimientos de propiedad que se usan para almacenar y recuperar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="4489e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4489e-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="4489e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="4489e-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="4489e-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-106">Optional.</span></span> <span data-ttu-id="4489e-107">Lista de atributos que se aplican a esta propiedad o `Get` o `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4489e-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="4489e-108">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="4489e-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-109">Optional.</span></span> <span data-ttu-id="4489e-110">Especifica que esta propiedad es la propiedad predeterminada de la clase o estructura en la que se define.</span><span class="sxs-lookup"><span data-stu-id="4489e-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="4489e-111">Las propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="4489e-112">Si declara la propiedad como `Default`, no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="4489e-113">Opcional en la instrucción `Property` y en, como máximo, una de las instrucciones `Get` y `Set`.</span><span class="sxs-lookup"><span data-stu-id="4489e-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="4489e-114">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4489e-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="4489e-115">Public</span><span class="sxs-lookup"><span data-stu-id="4489e-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="4489e-116">Protected</span><span class="sxs-lookup"><span data-stu-id="4489e-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="4489e-117">Friend</span><span class="sxs-lookup"><span data-stu-id="4489e-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="4489e-118">Private</span><span class="sxs-lookup"><span data-stu-id="4489e-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="4489e-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="4489e-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="4489e-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="4489e-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="4489e-121">Vea [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="4489e-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-122">Optional.</span></span> <span data-ttu-id="4489e-123">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4489e-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="4489e-124">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="4489e-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="4489e-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="4489e-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="4489e-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="4489e-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="4489e-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4489e-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="4489e-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4489e-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="4489e-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-129">Optional.</span></span> <span data-ttu-id="4489e-130">Vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="4489e-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-131">Optional.</span></span> <span data-ttu-id="4489e-132">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="4489e-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-133">Optional.</span></span> <span data-ttu-id="4489e-134">Vea [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="4489e-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-135">Optional.</span></span> <span data-ttu-id="4489e-136">Vea [WriteOnly](../modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="4489e-137">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-137">Optional.</span></span> <span data-ttu-id="4489e-138">Vea [iterator](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="4489e-139">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4489e-139">Required.</span></span> <span data-ttu-id="4489e-140">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-140">Name of the property.</span></span> <span data-ttu-id="4489e-141">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="4489e-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-142">Optional.</span></span> <span data-ttu-id="4489e-143">Lista de nombres de variables locales que representan los parámetros de esta propiedad y posibles parámetros adicionales del procedimiento `Set`.</span><span class="sxs-lookup"><span data-stu-id="4489e-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="4489e-144">Vea [lista de parámetros](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="4489e-145">Es obligatorio si se `On``Option Strict`.</span><span class="sxs-lookup"><span data-stu-id="4489e-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="4489e-146">Tipo de datos del valor devuelto por esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="4489e-147">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-147">Optional.</span></span> <span data-ttu-id="4489e-148">Indica que esta propiedad implementa una o más propiedades, cada una de las cuales se define en una interfaz implementada por la clase o estructura que contiene esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="4489e-149">Vea [Implements (instrucción](implements-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="4489e-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="4489e-150">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="4489e-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4489e-151">Lista de propiedades que se implementan.</span><span class="sxs-lookup"><span data-stu-id="4489e-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="4489e-152">Cada `implementedproperty` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="4489e-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="4489e-153">Parte</span><span class="sxs-lookup"><span data-stu-id="4489e-153">Part</span></span>|<span data-ttu-id="4489e-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="4489e-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="4489e-155">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4489e-155">Required.</span></span> <span data-ttu-id="4489e-156">Nombre de una interfaz implementada por la clase o estructura que contiene esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="4489e-157">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4489e-157">Required.</span></span> <span data-ttu-id="4489e-158">Nombre por el que se define la propiedad en `interface`.</span><span class="sxs-lookup"><span data-stu-id="4489e-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="4489e-159">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-159">Optional.</span></span> <span data-ttu-id="4489e-160">Obligatorio si la propiedad está marcada como `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="4489e-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="4489e-161">Inicia una `Get` procedimiento de propiedad que se usa para devolver el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="4489e-162">La instrucción `Get` no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="4489e-163">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-163">Optional.</span></span> <span data-ttu-id="4489e-164">Bloque de instrucciones que se va a ejecutar en el procedimiento `Get` o `Set`.</span><span class="sxs-lookup"><span data-stu-id="4489e-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="4489e-165">Finaliza el procedimiento de la propiedad `Get`.</span><span class="sxs-lookup"><span data-stu-id="4489e-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="4489e-166">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4489e-166">Optional.</span></span> <span data-ttu-id="4489e-167">Obligatorio si la propiedad está marcada como `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="4489e-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="4489e-168">Inicia una `Set` procedimiento de propiedad que se usa para almacenar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="4489e-169">La instrucción `Set` no se utiliza con [las propiedades implementadas automáticamente](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4489e-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="4489e-170">Finaliza el procedimiento de la propiedad `Set`.</span><span class="sxs-lookup"><span data-stu-id="4489e-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="4489e-171">Finaliza la definición de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="4489e-172">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4489e-172">Remarks</span></span>

<span data-ttu-id="4489e-173">La instrucción `Property` presenta la declaración de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="4489e-174">Una propiedad puede tener un procedimiento `Get` (solo lectura), un procedimiento `Set` (solo escritura) o ambos (lectura y escritura).</span><span class="sxs-lookup"><span data-stu-id="4489e-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="4489e-175">Puede omitir el procedimiento `Get` y `Set` al utilizar una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4489e-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="4489e-176">Para obtener más información, vea [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md) (Propiedades implementadas automáticamente).</span><span class="sxs-lookup"><span data-stu-id="4489e-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="4489e-177">Solo se puede usar `Property` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="4489e-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="4489e-178">Esto significa que el contexto de la *declaración* de una propiedad debe ser una clase, una estructura, un módulo o una interfaz, y no puede ser un archivo de código fuente, un espacio de nombres, un procedimiento o un bloque.</span><span class="sxs-lookup"><span data-stu-id="4489e-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="4489e-179">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="4489e-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="4489e-180">De forma predeterminada, las propiedades usan el acceso público.</span><span class="sxs-lookup"><span data-stu-id="4489e-180">By default, properties use public access.</span></span> <span data-ttu-id="4489e-181">Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en la instrucción `Property` y, opcionalmente, puede ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="4489e-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="4489e-182">Visual Basic pasa un parámetro al procedimiento `Set` durante las asignaciones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4489e-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="4489e-183">Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`.</span><span class="sxs-lookup"><span data-stu-id="4489e-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="4489e-184">Este parámetro contiene el valor que se va a asignar a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="4489e-185">Normalmente, este valor se almacena en una variable local privada y se devuelve cada vez que se llama al procedimiento `Get`.</span><span class="sxs-lookup"><span data-stu-id="4489e-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="4489e-186">Reglas</span><span class="sxs-lookup"><span data-stu-id="4489e-186">Rules</span></span>

- <span data-ttu-id="4489e-187">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="4489e-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="4489e-188">Si va a definir una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el `Get` o el procedimiento de `Set`, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="4489e-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="4489e-189">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="4489e-190">Por ejemplo, si la propiedad se declara `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.</span><span class="sxs-lookup"><span data-stu-id="4489e-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="4489e-191">Si va a definir una propiedad `ReadOnly` o `WriteOnly`, el procedimiento de propiedad única (`Get` o `Set`, respectivamente) representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="4489e-192">No se puede declarar un nivel de acceso diferente para este procedimiento, ya que esto establecería dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="4489e-193">**Tipo de valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="4489e-193">**Return Type.**</span></span> <span data-ttu-id="4489e-194">La instrucción `Property` puede declarar el tipo de datos del valor que devuelve.</span><span class="sxs-lookup"><span data-stu-id="4489e-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="4489e-195">Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="4489e-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="4489e-196">Si no se especifica `returntype`, la propiedad devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="4489e-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="4489e-197">**Aplicación.**</span><span class="sxs-lookup"><span data-stu-id="4489e-197">**Implementation.**</span></span> <span data-ttu-id="4489e-198">Si esta propiedad utiliza la palabra clave `Implements`, la clase o estructura contenedora debe tener una instrucción `Implements` inmediatamente después de su instrucción `Class` o `Structure`.</span><span class="sxs-lookup"><span data-stu-id="4489e-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4489e-199">La instrucción `Implements` debe incluir cada interfaz especificada en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4489e-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="4489e-200">Sin embargo, el nombre por el que una interfaz define el `Property` (en `definedname`) no tiene que ser el mismo que el nombre de esta propiedad (en `name`).</span><span class="sxs-lookup"><span data-stu-id="4489e-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="4489e-201">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="4489e-201">Behavior</span></span>

- <span data-ttu-id="4489e-202">**Devolver desde un procedimiento de propiedad.**</span><span class="sxs-lookup"><span data-stu-id="4489e-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="4489e-203">Cuando el procedimiento `Get` o `Set` vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.</span><span class="sxs-lookup"><span data-stu-id="4489e-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="4489e-204">Las instrucciones `Exit Property` y `Return` producen una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="4489e-205">Cualquier número de instrucciones `Exit Property` y `Return` puede aparecer en cualquier parte del procedimiento y se pueden mezclar instrucciones `Exit Property` y `Return`.</span><span class="sxs-lookup"><span data-stu-id="4489e-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="4489e-206">**Valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="4489e-206">**Return Value.**</span></span> <span data-ttu-id="4489e-207">Para devolver un valor de un procedimiento `Get`, puede asignar el valor al nombre de la propiedad o incluirlo en una instrucción `Return`.</span><span class="sxs-lookup"><span data-stu-id="4489e-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="4489e-208">En el ejemplo siguiente se asigna el valor devuelto al nombre de propiedad `quoteForTheDay` y, a continuación, se usa la instrucción `Exit Property` para devolver.</span><span class="sxs-lookup"><span data-stu-id="4489e-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="4489e-209">Si usa `Exit Property` sin asignar un valor a `name`, el procedimiento `Get` devuelve el valor predeterminado del tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4489e-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="4489e-210">La instrucción `Return` al mismo tiempo asigna el valor devuelto del procedimiento `Get` y sale del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4489e-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="4489e-211">En el ejemplo siguiente se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="4489e-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="4489e-212">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4489e-212">Example</span></span>

<span data-ttu-id="4489e-213">En el ejemplo siguiente se declara una propiedad en una clase.</span><span class="sxs-lookup"><span data-stu-id="4489e-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="4489e-214">Vea también</span><span class="sxs-lookup"><span data-stu-id="4489e-214">See also</span></span>

- [<span data-ttu-id="4489e-215">Propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="4489e-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="4489e-216">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="4489e-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="4489e-217">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4489e-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="4489e-218">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4489e-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="4489e-219">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="4489e-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="4489e-220">Default</span><span class="sxs-lookup"><span data-stu-id="4489e-220">Default</span></span>](../modifiers/default.md)
