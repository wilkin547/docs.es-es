---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 5600744aeca79a54f51a1f9ecd0ef00fed4b00fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351330"
---
# <a name="private-visual-basic"></a><span data-ttu-id="c970d-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c970d-102">Private (Visual Basic)</span></span>
<span data-ttu-id="c970d-103">Especifica que solo se puede tener acceso a uno o varios elementos de programación declarados desde dentro del contexto de declaración, incluido desde dentro de cualquier tipo contenido.</span><span class="sxs-lookup"><span data-stu-id="c970d-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c970d-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c970d-104">Remarks</span></span>  
 <span data-ttu-id="c970d-105">Si un elemento de programación representa la funcionalidad de propiedad o contiene datos confidenciales, normalmente querrá limitar el acceso a él lo máximo posible.</span><span class="sxs-lookup"><span data-stu-id="c970d-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="c970d-106">Para lograr la limitación máxima, solo se permite el módulo, la clase o la estructura que la define para tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="c970d-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="c970d-107">Para limitar el acceso a un elemento de esta manera, puede declararlo con `Private`.</span><span class="sxs-lookup"><span data-stu-id="c970d-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="c970d-108">También puede usar el modificador de acceso [protegido privado](private-protected.md) , que hace que un miembro sea accesible desde dentro de esa clase y desde las clases derivadas que se encuentran en el ensamblado que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c970d-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="c970d-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="c970d-109">Rules</span></span>  

- <span data-ttu-id="c970d-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="c970d-110">**Declaration Context.**</span></span> <span data-ttu-id="c970d-111">Solo se puede usar `Private` en un nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="c970d-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="c970d-112">Esto significa que el contexto de la declaración de un elemento `Private` debe ser un módulo, una clase o una estructura, y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c970d-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c970d-113">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="c970d-113">Behavior</span></span>  
  
- <span data-ttu-id="c970d-114">**Nivel de acceso.**</span><span class="sxs-lookup"><span data-stu-id="c970d-114">**Access Level.**</span></span> <span data-ttu-id="c970d-115">Todo el código dentro de un contexto de declaración puede tener acceso a sus elementos `Private`.</span><span class="sxs-lookup"><span data-stu-id="c970d-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="c970d-116">Esto incluye el código dentro de un tipo contenido, como una clase anidada o una expresión de asignación en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="c970d-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="c970d-117">Ningún código fuera del contexto de la declaración puede tener acceso a sus elementos `Private`.</span><span class="sxs-lookup"><span data-stu-id="c970d-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="c970d-118">**Modificadores de acceso.**</span><span class="sxs-lookup"><span data-stu-id="c970d-118">**Access Modifiers.**</span></span> <span data-ttu-id="c970d-119">Las palabras clave que especifican el nivel de acceso se denominan *modificadores de acceso*.</span><span class="sxs-lookup"><span data-stu-id="c970d-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="c970d-120">Para obtener una comparación de los modificadores de acceso, vea [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c970d-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="c970d-121">El modificador `Private` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c970d-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c970d-122">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="c970d-123">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="c970d-124">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="c970d-125">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="c970d-126">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="c970d-127">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="c970d-128">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="c970d-129">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="c970d-130">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="c970d-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="c970d-132">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="c970d-133">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c970d-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c970d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c970d-134">See also</span></span>

- [<span data-ttu-id="c970d-135">Public</span><span class="sxs-lookup"><span data-stu-id="c970d-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="c970d-136">Protected</span><span class="sxs-lookup"><span data-stu-id="c970d-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="c970d-137">Friend</span><span class="sxs-lookup"><span data-stu-id="c970d-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="c970d-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="c970d-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="c970d-139">[Protected Friend](./protected-friend.md)    [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="c970d-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="c970d-140">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c970d-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="c970d-141">Estructuras</span><span class="sxs-lookup"><span data-stu-id="c970d-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c970d-142">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="c970d-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
