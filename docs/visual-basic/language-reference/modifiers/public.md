---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 0c85564503f3c83e436044cd92ee3014945f1ef3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818389"
---
# <a name="public-visual-basic"></a><span data-ttu-id="f3c57-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3c57-102">Public (Visual Basic)</span></span>
<span data-ttu-id="f3c57-103">Especifica que uno o varios elementos de programación declarados no tienen acceso restricciones.</span><span class="sxs-lookup"><span data-stu-id="f3c57-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3c57-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3c57-104">Remarks</span></span>  
 <span data-ttu-id="f3c57-105">Si va a publicar un componente o un conjunto de componentes, como una biblioteca de clases, normalmente desea que los elementos de programación para ser accesibles para cualquier código que interactúa con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f3c57-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="f3c57-106">Para otorgar este acceso ilimitado en un elemento, puede declarar con `Public`.</span><span class="sxs-lookup"><span data-stu-id="f3c57-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="f3c57-107">Acceso público es el nivel normal para un elemento de programación cuando no es necesario limitar el acceso a él.</span><span class="sxs-lookup"><span data-stu-id="f3c57-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="f3c57-108">Tenga en cuenta que el nivel de acceso de un elemento se declara dentro de una interfaz, módulo, clase o estructura el valor predeterminado es `Public` si no se declara en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="f3c57-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f3c57-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="f3c57-109">Rules</span></span>  
  
-   <span data-ttu-id="f3c57-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="f3c57-110">**Declaration Context.**</span></span> <span data-ttu-id="f3c57-111">Puede usar `Public` sólo en el nivel de módulo, interfaz o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f3c57-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="f3c57-112">Esto significa que el contexto de declaración de un `Public` elemento debe ser un archivo de código fuente, el espacio de nombres, la interfaz, el módulo, la clase o estructura y no puede ser un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f3c57-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f3c57-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="f3c57-113">Behavior</span></span>  
  
-   <span data-ttu-id="f3c57-114">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="f3c57-114">**Access Level.**</span></span> <span data-ttu-id="f3c57-115">Puede tener acceso todo el código que puede tener acceso a un módulo, clase o estructura su `Public` elementos.</span><span class="sxs-lookup"><span data-stu-id="f3c57-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="f3c57-116">**Acceso predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="f3c57-116">**Default Access.**</span></span> <span data-ttu-id="f3c57-117">Variables locales dentro de una procedimiento de forma predeterminada al acceso público y no pueden utilizar cualquier modificador de acceso en ellas.</span><span class="sxs-lookup"><span data-stu-id="f3c57-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="f3c57-118">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="f3c57-118">**Access Modifiers.**</span></span> <span data-ttu-id="f3c57-119">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="f3c57-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="f3c57-120">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f3c57-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="f3c57-121">El modificador `Public` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f3c57-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="f3c57-122">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="f3c57-123">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="f3c57-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="f3c57-125">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="f3c57-126">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="f3c57-127">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="f3c57-128">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="f3c57-129">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="f3c57-130">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="f3c57-131">Module (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="f3c57-132">Operator (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="f3c57-133">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="f3c57-134">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="f3c57-135">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f3c57-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f3c57-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3c57-136">See also</span></span>

- [<span data-ttu-id="f3c57-137">Protected</span><span class="sxs-lookup"><span data-stu-id="f3c57-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="f3c57-138">Friend</span><span class="sxs-lookup"><span data-stu-id="f3c57-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="f3c57-139">Private</span><span class="sxs-lookup"><span data-stu-id="f3c57-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="f3c57-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="f3c57-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="f3c57-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="f3c57-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="f3c57-142">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3c57-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f3c57-143">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="f3c57-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="f3c57-144">Estructuras</span><span class="sxs-lookup"><span data-stu-id="f3c57-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="f3c57-145">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="f3c57-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
