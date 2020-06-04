---
title: Público
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415354"
---
# <a name="public-visual-basic"></a><span data-ttu-id="d6e90-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6e90-102">Public (Visual Basic)</span></span>
<span data-ttu-id="d6e90-103">Especifica que uno o varios elementos de programación declarados no tienen restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="d6e90-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e90-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d6e90-104">Remarks</span></span>  
 <span data-ttu-id="d6e90-105">Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación sean accesibles por cualquier código que interopere con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d6e90-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="d6e90-106">Para atribuir este acceso ilimitado en un elemento, puede declararlo con `Public` .</span><span class="sxs-lookup"><span data-stu-id="d6e90-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="d6e90-107">El acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él.</span><span class="sxs-lookup"><span data-stu-id="d6e90-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="d6e90-108">Tenga en cuenta que el nivel de acceso de un elemento declarado dentro de una interfaz, módulo, clase o estructura tiene como valor predeterminado `Public` si no lo declara de otro modo.</span><span class="sxs-lookup"><span data-stu-id="d6e90-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d6e90-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="d6e90-109">Rules</span></span>  
  
- <span data-ttu-id="d6e90-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="d6e90-110">**Declaration Context.**</span></span> <span data-ttu-id="d6e90-111">Solo se puede usar `Public` en el nivel de módulo, interfaz o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d6e90-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="d6e90-112">Esto significa que el contexto de la declaración de un `Public` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura, y no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d6e90-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d6e90-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d6e90-113">Behavior</span></span>  
  
- <span data-ttu-id="d6e90-114">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="d6e90-114">**Access Level.**</span></span> <span data-ttu-id="d6e90-115">Todo el código que puede tener acceso a un módulo, clase o estructura puede tener acceso a sus `Public` elementos.</span><span class="sxs-lookup"><span data-stu-id="d6e90-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="d6e90-116">**Acceso predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="d6e90-116">**Default Access.**</span></span> <span data-ttu-id="d6e90-117">Las variables locales dentro de un procedimiento tienen como valor predeterminado el acceso público y no se pueden usar modificadores de acceso en ellas.</span><span class="sxs-lookup"><span data-stu-id="d6e90-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="d6e90-118">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="d6e90-118">**Access Modifiers.**</span></span> <span data-ttu-id="d6e90-119">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="d6e90-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="d6e90-120">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d6e90-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="d6e90-121">El modificador `Public` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6e90-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d6e90-122">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="d6e90-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="d6e90-123">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="d6e90-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="d6e90-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d6e90-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="d6e90-125">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6e90-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="d6e90-126">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="d6e90-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="d6e90-127">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="d6e90-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="d6e90-128">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6e90-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="d6e90-129">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="d6e90-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="d6e90-130">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="d6e90-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="d6e90-131">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6e90-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="d6e90-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d6e90-132">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 [<span data-ttu-id="d6e90-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d6e90-133">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="d6e90-134">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6e90-134">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="d6e90-135">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="d6e90-135">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d6e90-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6e90-136">See also</span></span>

- [<span data-ttu-id="d6e90-137">Contra</span><span class="sxs-lookup"><span data-stu-id="d6e90-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="d6e90-138">Respecto</span><span class="sxs-lookup"><span data-stu-id="d6e90-138">Friend</span></span>](friend.md)
- [<span data-ttu-id="d6e90-139">Privado</span><span class="sxs-lookup"><span data-stu-id="d6e90-139">Private</span></span>](private.md)
- [<span data-ttu-id="d6e90-140">Privado protegido</span><span class="sxs-lookup"><span data-stu-id="d6e90-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="d6e90-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d6e90-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="d6e90-142">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6e90-142">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d6e90-143">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d6e90-143">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d6e90-144">Estructuras</span><span class="sxs-lookup"><span data-stu-id="d6e90-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d6e90-145">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="d6e90-145">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
