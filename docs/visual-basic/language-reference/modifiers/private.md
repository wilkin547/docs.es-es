---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 40b64b8d2b6306d458b7a9cc657c5b7dc4270eb2
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2018
ms.locfileid: "34234560"
---
# <a name="private-visual-basic"></a><span data-ttu-id="92988-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92988-102">Private (Visual Basic)</span></span>
<span data-ttu-id="92988-103">Especifica que uno o varios elementos de programación declarados son accesibles únicamente desde dentro de su contexto de declaración, incluyendo desde dentro de los tipos contenidos.</span><span class="sxs-lookup"><span data-stu-id="92988-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92988-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92988-104">Remarks</span></span>  
 <span data-ttu-id="92988-105">Si un elemento de programación representa la funcionalidad de propietario, o contiene datos confidenciales, normalmente es conveniente limitar el acceso a él como estrictamente como sea posible.</span><span class="sxs-lookup"><span data-stu-id="92988-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="92988-106">Alcanzar la limitación máxima al permitir que el módulo, clase o estructura que define para tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="92988-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="92988-107">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private`.</span><span class="sxs-lookup"><span data-stu-id="92988-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="92988-108">También puede usar el [privada protegida](private-protected.md) modificador de acceso, lo que hace que un miembro accesible desde dentro de esa clase y desde las clases derivadas que se encuentra en el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="92988-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="92988-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="92988-109">Rules</span></span>  

-   <span data-ttu-id="92988-110">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="92988-110">**Declaration Context.**</span></span> <span data-ttu-id="92988-111">Solo se puede usar `Private` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="92988-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="92988-112">Esto significa que el contexto de la declaración de un `Private` elemento debe ser un módulo, clase o estructura y no puede ser un archivo de código fuente, el espacio de nombres, la interfaz o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="92988-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="92988-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="92988-113">Behavior</span></span>  
  
-   <span data-ttu-id="92988-114">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="92988-114">**Access Level.**</span></span> <span data-ttu-id="92988-115">Puede tener acceso todo el código dentro de un contexto de declaración su `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="92988-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="92988-116">Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="92988-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="92988-117">Ningún código fuera del contexto de declaración puede tener acceso a su `Private` elementos.</span><span class="sxs-lookup"><span data-stu-id="92988-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="92988-118">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="92988-118">**Access Modifiers.**</span></span> <span data-ttu-id="92988-119">Las palabras clave que especifican el nivel de acceso se denominan *los modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="92988-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="92988-120">Para obtener una comparación de los modificadores de acceso, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="92988-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="92988-121">El modificador `Private` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="92988-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="92988-122">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="92988-123">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="92988-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="92988-125">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="92988-126">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="92988-127">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="92988-128">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="92988-129">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="92988-130">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="92988-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="92988-132">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="92988-133">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="92988-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="92988-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="92988-134">See Also</span></span>  
 [<span data-ttu-id="92988-135">Public</span><span class="sxs-lookup"><span data-stu-id="92988-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="92988-136">Protected</span><span class="sxs-lookup"><span data-stu-id="92988-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="92988-137">Friend</span><span class="sxs-lookup"><span data-stu-id="92988-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 <span data-ttu-id="92988-138">[Privado protegido](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="92988-138">[Private Protected](./private-protected.md) </span></span>  
 <span data-ttu-id="92988-139">[Protected Friend](./protected-friend.md)[tener acceso a niveles en Visual Basic    ](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="92988-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>  
 [<span data-ttu-id="92988-140">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="92988-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="92988-141">Estructuras</span><span class="sxs-lookup"><span data-stu-id="92988-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="92988-142">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="92988-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
