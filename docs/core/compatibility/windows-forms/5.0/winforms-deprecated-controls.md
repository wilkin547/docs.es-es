---
title: 'Cambio importante: Controles de barra de estado quitados'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde algunos controles de Windows Forms ya no están disponibles.
ms.date: 07/18/2020
ms.openlocfilehash: 70aaa20f3fee1f4c342c4d9e547b0658aaf533b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760228"
---
# <a name="removed-status-bar-controls"></a><span data-ttu-id="3b6ad-103">Controles de barra de estado quitados</span><span class="sxs-lookup"><span data-stu-id="3b6ad-103">Removed status bar controls</span></span>

<span data-ttu-id="3b6ad-104">A partir de .NET 5.0, algunos controles de Windows Forms ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3b6ad-104">Starting in .NET 5.0, some Windows Forms controls are no longer available.</span></span>

## <a name="change-description"></a><span data-ttu-id="3b6ad-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="3b6ad-105">Change description</span></span>

<span data-ttu-id="3b6ad-106">A partir de .NET 5.0, algunos de los controles de Windows Forms relacionados con la barra de estado ya no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3b6ad-106">Starting with .NET 5.0, some of the status bar-related Windows Forms controls are no longer available.</span></span> <span data-ttu-id="3b6ad-107">Los controles de reemplazo, con un mejor diseño y soporte técnico, se introdujeron en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="3b6ad-107">Replacement controls that have better design and support were introduced in .NET Framework 2.0.</span></span> <span data-ttu-id="3b6ad-108">Los controles en desuso se eliminaron previamente de los cuadros de herramientas del diseñador, pero todavía estaban disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="3b6ad-108">The deprecated controls were previously removed from designer toolboxes but were still available to be used.</span></span> <span data-ttu-id="3b6ad-109">Ahora, se han quitado por completo.</span><span class="sxs-lookup"><span data-stu-id="3b6ad-109">Now, they have been completely removed.</span></span>

<span data-ttu-id="3b6ad-110">Los siguientes tipos ya no están disponibles:</span><span class="sxs-lookup"><span data-stu-id="3b6ad-110">The following types are no longer available:</span></span>

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

## <a name="version-introduced"></a><span data-ttu-id="3b6ad-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3b6ad-111">Version introduced</span></span>

<span data-ttu-id="3b6ad-112">5.0</span><span class="sxs-lookup"><span data-stu-id="3b6ad-112">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="3b6ad-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3b6ad-113">Recommended action</span></span>

<span data-ttu-id="3b6ad-114">Vaya a las API de reemplazo de estos controles y sus escenarios:</span><span class="sxs-lookup"><span data-stu-id="3b6ad-114">Move to the replacement APIs for these controls and their scenarios:</span></span>

| <span data-ttu-id="3b6ad-115">Control anterior (API)</span><span class="sxs-lookup"><span data-stu-id="3b6ad-115">Old Control (API)</span></span> | <span data-ttu-id="3b6ad-116">Reemplazo recomendado</span><span class="sxs-lookup"><span data-stu-id="3b6ad-116">Recommended Replacement</span></span>                          |
|-------------------|--------------------------------------------------|
| <span data-ttu-id="3b6ad-117">StatusBar</span><span class="sxs-lookup"><span data-stu-id="3b6ad-117">StatusBar</span></span>         | <xref:System.Windows.Forms.StatusStrip>          |
| <span data-ttu-id="3b6ad-118">StatusBarPanel</span><span class="sxs-lookup"><span data-stu-id="3b6ad-118">StatusBarPanel</span></span>    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

## <a name="affected-apis"></a><span data-ttu-id="3b6ad-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3b6ad-119">Affected APIs</span></span>

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

### Category

Windows Forms

-->
