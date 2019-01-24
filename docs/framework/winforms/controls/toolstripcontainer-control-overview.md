---
title: Información general del control ToolStripContainer
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: 1f8d8bf8edd7968ed2d2a5c4ddd654dccf318f71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654053"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="3774d-102">Información general del control ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="3774d-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="3774d-103">Un <xref:System.Windows.Forms.ToolStripContainer> tiene paneles a su izquierda, derecha, superior y lados de la parte inferior para colocar y compartir el espacio <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, y <xref:System.Windows.Forms.StatusStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="3774d-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="3774d-104">Los diferentes controles <xref:System.Windows.Forms.ToolStrip> se apilan verticalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> izquierdo o derecho.</span><span class="sxs-lookup"><span data-stu-id="3774d-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="3774d-105">Se apilan horizontalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> superior o inferior.</span><span class="sxs-lookup"><span data-stu-id="3774d-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="3774d-106">Puede usar el <xref:System.Windows.Forms.ToolStripContentPanel> central del <xref:System.Windows.Forms.ToolStripContainer> para colocar controles tradicionales en el formulario.</span><span class="sxs-lookup"><span data-stu-id="3774d-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="3774d-107">Los controles <xref:System.Windows.Forms.ToolStripContainer> se pueden seleccionar (uno solo o todos ellos) en tiempo de diseño y se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="3774d-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="3774d-108">Cada panel de un <xref:System.Windows.Forms.ToolStripContainer> es ampliable y plegable y cambia el tamaño con los controles que contiene.</span><span class="sxs-lookup"><span data-stu-id="3774d-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="3774d-109">Miembros importantes de ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="3774d-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="3774d-110">nombre</span><span class="sxs-lookup"><span data-stu-id="3774d-110">Name</span></span>|<span data-ttu-id="3774d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3774d-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="3774d-112">Obtiene el panel inferior del objeto <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="3774d-113">Obtiene o establece un valor que indica si está visible el panel inferior del control <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="3774d-114">Obtiene el panel izquierdo del objeto <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="3774d-115">Obtiene o establece un valor que indica si está visible el panel izquierdo del control <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="3774d-116">Obtiene el panel derecho del objeto <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="3774d-117">Obtiene o establece un valor que indica si está visible el panel derecho del control <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="3774d-118">Obtiene el panel superior del objeto <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="3774d-119">Obtiene o establece un valor que indica si está visible el panel superior del control <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="3774d-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3774d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3774d-120">See also</span></span>
- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
