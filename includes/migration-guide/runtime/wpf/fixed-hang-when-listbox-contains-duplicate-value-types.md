---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496581"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a><span data-ttu-id="c61b3-101">Se ha corregido un bloqueo cuando ListBox contiene tipos de valores duplicados</span><span class="sxs-lookup"><span data-stu-id="c61b3-101">Fixed a hang when ListBox contains duplicate value-types</span></span>

#### <a name="details"></a><span data-ttu-id="c61b3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c61b3-102">Details</span></span>

<span data-ttu-id="c61b3-103">Se ha corregido un problema por el que un elemento de virtualización<xref:System.Windows.Controls.ItemsControl> dejaba de responder durante el desplazamiento cuando la colección de elementos contenía objetos de tipo de valor duplicados.</span><span class="sxs-lookup"><span data-stu-id="c61b3-103">Fixed a problem where a virtualizing<xref:System.Windows.Controls.ItemsControl> can hang during scrolling when its Items collection contains duplicate value-typed objects.</span></span>

| <span data-ttu-id="c61b3-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c61b3-104">Name</span></span>    | <span data-ttu-id="c61b3-105">Valor</span><span class="sxs-lookup"><span data-stu-id="c61b3-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c61b3-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c61b3-106">Scope</span></span>   |<span data-ttu-id="c61b3-107">Major</span><span class="sxs-lookup"><span data-stu-id="c61b3-107">Major</span></span>|
|<span data-ttu-id="c61b3-108">Versión</span><span class="sxs-lookup"><span data-stu-id="c61b3-108">Version</span></span>|<span data-ttu-id="c61b3-109">4.8</span><span class="sxs-lookup"><span data-stu-id="c61b3-109">4.8</span></span>|
|<span data-ttu-id="c61b3-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="c61b3-110">Type</span></span>|<span data-ttu-id="c61b3-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c61b3-111">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c61b3-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c61b3-112">Affected APIs</span></span>

<span data-ttu-id="c61b3-113">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="c61b3-113">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
