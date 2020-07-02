---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620710"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="bdbd6-101">Los elementos DataTemplate de WPF ahora son visibles en la UIA</span><span class="sxs-lookup"><span data-stu-id="bdbd6-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="bdbd6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bdbd6-102">Details</span></span>

<span data-ttu-id="bdbd6-103">Anteriormente, los elementos <xref:System.Windows.DataTemplate?displayProperty=fullName> no eran visibles para la automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="bdbd6-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="bdbd6-104">A partir de la versión 4.5, la automatización de la IU detectará estos elementos.</span><span class="sxs-lookup"><span data-stu-id="bdbd6-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="bdbd6-105">Esto resulta útil en muchos casos, pero puede interrumpir las pruebas que dependan de árboles de la UIA que no contengan elementos <xref:System.Windows.DataTemplate?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="bdbd6-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bdbd6-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bdbd6-106">Suggestion</span></span>

<span data-ttu-id="bdbd6-107">Puede ser necesario actualizar las pruebas de automatización de la interfaz de usuario para esta aplicación con el fin de procesar el árbol de la UIA que ahora incluye elementos <xref:System.Windows.DataTemplate?displayProperty=fullName> que antes no eran visibles.</span><span class="sxs-lookup"><span data-stu-id="bdbd6-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="bdbd6-108">Por ejemplo, en aquellas pruebas en las que se espere que haya ciertos elementos contiguos entre sí, ahora puede ser necesario esperar ciertos elementos intermedios de la UIA que antes no eran visibles.</span><span class="sxs-lookup"><span data-stu-id="bdbd6-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="bdbd6-109">También puede ser necesario actualizar con nuevos valores pruebas que dependan de ciertos recuentos o índices para elementos de la UIA.</span><span class="sxs-lookup"><span data-stu-id="bdbd6-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="bdbd6-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="bdbd6-110">Name</span></span>    | <span data-ttu-id="bdbd6-111">Valor</span><span class="sxs-lookup"><span data-stu-id="bdbd6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bdbd6-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bdbd6-112">Scope</span></span>   |<span data-ttu-id="bdbd6-113">Borde</span><span class="sxs-lookup"><span data-stu-id="bdbd6-113">Edge</span></span>|
|<span data-ttu-id="bdbd6-114">Versión</span><span class="sxs-lookup"><span data-stu-id="bdbd6-114">Version</span></span>|<span data-ttu-id="bdbd6-115">4.5</span><span class="sxs-lookup"><span data-stu-id="bdbd6-115">4.5</span></span>|
|<span data-ttu-id="bdbd6-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="bdbd6-116">Type</span></span>|<span data-ttu-id="bdbd6-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="bdbd6-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bdbd6-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bdbd6-118">Affected APIs</span></span>

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
