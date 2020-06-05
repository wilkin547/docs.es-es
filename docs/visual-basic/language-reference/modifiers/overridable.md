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
ms.openlocfilehash: dcbabde8464dd8a0ce5fad24d7d72b1e780270d3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392124"
---
# <a name="overridable-visual-basic"></a><span data-ttu-id="4b9f0-102">Overridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b9f0-102">Overridable (Visual Basic)</span></span>
<span data-ttu-id="4b9f0-103">Especifica que una propiedad o un procedimiento se puede invalidar mediante una propiedad o un procedimiento con el mismo nombre en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-103">Specifies that a property or procedure can be overridden by an identically named property or procedure in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b9f0-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b9f0-104">Remarks</span></span>  
 <span data-ttu-id="4b9f0-105">El `Overridable` modificador permite que una propiedad o un método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-105">The `Overridable` modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="4b9f0-106">El modificador [NotOverridable](notoverridable.md) evita que una propiedad o un método se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-106">The [NotOverridable](notoverridable.md) modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="4b9f0-107">Para más información, vea [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="4b9f0-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="4b9f0-108">Si `Overridable` `NotOverridable` no se especifica el modificador o, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="4b9f0-109">Si la propiedad o el método reemplaza una propiedad o un método de clase base, el valor predeterminado es `Overridable` ; de lo contrario, es `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="4b9f0-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="4b9f0-110">Puede sombrear o reemplazar para volver a definir un elemento heredado, pero hay diferencias significativas entre los dos enfoques.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-110">You can shadow or override to redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="4b9f0-111">Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="4b9f0-111">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="4b9f0-112">Un elemento que se puede reemplazar se denomina a veces elemento *virtual* .</span><span class="sxs-lookup"><span data-stu-id="4b9f0-112">An element that can be overridden is sometimes referred to as a *virtual* element.</span></span> <span data-ttu-id="4b9f0-113">Si se puede invalidar, pero no es necesario, a veces también se denomina elemento *concreto* .</span><span class="sxs-lookup"><span data-stu-id="4b9f0-113">If it can be overridden, but does not have to be, it is sometimes also called a *concrete* element.</span></span>  
  
 <span data-ttu-id="4b9f0-114">Solo se puede usar `Overridable` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-114">You can use `Overridable` only in a property or procedure declaration statement.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="4b9f0-115">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="4b9f0-115">Combined Modifiers</span></span>  
 <span data-ttu-id="4b9f0-116">No se puede especificar `Overridable` o `NotOverridable` para un `Private` método.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-116">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="4b9f0-117">No se puede especificar `Overridable` junto con `MustOverride` , `NotOverridable` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-117">You cannot specify `Overridable` together with `MustOverride`, `NotOverridable`, or `Shared` in the same declaration.</span></span>  
  
 <span data-ttu-id="4b9f0-118">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="4b9f0-118">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="4b9f0-119">Uso</span><span class="sxs-lookup"><span data-stu-id="4b9f0-119">Usage</span></span>  
 <span data-ttu-id="4b9f0-120">El modificador `Overridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b9f0-120">The `Overridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="4b9f0-121">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="4b9f0-121">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="4b9f0-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4b9f0-122">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="4b9f0-123">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="4b9f0-123">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="4b9f0-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b9f0-124">See also</span></span>

- [<span data-ttu-id="4b9f0-125">Modificadores</span><span class="sxs-lookup"><span data-stu-id="4b9f0-125">Modifiers</span></span>](index.md)
- [<span data-ttu-id="4b9f0-126">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="4b9f0-126">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="4b9f0-127">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4b9f0-127">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="4b9f0-128">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4b9f0-128">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="4b9f0-129">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="4b9f0-129">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="4b9f0-130">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4b9f0-130">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="4b9f0-131">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b9f0-131">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
