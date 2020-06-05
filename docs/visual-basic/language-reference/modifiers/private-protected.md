---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: b7d9f81e41950b92c787e2e50fb94fe3d7c07559
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362234"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="db66e-102">Privado protegido (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db66e-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="db66e-103">La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="db66e-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="db66e-104">Un `Private Protected` miembro es accesible para todos los miembros de la clase contenedora, así como para los tipos derivados de la clase contenedora, pero solo si se encuentran en el ensamblado contenedor.</span><span class="sxs-lookup"><span data-stu-id="db66e-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="db66e-105">Solo se puede especificar `Private Protected` en miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="db66e-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="db66e-106">`Private Protected`Visual Basic 15,5 y versiones posteriores admiten el modificador de acceso.</span><span class="sxs-lookup"><span data-stu-id="db66e-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="db66e-107">Para usarlo, puede Agregar el siguiente elemento al archivo de proyecto de Visual Basic ( \* . vbproj).</span><span class="sxs-lookup"><span data-stu-id="db66e-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="db66e-108">Siempre que Visual Basic 15,5 o posterior esté instalado en el sistema, le permite aprovechar todas las características de lenguaje compatibles con la versión más reciente del compilador de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="db66e-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="db66e-109">Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="db66e-109">For more information see [setting the Visual Basic language version](../configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="db66e-110">En Visual Studio, la selección de la ayuda F1 en `private protected` proporciona ayuda para [privado](private.md) o [protegido](protected.md).</span><span class="sxs-lookup"><span data-stu-id="db66e-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="db66e-111">El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="db66e-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="db66e-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="db66e-112">Rules</span></span>

- <span data-ttu-id="db66e-113">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="db66e-113">**Declaration Context.**</span></span> <span data-ttu-id="db66e-114">Solo se puede usar `Private Protected` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="db66e-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="db66e-115">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="db66e-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="db66e-116">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="db66e-116">Behavior</span></span>

- <span data-ttu-id="db66e-117">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="db66e-117">**Access Level.**</span></span> <span data-ttu-id="db66e-118">Todo el código de una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="db66e-118">All code in a class can access its elements.</span></span> <span data-ttu-id="db66e-119">El código de cualquier clase que se deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todos los `Private Protected` elementos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="db66e-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="db66e-120">Sin embargo, el código de cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede tener acceso a los elementos de la clase base `Private Protected` .</span><span class="sxs-lookup"><span data-stu-id="db66e-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="db66e-121">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="db66e-121">**Access Modifiers.**</span></span> <span data-ttu-id="db66e-122">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="db66e-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="db66e-123">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="db66e-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="db66e-124">El modificador `Private Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="db66e-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="db66e-125">[Instrucción de clase](../statements/class-statement.md) de una clase anidada</span><span class="sxs-lookup"><span data-stu-id="db66e-125">[Class Statement](../statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="db66e-126">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="db66e-126">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="db66e-127">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="db66e-127">Declare Statement</span></span>](../statements/declare-statement.md)

- <span data-ttu-id="db66e-128">[Instrucción delegada](../statements/delegate-statement.md) de un delegado anidado en una clase</span><span class="sxs-lookup"><span data-stu-id="db66e-128">[Delegate Statement](../statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="db66e-129">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="db66e-129">Dim Statement</span></span>](../statements/dim-statement.md)

- <span data-ttu-id="db66e-130">[Instrucción enum](../statements/enum-statement.md) de una enumeración anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="db66e-130">[Enum Statement](../statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="db66e-131">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="db66e-131">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="db66e-132">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="db66e-132">Function Statement</span></span>](../statements/function-statement.md)

- <span data-ttu-id="db66e-133">[Instrucción de interfaz](../statements/interface-statement.md) de una interfaz anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="db66e-133">[Interface Statement](../statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="db66e-134">Property Statement</span><span class="sxs-lookup"><span data-stu-id="db66e-134">Property Statement</span></span>](../statements/property-statement.md)

- <span data-ttu-id="db66e-135">[Instrucción Structure](../statements/structure-statement.md) de una estructura anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="db66e-135">[Structure Statement](../statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="db66e-136">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="db66e-136">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="db66e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db66e-137">See also</span></span>

- [<span data-ttu-id="db66e-138">Público</span><span class="sxs-lookup"><span data-stu-id="db66e-138">Public</span></span>](public.md)
- [<span data-ttu-id="db66e-139">Contra</span><span class="sxs-lookup"><span data-stu-id="db66e-139">Protected</span></span>](protected.md)
- [<span data-ttu-id="db66e-140">Respecto</span><span class="sxs-lookup"><span data-stu-id="db66e-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="db66e-141">Privado</span><span class="sxs-lookup"><span data-stu-id="db66e-141">Private</span></span>](private.md)
- [<span data-ttu-id="db66e-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="db66e-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="db66e-143">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db66e-143">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="db66e-144">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="db66e-144">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="db66e-145">Estructuras</span><span class="sxs-lookup"><span data-stu-id="db66e-145">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="db66e-146">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="db66e-146">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
