---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497392"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="e6577-101">Menús emergentes encadenados con StaysOpen=False</span><span class="sxs-lookup"><span data-stu-id="e6577-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="e6577-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e6577-102">Details</span></span>

<span data-ttu-id="e6577-103">Se supone que un menú emergente con StaysOpen=False se cierra al hacer clic fuera de la ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="e6577-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="e6577-104">Cuando se encadenaban dos o más de estos elementos Popup (es decir, uno contiene al otro), se producían muchos problemas, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6577-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="e6577-105">Se abren dos niveles, se hace clic fuera de P2 pero dentro de P1.</span><span class="sxs-lookup"><span data-stu-id="e6577-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="e6577-106">No sucede nada.</span><span class="sxs-lookup"><span data-stu-id="e6577-106">Nothing happens.</span></span></li><li><span data-ttu-id="e6577-107">Se abren dos niveles, se hace clic fuera de P1.</span><span class="sxs-lookup"><span data-stu-id="e6577-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="e6577-108">Los dos menús emergentes se cierran.</span><span class="sxs-lookup"><span data-stu-id="e6577-108">Both popups close.</span></span></li><li><span data-ttu-id="e6577-109">Se abren y se cierran dos niveles.</span><span class="sxs-lookup"><span data-stu-id="e6577-109">Open and close two levels.</span></span>  <span data-ttu-id="e6577-110">Después, se intenta volver a abrir P2.</span><span class="sxs-lookup"><span data-stu-id="e6577-110">Then try to open P2 again.</span></span>  <span data-ttu-id="e6577-111">No sucede nada.</span><span class="sxs-lookup"><span data-stu-id="e6577-111">Nothing happens.</span></span></li><li><span data-ttu-id="e6577-112">Se intenta abrir tres niveles.</span><span class="sxs-lookup"><span data-stu-id="e6577-112">Try to open three levels.</span></span>  <span data-ttu-id="e6577-113">No se puede.</span><span class="sxs-lookup"><span data-stu-id="e6577-113">You can't.</span></span>  <span data-ttu-id="e6577-114">(No sucede nada o se cierra el primero de los dos niveles, en función de dónde se hizo clic). Estos casos (y otras variantes) ahora funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="e6577-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="e6577-115">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e6577-115">Name</span></span>    | <span data-ttu-id="e6577-116">Valor</span><span class="sxs-lookup"><span data-stu-id="e6577-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e6577-117">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e6577-117">Scope</span></span>   |<span data-ttu-id="e6577-118">Borde</span><span class="sxs-lookup"><span data-stu-id="e6577-118">Edge</span></span>|
|<span data-ttu-id="e6577-119">Versión</span><span class="sxs-lookup"><span data-stu-id="e6577-119">Version</span></span>|<span data-ttu-id="e6577-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="e6577-120">4.7.1</span></span>|
|<span data-ttu-id="e6577-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6577-121">Type</span></span>|<span data-ttu-id="e6577-122">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="e6577-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e6577-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e6577-123">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
