---
title: "Información general del control ToolStripContainer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4abc783961177a55cdb81cefd21ed2d7aefb0620
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="d3951-102">Información general del control ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="d3951-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="d3951-103">A <xref:System.Windows.Forms.ToolStripContainer> , tenga paneles en su izquierda, derecha, arriba y lados de la parte inferior para colocar y compartir el espacio <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, y <xref:System.Windows.Forms.StatusStrip> controles.</span><span class="sxs-lookup"><span data-stu-id="d3951-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="d3951-104">Los diferentes controles <xref:System.Windows.Forms.ToolStrip> se apilan verticalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> izquierdo o derecho.</span><span class="sxs-lookup"><span data-stu-id="d3951-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="d3951-105">Se apilan horizontalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> superior o inferior.</span><span class="sxs-lookup"><span data-stu-id="d3951-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="d3951-106">Puede usar el <xref:System.Windows.Forms.ToolStripContentPanel> central del <xref:System.Windows.Forms.ToolStripContainer> para colocar controles tradicionales en el formulario.</span><span class="sxs-lookup"><span data-stu-id="d3951-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="d3951-107">Los controles <xref:System.Windows.Forms.ToolStripContainer> se pueden seleccionar (uno solo o todos ellos) en tiempo de diseño y se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="d3951-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="d3951-108">Cada panel de un <xref:System.Windows.Forms.ToolStripContainer> se pueden expandir y contraer y cambia el tamaño de los controles que contiene.</span><span class="sxs-lookup"><span data-stu-id="d3951-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="d3951-109">Miembros importantes de ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="d3951-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="d3951-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="d3951-110">Name</span></span>|<span data-ttu-id="d3951-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3951-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="d3951-112">Obtiene el panel inferior de la <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="d3951-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="d3951-113">Obtiene o establece un valor que indica si el panel inferior de la <xref:System.Windows.Forms.ToolStripContainer> está visible.</span><span class="sxs-lookup"><span data-stu-id="d3951-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="d3951-114">Obtiene el panel izquierdo de la <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="d3951-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="d3951-115">Obtiene o establece un valor que indica si el panel izquierdo de la <xref:System.Windows.Forms.ToolStripContainer> está visible.</span><span class="sxs-lookup"><span data-stu-id="d3951-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="d3951-116">Obtiene el panel derecho de la <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="d3951-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="d3951-117">Obtiene o establece un valor que indica si el panel derecho de la <xref:System.Windows.Forms.ToolStripContainer> está visible.</span><span class="sxs-lookup"><span data-stu-id="d3951-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="d3951-118">Obtiene el panel superior de la <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="d3951-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="d3951-119">Obtiene o establece un valor que indica si el panel superior de la <xref:System.Windows.Forms.ToolStripContainer> está visible.</span><span class="sxs-lookup"><span data-stu-id="d3951-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3951-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3951-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
