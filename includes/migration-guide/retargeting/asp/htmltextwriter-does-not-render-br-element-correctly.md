---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615743"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="fa58c-101">HtmlTextWriter no representa el elemento `<br/>` de forma correcta</span><span class="sxs-lookup"><span data-stu-id="fa58c-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

#### <a name="details"></a><span data-ttu-id="fa58c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa58c-102">Details</span></span>

<span data-ttu-id="fa58c-103">A partir de .NET Framework 4.6, al llamar a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> y <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento `<BR />` solo insertará correctamente un `<BR />` (en lugar de dos).</span><span class="sxs-lookup"><span data-stu-id="fa58c-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a `<BR />` element will correctly insert only one `<BR />` (instead of two)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fa58c-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="fa58c-104">Suggestion</span></span>

<span data-ttu-id="fa58c-105">Si alguna aplicación dependía de la etiqueta `<BR />` adicional, debería llamarse a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> una segunda vez.</span><span class="sxs-lookup"><span data-stu-id="fa58c-105">If an app depended on the extra `<BR />` tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="fa58c-106">Tenga en cuenta que este cambio de comportamiento solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6 o una versión posterior, por lo que otra opción es seleccionar como destino una versión anterior de .NET Framework para conseguir el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="fa58c-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>

| <span data-ttu-id="fa58c-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="fa58c-107">Name</span></span>    | <span data-ttu-id="fa58c-108">Valor</span><span class="sxs-lookup"><span data-stu-id="fa58c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fa58c-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="fa58c-109">Scope</span></span>   | <span data-ttu-id="fa58c-110">Borde</span><span class="sxs-lookup"><span data-stu-id="fa58c-110">Edge</span></span>        |
| <span data-ttu-id="fa58c-111">Versión</span><span class="sxs-lookup"><span data-stu-id="fa58c-111">Version</span></span> | <span data-ttu-id="fa58c-112">4.6</span><span class="sxs-lookup"><span data-stu-id="fa58c-112">4.6</span></span>         |
| <span data-ttu-id="fa58c-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="fa58c-113">Type</span></span>    | <span data-ttu-id="fa58c-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="fa58c-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="fa58c-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fa58c-115">Affected APIs</span></span>

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
