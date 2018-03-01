---
title: "Información general sobre el control MenuStrip (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eb27503fffc798b644f95fd213f8f23bdb3e228a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="2566a-102">Información general sobre el control MenuStrip (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2566a-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="2566a-103">Los menús exponen la funcionalidad a los usuarios, se conservan los comandos que están agrupados por un tema común.</span><span class="sxs-lookup"><span data-stu-id="2566a-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="2566a-104">El <xref:System.Windows.Forms.MenuStrip> control es una novedad de esta versión de Visual Studio y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2566a-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="2566a-105">Con el control, puede crear fácilmente menús como los que se encuentran en Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="2566a-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="2566a-106">El <xref:System.Windows.Forms.MenuStrip> control es compatible con la interfaz de múltiples documentos (MDI) y combinación de menús, información sobre herramientas y desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="2566a-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="2566a-107">Puede mejorar la facilidad de uso y mejorar la legibilidad de los menús agregando teclas de acceso, teclas de método abreviado, marcas de verificación, imágenes y barras separadoras.</span><span class="sxs-lookup"><span data-stu-id="2566a-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="2566a-108">El <xref:System.Windows.Forms.MenuStrip> control reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.MainMenu> control; sin embargo, el <xref:System.Windows.Forms.MainMenu> control se conserva para compatibilidad con versiones anteriores y uso futuro, si elige.</span><span class="sxs-lookup"><span data-stu-id="2566a-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="2566a-109">Formas de utilizar el Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="2566a-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="2566a-110">Use el <xref:System.Windows.Forms.MenuStrip> el control al:</span><span class="sxs-lookup"><span data-stu-id="2566a-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="2566a-111">Crear fácilmente personalizada, comúnmente empleados menús que admiten usuario interfaz y el diseño características avanzadas, como texto y ordenación de imagen y alineación, operaciones de arrastrar y colocar, MDI, desbordamiento y modos alternativos de acceso a los comandos de menú.</span><span class="sxs-lookup"><span data-stu-id="2566a-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="2566a-112">Admite la apariencia habitual y el comportamiento del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2566a-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="2566a-113">Controlar los eventos de forma coherente para todos los contenedores y los elementos contenidos, de la misma manera controlar los eventos de otros controles.</span><span class="sxs-lookup"><span data-stu-id="2566a-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="2566a-114">La siguiente tabla muestra algunas propiedades especialmente importantes de <xref:System.Windows.Forms.MenuStrip> y asociados de clases.</span><span class="sxs-lookup"><span data-stu-id="2566a-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="2566a-115">Property</span><span class="sxs-lookup"><span data-stu-id="2566a-115">Property</span></span>|<span data-ttu-id="2566a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="2566a-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="2566a-117">Obtiene o establece el <xref:System.Windows.Forms.ToolStripMenuItem> que se usa para mostrar una lista de formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="2566a-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="2566a-118">Obtiene o establece cómo se combinan los menús secundarios con menús primarios en aplicaciones MDI.</span><span class="sxs-lookup"><span data-stu-id="2566a-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="2566a-119">Obtiene o establece la posición de un elemento combinado dentro de un menú en aplicaciones MDI.</span><span class="sxs-lookup"><span data-stu-id="2566a-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="2566a-120">Obtiene o establece un valor que indica si el formulario es un contenedor para formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="2566a-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="2566a-121">Obtiene o establece un valor que indica si se muestra información sobre herramientas para el <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2566a-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="2566a-122">Obtiene o establece un valor que indica si <xref:System.Windows.Forms.MenuStrip> admite la funcionalidad del desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="2566a-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="2566a-123">Obtiene o establece las teclas de método abreviado asociadas a la <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="2566a-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="2566a-124">Obtiene o establece un valor que indica si el método abreviado de claves que están asociadas a la <xref:System.Windows.Forms.ToolStripMenuItem> se muestran junto a la <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="2566a-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="2566a-125">La siguiente tabla muestra las importantes <xref:System.Windows.Forms.MenuStrip> clases complementarias.</span><span class="sxs-lookup"><span data-stu-id="2566a-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="2566a-126">Clase</span><span class="sxs-lookup"><span data-stu-id="2566a-126">Class</span></span>|<span data-ttu-id="2566a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="2566a-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="2566a-128">Representa una opción seleccionable mostrada en un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="2566a-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="2566a-129">Representa un menú contextual.</span><span class="sxs-lookup"><span data-stu-id="2566a-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="2566a-130">Representa un control que permite al usuario seleccionar un único elemento de una lista que se muestra cuando el usuario hace clic en un <xref:System.Windows.Forms.ToolStripDropDownButton> o un elemento de menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="2566a-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="2566a-131">Proporciona la funcionalidad básica para los controles derivan de <xref:System.Windows.Forms.ToolStripItem> que mostrar los elementos de lista desplegable al hacer clic en.</span><span class="sxs-lookup"><span data-stu-id="2566a-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2566a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2566a-132">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
