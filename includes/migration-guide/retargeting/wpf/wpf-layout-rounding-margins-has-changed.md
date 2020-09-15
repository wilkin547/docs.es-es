---
ms.openlocfilehash: f907cb1939e111c586d68243e6b8a8e291974e36
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615774"
---
### <a name="wpf-layout-rounding-of-margins-has-changed"></a><span data-ttu-id="4f136-101">Ha cambiado el redondeo del diseño de márgenes en WPF</span><span class="sxs-lookup"><span data-stu-id="4f136-101">WPF layout rounding of margins has changed</span></span>

#### <a name="details"></a><span data-ttu-id="4f136-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4f136-102">Details</span></span>

<span data-ttu-id="4f136-103">Ha cambiado la manera en la que se redondean los márgenes, así como los bordes y el fondo de estos.</span><span class="sxs-lookup"><span data-stu-id="4f136-103">The way in which margins are rounded and borders and the background inside of them has changed.</span></span> <span data-ttu-id="4f136-104">Debido a este cambio:</span><span class="sxs-lookup"><span data-stu-id="4f136-104">As a result of this change:</span></span>

- <span data-ttu-id="4f136-105">El ancho o alto de los elementos puede aumentar o disminuir un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="4f136-105">The width or height of elements may grow or shrink by at most one pixel.</span></span>
- <span data-ttu-id="4f136-106">La posición de un objeto se puede mover un píxel como máximo.</span><span class="sxs-lookup"><span data-stu-id="4f136-106">The placement of an object can move by at most one pixel.</span></span>
- <span data-ttu-id="4f136-107">Los elementos centrados pueden estar descentrados como máximo en un píxel en vertical o en horizontal.</span><span class="sxs-lookup"><span data-stu-id="4f136-107">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>
<span data-ttu-id="4f136-108">De forma predeterminada, este nuevo diseño solo está habilitado para las aplicaciones que tienen como destino .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="4f136-108">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4f136-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4f136-109">Suggestion</span></span>

<span data-ttu-id="4f136-110">Dado que esta modificación tiende a eliminar el recorte de la parte derecha o inferior de los controles WPF en PPP altos, las aplicaciones destinadas a versiones anteriores de .NET Framework que se ejecutan en .NET Framework 4.6 pueden optar por este nuevo comportamiento agregando la siguiente línea a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="4f136-110">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false&quot; /&gt;&#39;&#13;&#10;</code></pre>

<span data-ttu-id="4f136-111">Las aplicaciones que tienen como destino .NET Framework 4.6 pero que quieren que los controles de WPF se representen con el algoritmo de diseño anterior pueden hacerlo mediante la adición de la línea siguiente a la sección `<runtime>` del archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="4f136-111">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the `<runtime>` section of the app.config file:</span></span>

<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true&quot; /&gt;&#39;.&#13;&#10;</code></pre>

| <span data-ttu-id="4f136-112">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="4f136-112">Name</span></span>    | <span data-ttu-id="4f136-113">Valor</span><span class="sxs-lookup"><span data-stu-id="4f136-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4f136-114">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4f136-114">Scope</span></span>   | <span data-ttu-id="4f136-115">Secundaria</span><span class="sxs-lookup"><span data-stu-id="4f136-115">Minor</span></span>       |
| <span data-ttu-id="4f136-116">Versión</span><span class="sxs-lookup"><span data-stu-id="4f136-116">Version</span></span> | <span data-ttu-id="4f136-117">4.6</span><span class="sxs-lookup"><span data-stu-id="4f136-117">4.6</span></span>         |
| <span data-ttu-id="4f136-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="4f136-118">Type</span></span>    | <span data-ttu-id="4f136-119">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4f136-119">Retargeting</span></span> |
