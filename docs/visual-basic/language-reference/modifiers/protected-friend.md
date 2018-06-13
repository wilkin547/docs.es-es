---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306550"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="b5714-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5714-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="b5714-103">El `Protected Friend` combinación de palabra clave es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="b5714-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="b5714-104">Confiere ambos [Friend](friend.md) acceso y [Protected](protected.md) acceso a los elementos declarados, para que sean accesibles desde cualquier lugar en el mismo ensamblado, desde su propia clase y desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="b5714-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="b5714-105">Puede especificar `Protected Friend` sólo en los miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="b5714-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="b5714-106">En Visual Studio, seleccione Ayuda de F1 en `protected friend` proporciona ayuda para cualquiera [protegido](protected.md) o [friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="b5714-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="b5714-107">El IDE elige el token único en el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="b5714-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="b5714-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="b5714-108">Rules</span></span>

- <span data-ttu-id="b5714-109">**Contexto de la declaración.**</span><span class="sxs-lookup"><span data-stu-id="b5714-109">**Declaration Context.**</span></span> <span data-ttu-id="b5714-110">Puede usar `Protected Friend` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="b5714-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="b5714-111">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, espacio de nombres, interfaz, módulo, estructura o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b5714-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b5714-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5714-112">See Also</span></span>

[<span data-ttu-id="b5714-113">Public</span><span class="sxs-lookup"><span data-stu-id="b5714-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="b5714-114">Protected</span><span class="sxs-lookup"><span data-stu-id="b5714-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="b5714-115">[Friend](friend.md) </span><span class="sxs-lookup"><span data-stu-id="b5714-115">[Friend](friend.md) </span></span>  
[<span data-ttu-id="b5714-116">Private</span><span class="sxs-lookup"><span data-stu-id="b5714-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="b5714-117">[Privado protegido](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="b5714-117">[Private Protected](./private-protected.md) </span></span>  
[<span data-ttu-id="b5714-118">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5714-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="b5714-119">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="b5714-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="b5714-120">Estructuras</span><span class="sxs-lookup"><span data-stu-id="b5714-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="b5714-121">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="b5714-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
