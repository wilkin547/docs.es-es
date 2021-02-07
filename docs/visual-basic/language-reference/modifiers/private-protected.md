---
description: 'Más información acerca de: Private Protected (Visual Basic)'
title: Private Protected
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: eb521ace77cd16f4904657cbdc035575e98e98fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700967"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="78adc-103">Privado protegido (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78adc-103">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="78adc-104">La combinación de palabras claves `Private Protected` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="78adc-104">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="78adc-105">Un `Private Protected` miembro es accesible para todos los miembros de la clase contenedora, así como para los tipos derivados de la clase contenedora, pero solo si se encuentran en el ensamblado contenedor.</span><span class="sxs-lookup"><span data-stu-id="78adc-105">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="78adc-106">Solo se puede especificar `Private Protected` en miembros de clases; no se puede aplicar `Private Protected` a los miembros de una estructura porque las estructuras no se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="78adc-106">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="78adc-107">`Private Protected`Visual Basic 15,5 y versiones posteriores admiten el modificador de acceso.</span><span class="sxs-lookup"><span data-stu-id="78adc-107">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="78adc-108">Para usarlo, puede Agregar el siguiente elemento al archivo de proyecto de Visual Basic ( \* . vbproj).</span><span class="sxs-lookup"><span data-stu-id="78adc-108">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="78adc-109">Siempre que Visual Basic 15,5 o posterior esté instalado en el sistema, le permite aprovechar todas las características de lenguaje compatibles con la versión más reciente del compilador de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="78adc-109">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="78adc-110">Para obtener más información, vea [establecer la versión de lenguaje Visual Basic](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="78adc-110">For more information see [setting the Visual Basic language version](../configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="78adc-111">En Visual Studio, la selección de la ayuda F1 en `private protected` proporciona ayuda para [privado](private.md) o [protegido](protected.md).</span><span class="sxs-lookup"><span data-stu-id="78adc-111">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="78adc-112">El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="78adc-112">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="78adc-113">Reglas</span><span class="sxs-lookup"><span data-stu-id="78adc-113">Rules</span></span>

- <span data-ttu-id="78adc-114">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="78adc-114">**Declaration Context.**</span></span> <span data-ttu-id="78adc-115">Solo se puede usar `Private Protected` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="78adc-115">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="78adc-116">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="78adc-116">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="78adc-117">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="78adc-117">Behavior</span></span>

- <span data-ttu-id="78adc-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="78adc-118">**Access Level.**</span></span> <span data-ttu-id="78adc-119">Todo el código de una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="78adc-119">All code in a class can access its elements.</span></span> <span data-ttu-id="78adc-120">El código de cualquier clase que se deriva de una clase base y se encuentra en el mismo ensamblado puede tener acceso a todos los `Private Protected` elementos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="78adc-120">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="78adc-121">Sin embargo, el código de cualquier clase que deriva de una clase base y se encuentra en un ensamblado diferente no puede tener acceso a los elementos de la clase base `Private Protected` .</span><span class="sxs-lookup"><span data-stu-id="78adc-121">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="78adc-122">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="78adc-122">**Access Modifiers.**</span></span> <span data-ttu-id="78adc-123">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="78adc-123">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="78adc-124">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="78adc-124">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="78adc-125">El modificador `Private Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="78adc-125">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="78adc-126">[Instrucción de clase](../statements/class-statement.md) de una clase anidada</span><span class="sxs-lookup"><span data-stu-id="78adc-126">[Class Statement](../statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="78adc-127">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="78adc-127">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="78adc-128">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="78adc-128">Declare Statement</span></span>](../statements/declare-statement.md)

- <span data-ttu-id="78adc-129">[Instrucción delegada](../statements/delegate-statement.md) de un delegado anidado en una clase</span><span class="sxs-lookup"><span data-stu-id="78adc-129">[Delegate Statement](../statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="78adc-130">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="78adc-130">Dim Statement</span></span>](../statements/dim-statement.md)

- <span data-ttu-id="78adc-131">[Instrucción enum](../statements/enum-statement.md) de una enumeración anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="78adc-131">[Enum Statement](../statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="78adc-132">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="78adc-132">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="78adc-133">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="78adc-133">Function Statement</span></span>](../statements/function-statement.md)

- <span data-ttu-id="78adc-134">[Instrucción de interfaz](../statements/interface-statement.md) de una interfaz anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="78adc-134">[Interface Statement](../statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="78adc-135">Property Statement</span><span class="sxs-lookup"><span data-stu-id="78adc-135">Property Statement</span></span>](../statements/property-statement.md)

- <span data-ttu-id="78adc-136">[Instrucción Structure](../statements/structure-statement.md) de una estructura anidada en una clase</span><span class="sxs-lookup"><span data-stu-id="78adc-136">[Structure Statement](../statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="78adc-137">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="78adc-137">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="78adc-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="78adc-138">See also</span></span>

- [<span data-ttu-id="78adc-139">Público</span><span class="sxs-lookup"><span data-stu-id="78adc-139">Public</span></span>](public.md)
- [<span data-ttu-id="78adc-140">Protegido</span><span class="sxs-lookup"><span data-stu-id="78adc-140">Protected</span></span>](protected.md)
- [<span data-ttu-id="78adc-141">Friend</span><span class="sxs-lookup"><span data-stu-id="78adc-141">Friend</span></span>](friend.md)
- [<span data-ttu-id="78adc-142">Privado</span><span class="sxs-lookup"><span data-stu-id="78adc-142">Private</span></span>](private.md)
- [<span data-ttu-id="78adc-143">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="78adc-143">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="78adc-144">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78adc-144">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="78adc-145">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="78adc-145">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="78adc-146">Estructuras</span><span class="sxs-lookup"><span data-stu-id="78adc-146">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="78adc-147">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="78adc-147">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
