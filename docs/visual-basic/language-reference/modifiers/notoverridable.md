---
title: NotOverridable
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
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351442"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="0a8cc-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a8cc-102">NotOverridable (Visual Basic)</span></span>
<span data-ttu-id="0a8cc-103">Especifica que una propiedad o un procedimiento no se pueden invalidar en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a8cc-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a8cc-104">Remarks</span></span>  
 <span data-ttu-id="0a8cc-105">El modificador `NotOverridable` impide que una propiedad o un método se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="0a8cc-106">El modificador [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) permite que una propiedad o un método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-106">The [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="0a8cc-107">Para más información, vea [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="0a8cc-107">For more information, see [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="0a8cc-108">Si no se especifica el modificador `Overridable` o `NotOverridable`, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="0a8cc-109">Si la propiedad o el método reemplaza una propiedad o un método de clase base, la configuración predeterminada es `Overridable`; de lo contrario, se `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="0a8cc-110">Un elemento que no se puede invalidar se denomina a veces elemento *sellado* .</span><span class="sxs-lookup"><span data-stu-id="0a8cc-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="0a8cc-111">Solo se puede usar `NotOverridable` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="0a8cc-112">Solo puede especificar `NotOverridable` en una propiedad o un procedimiento que invalide otra propiedad o procedimiento, es decir, solo en combinación con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="0a8cc-113">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="0a8cc-113">Combined Modifiers</span></span>  
 <span data-ttu-id="0a8cc-114">No se puede especificar `Overridable` ni `NotOverridable` para un método `Private`.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="0a8cc-115">No se puede especificar `NotOverridable` junto con `MustOverride`, `Overridable`o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="0a8cc-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="0a8cc-116">Uso</span><span class="sxs-lookup"><span data-stu-id="0a8cc-116">Usage</span></span>  
 <span data-ttu-id="0a8cc-117">El modificador `NotOverridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a8cc-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0a8cc-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0a8cc-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="0a8cc-119">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0a8cc-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="0a8cc-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0a8cc-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a8cc-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a8cc-121">See also</span></span>

- [<span data-ttu-id="0a8cc-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="0a8cc-122">Modifiers</span></span>](../../../visual-basic/language-reference/modifiers/index.md)
- [<span data-ttu-id="0a8cc-123">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="0a8cc-123">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="0a8cc-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="0a8cc-124">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="0a8cc-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="0a8cc-125">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="0a8cc-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="0a8cc-126">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="0a8cc-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0a8cc-127">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="0a8cc-128">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0a8cc-128">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
