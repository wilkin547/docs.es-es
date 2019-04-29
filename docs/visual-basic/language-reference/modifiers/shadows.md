---
title: Shadows (Visual Basic)
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
ms.openlocfilehash: c314db90a1a0f89613e20897387bdec8ec534837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778734"
---
# <a name="shadows-visual-basic"></a><span data-ttu-id="ff56b-102">Shadows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff56b-102">Shadows (Visual Basic)</span></span>
<span data-ttu-id="ff56b-103">Especifica que un elemento de programación declarado vuelve a declarar y oculta un elemento con el mismo nombre, o un conjunto de elementos sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="ff56b-103">Specifies that a declared programming element redeclares and hides an identically named element, or set of overloaded elements, in a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff56b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff56b-104">Remarks</span></span>  
 <span data-ttu-id="ff56b-105">El propósito principal de sombreado (también conocido como *ocultar por nombre*) consiste en conservar la definición de los miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="ff56b-105">The main purpose of shadowing (which is also known as *hiding by name*) is to preserve the definition of your class members.</span></span> <span data-ttu-id="ff56b-106">La clase base puede sufrir un cambio que se crea un elemento con el mismo nombre que ya ha definido.</span><span class="sxs-lookup"><span data-stu-id="ff56b-106">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="ff56b-107">Si esto ocurre, el `Shadows` modificador fuerza hace referencia a través de su clase se resuelvan en el miembro está definido, en lugar de para el nuevo elemento de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ff56b-107">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
 <span data-ttu-id="ff56b-108">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="ff56b-108">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="ff56b-109">Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="ff56b-109">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ff56b-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="ff56b-110">Rules</span></span>  
  
- <span data-ttu-id="ff56b-111">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="ff56b-111">**Declaration Context.**</span></span> <span data-ttu-id="ff56b-112">Puede usar `Shadows` sólo en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="ff56b-112">You can use `Shadows` only at class level.</span></span> <span data-ttu-id="ff56b-113">Esto significa que el contexto de declaración de un `Shadows` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ff56b-113">This means the declaration context for a `Shadows` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
     <span data-ttu-id="ff56b-114">Puede declarar un único elemento sombreado en una única instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="ff56b-114">You can declare only one shadowing element in a single declaration statement.</span></span>  
  
- <span data-ttu-id="ff56b-115">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="ff56b-115">**Combined Modifiers.**</span></span> <span data-ttu-id="ff56b-116">No puede especificar `Shadows` junto con `Overloads`, `Overrides`, o `Static` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="ff56b-116">You cannot specify `Shadows` together with `Overloads`, `Overrides`, or `Static` in the same declaration.</span></span>  
  
- <span data-ttu-id="ff56b-117">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="ff56b-117">**Element Types.**</span></span> <span data-ttu-id="ff56b-118">Puede reemplazar cualquier tipo de elemento declarado con cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="ff56b-118">You can shadow any kind of declared element with any other kind.</span></span> <span data-ttu-id="ff56b-119">Si sombrea una propiedad o procedimiento con otra propiedad o procedimiento, los parámetros y el tipo de valor devuelto no es necesario para que coincida con los de la propiedad de clase base o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ff56b-119">If you shadow a property or procedure with another property or procedure, the parameters and the return type do not have to match those in the base class property or procedure.</span></span>  
  
- <span data-ttu-id="ff56b-120">**Acceso a.**</span><span class="sxs-lookup"><span data-stu-id="ff56b-120">**Accessing.**</span></span> <span data-ttu-id="ff56b-121">El elemento sombreado en la clase base está disponible normalmente desde dentro de la clase derivada que lo reemplaza.</span><span class="sxs-lookup"><span data-stu-id="ff56b-121">The shadowed element in the base class is normally unavailable from within the derived class that shadows it.</span></span> <span data-ttu-id="ff56b-122">Sin embargo, se aplican las consideraciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ff56b-122">However, the following considerations apply.</span></span>  
  
    - <span data-ttu-id="ff56b-123">Si el elemento reemplazado no es accesible desde el código que hace referencia a él, la referencia se resuelve en el elemento sombreado.</span><span class="sxs-lookup"><span data-stu-id="ff56b-123">If the shadowing element is not accessible from the code referring to it, the reference is resolved to the shadowed element.</span></span> <span data-ttu-id="ff56b-124">Por ejemplo, si un `Private` elemento oculta o prevalece sobre un elemento de clase base, el código que no tiene permiso para tener acceso a la `Private` elemento tiene acceso al elemento de clase base en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ff56b-124">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>  
  
    - <span data-ttu-id="ff56b-125">Ocultar un elemento, es posible acceder el elemento sombreado a través de un objeto declarado con el tipo de la clase base.</span><span class="sxs-lookup"><span data-stu-id="ff56b-125">If you shadow an element, you can still access the shadowed element through an object declared with the type of the base class.</span></span> <span data-ttu-id="ff56b-126">También puede acceder a través de `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="ff56b-126">You can also access it through `MyBase`.</span></span>  
  
 <span data-ttu-id="ff56b-127">El modificador `Shadows` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff56b-127">The `Shadows` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ff56b-128">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="ff56b-129">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="ff56b-130">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ff56b-131">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="ff56b-132">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="ff56b-133">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="ff56b-134">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="ff56b-135">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ff56b-136">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="ff56b-137">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ff56b-138">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="ff56b-139">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ff56b-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff56b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff56b-140">See also</span></span>

- [<span data-ttu-id="ff56b-141">Shared</span><span class="sxs-lookup"><span data-stu-id="ff56b-141">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="ff56b-142">Static</span><span class="sxs-lookup"><span data-stu-id="ff56b-142">Static</span></span>](../../../visual-basic/language-reference/modifiers/static.md)
- [<span data-ttu-id="ff56b-143">Private</span><span class="sxs-lookup"><span data-stu-id="ff56b-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="ff56b-144">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="ff56b-144">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="ff56b-145">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="ff56b-145">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="ff56b-146">MustOverride</span><span class="sxs-lookup"><span data-stu-id="ff56b-146">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="ff56b-147">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="ff56b-147">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="ff56b-148">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="ff56b-148">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="ff56b-149">Overridable</span><span class="sxs-lookup"><span data-stu-id="ff56b-149">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="ff56b-150">Overrides</span><span class="sxs-lookup"><span data-stu-id="ff56b-150">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="ff56b-151">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff56b-151">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
