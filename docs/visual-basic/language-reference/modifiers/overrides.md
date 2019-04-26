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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920577"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="47b79-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47b79-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="47b79-103">Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="47b79-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47b79-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47b79-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="47b79-105">Reglas</span><span class="sxs-lookup"><span data-stu-id="47b79-105">Rules</span></span>  
  
-   <span data-ttu-id="47b79-106">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="47b79-106">**Declaration Context.**</span></span> <span data-ttu-id="47b79-107">Puede usar `Overrides` únicamente en una instrucción de declaración de procedimiento o propiedad.</span><span class="sxs-lookup"><span data-stu-id="47b79-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="47b79-108">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="47b79-108">**Combined Modifiers.**</span></span> <span data-ttu-id="47b79-109">No es posible especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="47b79-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="47b79-110">Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="47b79-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="47b79-111">**Firmas coincidentes.**</span><span class="sxs-lookup"><span data-stu-id="47b79-111">**Matching Signatures.**</span></span> <span data-ttu-id="47b79-112">Debe coincidir con la firma de esta declaración de la *firma* de la propiedad o procedimiento que reemplaza.</span><span class="sxs-lookup"><span data-stu-id="47b79-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="47b79-113">Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="47b79-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="47b79-114">Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="47b79-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="47b79-115">El nivel de acceso.</span><span class="sxs-lookup"><span data-stu-id="47b79-115">The access level</span></span>  
  
    -   <span data-ttu-id="47b79-116">El tipo de valor devuelto, si lo hay.</span><span class="sxs-lookup"><span data-stu-id="47b79-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="47b79-117">**Firmas genéricas.**</span><span class="sxs-lookup"><span data-stu-id="47b79-117">**Generic Signatures.**</span></span> <span data-ttu-id="47b79-118">En los procedimientos genéricos, la firma incluye el número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="47b79-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="47b79-119">Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.</span><span class="sxs-lookup"><span data-stu-id="47b79-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="47b79-120">**Coincidencia adicional.**</span><span class="sxs-lookup"><span data-stu-id="47b79-120">**Additional Matching.**</span></span> <span data-ttu-id="47b79-121">Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="47b79-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="47b79-122">Modificador de nivel de acceso (como [pública](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="47b79-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="47b79-123">Mecanismo de paso de cada parámetro ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="47b79-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="47b79-124">Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.</span><span class="sxs-lookup"><span data-stu-id="47b79-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="47b79-125">**Sombrear y reemplazar.**</span><span class="sxs-lookup"><span data-stu-id="47b79-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="47b79-126">Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.</span><span class="sxs-lookup"><span data-stu-id="47b79-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="47b79-127">Para obtener más información, consulte [sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="47b79-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="47b79-128">Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="47b79-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="47b79-129">El modificador `Overrides` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="47b79-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="47b79-130">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="47b79-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="47b79-131">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="47b79-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="47b79-132">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="47b79-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="47b79-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="47b79-133">See also</span></span>

- [<span data-ttu-id="47b79-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="47b79-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="47b79-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="47b79-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="47b79-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="47b79-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="47b79-137">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="47b79-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="47b79-138">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47b79-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="47b79-139">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47b79-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="47b79-140">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="47b79-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
