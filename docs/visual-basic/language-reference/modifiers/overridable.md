---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7d5dd33f8591be1b4305e954e55e035882626c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="a309c-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a309c-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="a309c-103">Especifica que una propiedad o procedimiento puede reemplazarse por una propiedad con el mismo nombre o un procedimiento en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a309c-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a309c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a309c-104">Remarks</span></span>  
 <span data-ttu-id="a309c-105">El `Overridable` modificador permite que una propiedad o método en una clase para que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a309c-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="a309c-106">El [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modificador impide que una propiedad o método se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a309c-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="a309c-107">Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="a309c-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="a309c-108">Si el `Overridable` o `NotOverridable` modificador no se especifica, el valor predeterminado depende de si la propiedad o método invalida un método o propiedad de clase base.</span><span class="sxs-lookup"><span data-stu-id="a309c-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="a309c-109">Si la propiedad o método invalida un método o propiedad de clase base, el valor predeterminado es `Overridable`; en caso contrario, es `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="a309c-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="a309c-110">Puede ocultar o invalide este método para volver a definir un elemento heredado, pero hay diferencias significativas entre los dos enfoques.</span><span class="sxs-lookup"><span data-stu-id="a309c-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="a309c-111">Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="a309c-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="a309c-112">Un elemento que se puede invalidar a veces se conoce como un *virtuales* elemento.</span><span class="sxs-lookup"><span data-stu-id="a309c-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="a309c-113">Si se puede invalidar, pero no tiene que ser, a veces también se denomina un *concreta* elemento.</span><span class="sxs-lookup"><span data-stu-id="a309c-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="a309c-114">Puede usar `Overridable` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="a309c-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="a309c-115">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="a309c-115">Combined Modifiers</span></span>  
 <span data-ttu-id="a309c-116">No se puede especificar `Overridable` o `NotOverridable` para un `Private` método.</span><span class="sxs-lookup"><span data-stu-id="a309c-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="a309c-117">No se puede especificar `Overridable` junto con `MustOverride`, `NotOverridable`, o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="a309c-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="a309c-118">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="a309c-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="a309c-119">Uso</span><span class="sxs-lookup"><span data-stu-id="a309c-119">Usage</span></span>  
 <span data-ttu-id="a309c-120">El modificador `Overridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a309c-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a309c-121">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a309c-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a309c-122">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a309c-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a309c-123">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a309c-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a309c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a309c-124">See Also</span></span>  
 [<span data-ttu-id="a309c-125">Modificadores</span><span class="sxs-lookup"><span data-stu-id="a309c-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)  
 [<span data-ttu-id="a309c-126">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="a309c-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="a309c-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="a309c-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [<span data-ttu-id="a309c-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="a309c-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [<span data-ttu-id="a309c-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="a309c-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="a309c-130">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a309c-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="a309c-131">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a309c-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
