---
title: "Mitigación: Asignación de espacio del control de cuadrícula en columnas de estrella"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a><span data-ttu-id="1f4c3-102">Mitigación: Asignación de espacio del control de cuadrícula en columnas de estrella</span><span class="sxs-lookup"><span data-stu-id="1f4c3-102">Mitigation: Grid Control&#39;s Space Allocation to Star-columns</span></span>

<span data-ttu-id="1f4c3-103">A partir de las aplicaciones que tienen como destino .NET Framework 4.7, WPF reemplaza el algoritmo que el control <xref:System.Windows.Controls.Grid> utiliza para asignar espacio a las columnas \*.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-103">Starting with applications that the .NET Framework 4.7, WPF replaces the algorithm that the <xref:System.Windows.Controls.Grid> control uses to allocate space to \*-columns.</span></span> 

## <a name="whats-changed"></a><span data-ttu-id="1f4c3-104">Cambios</span><span class="sxs-lookup"><span data-stu-id="1f4c3-104">What's changed</span></span>

<span data-ttu-id="1f4c3-105">El nuevo algoritmo corrige varios errores presentes en el algoritmo antiguo:</span><span class="sxs-lookup"><span data-stu-id="1f4c3-105">The new algorithm fixes several bugs present in the old algorithm:</span></span>

1. <span data-ttu-id="1f4c3-106">La asignación total a columnas puede superar el ancho de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-106">Total allocation to columns can exceed the Grid's width.</span></span> <span data-ttu-id="1f4c3-107">Esto puede ocurrir cuando se asigna espacio a una columna cuya parte proporcional es inferior a su tamaño mínimo.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-107">This can occur when allocating space to a column whose proportional share is less than its minimum size.</span></span> <span data-ttu-id="1f4c3-108">El algoritmo asigna el tamaño mínimo, lo que disminuye el espacio disponible para otras columnas.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-108">The algorithm allocates the minimum size, which decreases the space available to other columns.</span></span> <span data-ttu-id="1f4c3-109">Si no hay ninguna columna \* que asignar, la asignación total será demasiado grande.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-109">If there are no \*-columns left to allocate, the total allocation will be too large.</span></span>

1. <span data-ttu-id="1f4c3-110">La asignación total puede no alcanzar el ancho de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-110">Total allocation can fall short of the Grid's width.</span></span> <span data-ttu-id="1f4c3-111">Este es el doble problema que presenta el n.º 1, que surge cuando se asigna a una columna cuya parte proporcional es superior al tamaño máximo, sin columnas \* para ocupar el margen de demora.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-111">This is the dual problem to #1, arising when allocating to a column whose proportional share is greater than its maximum size, with no \*-columns left to take up the slack.</span></span>

1. <span data-ttu-id="1f4c3-112">Las dos columnas \* pueden recibir ubicaciones no proporcionales a sus pesos.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-112">Two \*-columns can receive allocations not proportional to their -weights.</span></span> <span data-ttu-id="1f4c3-113">Esta es una versión más ligera de n.º 1/n.º 2, que surge cuando se asigna a las columnas * A, B y C (en ese orden), donde la parte proporcional de B infringe la limitación mínima (o máxima).</span><span class="sxs-lookup"><span data-stu-id="1f4c3-113">This is a milder version of #1/#2, arising when allocating to *-columns A, B, and C (in that order), where B's proportional share violates its min (or max) constraint.</span></span> <span data-ttu-id="1f4c3-114">Como ocurría anteriormente, esto cambia el espacio disponible en la columna C, que obtiene menos (o más) asignación proporcional respecto a A.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-114">As above, this changes the space available to column C, who gets less (or more) proportional allocation than A did,</span></span>

1. <span data-ttu-id="1f4c3-115">Las columnas con pesos extremadamente grandes (> 10 ^ 298) se tratan como si tuvieran peso 10 ^ 298.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-115">Columns with extremely large weights (> 10^298) are all treated as if they had weight 10^298.</span></span> <span data-ttu-id="1f4c3-116">Las diferencias proporcionales entre ellas (y entre columnas con pesos ligeramente más reducidos) no se han respetado.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-116">Proportional differences between them (and between columns with slightly smaller weights) are not honored.</span></span>

1. <span data-ttu-id="1f4c3-117">Las columnas con pesos infinitos no se han administrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-117">Columns with infinite weights are not handled correctly.</span></span> <span data-ttu-id="1f4c3-118">[De hecho, no puede establecer un peso en infinito, pero esta es una restricción artificial.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-118">[Actually you can't set a weight to Infinity, but this is an artificial restriction.</span></span> <span data-ttu-id="1f4c3-119">El código de ubicación estaba intentando administrarlo, pero de forma incorrecta].</span><span class="sxs-lookup"><span data-stu-id="1f4c3-119">The allocation code was trying to handle it, but doing a bad job.]</span></span>

1. <span data-ttu-id="1f4c3-120">Algunos problemas leves al evitar el desbordamiento, el subdesbordamiento, la pérdida de precisión y problemas de punto flotante similares.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-120">Several minor problems while avoiding overflow, underflow, loss of precision and similar floating-point issues.</span></span>

1. <span data-ttu-id="1f4c3-121">Los ajustes del redondeo del diseño son incorrectos en los puntos por pulgada suficientemente elevados.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-121">Adjustments for layout rounding are incorrect at sufficiently high DPI.</span></span>

<span data-ttu-id="1f4c3-122">El nuevo algoritmo genera resultados que cumplen los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="1f4c3-122">The new algorithm produces results that meet the following criteria:</span></span>

<span data-ttu-id="1f4c3-123">Un archivo .</span><span class="sxs-lookup"><span data-stu-id="1f4c3-123">A.</span></span> <span data-ttu-id="1f4c3-124">El ancho real asignado a una columna * nunca es inferior al ancho mínimo ni superior al ancho máximo.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-124">The actual width assigned to a *-column is never less than its minimum width nor greater than its maximum width.</span></span>

<span data-ttu-id="1f4c3-125">B.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-125">B.</span></span> <span data-ttu-id="1f4c3-126">Cada columna a la que no se le asigne un ancho mínimo o máximo, se le asigna un ancho proporcional a su peso.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-126">Each -column that is not assigned its minimum or maximum width is assigned a width proportional to its -weight.</span></span> <span data-ttu-id="1f4c3-127">Para ser precisos, si dos columnas se declaran con un ancho x e y respectivamente, y si ninguna columna tiene un ancho mínimo o máximo, los anchos reales v y w asignados a las columnas tienen la misma proporción: v / w == x / y.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-127">To be precise, if two columns are declared with width x and y respectively, and if neither column receives its minimum or maximum width, the actual widths v and w assigned to the columns are in the same proportion: v / w == x / y.</span></span>

<span data-ttu-id="1f4c3-128">C.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-128">C.</span></span> <span data-ttu-id="1f4c3-129">El ancho total asignado a las columnas \* proporcionales es igual al espacio disponible después de la asignación a las columnas restringidas (columnas \*, automáticas y fijas a las que se asignan el ancho mínimo o máximo).</span><span class="sxs-lookup"><span data-stu-id="1f4c3-129">The total width allocated to "proportional" \*-columns is equal to the space available after allocating to the constrained columns (fixed, auto, and \*-columns that are allocated their min or max width).</span></span> <span data-ttu-id="1f4c3-130">Debe ser cero, por ejemplo si la suma de los anchos mínimos supera el ancho disponible de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-130">This might be zero, for instance if the sum of the minimum widths exceeds the Grid's availbable width.</span></span>

<span data-ttu-id="1f4c3-131">D.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-131">D.</span></span> <span data-ttu-id="1f4c3-132">Todas estas instrucciones tienen que interpretarse en relación con el diseño "ideal".</span><span class="sxs-lookup"><span data-stu-id="1f4c3-132">All these statements are to be interpreted with respect to the "ideal" layout.</span></span> <span data-ttu-id="1f4c3-133">Cuando se aplica el redondeo del diseño, los anchos reales pueden diferir de los ideales como máximo un píxel.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-133">When layout rounding is in effect, the actual widths can differ from the ideal widths by as much as one pixel.</span></span>

<span data-ttu-id="1f4c3-134">Se respetó el algoritmo antiguo (A), pero se produjo un error al respetar los demás criterios en los casos descritos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-134">The old algorithm honored (A) but failed to honor the other criteria in the cases outlined above.</span></span>

<span data-ttu-id="1f4c3-135">Toda la información que se indica sobre las columnas y los anchos en este tema se aplica también a las filas y las alturas.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-135">Everything said about columns and widths in this topic applies as well to rows and heights.</span></span>

## <a name="impact"></a><span data-ttu-id="1f4c3-136">Impacto</span><span class="sxs-lookup"><span data-stu-id="1f4c3-136">Impact</span></span>

<span data-ttu-id="1f4c3-137">El nuevo algoritmo cambia el ancho real asignado a las columnas \* en una serie de casos:</span><span class="sxs-lookup"><span data-stu-id="1f4c3-137">The new algorithm changes the actual width assigned to \*-columns in a number of cases:</span></span>

- <span data-ttu-id="1f4c3-138">Cuando una o más columnas \* tienen un ancho mínimo o máximo que invalida la asignación proporcional para esa columna.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-138">When one or more \*-columns also have a minimum or maximum width that overrides the proportional allocation for that column.</span></span> <span data-ttu-id="1f4c3-139">(El ancho mínimo puede derivarse de la declaración <xref:System.Windows.FrameworkElement.MinWidth%2A> explícita o de un mínimo implícito obtenido del contenido de la columna.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-139">(The minimum width can derive from an explicit <xref:System.Windows.FrameworkElement.MinWidth%2A> declaration, or from an implicit minimum obtained from the column's content.</span></span> <span data-ttu-id="1f4c3-140">El ancho máximo solo puede definirse de forma explícita, a partir de una declaración <xref:System.Windows.FrameworkElement.MaxWidth%2A>).</span><span class="sxs-lookup"><span data-stu-id="1f4c3-140">The maximum width can only be defined explicitly, from a <xref:System.Windows.FrameworkElement.MaxWidth%2A> declaration.)</span></span>

- <span data-ttu-id="1f4c3-141">Cuando una o más columnas \* declaran un peso \* extremadamente grande, superior a 10^298.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-141">When one or more \*-columns declare an extremely large \*-weight, greater than 10^298.</span></span>

- <span data-ttu-id="1f4c3-142">Cuando los pesos \* son suficientemente distintos como para detectar una inestabilidad de punto flotante (desbordamiento, subdesbordamiento y pérdida de precisión).</span><span class="sxs-lookup"><span data-stu-id="1f4c3-142">When the \*-weights are sufficiently different to encounter floating-point instability (overflow, underflow, loss of precision).</span></span>

- <span data-ttu-id="1f4c3-143">Cuando se habilita el redondeo del diseño, y el punto por pulgada de visualización efectivo es suficientemente alto.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-143">When layout rounding is enabled, and the effective display DPI is sufficiently high.</span></span>

<span data-ttu-id="1f4c3-144">En los primeros dos casos, los anchos producidos por el nuevo algoritmo pueden ser significativamente distintos de los producidos por el algoritmo antiguo; en el último caso, la diferencia será como máximo de uno o dos píxeles.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-144">In the first two cases, the widths produced by the new algorithm can be significantly different from those produced by the old algorithm; in the last case, the difference will be at most one or two pixels.</span></span>

## <a name="mitigation"></a><span data-ttu-id="1f4c3-145">Mitigación</span><span class="sxs-lookup"><span data-stu-id="1f4c3-145">Mitigation</span></span>

<span data-ttu-id="1f4c3-146">De forma predeterminada, las aplicaciones que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.7 utilizarán el nuevo algoritmo, mientras que las aplicaciones que tienen como destino NET Framework 4.6.2 o versiones anteriores, usarán el algoritmo antiguo.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-146">By default, apps that target versions of the .NET Framework starting with the .NET Framework 4.7 will use the new algorithm, while apps that target the .NET Framework 4.6.2 or earlier versions will use the old algorithm.</span></span>

<span data-ttu-id="1f4c3-147">Para invalidar el valor predeterminado, utilice el siguiente ajuste de configuración:</span><span class="sxs-lookup"><span data-stu-id="1f4c3-147">To override the default, use the following configuration setting:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

<span data-ttu-id="1f4c3-148">El valor 'true' selecciona el algoritmo antiguo y el valor 'false' el nuevo.</span><span class="sxs-lookup"><span data-stu-id="1f4c3-148">The value 'true' selects the old algorithm, and 'false' selects the new algorithm.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f4c3-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f4c3-149">See also</span></span>
[<span data-ttu-id="1f4c3-150">Cambios de redestinación en .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="1f4c3-150">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

