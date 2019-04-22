---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 91a1cedc66fd66e336b6e7976ad87ad638cb43c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816891"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="3d4d0-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d4d0-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="3d4d0-103">Especifica que una propiedad o procedimiento puede reemplazarse por una propiedad con el mismo nombre o un procedimiento en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d4d0-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d4d0-104">Remarks</span></span>  
 <span data-ttu-id="3d4d0-105">El `Overridable` modificador permite que una propiedad o método en una clase que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="3d4d0-106">El [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modificador evita que una propiedad o método que se invalida en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="3d4d0-107">Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="3d4d0-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="3d4d0-108">Si el `Overridable` o `NotOverridable` modificador no se especifica, el valor predeterminado depende de si la propiedad o método invalida un método o propiedad de clase base.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="3d4d0-109">Si la propiedad o método reemplaza un método o propiedad de clase base, el valor predeterminado es `Overridable`; en caso contrario, es `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="3d4d0-110">Puede ocultar o reemplazar para volver a definir un elemento heredado, pero hay diferencias significativas entre los dos enfoques.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="3d4d0-111">Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="3d4d0-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="3d4d0-112">Un elemento que se puede invalidar a veces se conoce como un *virtual* elemento.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="3d4d0-113">Si se puede invalidar, pero no tiene que ser, a veces también se denomina un *concreta* elemento.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="3d4d0-114">Puede usar `Overridable` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="3d4d0-115">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="3d4d0-115">Combined Modifiers</span></span>  
 <span data-ttu-id="3d4d0-116">No puede especificar `Overridable` o `NotOverridable` para un `Private` método.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="3d4d0-117">No puede especificar `Overridable` junto con `MustOverride`, `NotOverridable`, o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="3d4d0-118">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="3d4d0-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="3d4d0-119">Uso</span><span class="sxs-lookup"><span data-stu-id="3d4d0-119">Usage</span></span>  
 <span data-ttu-id="3d4d0-120">El modificador `Overridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d4d0-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="3d4d0-121">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3d4d0-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="3d4d0-122">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3d4d0-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="3d4d0-123">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3d4d0-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d4d0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d4d0-124">See also</span></span>

- [<span data-ttu-id="3d4d0-125">Modificadores</span><span class="sxs-lookup"><span data-stu-id="3d4d0-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="3d4d0-126">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="3d4d0-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="3d4d0-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="3d4d0-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="3d4d0-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="3d4d0-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="3d4d0-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="3d4d0-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="3d4d0-130">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3d4d0-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="3d4d0-131">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d4d0-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
