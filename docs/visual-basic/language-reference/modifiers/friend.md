---
description: 'Más información acerca de: Friend (Visual Basic)'
title: Friend
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: ef2444555c05d6a4b24048316e282d269d4b7f1b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774595"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="8f6cd-103">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f6cd-103">Friend (Visual Basic)</span></span>

<span data-ttu-id="8f6cd-104">Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del ensamblado que contiene su declaración.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-104">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f6cd-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8f6cd-105">Remarks</span></span>  

 <span data-ttu-id="8f6cd-106">En muchos casos, desea que los elementos de programación, como clases y estructuras, se usen en todo el ensamblado, no solo en el componente que los declara.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-106">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="8f6cd-107">Sin embargo, es posible que no desee que el código fuera del ensamblado tenga acceso a ellos (por ejemplo, si la aplicación es propietaria).</span><span class="sxs-lookup"><span data-stu-id="8f6cd-107">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="8f6cd-108">Si desea limitar el acceso a un elemento de esta manera, puede declararlo mediante el `Friend` modificador.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-108">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="8f6cd-109">El código de otras clases, estructuras y módulos que se compilan en el mismo ensamblado pueden tener acceso a todos los `Friend` elementos de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-109">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="8f6cd-110">`Friend` el acceso es a menudo el nivel preferido para los elementos de programación de una aplicación y `Friend` es el nivel de acceso predeterminado de una interfaz, un módulo, una clase o una estructura.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-110">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="8f6cd-111">Solo se puede usar `Friend` en el nivel de módulo, interfaz o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-111">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="8f6cd-112">Por consiguiente, el contexto de la declaración de un `Friend` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura; no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-112">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="8f6cd-113">También puede usar el modificador de acceso [Friend protegido](protected-friend.md) , que hace que un miembro de clase sea accesible desde dentro de esa clase, desde las clases derivadas y desde el mismo ensamblado en el que se define la clase.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-113">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="8f6cd-114">Para restringir el acceso a un miembro de dentro de su clase y de las clases derivadas en el mismo ensamblado, se utiliza el modificador de acceso [protegido privado](private-protected.md) .</span><span class="sxs-lookup"><span data-stu-id="8f6cd-114">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="8f6cd-115">Para obtener una comparación de `Friend` y los demás modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8f6cd-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f6cd-116">Puede especificar que otro ensamblado es un ensamblado de confianza, lo que le permite tener acceso a todos los tipos y miembros marcados como `Friend` .</span><span class="sxs-lookup"><span data-stu-id="8f6cd-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="8f6cd-117">Para más información, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="8f6cd-117">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="8f6cd-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f6cd-118">Example</span></span>  

 <span data-ttu-id="8f6cd-119">La siguiente clase usa el `Friend` modificador para permitir que otros elementos de programación del mismo ensamblado tengan acceso a determinados miembros.</span><span class="sxs-lookup"><span data-stu-id="8f6cd-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="8f6cd-120">Uso</span><span class="sxs-lookup"><span data-stu-id="8f6cd-120">Usage</span></span>  

 <span data-ttu-id="8f6cd-121">Puede usar el `Friend` modificador en estos contextos:</span><span class="sxs-lookup"><span data-stu-id="8f6cd-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="8f6cd-122">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="8f6cd-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="8f6cd-123">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="8f6cd-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="8f6cd-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="8f6cd-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="8f6cd-125">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8f6cd-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="8f6cd-126">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="8f6cd-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="8f6cd-127">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="8f6cd-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="8f6cd-128">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8f6cd-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="8f6cd-129">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="8f6cd-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="8f6cd-130">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="8f6cd-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="8f6cd-131">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8f6cd-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="8f6cd-132">Property Statement</span><span class="sxs-lookup"><span data-stu-id="8f6cd-132">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="8f6cd-133">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8f6cd-133">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="8f6cd-134">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="8f6cd-134">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f6cd-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f6cd-135">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="8f6cd-136">Público</span><span class="sxs-lookup"><span data-stu-id="8f6cd-136">Public</span></span>](public.md)
- [<span data-ttu-id="8f6cd-137">Protegido</span><span class="sxs-lookup"><span data-stu-id="8f6cd-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="8f6cd-138">Privado</span><span class="sxs-lookup"><span data-stu-id="8f6cd-138">Private</span></span>](private.md)
- [<span data-ttu-id="8f6cd-139">Private Protected</span><span class="sxs-lookup"><span data-stu-id="8f6cd-139">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="8f6cd-140">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="8f6cd-140">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="8f6cd-141">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f6cd-141">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="8f6cd-142">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8f6cd-142">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="8f6cd-143">Estructuras</span><span class="sxs-lookup"><span data-stu-id="8f6cd-143">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="8f6cd-144">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="8f6cd-144">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
