---
title: Privado protegido (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920502"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="c81f0-102">Privado protegido (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c81f0-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="c81f0-103">La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="c81f0-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="c81f0-104">Un `Private Protected` miembro es accesible por todos los miembros de su clase contenedora, así como tipos derivados de la clase contenedora, pero solo si están presentes en el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c81f0-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="c81f0-105">Puede especificar `Private Protected` solo en los miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se puede heredar.</span><span class="sxs-lookup"><span data-stu-id="c81f0-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="c81f0-106">El `Private Protected` modificador de acceso es compatible con Visual Basic 15.5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c81f0-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="c81f0-107">Para ello, puede agregar el elemento siguiente a su proyecto de Visual Basic (\*.vbproj) archivo.</span><span class="sxs-lookup"><span data-stu-id="c81f0-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="c81f0-108">Siempre que Visual Basic 15.5 o posterior esté instalado en el sistema, le permite aprovechar todas las características del lenguaje compatible con la versión más reciente del compilador de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="c81f0-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="c81f0-109">Para obtener más información, consulte [configuración de la versión de idioma de Visual Basic](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="c81f0-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c81f0-110">En Visual Studio, seleccione Ayuda de F1 en `private protected` proporciona ayuda para cualquiera [privada](private.md) o [protegido](protected.md).</span><span class="sxs-lookup"><span data-stu-id="c81f0-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="c81f0-111">El IDE elige el token solo bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="c81f0-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="c81f0-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="c81f0-112">Rules</span></span>

- <span data-ttu-id="c81f0-113">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="c81f0-113">**Declaration Context.**</span></span> <span data-ttu-id="c81f0-114">Puede usar `Private Protected` sólo en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="c81f0-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="c81f0-115">Esto significa que el contexto de declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c81f0-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="c81f0-116">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="c81f0-116">Behavior</span></span>

- <span data-ttu-id="c81f0-117">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="c81f0-117">**Access Level.**</span></span> <span data-ttu-id="c81f0-118">Todo el código en una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="c81f0-118">All code in a class can access its elements.</span></span> <span data-ttu-id="c81f0-119">Código de cualquier clase que deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todas las `Private Protected` elementos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="c81f0-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="c81f0-120">Sin embargo, el código en cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede acceder a la clase base `Private Protected` elementos.</span><span class="sxs-lookup"><span data-stu-id="c81f0-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="c81f0-121">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="c81f0-121">**Access Modifiers.**</span></span> <span data-ttu-id="c81f0-122">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="c81f0-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="c81f0-123">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c81f0-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="c81f0-124">El modificador `Private Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c81f0-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="c81f0-125">[Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md) de una clase anidada</span><span class="sxs-lookup"><span data-stu-id="c81f0-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="c81f0-126">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="c81f0-127">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="c81f0-128">[Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md) de un delegado anidado en una clase</span><span class="sxs-lookup"><span data-stu-id="c81f0-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="c81f0-129">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="c81f0-130">[Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md) de una enumeración anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="c81f0-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="c81f0-131">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="c81f0-132">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="c81f0-133">[Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md) de una interfaz anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="c81f0-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="c81f0-134">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="c81f0-135">[Estructura de la instrucción](../../../visual-basic/language-reference/statements/structure-statement.md) de una estructura anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="c81f0-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="c81f0-136">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c81f0-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="c81f0-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="c81f0-137">See also</span></span>

- [<span data-ttu-id="c81f0-138">Public</span><span class="sxs-lookup"><span data-stu-id="c81f0-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="c81f0-139">Protected</span><span class="sxs-lookup"><span data-stu-id="c81f0-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="c81f0-140">Friend</span><span class="sxs-lookup"><span data-stu-id="c81f0-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="c81f0-141">Private</span><span class="sxs-lookup"><span data-stu-id="c81f0-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="c81f0-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="c81f0-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="c81f0-143">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c81f0-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="c81f0-144">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c81f0-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="c81f0-145">Estructuras</span><span class="sxs-lookup"><span data-stu-id="c81f0-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c81f0-146">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="c81f0-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
