---
description: 'Más información sobre: cláusula Implements (Visual Basic)'
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
ms.openlocfilehash: 360d8812a7c49d6462818246b1448e171dcd597f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769005"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="afdb5-103">Implements (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afdb5-103">Implements Clause (Visual Basic)</span></span>

<span data-ttu-id="afdb5-104">Indica que un miembro de clase o estructura proporciona la implementación para un miembro definido en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="afdb5-104">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afdb5-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="afdb5-105">Remarks</span></span>  

<span data-ttu-id="afdb5-106">La `Implements` palabra clave no es lo mismo que la [instrucción Implements](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="afdb5-106">The `Implements` keyword is not the same as the [Implements Statement](implements-statement.md).</span></span> <span data-ttu-id="afdb5-107">La instrucción se usa `Implements` para especificar que una clase o estructura implementa una o más interfaces y, a continuación, para cada miembro, se usa la `Implements` palabra clave para especificar qué interfaz y qué miembro implementa.</span><span class="sxs-lookup"><span data-stu-id="afdb5-107">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="afdb5-108">Si una clase o estructura implementa una interfaz, debe incluir la `Implements` instrucción inmediatamente después de la instrucción de [clase](class-statement.md) o [instrucción de estructura](structure-statement.md), y debe implementar todos los miembros definidos por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="afdb5-108">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](class-statement.md) or [Structure Statement](structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="afdb5-109">Reimplementación</span><span class="sxs-lookup"><span data-stu-id="afdb5-109">Reimplementation</span></span>  

<span data-ttu-id="afdb5-110">En una clase derivada, puede volver a implementar un miembro de interfaz que la clase base ya ha implementado.</span><span class="sxs-lookup"><span data-stu-id="afdb5-110">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="afdb5-111">Esto no es lo mismo que reemplazar el miembro de clase base en los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="afdb5-111">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="afdb5-112">No es necesario [reemplazar](../modifiers/overridable.md) el miembro de la clase base para que se pueda volver a implementar.</span><span class="sxs-lookup"><span data-stu-id="afdb5-112">The base class member does not need to be [Overridable](../modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="afdb5-113">Puede volver a implementar el miembro con un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="afdb5-113">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="afdb5-114">La `Implements` palabra clave se puede usar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="afdb5-114">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="afdb5-115">Event (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="afdb5-115">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="afdb5-116">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="afdb5-116">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="afdb5-117">Property Statement</span><span class="sxs-lookup"><span data-stu-id="afdb5-117">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="afdb5-118">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="afdb5-118">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="afdb5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="afdb5-119">See also</span></span>

- [<span data-ttu-id="afdb5-120">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="afdb5-120">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="afdb5-121">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="afdb5-121">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="afdb5-122">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="afdb5-122">Class Statement</span></span>](class-statement.md)
- [<span data-ttu-id="afdb5-123">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="afdb5-123">Structure Statement</span></span>](structure-statement.md)
