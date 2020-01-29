---
title: Información general sobre el control MenuStrip
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734466"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="7f98d-102">Información general sobre el control MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7f98d-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="7f98d-103">Los menús exponen la funcionalidad a los usuarios manteniendo los comandos agrupados por un tema común.</span><span class="sxs-lookup"><span data-stu-id="7f98d-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="7f98d-104">El control <xref:System.Windows.Forms.MenuStrip> se presentó en la versión 2,0 del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f98d-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="7f98d-105">Con el control de <xref:System.Windows.Forms.MenuStrip>, puede crear fácilmente menús como los que se encuentran en Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7f98d-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="7f98d-106">El control <xref:System.Windows.Forms.MenuStrip> es compatible con la interfaz de múltiples documentos (MDI) y la combinación de menús, la información sobre herramientas y el desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="7f98d-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="7f98d-107">Puede mejorar la facilidad de uso y la legibilidad de los menús agregando teclas de acceso, teclas de método abreviado, marcas de verificación, imágenes y barras separadoras.</span><span class="sxs-lookup"><span data-stu-id="7f98d-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="7f98d-108">El control <xref:System.Windows.Forms.MenuStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.MainMenu>. sin embargo, el control de <xref:System.Windows.Forms.MainMenu> se conserva por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="7f98d-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="7f98d-109">Formas de usar el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="7f98d-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="7f98d-110">Utilice el control <xref:System.Windows.Forms.MenuStrip> para:</span><span class="sxs-lookup"><span data-stu-id="7f98d-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="7f98d-111">Cree menús fáciles de personalizar y de uso frecuente que admitan características avanzadas de la interfaz de usuario y el diseño, como el orden y la alineación de texto e imagen, operaciones de arrastrar y colocar, MDI, desbordamiento y modos alternativos de acceso a comandos de menú.</span><span class="sxs-lookup"><span data-stu-id="7f98d-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="7f98d-112">Admitir la apariencia y el comportamiento típicos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7f98d-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="7f98d-113">Controle los eventos de forma coherente para todos los contenedores y elementos contenidos, de la misma manera que controla los eventos de otros controles.</span><span class="sxs-lookup"><span data-stu-id="7f98d-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="7f98d-114">En la tabla siguiente se muestran algunas propiedades especialmente importantes de <xref:System.Windows.Forms.MenuStrip> y las clases asociadas.</span><span class="sxs-lookup"><span data-stu-id="7f98d-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="7f98d-115">La propiedad</span><span class="sxs-lookup"><span data-stu-id="7f98d-115">Property</span></span>|<span data-ttu-id="7f98d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f98d-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="7f98d-117">Obtiene o establece el <xref:System.Windows.Forms.ToolStripMenuItem> que se usa para mostrar una lista de formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="7f98d-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="7f98d-118">Obtiene o establece cómo se combinan los menús secundarios con los menús primarios en las aplicaciones MDI.</span><span class="sxs-lookup"><span data-stu-id="7f98d-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="7f98d-119">Obtiene o establece la posición de un elemento combinado en un menú de aplicaciones MDI.</span><span class="sxs-lookup"><span data-stu-id="7f98d-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="7f98d-120">Obtiene o establece un valor que indica si el formulario es un contenedor de formularios MDI secundarios.</span><span class="sxs-lookup"><span data-stu-id="7f98d-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="7f98d-121">Obtiene o establece un valor que indica si se muestra información sobre herramientas para el <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7f98d-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="7f98d-122">Obtiene o establece un valor que indica si <xref:System.Windows.Forms.MenuStrip> admite la funcionalidad del desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="7f98d-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="7f98d-123">Obtiene o establece las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="7f98d-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="7f98d-124">Obtiene o establece un valor que indica si las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem> se muestran al lado de <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="7f98d-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="7f98d-125">En la tabla siguiente se muestran las clases de complementos de <xref:System.Windows.Forms.MenuStrip> importantes.</span><span class="sxs-lookup"><span data-stu-id="7f98d-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="7f98d-126">Clase</span><span class="sxs-lookup"><span data-stu-id="7f98d-126">Class</span></span>|<span data-ttu-id="7f98d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f98d-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="7f98d-128">Representa una opción seleccionable mostrada en un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7f98d-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="7f98d-129">Representa un menú contextual.</span><span class="sxs-lookup"><span data-stu-id="7f98d-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="7f98d-130">Representa un control que permite al usuario seleccionar un solo elemento de una lista que se muestra cuando el usuario hace clic en un <xref:System.Windows.Forms.ToolStripDropDownButton> o en un elemento de menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="7f98d-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="7f98d-131">Proporciona la funcionalidad básica para los controles derivados de <xref:System.Windows.Forms.ToolStripItem> que muestran los elementos desplegables cuando se hace clic en ellos.</span><span class="sxs-lookup"><span data-stu-id="7f98d-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f98d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f98d-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
