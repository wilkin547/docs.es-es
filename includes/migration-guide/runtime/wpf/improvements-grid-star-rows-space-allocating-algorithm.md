---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622094"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="61c47-101">Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella</span><span class="sxs-lookup"><span data-stu-id="61c47-101">Improvements to Grid star-rows space allocating algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="61c47-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="61c47-102">Details</span></span>

<span data-ttu-id="61c47-103">Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="61c47-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="61c47-104">En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="61c47-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61c47-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="61c47-105">Suggestion</span></span>

<span data-ttu-id="61c47-106">Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="61c47-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>

| <span data-ttu-id="61c47-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="61c47-107">Name</span></span>    | <span data-ttu-id="61c47-108">Valor</span><span class="sxs-lookup"><span data-stu-id="61c47-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61c47-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="61c47-109">Scope</span></span>   |<span data-ttu-id="61c47-110">Major</span><span class="sxs-lookup"><span data-stu-id="61c47-110">Major</span></span>|
|<span data-ttu-id="61c47-111">Versión</span><span class="sxs-lookup"><span data-stu-id="61c47-111">Version</span></span>|<span data-ttu-id="61c47-112">4.8</span><span class="sxs-lookup"><span data-stu-id="61c47-112">4.8</span></span>|
|<span data-ttu-id="61c47-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="61c47-113">Type</span></span>|<span data-ttu-id="61c47-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="61c47-114">Runtime</span></span>|
