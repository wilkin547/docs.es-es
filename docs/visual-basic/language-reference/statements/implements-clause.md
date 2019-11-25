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
ms.openlocfilehash: f114aee75356e59eafd9d3ba6af9c64402cb374f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345870"
---
# <a name="implements-clause-visual-basic"></a><span data-ttu-id="2dcfc-102">Implements (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-102">Implements Clause (Visual Basic)</span></span>
<span data-ttu-id="2dcfc-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-103">Indicates that a class or structure member is providing the implementation for a member defined in an interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dcfc-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2dcfc-104">Remarks</span></span>  
<span data-ttu-id="2dcfc-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2dcfc-105">The `Implements` keyword is not the same as the [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span> <span data-ttu-id="2dcfc-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-106">You use the `Implements` statement to specify that a class or structure implements one or more interfaces, and then for each member you use the `Implements` keyword to specify which interface and which member it implements.</span></span>

<span data-ttu-id="2dcfc-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-107">If a class or structure implements an interface, it must include the `Implements` statement immediately after the [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) or [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md), and it must implement all the members defined by the interface.</span></span>

## <a name="reimplementation"></a><span data-ttu-id="2dcfc-108">Reimplementation</span><span class="sxs-lookup"><span data-stu-id="2dcfc-108">Reimplementation</span></span>  
<span data-ttu-id="2dcfc-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-109">In a derived class, you can reimplement an interface member that the base class has already implemented.</span></span> <span data-ttu-id="2dcfc-110">This is different from overriding the base class member in the following respects:</span><span class="sxs-lookup"><span data-stu-id="2dcfc-110">This is different from overriding the base class member in the following respects:</span></span>

- <span data-ttu-id="2dcfc-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-111">The base class member does not need to be [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) to be reimplemented.</span></span>
- <span data-ttu-id="2dcfc-112">You can reimplement the member with a different name.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-112">You can reimplement the member with a different name.</span></span>

<span data-ttu-id="2dcfc-113">The `Implements` keyword can be used in the following contexts:</span><span class="sxs-lookup"><span data-stu-id="2dcfc-113">The `Implements` keyword can be used in the following contexts:</span></span>

- [<span data-ttu-id="2dcfc-114">Event (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="2dcfc-115">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-115">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="2dcfc-116">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-116">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="2dcfc-117">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-117">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2dcfc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dcfc-118">See also</span></span>

- [<span data-ttu-id="2dcfc-119">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-119">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="2dcfc-120">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-120">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="2dcfc-121">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="2dcfc-122">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2dcfc-122">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
