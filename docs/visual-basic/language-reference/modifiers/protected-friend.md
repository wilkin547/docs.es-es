---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151780"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="6a9a4-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a9a4-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="6a9a4-103">La combinación de palabras claves `Protected Friend` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="6a9a4-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="6a9a4-104">Concede tanto [Friend](friend.md) acceso y [Protected](protected.md) acceso a los elementos declarados, para que sean accesibles desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="6a9a4-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="6a9a4-105">Puede especificar `Protected Friend` solo en los miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no se puede heredar.</span><span class="sxs-lookup"><span data-stu-id="6a9a4-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="6a9a4-106">En Visual Studio, seleccione Ayuda de F1 en `protected friend` proporciona ayuda para cualquiera [protegido](protected.md) o [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="6a9a4-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="6a9a4-107">El IDE elige el token solo bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="6a9a4-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="6a9a4-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="6a9a4-108">Rules</span></span>

- <span data-ttu-id="6a9a4-109">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="6a9a4-109">**Declaration Context.**</span></span> <span data-ttu-id="6a9a4-110">Puede usar `Protected Friend` sólo en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="6a9a4-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="6a9a4-111">Esto significa que el contexto de declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6a9a4-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="6a9a4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a9a4-112">See also</span></span>

- [<span data-ttu-id="6a9a4-113">Public</span><span class="sxs-lookup"><span data-stu-id="6a9a4-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="6a9a4-114">Protected</span><span class="sxs-lookup"><span data-stu-id="6a9a4-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="6a9a4-115">Friend</span><span class="sxs-lookup"><span data-stu-id="6a9a4-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="6a9a4-116">Private</span><span class="sxs-lookup"><span data-stu-id="6a9a4-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="6a9a4-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="6a9a4-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="6a9a4-118">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6a9a4-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="6a9a4-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6a9a4-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="6a9a4-120">Estructuras</span><span class="sxs-lookup"><span data-stu-id="6a9a4-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6a9a4-121">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="6a9a4-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
