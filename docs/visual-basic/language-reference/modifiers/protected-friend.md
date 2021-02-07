---
description: 'Más información acerca de: protected Friend (Visual Basic)'
title: Protected Friend
ms.date: 05/10/2018
f1_keywords:
- vb.ProtectedFriend
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: dcc8fd2b1aa99f910f002ac05178d379532fb73d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700980"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="79c05-103">Friend protegido (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79c05-103">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="79c05-104">La combinación de palabras claves `Protected Friend` es un modificador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="79c05-104">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="79c05-105">Confiere acceso de [confianza](friend.md) y acceso [protegido](protected.md) en los elementos declarados, por lo que son accesibles desde cualquier lugar del mismo ensamblado, desde su propia clase y desde las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="79c05-105">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="79c05-106">Solo se puede especificar `Protected Friend` en miembros de clases; no se puede aplicar `Protected Friend` a los miembros de una estructura porque las estructuras no se pueden heredar.</span><span class="sxs-lookup"><span data-stu-id="79c05-106">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="79c05-107">En Visual Studio, al seleccionar la ayuda F1 en se `protected friend` proporciona ayuda para [Protected](protected.md) o [Friend](friend.md).</span><span class="sxs-lookup"><span data-stu-id="79c05-107">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="79c05-108">El IDE elige el token único bajo el cursor en lugar de la palabra compuesta.</span><span class="sxs-lookup"><span data-stu-id="79c05-108">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="79c05-109">Reglas</span><span class="sxs-lookup"><span data-stu-id="79c05-109">Rules</span></span>

<span data-ttu-id="79c05-110">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="79c05-110">**Declaration Context.**</span></span> <span data-ttu-id="79c05-111">Solo se puede usar `Protected Friend` en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="79c05-111">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="79c05-112">Esto significa que el contexto de la declaración de un `Protected` elemento debe ser una clase y no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, un módulo, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="79c05-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="79c05-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="79c05-113">See also</span></span>

- [<span data-ttu-id="79c05-114">Público</span><span class="sxs-lookup"><span data-stu-id="79c05-114">Public</span></span>](public.md)
- [<span data-ttu-id="79c05-115">Protegido</span><span class="sxs-lookup"><span data-stu-id="79c05-115">Protected</span></span>](protected.md)
- [<span data-ttu-id="79c05-116">Friend</span><span class="sxs-lookup"><span data-stu-id="79c05-116">Friend</span></span>](friend.md)
- [<span data-ttu-id="79c05-117">Privado</span><span class="sxs-lookup"><span data-stu-id="79c05-117">Private</span></span>](private.md)
- [<span data-ttu-id="79c05-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="79c05-118">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="79c05-119">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79c05-119">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="79c05-120">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="79c05-120">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="79c05-121">Estructuras</span><span class="sxs-lookup"><span data-stu-id="79c05-121">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="79c05-122">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="79c05-122">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
