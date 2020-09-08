---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497301"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="e42f6-101">Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella</span><span class="sxs-lookup"><span data-stu-id="e42f6-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="e42f6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e42f6-102">Details</span></span>

<span data-ttu-id="e42f6-103">Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="e42f6-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="e42f6-104">En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e42f6-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e42f6-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e42f6-105">Suggestion</span></span>

<span data-ttu-id="e42f6-106">Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="e42f6-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="e42f6-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e42f6-107">Name</span></span>    | <span data-ttu-id="e42f6-108">Valor</span><span class="sxs-lookup"><span data-stu-id="e42f6-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e42f6-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e42f6-109">Scope</span></span>   |<span data-ttu-id="e42f6-110">Major</span><span class="sxs-lookup"><span data-stu-id="e42f6-110">Major</span></span>|
|<span data-ttu-id="e42f6-111">Versión</span><span class="sxs-lookup"><span data-stu-id="e42f6-111">Version</span></span>|<span data-ttu-id="e42f6-112">4.8</span><span class="sxs-lookup"><span data-stu-id="e42f6-112">4.8</span></span>|
|<span data-ttu-id="e42f6-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="e42f6-113">Type</span></span>|<span data-ttu-id="e42f6-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e42f6-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e42f6-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e42f6-115">Affected APIs</span></span>

<span data-ttu-id="e42f6-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="e42f6-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
