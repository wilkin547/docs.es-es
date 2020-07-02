---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621398"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="6676a-101">El cambio de la propiedad IsEnabled del elemento primario de un control TextBlock afecta a todos los controles secundarios</span><span class="sxs-lookup"><span data-stu-id="6676a-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="6676a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6676a-102">Details</span></span>

<span data-ttu-id="6676a-103">A partir de .NET Framework 4.6.2, el cambio de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> del elemento primario de un control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> afecta a todos los controles secundarios (como los hipervínculos y los botones) del control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. En .NET Framework 4.6.1 y versiones anteriores, los controles dentro de un <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> no siempre reflejaban el estado de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> del elemento <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> primario.</span><span class="sxs-lookup"><span data-stu-id="6676a-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6676a-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6676a-104">Suggestion</span></span>

<span data-ttu-id="6676a-105">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6676a-105">None.</span></span> <span data-ttu-id="6676a-106">Este cambio se ajusta al comportamiento esperado de los controles dentro de un control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6676a-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="6676a-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="6676a-107">Name</span></span>    | <span data-ttu-id="6676a-108">Valor</span><span class="sxs-lookup"><span data-stu-id="6676a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6676a-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6676a-109">Scope</span></span>   |<span data-ttu-id="6676a-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6676a-110">Minor</span></span>|
|<span data-ttu-id="6676a-111">Versión</span><span class="sxs-lookup"><span data-stu-id="6676a-111">Version</span></span>|<span data-ttu-id="6676a-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="6676a-112">4.6.2</span></span>|
|<span data-ttu-id="6676a-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="6676a-113">Type</span></span>|<span data-ttu-id="6676a-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6676a-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6676a-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6676a-115">Affected APIs</span></span>

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
