---
ms.openlocfilehash: 55a26f1ab27792cbedf3f31b797f37d3f768d51a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496371"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="eb50c-101">Se ha corregido el procesamiento de ASP.NET en InputAttributes y LabelAttributes para el control de casilla de WebForms</span><span class="sxs-lookup"><span data-stu-id="eb50c-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="eb50c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="eb50c-102">Details</span></span>

<span data-ttu-id="eb50c-103">Para las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> que se agregan mediante programación a un control <xref:System.Web.UI.WebControls.CheckBox> de WebForms se pierden después del postback.</span><span class="sxs-lookup"><span data-stu-id="eb50c-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="eb50c-104">Para las aplicaciones que tienen como destino .NET Framework 4.8 o versiones posteriores, se mantienen después del postback.</span><span class="sxs-lookup"><span data-stu-id="eb50c-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eb50c-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="eb50c-105">Suggestion</span></span>

<span data-ttu-id="eb50c-106">Para obtener el comportamiento correcto para restaurar los atributos en el postback, establezca <code>targetFrameworkVersion</code> en 4.8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="eb50c-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="eb50c-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eb50c-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="eb50c-108">Si se establece en una versión inferior, o en ninguna, se conserva el antiguo comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="eb50c-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="eb50c-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="eb50c-109">Name</span></span>    | <span data-ttu-id="eb50c-110">Valor</span><span class="sxs-lookup"><span data-stu-id="eb50c-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eb50c-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="eb50c-111">Scope</span></span>   |<span data-ttu-id="eb50c-112">Desconocido</span><span class="sxs-lookup"><span data-stu-id="eb50c-112">Unknown</span></span>|
|<span data-ttu-id="eb50c-113">Versión</span><span class="sxs-lookup"><span data-stu-id="eb50c-113">Version</span></span>|<span data-ttu-id="eb50c-114">4.8</span><span class="sxs-lookup"><span data-stu-id="eb50c-114">4.8</span></span>|
|<span data-ttu-id="eb50c-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb50c-115">Type</span></span>|<span data-ttu-id="eb50c-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="eb50c-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eb50c-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="eb50c-117">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.UI.WebControls.CheckBox`

-->
