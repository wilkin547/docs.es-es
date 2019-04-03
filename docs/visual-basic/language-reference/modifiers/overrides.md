---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 9eb19bf5e89b12a32cae28b2c087570acc10f3ad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826592"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="b8a57-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8a57-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="b8a57-103">Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="b8a57-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8a57-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8a57-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b8a57-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="b8a57-105">Rules</span></span>  
  
-   <span data-ttu-id="b8a57-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="b8a57-106">**Declaration Context.**</span></span> <span data-ttu-id="b8a57-107">Puede usar `Overrides` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="b8a57-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="b8a57-108">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="b8a57-108">**Combined Modifiers.**</span></span> <span data-ttu-id="b8a57-109">No es posible especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="b8a57-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="b8a57-110">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="b8a57-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="b8a57-111">**Firmas coincidentes.**</span><span class="sxs-lookup"><span data-stu-id="b8a57-111">**Matching Signatures.**</span></span> <span data-ttu-id="b8a57-112">Debe coincidir con la firma de esta declaración de la *firma* de la propiedad o procedimiento que reemplaza.</span><span class="sxs-lookup"><span data-stu-id="b8a57-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="b8a57-113">Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="b8a57-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="b8a57-114">Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b8a57-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="b8a57-115">El nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="b8a57-115">The access level</span></span>  
  
    -   <span data-ttu-id="b8a57-116">El tipo de valor devuelto, si lo hay.</span><span class="sxs-lookup"><span data-stu-id="b8a57-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="b8a57-117">**Firmas genéricas.**</span><span class="sxs-lookup"><span data-stu-id="b8a57-117">**Generic Signatures.**</span></span> <span data-ttu-id="b8a57-118">En los procedimientos genéricos, la firma incluye el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="b8a57-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="b8a57-119">Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.</span><span class="sxs-lookup"><span data-stu-id="b8a57-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="b8a57-120">**Coincidencia adicional.**</span><span class="sxs-lookup"><span data-stu-id="b8a57-120">**Additional Matching.**</span></span> <span data-ttu-id="b8a57-121">Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b8a57-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="b8a57-122">Modificador de nivel de acceso (como [pública](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="b8a57-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="b8a57-123">Mecanismo de paso de cada parámetro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="b8a57-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="b8a57-124">Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="b8a57-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="b8a57-125">**Sombrear y reemplazar.**</span><span class="sxs-lookup"><span data-stu-id="b8a57-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="b8a57-126">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="b8a57-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="b8a57-127">Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="b8a57-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="b8a57-128">Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="b8a57-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="b8a57-129">El modificador `Overrides` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b8a57-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="b8a57-130">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b8a57-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="b8a57-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b8a57-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="b8a57-132">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b8a57-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="b8a57-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8a57-133">See also</span></span>

- [<span data-ttu-id="b8a57-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="b8a57-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="b8a57-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="b8a57-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="b8a57-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="b8a57-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="b8a57-137">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b8a57-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="b8a57-138">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8a57-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="b8a57-139">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8a57-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="b8a57-140">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="b8a57-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
