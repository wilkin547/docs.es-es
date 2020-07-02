---
ms.openlocfilehash: a82b720fd4e771481ea1142a88a095443afa0d5b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614942"
---
### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="85ab1-101">El foco del teclado se mueve ahora correctamente entre varios niveles de hospedaje de WinForms y WPF</span><span class="sxs-lookup"><span data-stu-id="85ab1-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

#### <a name="details"></a><span data-ttu-id="85ab1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="85ab1-102">Details</span></span>

<span data-ttu-id="85ab1-103">Suponga que una aplicación de WPF hospeda un control de WinForms que, a su vez, hospeda controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="85ab1-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="85ab1-104">Es posible que los usuarios no puedan presionar Tab para salir de la capa de WinForms si el primer control o el último de esa capa es `System.Windows.Forms.Integration.ElementHost` de WPF.</span><span class="sxs-lookup"><span data-stu-id="85ab1-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF `System.Windows.Forms.Integration.ElementHost`.</span></span> <span data-ttu-id="85ab1-105">Este cambio soluciona este problema y los usuarios ahora pueden presionar Tab para salir de la capa de WinForms. Las aplicaciones automatizadas que se basan en que el foco no escape nunca de la capa de WinForms ya no funcionarán según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="85ab1-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="85ab1-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="85ab1-106">Suggestion</span></span>

<span data-ttu-id="85ab1-107">Un desarrollador que quiera usar este cambio mientras selecciona como destino una versión de la plataforma inferior a .NET Framework 4.7.2 puede establecer en false el conjunto siguiente de marcas de AppContext para habilitar el cambio.</span><span class="sxs-lookup"><span data-stu-id="85ab1-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

<span data-ttu-id="85ab1-108">Las aplicaciones de WPF deben participar en todas las mejoras de accesibilidad anteriores para obtener las mejoras siguientes.</span><span class="sxs-lookup"><span data-stu-id="85ab1-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="85ab1-109">En otras palabras, se deben establecer los modificadores `Switch.UseLegacyAccessibilityFeatures` y `Switch.UseLegacyAccessibilityFeatures.2`. Un desarrollador que requiera la funcionalidad anterior mientras selecciona como destino .NET Framework 4.7.2 o una versión posterior puede establecer en true la marca de AppContext siguiente para deshabilitar el cambio.</span><span class="sxs-lookup"><span data-stu-id="85ab1-109">In other words, both the `Switch.UseLegacyAccessibilityFeatures` and the `Switch.UseLegacyAccessibilityFeatures.2` switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="85ab1-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="85ab1-110">Name</span></span>    | <span data-ttu-id="85ab1-111">Valor</span><span class="sxs-lookup"><span data-stu-id="85ab1-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="85ab1-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="85ab1-112">Scope</span></span>   | <span data-ttu-id="85ab1-113">Borde</span><span class="sxs-lookup"><span data-stu-id="85ab1-113">Edge</span></span>        |
| <span data-ttu-id="85ab1-114">Versión</span><span class="sxs-lookup"><span data-stu-id="85ab1-114">Version</span></span> | <span data-ttu-id="85ab1-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="85ab1-115">4.7.2</span></span>       |
| <span data-ttu-id="85ab1-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="85ab1-116">Type</span></span>    | <span data-ttu-id="85ab1-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="85ab1-117">Retargeting</span></span> |
