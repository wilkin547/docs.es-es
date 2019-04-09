---
title: Información general sobre tipos de control de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: e9cbff2ec6496cabe827e075b737a8c6f16fee93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147724"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="4d2da-102">Información general sobre tipos de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="4d2da-102">UI Automation Control Types Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="4d2da-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="4d2da-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4d2da-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="4d2da-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="4d2da-105">tipos de control son identificadores conocidos que pueden usarse para indicar qué tipo de control determinado representa un elemento, como un cuadro combinado o un botón.</span><span class="sxs-lookup"><span data-stu-id="4d2da-105">control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="4d2da-106">El hecho de disponer de un identificador conocido ayuda a los dispositivos de tecnología de asistencia a determinar qué tipos de controles están disponibles en la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y cómo interactuar con los controles.</span><span class="sxs-lookup"><span data-stu-id="4d2da-106">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="4d2da-107">Requisitos de los tipos de control de la automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4d2da-107">UI Automation Control Type Requisites</span></span>  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] <span data-ttu-id="4d2da-108">tipos de control proporcionan un conjunto de condiciones que deben cumplir los proveedores.</span><span class="sxs-lookup"><span data-stu-id="4d2da-108">control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="4d2da-109">Cuando se cumplen estas condiciones, el control puede usar el nombre de tipo de control específico.</span><span class="sxs-lookup"><span data-stu-id="4d2da-109">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="4d2da-110">Cada tipo de control tiene condiciones para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4d2da-110">Each control type has conditions for the following:</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="4d2da-111">patrones de control: qué patrones de control deben ser compatibles, qué control patrones son opcionales, y qué patrones de control no deben ser compatibles con el control.</span><span class="sxs-lookup"><span data-stu-id="4d2da-111">control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="4d2da-112">los valores de propiedad, se admiten los valores de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4d2da-112">property values—which property values are supported.</span></span>  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] <span data-ttu-id="4d2da-113">estructura de árbol: necesario [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] estructura para el control de árbol.</span><span class="sxs-lookup"><span data-stu-id="4d2da-113">tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="4d2da-114">Cuando un control cumple las condiciones de un tipo de control particular, el valor de la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> indicará ese tipo de control.</span><span class="sxs-lookup"><span data-stu-id="4d2da-114">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="4d2da-115">Tipos actuales de control de automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4d2da-115">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="4d2da-116">La siguiente lista contiene el conjunto actual de tipos de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4d2da-116">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
-   [<span data-ttu-id="4d2da-117">Compatibilidad de UI Automation para el tipo de control Button</span><span class="sxs-lookup"><span data-stu-id="4d2da-117">UI Automation Support for the Button Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [<span data-ttu-id="4d2da-118">Compatibilidad de UI Automation para el tipo de control Calendar</span><span class="sxs-lookup"><span data-stu-id="4d2da-118">UI Automation Support for the Calendar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-119">Compatibilidad de UI Automation para el tipo de control CheckBox</span><span class="sxs-lookup"><span data-stu-id="4d2da-119">UI Automation Support for the CheckBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [<span data-ttu-id="4d2da-120">Compatibilidad de UI Automation para el tipo de control ComboBox</span><span class="sxs-lookup"><span data-stu-id="4d2da-120">UI Automation Support for the ComboBox Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [<span data-ttu-id="4d2da-121">Compatibilidad de UI Automation para el tipo de control DataGrid</span><span class="sxs-lookup"><span data-stu-id="4d2da-121">UI Automation Support for the DataGrid Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [<span data-ttu-id="4d2da-122">Compatibilidad de UI Automation para el tipo de control DataItem</span><span class="sxs-lookup"><span data-stu-id="4d2da-122">UI Automation Support for the DataItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [<span data-ttu-id="4d2da-123">Compatibilidad de UI Automation para el tipo de control Document</span><span class="sxs-lookup"><span data-stu-id="4d2da-123">UI Automation Support for the Document Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [<span data-ttu-id="4d2da-124">Compatibilidad de UI Automation para el tipo de control Edit</span><span class="sxs-lookup"><span data-stu-id="4d2da-124">UI Automation Support for the Edit Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [<span data-ttu-id="4d2da-125">Compatibilidad de UI Automation para el tipo de control Group</span><span class="sxs-lookup"><span data-stu-id="4d2da-125">UI Automation Support for the Group Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [<span data-ttu-id="4d2da-126">Compatibilidad de UI Automation para el tipo de control Header</span><span class="sxs-lookup"><span data-stu-id="4d2da-126">UI Automation Support for the Header Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [<span data-ttu-id="4d2da-127">Compatibilidad de la UI Automation para el tipo de control HeaderItem</span><span class="sxs-lookup"><span data-stu-id="4d2da-127">UI Automation Support for the HeaderItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [<span data-ttu-id="4d2da-128">Compatibilidad de UI Automation para el tipo de control Hyperlink</span><span class="sxs-lookup"><span data-stu-id="4d2da-128">UI Automation Support for the Hyperlink Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [<span data-ttu-id="4d2da-129">Compatibilidad de UI Automation para el tipo de control Image</span><span class="sxs-lookup"><span data-stu-id="4d2da-129">UI Automation Support for the Image Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [<span data-ttu-id="4d2da-130">Compatibilidad de UI Automation para el tipo de control List</span><span class="sxs-lookup"><span data-stu-id="4d2da-130">UI Automation Support for the List Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [<span data-ttu-id="4d2da-131">Compatibilidad de UI Automation para el tipo de control ListItem</span><span class="sxs-lookup"><span data-stu-id="4d2da-131">UI Automation Support for the ListItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [<span data-ttu-id="4d2da-132">Compatibilidad de UI Automation para el tipo de control Menu</span><span class="sxs-lookup"><span data-stu-id="4d2da-132">UI Automation Support for the Menu Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [<span data-ttu-id="4d2da-133">Compatibilidad de UI Automation para el tipo de control MenuBar</span><span class="sxs-lookup"><span data-stu-id="4d2da-133">UI Automation Support for the MenuBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-134">Compatibilidad de UI Automation para el tipo de control MenuItem</span><span class="sxs-lookup"><span data-stu-id="4d2da-134">UI Automation Support for the MenuItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [<span data-ttu-id="4d2da-135">Compatibilidad de UI Automation para el tipo de control Pane</span><span class="sxs-lookup"><span data-stu-id="4d2da-135">UI Automation Support for the Pane Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [<span data-ttu-id="4d2da-136">Compatibilidad de UI Automation para el tipo de control ProgressBar</span><span class="sxs-lookup"><span data-stu-id="4d2da-136">UI Automation Support for the ProgressBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-137">Compatibilidad de UI Automation para el tipo de control RadioButton</span><span class="sxs-lookup"><span data-stu-id="4d2da-137">UI Automation Support for the RadioButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [<span data-ttu-id="4d2da-138">Compatibilidad de UI Automation para el tipo de control ScrollBar</span><span class="sxs-lookup"><span data-stu-id="4d2da-138">UI Automation Support for the ScrollBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-139">Compatibilidad de UI Automation para el tipo de control Separator</span><span class="sxs-lookup"><span data-stu-id="4d2da-139">UI Automation Support for the Separator Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [<span data-ttu-id="4d2da-140">Compatibilidad de la UI Automation para el tipo de control Slider</span><span class="sxs-lookup"><span data-stu-id="4d2da-140">UI Automation Support for the Slider Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [<span data-ttu-id="4d2da-141">Compatibilidad de automatización de la IU para el tipo de control Spinner</span><span class="sxs-lookup"><span data-stu-id="4d2da-141">UI Automation Support for the Spinner Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [<span data-ttu-id="4d2da-142">Compatibilidad de UI Automation para el tipo de control SplitButton</span><span class="sxs-lookup"><span data-stu-id="4d2da-142">UI Automation Support for the SplitButton Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [<span data-ttu-id="4d2da-143">Compatibilidad de UI Automation para el tipo de control StatusBar</span><span class="sxs-lookup"><span data-stu-id="4d2da-143">UI Automation Support for the StatusBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-144">Compatibilidad de UI Automation para el tipo de control Tab</span><span class="sxs-lookup"><span data-stu-id="4d2da-144">UI Automation Support for the Tab Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [<span data-ttu-id="4d2da-145">Compatibilidad de UI Automation para el tipo de control TabItem</span><span class="sxs-lookup"><span data-stu-id="4d2da-145">UI Automation Support for the TabItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [<span data-ttu-id="4d2da-146">Compatibilidad de UI Automation para el tipo de control Table</span><span class="sxs-lookup"><span data-stu-id="4d2da-146">UI Automation Support for the Table Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [<span data-ttu-id="4d2da-147">Compatibilidad de UI Automation para el tipo de control Text</span><span class="sxs-lookup"><span data-stu-id="4d2da-147">UI Automation Support for the Text Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [<span data-ttu-id="4d2da-148">Compatibilidad de automatización de la interfaz de usuario para el tipo de control de posición</span><span class="sxs-lookup"><span data-stu-id="4d2da-148">UI Automation Support for the Thumb Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [<span data-ttu-id="4d2da-149">Compatibilidad de UI Automation para el tipo de control TitleBar</span><span class="sxs-lookup"><span data-stu-id="4d2da-149">UI Automation Support for the TitleBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-150">Compatibilidad de UI Automation para el tipo de control ToolBar</span><span class="sxs-lookup"><span data-stu-id="4d2da-150">UI Automation Support for the ToolBar Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [<span data-ttu-id="4d2da-151">Compatibilidad de UI Automation para el tipo de control ToolTip</span><span class="sxs-lookup"><span data-stu-id="4d2da-151">UI Automation Support for the ToolTip Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [<span data-ttu-id="4d2da-152">Compatibilidad de UI Automation para el tipo de control Tree</span><span class="sxs-lookup"><span data-stu-id="4d2da-152">UI Automation Support for the Tree Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [<span data-ttu-id="4d2da-153">Compatibilidad de UI Automation para el tipo de control TreeItem</span><span class="sxs-lookup"><span data-stu-id="4d2da-153">UI Automation Support for the TreeItem Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [<span data-ttu-id="4d2da-154">Compatibilidad de UI Automation para el tipo de control Window</span><span class="sxs-lookup"><span data-stu-id="4d2da-154">UI Automation Support for the Window Control Type</span></span>](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d2da-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d2da-155">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
