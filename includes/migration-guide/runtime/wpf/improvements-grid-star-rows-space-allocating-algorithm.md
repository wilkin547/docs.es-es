---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237612"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="ba698-101">Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella</span><span class="sxs-lookup"><span data-stu-id="ba698-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ba698-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba698-102">Details</span></span>|<span data-ttu-id="ba698-103">Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="ba698-103">Fixed a bug in the [algorithm for allocating sizes to](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="ba698-104">En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="ba698-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="ba698-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ba698-105">Suggestion</span></span>|<span data-ttu-id="ba698-106">Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="ba698-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="ba698-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ba698-107">Scope</span></span>|<span data-ttu-id="ba698-108">Major</span><span class="sxs-lookup"><span data-stu-id="ba698-108">Major</span></span>|
|<span data-ttu-id="ba698-109">Versión</span><span class="sxs-lookup"><span data-stu-id="ba698-109">Version</span></span>|<span data-ttu-id="ba698-110">4.8</span><span class="sxs-lookup"><span data-stu-id="ba698-110">4.8</span></span>|
|<span data-ttu-id="ba698-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="ba698-111">Type</span></span>|<span data-ttu-id="ba698-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ba698-112">Runtime</span></span>|
