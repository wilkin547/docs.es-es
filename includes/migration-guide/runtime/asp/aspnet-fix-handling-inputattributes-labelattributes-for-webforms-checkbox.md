---
ms.openlocfilehash: ae557ce57557d027dba35b7da213c08aee85f2c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622074"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="26bd1-101">Se ha corregido el procesamiento de ASP.NET en InputAttributes y LabelAttributes para el control de casilla de WebForms</span><span class="sxs-lookup"><span data-stu-id="26bd1-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="26bd1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="26bd1-102">Details</span></span>

<span data-ttu-id="26bd1-103">Para las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> y <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> que se agregan mediante programación a un control <xref:System.Web.UI.WebControls.CheckBox> de WebForms se pierden después del postback.</span><span class="sxs-lookup"><span data-stu-id="26bd1-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="26bd1-104">Para las aplicaciones que tienen como destino .NET Framework 4.8 o versiones posteriores, se mantienen después del postback.</span><span class="sxs-lookup"><span data-stu-id="26bd1-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="26bd1-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="26bd1-105">Suggestion</span></span>

<span data-ttu-id="26bd1-106">Para obtener el comportamiento correcto para restaurar los atributos en el postback, establezca <code>targetFrameworkVersion</code> en 4.8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="26bd1-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="26bd1-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="26bd1-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="26bd1-108">Si se establece en una versión inferior, o en ninguna, se conserva el antiguo comportamiento incorrecto.</span><span class="sxs-lookup"><span data-stu-id="26bd1-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="26bd1-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="26bd1-109">Name</span></span>    | <span data-ttu-id="26bd1-110">Valor</span><span class="sxs-lookup"><span data-stu-id="26bd1-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="26bd1-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="26bd1-111">Scope</span></span>   |<span data-ttu-id="26bd1-112">Desconocido</span><span class="sxs-lookup"><span data-stu-id="26bd1-112">Unknown</span></span>|
|<span data-ttu-id="26bd1-113">Versión</span><span class="sxs-lookup"><span data-stu-id="26bd1-113">Version</span></span>|<span data-ttu-id="26bd1-114">4.8</span><span class="sxs-lookup"><span data-stu-id="26bd1-114">4.8</span></span>|
|<span data-ttu-id="26bd1-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="26bd1-115">Type</span></span>|<span data-ttu-id="26bd1-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="26bd1-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="26bd1-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="26bd1-117">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType></li></ul>|
