---
ms.openlocfilehash: 27bd38edd81abb5ce5893021bcc96e7eeae7ae2c
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140885"
---
### <a name="removed-status-bar-controls"></a><span data-ttu-id="9eab7-101">Controles de barra de estado quitados</span><span class="sxs-lookup"><span data-stu-id="9eab7-101">Removed status bar controls</span></span>

<span data-ttu-id="9eab7-102">A partir de la versión preliminar 1 de .NET 5.0, algunos controles de Windows Forms ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9eab7-102">Starting in .NET 5.0 Preview 1, some Windows Forms controls are no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9eab7-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="9eab7-103">Change description</span></span>

<span data-ttu-id="9eab7-104">A partir de la versión preliminar 1 de .NET 5.0, algunos de los controles de Windows Forms relacionados con la barra de estado ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9eab7-104">Starting with .NET 5.0 Preview 1, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="9eab7-105">Los controles de reemplazo, con un mejor diseño y soporte técnico, se introdujeron en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="9eab7-105">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="9eab7-106">Los controles en desuso se eliminaron previamente de los cuadros de herramientas del diseñador, pero todavía estaban disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="9eab7-106">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="9eab7-107">Ahora, se han quitado por completo.</span><span class="sxs-lookup"><span data-stu-id="9eab7-107">Now, they have been completely removed.</span></span>

<span data-ttu-id="9eab7-108">Los siguientes tipos ya no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="9eab7-108">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a><span data-ttu-id="9eab7-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="9eab7-109">Version introduced</span></span>

<span data-ttu-id="9eab7-110">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="9eab7-110">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9eab7-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="9eab7-111">Recommended action</span></span>

<span data-ttu-id="9eab7-112">Vaya a las API de reemplazo de estos controles y sus escenarios:</span><span class="sxs-lookup"><span data-stu-id="9eab7-112">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="9eab7-113">Control anterior (API)</span><span class="sxs-lookup"><span data-stu-id="9eab7-113">Old Control (API)</span></span> | <span data-ttu-id="9eab7-114">Reemplazo recomendado</span><span class="sxs-lookup"><span data-stu-id="9eab7-114">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="9eab7-115">StatusBar</span><span class="sxs-lookup"><span data-stu-id="9eab7-115">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="9eab7-116">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="9eab7-116">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a><span data-ttu-id="9eab7-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="9eab7-117">Category</span></span>

<span data-ttu-id="9eab7-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9eab7-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9eab7-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9eab7-119">Affected APIs</span></span>

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!-- 

### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle` 

-->
