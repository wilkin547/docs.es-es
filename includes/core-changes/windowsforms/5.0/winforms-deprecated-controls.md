---
ms.openlocfilehash: c9720f51e40ada4cd2cf6997ba7006a232893553
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702469"
---
### <a name="removed-status-bar-controls"></a><span data-ttu-id="e541e-101">Controles de barra de estado quitados</span><span class="sxs-lookup"><span data-stu-id="e541e-101">Removed status bar controls</span></span>

<span data-ttu-id="e541e-102">A partir de la versión preliminar 1 de .NET 5.0, algunos controles de Windows Forms ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e541e-102">Starting in .NET 5.0 Preview 1, some Windows Forms controls are no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e541e-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e541e-103">Change description</span></span>

<span data-ttu-id="e541e-104">A partir de la versión preliminar 1 de .NET 5.0, algunos de los controles de Windows Forms relacionados con la barra de estado ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="e541e-104">Starting with .NET 5.0 Preview 1, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="e541e-105">Los controles de reemplazo, con un mejor diseño y soporte técnico, se introdujeron en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="e541e-105">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="e541e-106">Los controles en desuso se eliminaron previamente de los cuadros de herramientas del diseñador, pero todavía estaban disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="e541e-106">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="e541e-107">Ahora, se han quitado por completo.</span><span class="sxs-lookup"><span data-stu-id="e541e-107">Now, they have been completely removed.</span></span>

<span data-ttu-id="e541e-108">Los siguientes tipos ya no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="e541e-108">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a><span data-ttu-id="e541e-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e541e-109">Version introduced</span></span>

<span data-ttu-id="e541e-110">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="e541e-110">5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e541e-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e541e-111">Recommended action</span></span>

<span data-ttu-id="e541e-112">Vaya a las API de reemplazo de estos controles y sus escenarios:</span><span class="sxs-lookup"><span data-stu-id="e541e-112">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="e541e-113">Control anterior (API)</span><span class="sxs-lookup"><span data-stu-id="e541e-113">Old Control (API)</span></span> | <span data-ttu-id="e541e-114">Reemplazo recomendado</span><span class="sxs-lookup"><span data-stu-id="e541e-114">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="e541e-115">StatusBar</span><span class="sxs-lookup"><span data-stu-id="e541e-115">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="e541e-116">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="e541e-116">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a><span data-ttu-id="e541e-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="e541e-117">Category</span></span>

<span data-ttu-id="e541e-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e541e-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e541e-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e541e-119">Affected APIs</span></span>

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

#### Affected APIs

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
