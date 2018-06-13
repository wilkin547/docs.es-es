---
title: NotOverridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 3fae1a4b587c379dbc459cbc973982851e713785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600758"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="32c12-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32c12-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="32c12-103">Especifica que una propiedad o procedimiento no se puede invalidar en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32c12-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32c12-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32c12-104">Remarks</span></span>  
 <span data-ttu-id="32c12-105">El `NotOverridable` modificador impide que una propiedad o método se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32c12-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="32c12-106">El [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modificador permite que una propiedad o método en una clase para que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32c12-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="32c12-107">Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="32c12-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="32c12-108">Si el `Overridable` o `NotOverridable` modificador no se especifica, el valor predeterminado depende de si la propiedad o método invalida un método o propiedad de clase base.</span><span class="sxs-lookup"><span data-stu-id="32c12-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="32c12-109">Si la propiedad o método invalida un método o propiedad de clase base, el valor predeterminado es `Overridable`; en caso contrario, es `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="32c12-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="32c12-110">A veces se denomina un elemento que no se puede invalidar una *sellado* elemento.</span><span class="sxs-lookup"><span data-stu-id="32c12-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="32c12-111">Puede usar `NotOverridable` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="32c12-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="32c12-112">Puede especificar `NotOverridable` sólo en una propiedad o procedimiento que reemplaza otra propiedad o procedimiento, es decir, solo en combinación con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="32c12-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="32c12-113">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="32c12-113">Combined Modifiers</span></span>  
 <span data-ttu-id="32c12-114">No se puede especificar `Overridable` o `NotOverridable` para un `Private` método.</span><span class="sxs-lookup"><span data-stu-id="32c12-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="32c12-115">No se puede especificar `NotOverridable` junto con `MustOverride`, `Overridable`, o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="32c12-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="32c12-116">Uso</span><span class="sxs-lookup"><span data-stu-id="32c12-116">Usage</span></span>  
 <span data-ttu-id="32c12-117">El modificador `NotOverridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="32c12-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="32c12-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="32c12-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="32c12-119">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="32c12-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="32c12-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="32c12-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="32c12-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c12-121">See Also</span></span>  
 [<span data-ttu-id="32c12-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="32c12-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="32c12-123">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="32c12-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="32c12-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="32c12-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="32c12-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="32c12-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [<span data-ttu-id="32c12-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="32c12-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="32c12-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="32c12-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="32c12-128">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32c12-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
