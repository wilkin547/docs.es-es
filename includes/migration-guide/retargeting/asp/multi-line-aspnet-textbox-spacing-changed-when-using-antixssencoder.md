---
ms.openlocfilehash: 53860bb867522503c5cb9bd35e25fadd00a116a2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609171"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="b0aa4-101">Cambio de interlineado de los cuadros de texto multilínea de ASP.NET al usar AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="b0aa4-101">Multi-line ASP.NET TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="b0aa4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0aa4-102">Details</span></span>

<span data-ttu-id="b0aa4-103">En .NET Framework 4.0, se introdujeron líneas adicionales entre las líneas de un cuadro de texto multilínea en postback si se usaba el elemento <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="b0aa4-104">En .NET Framework 4.5 no se incluyen estos saltos de línea adicionales, pero únicamente si la aplicación web tiene como destino .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b0aa4-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b0aa4-105">Suggestion</span></span>

<span data-ttu-id="b0aa4-106">Tenga en cuenta que las aplicaciones web de la versión 4.0 redestinadas a .NET Framework 4.5 pueden tener cuadros de texto multilínea mejorados para dejar de introducir saltos de línea adicionales.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="b0aa4-107">Si este no es el comportamiento deseado, la aplicación puede tener el anterior cuando se ejecuta en .NET Framework 4.5 si se establece .NET Framework 4.0 como destino.</span><span class="sxs-lookup"><span data-stu-id="b0aa4-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="b0aa4-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b0aa4-108">Name</span></span>    | <span data-ttu-id="b0aa4-109">Valor</span><span class="sxs-lookup"><span data-stu-id="b0aa4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b0aa4-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b0aa4-110">Scope</span></span>   | <span data-ttu-id="b0aa4-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b0aa4-111">Minor</span></span>       |
| <span data-ttu-id="b0aa4-112">Versión</span><span class="sxs-lookup"><span data-stu-id="b0aa4-112">Version</span></span> | <span data-ttu-id="b0aa4-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b0aa4-113">4.5</span></span>         |
| <span data-ttu-id="b0aa4-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0aa4-114">Type</span></span>    | <span data-ttu-id="b0aa4-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="b0aa4-115">Retargeting</span></span> |
