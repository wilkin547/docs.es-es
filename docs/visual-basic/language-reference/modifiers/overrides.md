---
title: Invalidaciones
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
ms.openlocfilehash: 04f1cb27d6a8366c2dd13f8fdc1d975d382f1cfd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351381"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="2a0fd-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a0fd-102">Overrides (Visual Basic)</span></span>

<span data-ttu-id="2a0fd-103">Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="2a0fd-104">Reglas</span><span class="sxs-lookup"><span data-stu-id="2a0fd-104">Rules</span></span>

- <span data-ttu-id="2a0fd-105">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="2a0fd-105">**Declaration Context.**</span></span> <span data-ttu-id="2a0fd-106">Solo se puede usar `Overrides` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-106">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="2a0fd-107">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="2a0fd-107">**Combined Modifiers.**</span></span> <span data-ttu-id="2a0fd-108">No se puede especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-108">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="2a0fd-109">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-109">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="2a0fd-110">**Firmas coincidentes.**</span><span class="sxs-lookup"><span data-stu-id="2a0fd-110">**Matching Signatures.**</span></span> <span data-ttu-id="2a0fd-111">La firma de esta declaración debe coincidir exactamente con la *firma* de la propiedad o el procedimiento que reemplaza.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-111">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="2a0fd-112">Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-112">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="2a0fd-113">Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a0fd-113">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="2a0fd-114">El nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-114">The access level</span></span>

  - <span data-ttu-id="2a0fd-115">El tipo de valor devuelto, si lo hay.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-115">The return type, if any</span></span>

- <span data-ttu-id="2a0fd-116">**Firmas genéricas.**</span><span class="sxs-lookup"><span data-stu-id="2a0fd-116">**Generic Signatures.**</span></span> <span data-ttu-id="2a0fd-117">En los procedimientos genéricos, la firma incluye el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-117">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="2a0fd-118">Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-118">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="2a0fd-119">**Coincidencia adicional.**</span><span class="sxs-lookup"><span data-stu-id="2a0fd-119">**Additional Matching.**</span></span> <span data-ttu-id="2a0fd-120">Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a0fd-120">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="2a0fd-121">Modificador de nivel de acceso (por ejemplo, [Public](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="2a0fd-121">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>

  - <span data-ttu-id="2a0fd-122">Mecanismo de paso de cada parámetro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="2a0fd-122">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>

  - <span data-ttu-id="2a0fd-123">Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-123">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="2a0fd-124">**Sombrear e invalidar.**</span><span class="sxs-lookup"><span data-stu-id="2a0fd-124">**Shadowing and Overriding.**</span></span> <span data-ttu-id="2a0fd-125">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-125">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="2a0fd-126">Para obtener más información, vea [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="2a0fd-126">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="2a0fd-127">Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="2a0fd-127">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="2a0fd-128">El modificador `Overrides` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a0fd-128">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="2a0fd-129">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a0fd-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="2a0fd-130">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a0fd-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="2a0fd-131">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2a0fd-131">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="2a0fd-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a0fd-132">See also</span></span>

- [<span data-ttu-id="2a0fd-133">MustOverride</span><span class="sxs-lookup"><span data-stu-id="2a0fd-133">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="2a0fd-134">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="2a0fd-134">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="2a0fd-135">Overridable</span><span class="sxs-lookup"><span data-stu-id="2a0fd-135">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="2a0fd-136">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2a0fd-136">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="2a0fd-137">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a0fd-137">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="2a0fd-138">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a0fd-138">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="2a0fd-139">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="2a0fd-139">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
