---
title: Cláusula Implements
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 7c95cf76b1bac24e2a0f20857b8984d54ebbea85
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866164"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="d6769-102">Implements (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6769-102">Implements Clause (Visual Basic)</span></span>

<span data-ttu-id="d6769-103">Indica que un miembro de clase o estructura proporciona la implementación para un miembro definido en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="d6769-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6769-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6769-104">Remarks</span></span>  

<span data-ttu-id="d6769-105">La `Implements` palabra clave no es lo mismo que la [instrucción Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d6769-105">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="d6769-106">La instrucción se usa `Implements` para especificar que una clase o estructura implementa una o más interfaces y, a continuación, para cada miembro, se usa la `Implements` palabra clave para especificar qué interfaz y qué miembro implementa.</span><span class="sxs-lookup"><span data-stu-id="d6769-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="d6769-107">Si una clase o estructura implementa una interfaz, debe incluir la `Implements` instrucción inmediatamente después de la instrucción de [clase](class-statement.md) o [instrucción de estructura](structure-statement.md), y debe implementar todos los miembros definidos por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d6769-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="d6769-108">Reimplementación</span><span class="sxs-lookup"><span data-stu-id="d6769-108">Reimplementation</span></span>  

<span data-ttu-id="d6769-109">En una clase derivada, puede volver a implementar un miembro de interfaz que la clase base ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="d6769-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="d6769-110">Esto no es lo mismo que reemplazar el miembro de clase base en los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="d6769-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="d6769-111">No es necesario [reemplazar](../modifiers/overridable.md) el miembro de la clase base para que se pueda volver a implementar.</span><span class="sxs-lookup"><span data-stu-id="d6769-111">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="d6769-112">Puede volver a implementar el miembro con un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="d6769-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="d6769-113">La `Implements` palabra clave se puede usar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6769-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="d6769-114">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6769-114">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="d6769-115">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="d6769-115">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="d6769-116">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d6769-116">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="d6769-117">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="d6769-117">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d6769-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6769-118">See also</span></span>

- [<span data-ttu-id="d6769-119">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6769-119">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="d6769-120">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="d6769-120">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="d6769-121">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="d6769-121">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="d6769-122">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d6769-122">Structure Statement</span></span>](structure-statement.md)
