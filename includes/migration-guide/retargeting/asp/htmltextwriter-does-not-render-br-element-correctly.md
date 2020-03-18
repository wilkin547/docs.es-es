---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804536"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="3e10b-101">HtmlTextWriter no representa el elemento `<br/>` de forma correcta</span><span class="sxs-lookup"><span data-stu-id="3e10b-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3e10b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3e10b-102">Details</span></span>|<span data-ttu-id="3e10b-103">A partir de .NET Framework 4.6, al llamar a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> y <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento <code>&lt;BR /&gt;</code> solo insertará correctamente un <code>&lt;BR /&gt;</code> (en lugar de dos).</span><span class="sxs-lookup"><span data-stu-id="3e10b-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="3e10b-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3e10b-104">Suggestion</span></span>|<span data-ttu-id="3e10b-105">Si alguna aplicación dependía de la etiqueta <code>&lt;BR /&gt;</code> adicional, debería llamarse a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> una segunda vez.</span><span class="sxs-lookup"><span data-stu-id="3e10b-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="3e10b-106">Tenga en cuenta que este cambio de comportamiento solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6 o una versión posterior, por lo que otra opción es seleccionar como destino una versión anterior de .NET Framework para conseguir el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="3e10b-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="3e10b-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3e10b-107">Scope</span></span>|<span data-ttu-id="3e10b-108">Borde</span><span class="sxs-lookup"><span data-stu-id="3e10b-108">Edge</span></span>|
|<span data-ttu-id="3e10b-109">Versión</span><span class="sxs-lookup"><span data-stu-id="3e10b-109">Version</span></span>|<span data-ttu-id="3e10b-110">4.6</span><span class="sxs-lookup"><span data-stu-id="3e10b-110">4.6</span></span>|
|<span data-ttu-id="3e10b-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3e10b-111">Type</span></span>|<span data-ttu-id="3e10b-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="3e10b-112">Retargeting</span></span>|
|<span data-ttu-id="3e10b-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3e10b-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
