---
title: ListView (Control, formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- lists
- checked list items [Windows Forms], Windows Forms controls
- user interface [Windows Forms], creating
- lists [Windows Forms], items with icons
- icons [Windows Forms], listing with items
- list views
- ListView control [Windows Forms]
- list controls [Windows Forms], List view
ms.assetid: 9f71cf5c-82da-488a-a04e-ef52c0817187
ms.openlocfilehash: e30f4b21d8b8f1a4c5a168402ce5cc386d932f86
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510616"
---
# <a name="listview-control-windows-forms"></a><span data-ttu-id="f841a-102">ListView (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f841a-102">ListView Control (Windows Forms)</span></span>
<span data-ttu-id="f841a-103">El control `ListView` de Windows Forms muestra una lista de elementos con iconos.</span><span class="sxs-lookup"><span data-stu-id="f841a-103">The Windows Forms `ListView` control displays a list of items with icons.</span></span> <span data-ttu-id="f841a-104">Puede usar una vista de lista para crear una interfaz de usuario similar al panel derecho del Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="f841a-104">You can use a list view to create a user interface like the right pane of Windows Explorer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f841a-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f841a-105">In This Section</span></span>  
 [<span data-ttu-id="f841a-106">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="f841a-106">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 <span data-ttu-id="f841a-107">Describe este control y sus características clave y propiedades.</span><span class="sxs-lookup"><span data-stu-id="f841a-107">Describes this control and its key features and properties.</span></span>  
  
 [<span data-ttu-id="f841a-108">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-108">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-109">Describe cómo agregar o quitar elementos de una vista de lista.</span><span class="sxs-lookup"><span data-stu-id="f841a-109">Describes how to add or remove items from a list view.</span></span>  
  
 [<span data-ttu-id="f841a-110">Agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-110">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-111">Describe cómo crear columnas para mostrar información sobre cada elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="f841a-111">Describes how to create columns in order to display information about each list item.</span></span>  
  
 [<span data-ttu-id="f841a-112">Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-112">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-113">Describe cómo asociar una vista de lista con una lista de imágenes apropiada para mostrar iconos grandes o pequeños.</span><span class="sxs-lookup"><span data-stu-id="f841a-113">Describes how to associate a list view with an appropriate image list for displaying large or small icons.</span></span>  
  
 [<span data-ttu-id="f841a-114">Mostrar subelementos en columnas con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-114">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-115">Describe cómo mostrar información sobre cada elemento de lista en columnas.</span><span class="sxs-lookup"><span data-stu-id="f841a-115">Describes how to display information about each list item in columns.</span></span>  
  
 [<span data-ttu-id="f841a-116">Seleccionar un elemento del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-116">How to: Select an Item in the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-117">Describe cómo seleccionar un elemento mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f841a-117">Describes how to programmatically select an item.</span></span>  
  
 [<span data-ttu-id="f841a-118">Agrupar elementos en un control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-118">How to: Group Items in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-119">Describe cómo crear grupos para la presentación por categorías y cómo asignar elementos a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="f841a-119">Describes how to create groups for categorized display and how to assign items to each group.</span></span>  
  
 <span data-ttu-id="f841a-120">Esta característica solo está disponible para [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f841a-120">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="f841a-121">Habilitar la vista en mosaico en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-121">How to: Enable Tile View in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-122">Describe cómo mostrar elementos en mosaico, cada uno de los cuales consta de un icono grande y varias líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="f841a-122">Describes how to display items as tiles, each of which is comprised of a large icon and multiple lines of text.</span></span>  
  
 <span data-ttu-id="f841a-123">Esta característica solo está disponible para [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f841a-123">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="f841a-124">Mostrar una marca de inserción en un control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-124">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="f841a-125">Describe cómo implementar los comentarios del usuario para las operaciones de arrastrar y colocar en las que una marca de inserción indica la ubicación de destino para cada posición del puntero del mouse.</span><span class="sxs-lookup"><span data-stu-id="f841a-125">Describes how to implement user-feedback for drag-and-drop operations in which an insertion mark indicates the drop location for each mouse-pointer position.</span></span>  
  
 <span data-ttu-id="f841a-126">Esta característica solo está disponible para [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f841a-126">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="f841a-127">Agregar capacidades de búsqueda a un control ListView</span><span class="sxs-lookup"><span data-stu-id="f841a-127">How to: Add Search Capabilities to a ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 <span data-ttu-id="f841a-128">Describe cómo buscar un elemento mediante programación usando coordenadas de pantalla o búsqueda de texto.</span><span class="sxs-lookup"><span data-stu-id="f841a-128">Describes how to programmatically find an item using either text search or screen coordinates.</span></span>  
  
-   [<span data-ttu-id="f841a-129">Habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f841a-129">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>](enable-tile-view-in-a-wf-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="f841a-130">Agregar y quitar elementos de un control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f841a-130">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>](add-and-remove-items-with-wf-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="f841a-131">Agregar columnas al control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f841a-131">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>](how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="f841a-132">Agrupar elementos en un control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f841a-132">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>](how-to-group-items-in-a-windows-forms-listview-control-using-the-designer.md)  
  
-   [<span data-ttu-id="f841a-133">Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f841a-133">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>](creating-an-explorer-style-interface-with-the-listview-and-treeview.md)  
  
## <a name="reference"></a><span data-ttu-id="f841a-134">Referencia</span><span class="sxs-lookup"><span data-stu-id="f841a-134">Reference</span></span>  
 <span data-ttu-id="f841a-135">Clase <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="f841a-135"><xref:System.Windows.Forms.ListView> class</span></span>  
 <span data-ttu-id="f841a-136">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="f841a-136">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f841a-137">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f841a-137">Related Sections</span></span>  
 [<span data-ttu-id="f841a-138">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f841a-138">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 <span data-ttu-id="f841a-139">Describe cómo heredar de un elemento en una vista de lista o de un nodo en una vista de árbol para agregar los campos, métodos o constructores que necesite.</span><span class="sxs-lookup"><span data-stu-id="f841a-139">Describes how to inherit from an item in a list view or a node in a tree view in order to add any fields, methods, or constructors you need.</span></span>  
  
 [<span data-ttu-id="f841a-140">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="f841a-140">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 <span data-ttu-id="f841a-141">Explica qué es una lista de imágenes y sus características clave y propiedades.</span><span class="sxs-lookup"><span data-stu-id="f841a-141">Explains what an image list is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="f841a-142">Crear una interfaz de usuario de varios paneles con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-142">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="f841a-143">Proporciona instrucciones para diseñar un Windows Form con varios paneles.</span><span class="sxs-lookup"><span data-stu-id="f841a-143">Gives instructions for laying out a Windows Form with multiple panes.</span></span>  
  
 [<span data-ttu-id="f841a-144">Características de Windows XP y controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-144">Windows XP Features and Windows Forms Controls</span></span>](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 <span data-ttu-id="f841a-145">Explica cómo aprovechar las características específicas de Windows XP que se aplican al control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="f841a-145">Explains how to take advantage of Windows XP-specific features that apply to the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f841a-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="f841a-146">See Also</span></span>  
 [<span data-ttu-id="f841a-147">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f841a-147">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
