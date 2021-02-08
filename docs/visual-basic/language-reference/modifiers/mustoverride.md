---
description: 'Más información acerca de: MustOverride (Visual Basic)'
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: df7200a7f7ec4bfda34765747d6318bc50a38dd1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774530"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="efa30-103">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efa30-103">MustOverride (Visual Basic)</span></span>

<span data-ttu-id="efa30-104">Especifica que una propiedad o procedimiento no está implementado en esta clase y se debe invalidar en una clase derivada antes de que se pueda utilizar.</span><span class="sxs-lookup"><span data-stu-id="efa30-104">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efa30-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="efa30-105">Remarks</span></span>  

 <span data-ttu-id="efa30-106">Solo se puede usar `MustOverride` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="efa30-106">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="efa30-107">La propiedad o el procedimiento que especifica `MustOverride` debe ser miembro de una clase y la clase debe marcarse como [MustInherit](mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="efa30-107">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="efa30-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="efa30-108">Rules</span></span>  
  
- <span data-ttu-id="efa30-109">**Declaración incompleta.**</span><span class="sxs-lookup"><span data-stu-id="efa30-109">**Incomplete Declaration.**</span></span> <span data-ttu-id="efa30-110">Cuando se especifica `MustOverride` , no se proporcionan líneas de código adicionales para la propiedad o el procedimiento, ni siquiera la `End Function` instrucción, `End Property` o `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="efa30-110">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="efa30-111">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="efa30-111">**Combined Modifiers.**</span></span> <span data-ttu-id="efa30-112">No se puede especificar `MustOverride` junto con `NotOverridable` , `Overridable` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="efa30-112">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
- <span data-ttu-id="efa30-113">**Sombreado y reemplazos.**</span><span class="sxs-lookup"><span data-stu-id="efa30-113">**Shadowing and Overriding.**</span></span> <span data-ttu-id="efa30-114">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="efa30-114">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="efa30-115">Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="efa30-115">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
- <span data-ttu-id="efa30-116">**Términos alternativos.**</span><span class="sxs-lookup"><span data-stu-id="efa30-116">**Alternate Terms.**</span></span> <span data-ttu-id="efa30-117">Un elemento que no se puede usar excepto en una invalidación a veces se denomina elemento *virtual puro* .</span><span class="sxs-lookup"><span data-stu-id="efa30-117">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="efa30-118">El modificador `MustOverride` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="efa30-118">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="efa30-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="efa30-119">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="efa30-120">Property Statement</span><span class="sxs-lookup"><span data-stu-id="efa30-120">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="efa30-121">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="efa30-121">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="efa30-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa30-122">See also</span></span>

- [<span data-ttu-id="efa30-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="efa30-123">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="efa30-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="efa30-124">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="efa30-125">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="efa30-125">Overrides</span></span>](overrides.md)
- [<span data-ttu-id="efa30-126">MustInherit</span><span class="sxs-lookup"><span data-stu-id="efa30-126">MustInherit</span></span>](mustinherit.md)
- [<span data-ttu-id="efa30-127">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="efa30-127">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="efa30-128">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efa30-128">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
