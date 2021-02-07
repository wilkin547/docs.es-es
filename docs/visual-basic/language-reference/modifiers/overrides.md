---
description: 'Más información acerca de: invalidaciones (Visual Basic)'
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
ms.openlocfilehash: d118bf4e366ff8f84806586dfc3977612ed6eff4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730452"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="e91cd-103">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e91cd-103">Overrides (Visual Basic)</span></span>

<span data-ttu-id="e91cd-104">Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="e91cd-104">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>

## <a name="rules"></a><span data-ttu-id="e91cd-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="e91cd-105">Rules</span></span>

- <span data-ttu-id="e91cd-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="e91cd-106">**Declaration Context.**</span></span> <span data-ttu-id="e91cd-107">Solo se puede usar `Overrides` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e91cd-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="e91cd-108">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="e91cd-108">**Combined Modifiers.**</span></span> <span data-ttu-id="e91cd-109">No se puede especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="e91cd-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="e91cd-110">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="e91cd-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>

- <span data-ttu-id="e91cd-111">**Firmas coincidentes.**</span><span class="sxs-lookup"><span data-stu-id="e91cd-111">**Matching Signatures.**</span></span> <span data-ttu-id="e91cd-112">La firma de esta declaración debe coincidir exactamente con la *firma* de la propiedad o el procedimiento que reemplaza.</span><span class="sxs-lookup"><span data-stu-id="e91cd-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="e91cd-113">Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="e91cd-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>

  <span data-ttu-id="e91cd-114">Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e91cd-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>

  - <span data-ttu-id="e91cd-115">El nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="e91cd-115">The access level</span></span>

  - <span data-ttu-id="e91cd-116">El tipo de valor devuelto, si lo hay.</span><span class="sxs-lookup"><span data-stu-id="e91cd-116">The return type, if any</span></span>

- <span data-ttu-id="e91cd-117">**Firmas genéricas.**</span><span class="sxs-lookup"><span data-stu-id="e91cd-117">**Generic Signatures.**</span></span> <span data-ttu-id="e91cd-118">En los procedimientos genéricos, la firma incluye el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="e91cd-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="e91cd-119">Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.</span><span class="sxs-lookup"><span data-stu-id="e91cd-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>

- <span data-ttu-id="e91cd-120">**Coincidencia adicional.**</span><span class="sxs-lookup"><span data-stu-id="e91cd-120">**Additional Matching.**</span></span> <span data-ttu-id="e91cd-121">Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e91cd-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>

  - <span data-ttu-id="e91cd-122">Modificador de nivel de acceso (por ejemplo, [Public](public.md))</span><span class="sxs-lookup"><span data-stu-id="e91cd-122">Access-level modifier (such as [Public](public.md))</span></span>

  - <span data-ttu-id="e91cd-123">Mecanismo de paso de cada parámetro ([ByVal](byval.md) o [ByRef](byref.md))</span><span class="sxs-lookup"><span data-stu-id="e91cd-123">Passing mechanism of each parameter ([ByVal](byval.md) or [ByRef](byref.md))</span></span>

  - <span data-ttu-id="e91cd-124">Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="e91cd-124">Constraint lists on each type parameter of a generic procedure</span></span>

- <span data-ttu-id="e91cd-125">**Sombreado y reemplazos.**</span><span class="sxs-lookup"><span data-stu-id="e91cd-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="e91cd-126">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="e91cd-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="e91cd-127">Para obtener más información, vea [sombrear en Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="e91cd-127">For more information, see [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).</span></span>

<span data-ttu-id="e91cd-128">Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="e91cd-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="e91cd-129">El modificador `Overrides` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e91cd-129">The `Overrides` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="e91cd-130">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="e91cd-130">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="e91cd-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e91cd-131">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="e91cd-132">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="e91cd-132">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="e91cd-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e91cd-133">See also</span></span>

- [<span data-ttu-id="e91cd-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e91cd-134">MustOverride</span></span>](mustoverride.md)
- [<span data-ttu-id="e91cd-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e91cd-135">NotOverridable</span></span>](notoverridable.md)
- [<span data-ttu-id="e91cd-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="e91cd-136">Overridable</span></span>](overridable.md)
- [<span data-ttu-id="e91cd-137">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e91cd-137">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="e91cd-138">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e91cd-138">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="e91cd-139">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e91cd-139">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="e91cd-140">Type List</span><span class="sxs-lookup"><span data-stu-id="e91cd-140">Type List</span></span>](../statements/type-list.md)
