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
ms.openlocfilehash: f2b6a126435b111ef56ee2a9870ea6fbddf87901
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867681"
---
# <a name="public-visual-basic"></a><span data-ttu-id="d48aa-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d48aa-102">Public (Visual Basic)</span></span>

<span data-ttu-id="d48aa-103">Especifica que uno o varios elementos de programación declarados no tienen restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="d48aa-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d48aa-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d48aa-104">Remarks</span></span>  

 <span data-ttu-id="d48aa-105">Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación sean accesibles por cualquier código que interopere con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d48aa-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="d48aa-106">Para atribuir este acceso ilimitado en un elemento, puede declararlo con `Public` .</span><span class="sxs-lookup"><span data-stu-id="d48aa-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="d48aa-107">El acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él.</span><span class="sxs-lookup"><span data-stu-id="d48aa-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="d48aa-108">Tenga en cuenta que el nivel de acceso de un elemento declarado dentro de una interfaz, módulo, clase o estructura tiene como valor predeterminado `Public` si no lo declara de otro modo.</span><span class="sxs-lookup"><span data-stu-id="d48aa-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d48aa-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="d48aa-109">Rules</span></span>  
  
- <span data-ttu-id="d48aa-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="d48aa-110">**Declaration Context.**</span></span> <span data-ttu-id="d48aa-111">Solo se puede usar `Public` en el nivel de módulo, interfaz o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d48aa-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="d48aa-112">Esto significa que el contexto de la declaración de un `Public` elemento debe ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una clase o una estructura, y no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d48aa-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d48aa-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="d48aa-113">Behavior</span></span>  
  
- <span data-ttu-id="d48aa-114">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="d48aa-114">**Access Level.**</span></span> <span data-ttu-id="d48aa-115">Todo el código que puede tener acceso a un módulo, clase o estructura puede tener acceso a sus `Public` elementos.</span><span class="sxs-lookup"><span data-stu-id="d48aa-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="d48aa-116">**Acceso predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="d48aa-116">**Default Access.**</span></span> <span data-ttu-id="d48aa-117">Las variables locales dentro de un procedimiento tienen como valor predeterminado el acceso público y no se pueden usar modificadores de acceso en ellas.</span><span class="sxs-lookup"><span data-stu-id="d48aa-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="d48aa-118">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="d48aa-118">**Access Modifiers.**</span></span> <span data-ttu-id="d48aa-119">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="d48aa-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="d48aa-120">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d48aa-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="d48aa-121">El modificador `Public` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d48aa-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d48aa-122">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="d48aa-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="d48aa-123">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="d48aa-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="d48aa-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d48aa-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="d48aa-125">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d48aa-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="d48aa-126">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="d48aa-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="d48aa-127">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="d48aa-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="d48aa-128">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d48aa-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="d48aa-129">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="d48aa-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="d48aa-130">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="d48aa-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="d48aa-131">Module (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d48aa-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="d48aa-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="d48aa-132">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 [<span data-ttu-id="d48aa-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d48aa-133">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="d48aa-134">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d48aa-134">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="d48aa-135">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="d48aa-135">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d48aa-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d48aa-136">See also</span></span>

- [<span data-ttu-id="d48aa-137">Contra</span><span class="sxs-lookup"><span data-stu-id="d48aa-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="d48aa-138">Friend</span><span class="sxs-lookup"><span data-stu-id="d48aa-138">Friend</span></span>](friend.md)
- [<span data-ttu-id="d48aa-139">Privado</span><span class="sxs-lookup"><span data-stu-id="d48aa-139">Private</span></span>](private.md)
- [<span data-ttu-id="d48aa-140">Privado protegido</span><span class="sxs-lookup"><span data-stu-id="d48aa-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="d48aa-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d48aa-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="d48aa-142">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d48aa-142">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="d48aa-143">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="d48aa-143">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="d48aa-144">Estructuras</span><span class="sxs-lookup"><span data-stu-id="d48aa-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d48aa-145">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="d48aa-145">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
