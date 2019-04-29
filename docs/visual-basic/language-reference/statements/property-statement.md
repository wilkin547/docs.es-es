---
title: Declaración de propiedad (Visual Basic)
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
ms.openlocfilehash: 7b2d388cbcd1995178adf4102520ecaa1c9b1889
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783999"
---
# <a name="property-statement"></a><span data-ttu-id="b7bda-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b7bda-102">Property Statement</span></span>

<span data-ttu-id="b7bda-103">Declara el nombre de una propiedad y los procedimientos de propiedad que se utiliza para almacenar y recuperar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7bda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7bda-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="b7bda-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b7bda-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="b7bda-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-106">Optional.</span></span> <span data-ttu-id="b7bda-107">Lista de atributos que se aplican a esta propiedad o `Get` o `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b7bda-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="b7bda-108">Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="b7bda-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-109">Optional.</span></span> <span data-ttu-id="b7bda-110">Especifica que esta propiedad es la propiedad predeterminada para la clase o estructura en el que está definida.</span><span class="sxs-lookup"><span data-stu-id="b7bda-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="b7bda-111">Las propiedades predeterminadas deben aceptar parámetros y se pueden establecer y recuperar sin especificar el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="b7bda-112">Si se declara la propiedad como `Default`, no puede usar `Private` en la propiedad o en cualquiera de sus procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="b7bda-113">Opcional en el `Property` instrucción y en al menos uno de los `Get` y `Set` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b7bda-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="b7bda-114">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7bda-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="b7bda-115">Public</span><span class="sxs-lookup"><span data-stu-id="b7bda-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="b7bda-116">Protected</span><span class="sxs-lookup"><span data-stu-id="b7bda-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="b7bda-117">Friend</span><span class="sxs-lookup"><span data-stu-id="b7bda-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="b7bda-118">Private</span><span class="sxs-lookup"><span data-stu-id="b7bda-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="b7bda-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="b7bda-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="b7bda-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="b7bda-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="b7bda-121">Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="b7bda-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-122">Optional.</span></span> <span data-ttu-id="b7bda-123">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7bda-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="b7bda-124">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="b7bda-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="b7bda-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="b7bda-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="b7bda-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="b7bda-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="b7bda-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="b7bda-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="b7bda-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="b7bda-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="b7bda-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-129">Optional.</span></span> <span data-ttu-id="b7bda-130">Consulte [compartido](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="b7bda-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-131">Optional.</span></span> <span data-ttu-id="b7bda-132">Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="b7bda-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-133">Optional.</span></span> <span data-ttu-id="b7bda-134">Consulte [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="b7bda-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-135">Optional.</span></span> <span data-ttu-id="b7bda-136">Consulte [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="b7bda-137">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-137">Optional.</span></span> <span data-ttu-id="b7bda-138">Consulte [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="b7bda-139">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7bda-139">Required.</span></span> <span data-ttu-id="b7bda-140">Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-140">Name of the property.</span></span> <span data-ttu-id="b7bda-141">Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="b7bda-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-142">Optional.</span></span> <span data-ttu-id="b7bda-143">Lista de nombres de variable local que representa los parámetros de esta propiedad y los posibles parámetros adicionales de la `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b7bda-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="b7bda-144">Consulte [Lista_de_parámetros](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="b7bda-145">Es necesario si `Option Strict` es `On`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="b7bda-146">Tipo de datos del valor devuelto por esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="b7bda-147">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-147">Optional.</span></span> <span data-ttu-id="b7bda-148">Indica que esta propiedad implementa una o varias propiedades, cada uno definido en una interfaz implementada por la clase o estructura contenedora de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="b7bda-149">Consulte [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="b7bda-150">Es necesario si se proporciona `Implements`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="b7bda-151">Lista de propiedades que se implementan.</span><span class="sxs-lookup"><span data-stu-id="b7bda-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="b7bda-152">Cada `implementedproperty` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7bda-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="b7bda-153">Parte</span><span class="sxs-lookup"><span data-stu-id="b7bda-153">Part</span></span>|<span data-ttu-id="b7bda-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7bda-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="b7bda-155">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7bda-155">Required.</span></span> <span data-ttu-id="b7bda-156">Nombre de una interfaz implementada por esta propiedad contenedora de clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b7bda-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="b7bda-157">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b7bda-157">Required.</span></span> <span data-ttu-id="b7bda-158">Nombre por el que se define la propiedad en `interface`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="b7bda-159">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-159">Optional.</span></span> <span data-ttu-id="b7bda-160">Necesario si la propiedad se marca `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="b7bda-161">Se inicia un `Get` procedimiento de propiedad que se usa para devolver el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>

- `statements`

  <span data-ttu-id="b7bda-162">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-162">Optional.</span></span> <span data-ttu-id="b7bda-163">Bloque de instrucciones que se ejecutan dentro de la `Get` o `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b7bda-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="b7bda-164">Finaliza el `Get` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-164">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="b7bda-165">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b7bda-165">Optional.</span></span> <span data-ttu-id="b7bda-166">Necesario si la propiedad se marca `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="b7bda-167">Se inicia un `Set` procedimiento de propiedad que se usa para almacenar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>

- `End Set`

  <span data-ttu-id="b7bda-168">Finaliza el `Set` procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-168">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="b7bda-169">Termina la definición de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-169">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7bda-170">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7bda-170">Remarks</span></span>

<span data-ttu-id="b7bda-171">El `Property` instrucción introduce la declaración de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="b7bda-172">Una propiedad puede tener un `Get` procedimiento (solo lectura), un `Set` procedimiento (solo escritura), o ambas (lectura y escritura).</span><span class="sxs-lookup"><span data-stu-id="b7bda-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="b7bda-173">Puede omitir el `Get` y `Set` procedimiento cuando se usa una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b7bda-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="b7bda-174">Para obtener más información, vea [Propiedades implementadas automáticamente](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b7bda-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="b7bda-175">Puede usar `Property` sólo en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="b7bda-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="b7bda-176">Esto significa que el *contexto de declaración* para una propiedad debe ser una clase, estructura, módulo o interfaz y no puede ser un archivo de código fuente, espacio de nombres, procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="b7bda-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="b7bda-177">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="b7bda-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="b7bda-178">De forma predeterminada, las propiedades utilizan acceso público.</span><span class="sxs-lookup"><span data-stu-id="b7bda-178">By default, properties use public access.</span></span> <span data-ttu-id="b7bda-179">Puede ajustar el nivel de acceso de una propiedad con un modificador de acceso en el `Property` statement y, opcionalmente, puede ajustar uno de sus procedimientos de propiedad a un nivel de acceso más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="b7bda-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="b7bda-180">Visual Basic pasa un parámetro a la `Set` procedimiento durante las asignaciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="b7bda-181">Si no proporciona un parámetro para `Set`, el entorno de desarrollo integrado (IDE) utiliza un parámetro implícito denominado `value`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="b7bda-182">Este parámetro contiene el valor que se asignará a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="b7bda-183">Se suele almacenar este valor en una variable local privada y devolverlo cada vez que el `Get` se llama al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b7bda-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="b7bda-184">Reglas</span><span class="sxs-lookup"><span data-stu-id="b7bda-184">Rules</span></span>

- <span data-ttu-id="b7bda-185">**Niveles de acceso mixtos.**</span><span class="sxs-lookup"><span data-stu-id="b7bda-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="b7bda-186">Si va a definir una propiedad de lectura y escritura, opcionalmente, puede especificar un nivel de acceso diferente para el `Get` o `Set` procedimiento, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="b7bda-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="b7bda-187">Si lo hace, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="b7bda-188">Por ejemplo, si se declara la propiedad `Friend`, puede declarar el `Set` procedimiento `Private`, pero no `Public`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="b7bda-189">Si está definiendo un `ReadOnly` o `WriteOnly` propiedad, el procedimiento de propiedad único (`Get` o `Set`, respectivamente) representa toda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="b7bda-190">No se puede declarar un nivel de acceso diferente para este tipo de procedimiento, porque se establecerían dos niveles de acceso para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="b7bda-191">**Tipo de valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="b7bda-191">**Return Type.**</span></span> <span data-ttu-id="b7bda-192">El `Property` instrucción puede declarar el tipo de datos del valor que devuelve.</span><span class="sxs-lookup"><span data-stu-id="b7bda-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="b7bda-193">Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="b7bda-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="b7bda-194">Si no especifica `returntype`, la propiedad devuelve `Object`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-194">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="b7bda-195">**Implementación de.**</span><span class="sxs-lookup"><span data-stu-id="b7bda-195">**Implementation.**</span></span> <span data-ttu-id="b7bda-196">Si usa esta propiedad la `Implements` debe tener la palabra clave, la clase o estructura que contiene un `Implements` instrucción inmediatamente posterior a su `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b7bda-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="b7bda-197">El `Implements` instrucción debe incluir cada interfaz especificada en `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="b7bda-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="b7bda-198">Sin embargo, el nombre por el que una interfaz define el `Property` (en `definedname`) no tiene que ser el mismo que el nombre de esta propiedad (en `name`).</span><span class="sxs-lookup"><span data-stu-id="b7bda-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="b7bda-199">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="b7bda-199">Behavior</span></span>

- <span data-ttu-id="b7bda-200">**Devolución desde un procedimiento de propiedad.**</span><span class="sxs-lookup"><span data-stu-id="b7bda-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="b7bda-201">Cuando el `Get` o `Set` procedimiento vuelve al código de llamada, la ejecución continúa con la instrucción que sigue a la instrucción que lo invocó.</span><span class="sxs-lookup"><span data-stu-id="b7bda-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="b7bda-202">El `Exit Property` y `Return` instrucciones provocan una salida inmediata de un procedimiento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7bda-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="b7bda-203">Cualquier número de `Exit Property` y `Return` instrucciones pueden aparecer en cualquier lugar en el procedimiento, y puede mezclar `Exit Property` y `Return` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b7bda-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="b7bda-204">**Valor devuelto.**</span><span class="sxs-lookup"><span data-stu-id="b7bda-204">**Return Value.**</span></span> <span data-ttu-id="b7bda-205">Para devolver un valor de un `Get` procedimiento, puede asignar el valor al nombre de propiedad o incluirlo en un `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b7bda-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="b7bda-206">En el ejemplo siguiente se asigna el valor devuelto al nombre de propiedad `quoteForTheDay` y, a continuación, usa el `Exit Property` instrucción para devolver.</span><span class="sxs-lookup"><span data-stu-id="b7bda-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="b7bda-207">Si usas `Exit Property` sin asignar un valor a `name`, el `Get` procedimiento devuelve el valor predeterminado para el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="b7bda-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="b7bda-208">El `Return` instrucción al mismo tiempo asigna el `Get` procedimiento devolver valor y sale del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b7bda-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="b7bda-209">En el ejemplo siguiente se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="b7bda-209">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="b7bda-210">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7bda-210">Example</span></span>

<span data-ttu-id="b7bda-211">El ejemplo siguiente declara una propiedad en una clase.</span><span class="sxs-lookup"><span data-stu-id="b7bda-211">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="b7bda-212">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7bda-212">See also</span></span>

- [<span data-ttu-id="b7bda-213">Propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="b7bda-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="b7bda-214">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="b7bda-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="b7bda-215">Get (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b7bda-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="b7bda-216">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b7bda-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="b7bda-217">Lista de parámetros</span><span class="sxs-lookup"><span data-stu-id="b7bda-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="b7bda-218">Predetermiado</span><span class="sxs-lookup"><span data-stu-id="b7bda-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
