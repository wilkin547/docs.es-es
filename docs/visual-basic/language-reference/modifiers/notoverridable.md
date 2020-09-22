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
ms.openlocfilehash: 8eec54a12c7fb748df46e8c48a8b07eab983cc72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867872"
---
# <a name="notoverridable-visual-basic"></a><span data-ttu-id="6cf31-102">NotOverridable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cf31-102">NotOverridable (Visual Basic)</span></span>

<span data-ttu-id="6cf31-103">Especifica que una propiedad o un procedimiento no se pueden invalidar en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="6cf31-103">Specifies that a property or procedure cannot be overridden in a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cf31-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6cf31-104">Remarks</span></span>  

 <span data-ttu-id="6cf31-105">El `NotOverridable` modificador evita que una propiedad o un método se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="6cf31-105">The `NotOverridable` modifier prevents a property or method from being overridden in a derived class.</span></span>  <span data-ttu-id="6cf31-106">El modificador [Overridable](overridable.md) permite que una propiedad o un método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="6cf31-106">The [Overridable](overridable.md) modifier allows a property or method in a class to be overridden in a derived class.</span></span> <span data-ttu-id="6cf31-107">Para más información, vea [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="6cf31-107">For more information, see [Inheritance Basics](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="6cf31-108">Si `Overridable` `NotOverridable` no se especifica el modificador o, el valor predeterminado depende de si la propiedad o el método reemplaza a una propiedad o método de clase base.</span><span class="sxs-lookup"><span data-stu-id="6cf31-108">If the `Overridable` or `NotOverridable` modifier is not specified, the default setting depends on whether the property or method overrides a base class property or method.</span></span> <span data-ttu-id="6cf31-109">Si la propiedad o el método reemplaza una propiedad o un método de clase base, el valor predeterminado es `Overridable` ; de lo contrario, es `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="6cf31-109">If the property or method overrides a base class property or method, the default setting is `Overridable`; otherwise, it is `NotOverridable`.</span></span>  
  
 <span data-ttu-id="6cf31-110">Un elemento que no se puede invalidar se denomina a veces elemento *sellado* .</span><span class="sxs-lookup"><span data-stu-id="6cf31-110">An element that cannot be overridden is sometimes called a *sealed* element.</span></span>  
  
 <span data-ttu-id="6cf31-111">Solo se puede usar `NotOverridable` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="6cf31-111">You can use `NotOverridable` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="6cf31-112">Solo se puede especificar `NotOverridable` en una propiedad o un procedimiento que invalide otra propiedad o procedimiento, es decir, solo en combinación con `Overrides` .</span><span class="sxs-lookup"><span data-stu-id="6cf31-112">You can specify `NotOverridable` only on a property or procedure that overrides another property or procedure, that is, only in combination with `Overrides`.</span></span>  
  
## <a name="combined-modifiers"></a><span data-ttu-id="6cf31-113">Modificadores combinados</span><span class="sxs-lookup"><span data-stu-id="6cf31-113">Combined Modifiers</span></span>  

 <span data-ttu-id="6cf31-114">No se puede especificar `Overridable` o `NotOverridable` para un `Private` método.</span><span class="sxs-lookup"><span data-stu-id="6cf31-114">You cannot specify `Overridable` or `NotOverridable` for a `Private` method.</span></span>  
  
 <span data-ttu-id="6cf31-115">No se puede especificar `NotOverridable` junto con `MustOverride` , `Overridable` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="6cf31-115">You cannot specify `NotOverridable` together with `MustOverride`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="6cf31-116">Uso</span><span class="sxs-lookup"><span data-stu-id="6cf31-116">Usage</span></span>  

 <span data-ttu-id="6cf31-117">El modificador `NotOverridable` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6cf31-117">The `NotOverridable` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="6cf31-118">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="6cf31-118">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="6cf31-119">Property Statement</span><span class="sxs-lookup"><span data-stu-id="6cf31-119">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="6cf31-120">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="6cf31-120">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6cf31-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6cf31-121">See also</span></span>

- [<span data-ttu-id="6cf31-122">Modificadores</span><span class="sxs-lookup"><span data-stu-id="6cf31-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="6cf31-123">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="6cf31-123">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [<span data-ttu-id="6cf31-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="6cf31-124">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="6cf31-125">Overridable</span><span class="sxs-lookup"><span data-stu-id="6cf31-125">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="6cf31-126">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="6cf31-126">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="6cf31-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6cf31-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="6cf31-128">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6cf31-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
