---
description: 'Más información acerca de: protected (Visual Basic)'
title: Protegido
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 74a695e7c8ff06543a7118c935365e31af258171
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700941"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="68d43-103">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68d43-103">Protected (Visual Basic)</span></span>

<span data-ttu-id="68d43-104">Modificador de acceso de miembro que especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro de su propia clase o desde una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="68d43-104">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="68d43-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="68d43-105">Remarks</span></span>

<span data-ttu-id="68d43-106">A veces, un elemento de programación declarado en una clase contiene datos confidenciales o código restringido, y desea limitar el acceso al elemento.</span><span class="sxs-lookup"><span data-stu-id="68d43-106">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="68d43-107">Sin embargo, si la clase es heredable y espera una jerarquía de clases derivadas, podría ser necesario que estas clases derivadas tengan acceso a los datos o al código.</span><span class="sxs-lookup"><span data-stu-id="68d43-107">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="68d43-108">En tal caso, desea que el elemento sea accesible tanto desde la clase base como desde todas las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="68d43-108">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="68d43-109">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Protected` .</span><span class="sxs-lookup"><span data-stu-id="68d43-109">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="68d43-110">El `Protected` modificador de acceso se puede combinar con otros dos modificadores:</span><span class="sxs-lookup"><span data-stu-id="68d43-110">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="68d43-111">El modificador [Friend protegido](protected-friend.md) hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase.</span><span class="sxs-lookup"><span data-stu-id="68d43-111">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="68d43-112">El modificador [Private Protected](private-protected.md) hace que un miembro de clase sea accesible para los tipos derivados, pero solo dentro del ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="68d43-112">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="68d43-113">Reglas</span><span class="sxs-lookup"><span data-stu-id="68d43-113">Rules</span></span>

<span data-ttu-id="68d43-114">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="68d43-114">**Declaration Context.**</span></span> <span data-ttu-id="68d43-115">Solo se puede usar `Protected` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="68d43-115">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="68d43-116">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="68d43-116">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="68d43-117">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="68d43-117">Behavior</span></span>

- <span data-ttu-id="68d43-118">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="68d43-118">**Access Level.**</span></span> <span data-ttu-id="68d43-119">Todo el código de una clase puede tener acceso a sus elementos.</span><span class="sxs-lookup"><span data-stu-id="68d43-119">All code in a class can access its elements.</span></span> <span data-ttu-id="68d43-120">El código de cualquier clase que deriva de una clase base puede tener acceso a todos los `Protected` elementos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="68d43-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="68d43-121">Esto es cierto para todas las generaciones de derivación.</span><span class="sxs-lookup"><span data-stu-id="68d43-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="68d43-122">Esto significa que una clase puede tener acceso a los `Protected` elementos de la clase base de la clase base, etc.</span><span class="sxs-lookup"><span data-stu-id="68d43-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="68d43-123">El acceso protegido no es un superconjunto o subconjunto de acceso de confianza.</span><span class="sxs-lookup"><span data-stu-id="68d43-123">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="68d43-124">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="68d43-124">**Access Modifiers.**</span></span> <span data-ttu-id="68d43-125">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="68d43-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="68d43-126">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="68d43-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="68d43-127">El modificador `Protected` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="68d43-127">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="68d43-128">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="68d43-128">Class Statement</span></span>](../statements/class-statement.md)

- [<span data-ttu-id="68d43-129">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="68d43-129">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="68d43-130">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="68d43-130">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="68d43-131">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="68d43-131">Delegate Statement</span></span>](../statements/delegate-statement.md)

- [<span data-ttu-id="68d43-132">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="68d43-132">Dim Statement</span></span>](../statements/dim-statement.md)

- [<span data-ttu-id="68d43-133">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="68d43-133">Enum Statement</span></span>](../statements/enum-statement.md)

- [<span data-ttu-id="68d43-134">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="68d43-134">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="68d43-135">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="68d43-135">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="68d43-136">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="68d43-136">Interface Statement</span></span>](../statements/interface-statement.md)

- [<span data-ttu-id="68d43-137">Property Statement</span><span class="sxs-lookup"><span data-stu-id="68d43-137">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="68d43-138">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="68d43-138">Structure Statement</span></span>](../statements/structure-statement.md)

- [<span data-ttu-id="68d43-139">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="68d43-139">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="68d43-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="68d43-140">See also</span></span>

- [<span data-ttu-id="68d43-141">Público</span><span class="sxs-lookup"><span data-stu-id="68d43-141">Public</span></span>](public.md)
- [<span data-ttu-id="68d43-142">Friend</span><span class="sxs-lookup"><span data-stu-id="68d43-142">Friend</span></span>](friend.md)
- [<span data-ttu-id="68d43-143">Privado</span><span class="sxs-lookup"><span data-stu-id="68d43-143">Private</span></span>](private.md)
- [<span data-ttu-id="68d43-144">Private Protected</span><span class="sxs-lookup"><span data-stu-id="68d43-144">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="68d43-145">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="68d43-145">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="68d43-146">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="68d43-146">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="68d43-147">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="68d43-147">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="68d43-148">Estructuras</span><span class="sxs-lookup"><span data-stu-id="68d43-148">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="68d43-149">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="68d43-149">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
