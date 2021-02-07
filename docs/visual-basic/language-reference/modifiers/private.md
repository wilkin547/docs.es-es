---
description: 'Más información acerca de: privado (Visual Basic)'
title: Privada
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 20dcd943856e20ccb1b7cb5c0603fa5f313d2421
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700954"
---
# <a name="private-visual-basic"></a><span data-ttu-id="3ca87-103">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ca87-103">Private (Visual Basic)</span></span>

<span data-ttu-id="3ca87-104">Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del contexto de declaración, incluido desde dentro de cualquier tipo contenido.</span><span class="sxs-lookup"><span data-stu-id="3ca87-104">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ca87-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3ca87-105">Remarks</span></span>  

 <span data-ttu-id="3ca87-106">Si un elemento de programación representa la funcionalidad de propiedad o contiene datos confidenciales, normalmente querrá limitar el acceso a él lo máximo posible.</span><span class="sxs-lookup"><span data-stu-id="3ca87-106">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="3ca87-107">Para lograr la limitación máxima, solo se permite el módulo, la clase o la estructura que la define para tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="3ca87-107">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="3ca87-108">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private` .</span><span class="sxs-lookup"><span data-stu-id="3ca87-108">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="3ca87-109">También puede usar el modificador de acceso [protegido privado](private-protected.md) , que hace que un miembro sea accesible desde dentro de esa clase y desde las clases derivadas que se encuentran en el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="3ca87-109">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="3ca87-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="3ca87-110">Rules</span></span>  

- <span data-ttu-id="3ca87-111">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="3ca87-111">**Declaration Context.**</span></span> <span data-ttu-id="3ca87-112">Solo se puede usar `Private` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="3ca87-112">You can use `Private` only at module level.</span></span> <span data-ttu-id="3ca87-113">Esto significa que el contexto de la declaración de un `Private` elemento debe ser un módulo, una clase o una estructura, y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3ca87-113">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="3ca87-114">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="3ca87-114">Behavior</span></span>  
  
- <span data-ttu-id="3ca87-115">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="3ca87-115">**Access Level.**</span></span> <span data-ttu-id="3ca87-116">Todo el código dentro de un contexto de declaración puede tener acceso a sus `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="3ca87-116">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="3ca87-117">Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="3ca87-117">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="3ca87-118">Ningún código fuera del contexto de la declaración puede tener acceso a sus `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="3ca87-118">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="3ca87-119">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="3ca87-119">**Access Modifiers.**</span></span> <span data-ttu-id="3ca87-120">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="3ca87-120">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="3ca87-121">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3ca87-121">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="3ca87-122">El modificador `Private` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ca87-122">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3ca87-123">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="3ca87-123">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="3ca87-124">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="3ca87-124">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="3ca87-125">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="3ca87-125">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="3ca87-126">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3ca87-126">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="3ca87-127">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="3ca87-127">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="3ca87-128">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="3ca87-128">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="3ca87-129">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3ca87-129">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="3ca87-130">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="3ca87-130">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="3ca87-131">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="3ca87-131">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="3ca87-132">Property Statement</span><span class="sxs-lookup"><span data-stu-id="3ca87-132">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="3ca87-133">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3ca87-133">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="3ca87-134">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="3ca87-134">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ca87-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca87-135">See also</span></span>

- [<span data-ttu-id="3ca87-136">Público</span><span class="sxs-lookup"><span data-stu-id="3ca87-136">Public</span></span>](public.md)
- [<span data-ttu-id="3ca87-137">Protegido</span><span class="sxs-lookup"><span data-stu-id="3ca87-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="3ca87-138">Friend</span><span class="sxs-lookup"><span data-stu-id="3ca87-138">Friend</span></span>](friend.md)
- [<span data-ttu-id="3ca87-139">Private Protected</span><span class="sxs-lookup"><span data-stu-id="3ca87-139">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="3ca87-140">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="3ca87-140">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="3ca87-141">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3ca87-141">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="3ca87-142">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="3ca87-142">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="3ca87-143">Estructuras</span><span class="sxs-lookup"><span data-stu-id="3ca87-143">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3ca87-144">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="3ca87-144">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
