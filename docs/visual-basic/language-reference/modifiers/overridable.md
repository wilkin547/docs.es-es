---
title: Overridable
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
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351401"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="e9dc5-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9dc5-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="e9dc5-103">Especifica que una propiedad o un procedimiento se puede invalidar mediante una propiedad o un procedimiento con el mismo nombre en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9dc5-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9dc5-104">Remarks</span></span>  
 <span data-ttu-id="e9dc5-105">El modificador `Overridable` permite que una propiedad o un método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="e9dc5-106">El modificador [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) evita que una propiedad o un método se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-106">The [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="e9dc5-107">Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="e9dc5-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="e9dc5-108">Si no se especifica el modificador `Overridable` o `NotOverridable`, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="e9dc5-109">Si la propiedad o el método reemplaza una propiedad o un método de clase base, la configuración predeterminada es `Overridable`; de lo contrario, se `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="e9dc5-110">Puede sombrear o reemplazar para volver a definir un elemento heredado, pero hay diferencias significativas entre los dos enfoques.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e9dc5-111">Para obtener más información, vea [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e9dc5-111">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="e9dc5-112">Un elemento que se puede reemplazar se denomina a veces elemento *virtual* .</span><span class="sxs-lookup"><span data-stu-id="e9dc5-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="e9dc5-113">Si se puede invalidar, pero no es necesario, a veces también se denomina elemento *concreto* .</span><span class="sxs-lookup"><span data-stu-id="e9dc5-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="e9dc5-114">Solo se puede usar `Overridable` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="e9dc5-115">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="e9dc5-115">Combined Modifiers</span></span>  
 <span data-ttu-id="e9dc5-116">No se puede especificar `Overridable` ni `NotOverridable` para un método `Private`.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="e9dc5-117">No se puede especificar `Overridable` junto con `MustOverride`, `NotOverridable`o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="e9dc5-118">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="e9dc5-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e9dc5-119">Uso</span><span class="sxs-lookup"><span data-stu-id="e9dc5-119">Usage</span></span>  
 <span data-ttu-id="e9dc5-120">El modificador `Overridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9dc5-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e9dc5-121">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e9dc5-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e9dc5-122">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e9dc5-122">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="e9dc5-123">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e9dc5-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e9dc5-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9dc5-124">See also</span></span>

- [<span data-ttu-id="e9dc5-125">Modificadores</span><span class="sxs-lookup"><span data-stu-id="e9dc5-125">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="e9dc5-126">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="e9dc5-126">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="e9dc5-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e9dc5-127">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="e9dc5-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e9dc5-128">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="e9dc5-129">Overrides</span><span class="sxs-lookup"><span data-stu-id="e9dc5-129">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="e9dc5-130">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e9dc5-130">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e9dc5-131">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e9dc5-131">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
