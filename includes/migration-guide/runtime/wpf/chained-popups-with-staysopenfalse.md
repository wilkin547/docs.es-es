---
ms.openlocfilehash: 171b7a3a962f8259e64b88f1ae893e649b5f24bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621397"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="62f21-101">Menús emergentes encadenados con StaysOpen=False</span><span class="sxs-lookup"><span data-stu-id="62f21-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="62f21-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="62f21-102">Details</span></span>

<span data-ttu-id="62f21-103">Se supone que un menú emergente con StaysOpen=False se cierra al hacer clic fuera de la ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="62f21-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="62f21-104">Cuando se encadenaban dos o más de estos elementos Popup (es decir, uno contiene al otro), se producían muchos problemas, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="62f21-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="62f21-105">Se abren dos niveles, se hace clic fuera de P2 pero dentro de P1.</span><span class="sxs-lookup"><span data-stu-id="62f21-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="62f21-106">No sucede nada.</span><span class="sxs-lookup"><span data-stu-id="62f21-106">Nothing happens.</span></span></li><li><span data-ttu-id="62f21-107">Se abren dos niveles, se hace clic fuera de P1.</span><span class="sxs-lookup"><span data-stu-id="62f21-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="62f21-108">Los dos menús emergentes se cierran.</span><span class="sxs-lookup"><span data-stu-id="62f21-108">Both popups close.</span></span></li><li><span data-ttu-id="62f21-109">Se abren y se cierran dos niveles.</span><span class="sxs-lookup"><span data-stu-id="62f21-109">Open and close two levels.</span></span>  <span data-ttu-id="62f21-110">Después, se intenta volver a abrir P2.</span><span class="sxs-lookup"><span data-stu-id="62f21-110">Then try to open P2 again.</span></span>  <span data-ttu-id="62f21-111">No sucede nada.</span><span class="sxs-lookup"><span data-stu-id="62f21-111">Nothing happens.</span></span></li><li><span data-ttu-id="62f21-112">Se intenta abrir tres niveles.</span><span class="sxs-lookup"><span data-stu-id="62f21-112">Try to open three levels.</span></span>  <span data-ttu-id="62f21-113">No se puede.</span><span class="sxs-lookup"><span data-stu-id="62f21-113">You can't.</span></span>  <span data-ttu-id="62f21-114">(No sucede nada o se cierra el primero de los dos niveles, en función de dónde se hizo clic). Estos casos (y otras variantes) ahora funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="62f21-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="62f21-115">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="62f21-115">Name</span></span>    | <span data-ttu-id="62f21-116">Valor</span><span class="sxs-lookup"><span data-stu-id="62f21-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="62f21-117">Ámbito</span><span class="sxs-lookup"><span data-stu-id="62f21-117">Scope</span></span>   |<span data-ttu-id="62f21-118">Borde</span><span class="sxs-lookup"><span data-stu-id="62f21-118">Edge</span></span>|
|<span data-ttu-id="62f21-119">Versión</span><span class="sxs-lookup"><span data-stu-id="62f21-119">Version</span></span>|<span data-ttu-id="62f21-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="62f21-120">4.7.1</span></span>|
|<span data-ttu-id="62f21-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="62f21-121">Type</span></span>|<span data-ttu-id="62f21-122">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="62f21-122">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="62f21-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="62f21-123">Affected APIs</span></span>

-<xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
