---
description: 'Más información acerca de: Shadows (Visual Basic)'
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 4a455a78c36e15db977936b81c22e7a5b03d107e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700850"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="bbf6d-103">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbf6d-103">Shadows (Visual Basic)</span></span>

<span data-ttu-id="bbf6d-104">Especifica que un elemento de programación declarado vuelve a declarar y oculta un elemento con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-104">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>

## <a name="remarks"></a><span data-ttu-id="bbf6d-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bbf6d-105">Remarks</span></span>

<span data-ttu-id="bbf6d-106">El propósito principal de la sombra (que también se denomina *ocultar por nombre*) es conservar la definición de los miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-106">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="bbf6d-107">La clase base puede someterse a un cambio que crea un elemento con el mismo nombre que el que ya se ha definido.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="bbf6d-108">Si esto ocurre, el `Shadows` modificador fuerza las referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>

<span data-ttu-id="bbf6d-109">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-109">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="bbf6d-110">Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="bbf6d-110">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

## <a name="rules"></a><span data-ttu-id="bbf6d-111">Reglas</span><span class="sxs-lookup"><span data-stu-id="bbf6d-111">Rules</span></span>

- <span data-ttu-id="bbf6d-112">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="bbf6d-112">**Declaration Context.**</span></span> <span data-ttu-id="bbf6d-113">Solo se puede usar `Shadows` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-113">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="bbf6d-114">Esto significa que el contexto de la declaración de un `Shadows` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-114">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

  <span data-ttu-id="bbf6d-115">Solo puede declarar un elemento de sombreado en una instrucción de declaración única.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-115">You can declare only one shadowing element in a single declaration statement.</span></span>

- <span data-ttu-id="bbf6d-116">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="bbf6d-116">**Combined Modifiers.**</span></span> <span data-ttu-id="bbf6d-117">No se puede especificar `Shadows` junto con `Overloads` , `Overrides` o `Static` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-117">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>

- <span data-ttu-id="bbf6d-118">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="bbf6d-118">**Element Types.**</span></span> <span data-ttu-id="bbf6d-119">Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-119">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="bbf6d-120">Si sombrea una propiedad o un procedimiento con otra propiedad o procedimiento, los parámetros y el tipo de valor devuelto no tienen que coincidir con los de la propiedad o el procedimiento de la clase base.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-120">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>

- <span data-ttu-id="bbf6d-121">**Acceso a.**</span><span class="sxs-lookup"><span data-stu-id="bbf6d-121">**Accessing.**</span></span> <span data-ttu-id="bbf6d-122">Normalmente, el elemento sombreado de la clase base no está disponible en la clase derivada que lo sombrea.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-122">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="bbf6d-123">Sin embargo, se aplican las consideraciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-123">However, the following considerations apply.</span></span>

  - <span data-ttu-id="bbf6d-124">Si el elemento de sombreado no es accesible desde el código que hace referencia a él, la referencia se resuelve en el elemento sombreado.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-124">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="bbf6d-125">Por ejemplo, si un `Private` elemento sombrea un elemento de clase base, el código que no tiene permiso para obtener acceso al elemento de `Private` la clase base en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-125">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>

  - <span data-ttu-id="bbf6d-126">Si sombrea un elemento, todavía puede tener acceso al elemento sombreado a través de un objeto declarado con el tipo de la clase base.</span><span class="sxs-lookup"><span data-stu-id="bbf6d-126">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="bbf6d-127">También puede tener acceso a ella a través de `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="bbf6d-127">You can also access it through `MyBase`.</span></span>

<span data-ttu-id="bbf6d-128">El modificador `Shadows` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbf6d-128">The `Shadows` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="bbf6d-129">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="bbf6d-129">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="bbf6d-130">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="bbf6d-130">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="bbf6d-131">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="bbf6d-131">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="bbf6d-132">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="bbf6d-132">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="bbf6d-133">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="bbf6d-133">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="bbf6d-134">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="bbf6d-134">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="bbf6d-135">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="bbf6d-135">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="bbf6d-136">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="bbf6d-136">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="bbf6d-137">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="bbf6d-137">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="bbf6d-138">Property Statement</span><span class="sxs-lookup"><span data-stu-id="bbf6d-138">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="bbf6d-139">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="bbf6d-139">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="bbf6d-140">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="bbf6d-140">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="bbf6d-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbf6d-141">See also</span></span>

- [<span data-ttu-id="bbf6d-142">Compartido</span><span class="sxs-lookup"><span data-stu-id="bbf6d-142">Shared</span></span>](shared.md)
- [<span data-ttu-id="bbf6d-143">Estática</span><span class="sxs-lookup"><span data-stu-id="bbf6d-143">Static</span></span>](static.md)
- [<span data-ttu-id="bbf6d-144">Privado</span><span class="sxs-lookup"><span data-stu-id="bbf6d-144">Private</span></span>](private.md)
- [<span data-ttu-id="bbf6d-145">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="bbf6d-145">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="bbf6d-146">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="bbf6d-146">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="bbf6d-147">MustOverride</span><span class="sxs-lookup"><span data-stu-id="bbf6d-147">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="bbf6d-148">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="bbf6d-148">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="bbf6d-149">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="bbf6d-149">Overloads</span></span>](overloads.md)
- [<span data-ttu-id="bbf6d-150">Overridable</span><span class="sxs-lookup"><span data-stu-id="bbf6d-150">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="bbf6d-151">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="bbf6d-151">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="bbf6d-152">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bbf6d-152">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
