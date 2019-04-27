---
title: MustOverride (Visual Basic)
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
ms.openlocfilehash: 0ddd7d0d2a57afc02aa7483ba5e83b65c48af534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920762"
---
# <a name="mustoverride-visual-basic"></a><span data-ttu-id="6dab5-102">MustOverride (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6dab5-102">MustOverride (Visual Basic)</span></span>
<span data-ttu-id="6dab5-103">Especifica que una propiedad o procedimiento no se implementa en esta clase y se debe invalidar en una clase derivada antes de que se puede usar.</span><span class="sxs-lookup"><span data-stu-id="6dab5-103">Specifies that a property or procedure is not implemented in this class and must be overridden in a derived class before it can be used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dab5-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6dab5-104">Remarks</span></span>  
 <span data-ttu-id="6dab5-105">Puede usar `MustOverride` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="6dab5-105">You can use `MustOverride` only in a property or procedure declaration statement.</span></span> <span data-ttu-id="6dab5-106">La propiedad o procedimiento que especifica `MustOverride` debe ser un miembro de una clase, y la clase debe marcarse [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span><span class="sxs-lookup"><span data-stu-id="6dab5-106">The property or procedure that specifies `MustOverride` must be a member of a class, and the class must be marked [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="6dab5-107">Reglas</span><span class="sxs-lookup"><span data-stu-id="6dab5-107">Rules</span></span>  
  
-   <span data-ttu-id="6dab5-108">**Declaración incompleta.**</span><span class="sxs-lookup"><span data-stu-id="6dab5-108">**Incomplete Declaration.**</span></span> <span data-ttu-id="6dab5-109">Al especificar `MustOverride`, no proporciona líneas adicionales de código para la propiedad o procedimiento, no incluso la `End Function`, `End Property`, o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="6dab5-109">When you specify `MustOverride`, you do not supply any additional lines of code for the property or procedure, not even the `End Function`, `End Property`, or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="6dab5-110">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="6dab5-110">**Combined Modifiers.**</span></span> <span data-ttu-id="6dab5-111">No puede especificar `MustOverride` junto con `NotOverridable`, `Overridable`, o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="6dab5-111">You cannot specify `MustOverride` together with `NotOverridable`, `Overridable`, or `Shared` in the same declaration.</span></span>  
  
-   <span data-ttu-id="6dab5-112">**Sombrear y reemplazar.**</span><span class="sxs-lookup"><span data-stu-id="6dab5-112">**Shadowing and Overriding.**</span></span> <span data-ttu-id="6dab5-113">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="6dab5-113">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="6dab5-114">Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="6dab5-114">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
-   <span data-ttu-id="6dab5-115">**Términos alternativos.**</span><span class="sxs-lookup"><span data-stu-id="6dab5-115">**Alternate Terms.**</span></span> <span data-ttu-id="6dab5-116">Un elemento que no se puede usar, excepto en una invalidación a veces se denomina un *pura virtual* elemento.</span><span class="sxs-lookup"><span data-stu-id="6dab5-116">An element that cannot be used except in an override is sometimes called a *pure virtual* element.</span></span>  
  
 <span data-ttu-id="6dab5-117">El modificador `MustOverride` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6dab5-117">The `MustOverride` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="6dab5-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6dab5-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="6dab5-119">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6dab5-119">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="6dab5-120">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6dab5-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dab5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dab5-121">See also</span></span>

- [<span data-ttu-id="6dab5-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="6dab5-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="6dab5-123">Overridable</span><span class="sxs-lookup"><span data-stu-id="6dab5-123">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="6dab5-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="6dab5-124">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="6dab5-125">MustInherit</span><span class="sxs-lookup"><span data-stu-id="6dab5-125">MustInherit</span></span>](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [<span data-ttu-id="6dab5-126">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6dab5-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="6dab5-127">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6dab5-127">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
