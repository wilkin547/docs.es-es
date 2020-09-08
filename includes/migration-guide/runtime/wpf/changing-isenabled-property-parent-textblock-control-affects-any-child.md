---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497644"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="d8c70-101">El cambio de la propiedad IsEnabled del elemento primario de un control TextBlock afecta a todos los controles secundarios</span><span class="sxs-lookup"><span data-stu-id="d8c70-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="d8c70-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8c70-102">Details</span></span>

<span data-ttu-id="d8c70-103">A partir de .NET Framework 4.6.2, el cambio de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> del elemento primario de un control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> afecta a todos los controles secundarios (como los hipervínculos y los botones) del control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. En .NET Framework 4.6.1 y versiones anteriores, los controles dentro de un <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> no siempre reflejaban el estado de la propiedad <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> del elemento <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> primario.</span><span class="sxs-lookup"><span data-stu-id="d8c70-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d8c70-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d8c70-104">Suggestion</span></span>

<span data-ttu-id="d8c70-105">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d8c70-105">None.</span></span> <span data-ttu-id="d8c70-106">Este cambio se ajusta al comportamiento esperado de los controles dentro de un control <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d8c70-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="d8c70-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="d8c70-107">Name</span></span>    | <span data-ttu-id="d8c70-108">Valor</span><span class="sxs-lookup"><span data-stu-id="d8c70-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d8c70-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d8c70-109">Scope</span></span>   |<span data-ttu-id="d8c70-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="d8c70-110">Minor</span></span>|
|<span data-ttu-id="d8c70-111">Versión</span><span class="sxs-lookup"><span data-stu-id="d8c70-111">Version</span></span>|<span data-ttu-id="d8c70-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d8c70-112">4.6.2</span></span>|
|<span data-ttu-id="d8c70-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="d8c70-113">Type</span></span>|<span data-ttu-id="d8c70-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d8c70-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d8c70-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d8c70-115">Affected APIs</span></span>

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
