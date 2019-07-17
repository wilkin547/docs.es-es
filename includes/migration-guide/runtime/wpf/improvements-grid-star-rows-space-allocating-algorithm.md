---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802670"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a><span data-ttu-id="4e9c0-101">Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella</span><span class="sxs-lookup"><span data-stu-id="4e9c0-101">Improvements to Grid star-rows space allocating algorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4e9c0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4e9c0-102">Details</span></span>|<span data-ttu-id="4e9c0-103">Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="4e9c0-103">Fixed a bug in the [algorithm for allocating sizes to ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) in a <xref:System.Windows.Controls.Grid> introduced in .NET Framework 4.7.</span></span>  <span data-ttu-id="4e9c0-104">En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4e9c0-104">In some cases, such as a Grid with <code>Height=&quot;Auto&quot;</code> containing empty rows, rows were arranged at the wrong position, possibly outside the Grid altogether.</span></span>|
|<span data-ttu-id="4e9c0-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4e9c0-105">Suggestion</span></span>|<span data-ttu-id="4e9c0-106">Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="4e9c0-106">In order for the application to benefit from these changes, it must run on the .NET Framework 4.8 or later.</span></span>|
|<span data-ttu-id="4e9c0-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4e9c0-107">Scope</span></span>|<span data-ttu-id="4e9c0-108">Major</span><span class="sxs-lookup"><span data-stu-id="4e9c0-108">Major</span></span>|
|<span data-ttu-id="4e9c0-109">Versión</span><span class="sxs-lookup"><span data-stu-id="4e9c0-109">Version</span></span>|<span data-ttu-id="4e9c0-110">4.8</span><span class="sxs-lookup"><span data-stu-id="4e9c0-110">4.8</span></span>|
|<span data-ttu-id="4e9c0-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e9c0-111">Type</span></span>|<span data-ttu-id="4e9c0-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4e9c0-112">Runtime</span></span>|

