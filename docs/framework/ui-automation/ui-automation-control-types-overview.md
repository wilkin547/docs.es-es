---
title: Información general sobre tipos de control de UI Automation
description: Lea información general de los tipos de control de automatización de la interfaz de usuario, que son identificadores conocidos que se pueden usar para indicar qué tipo de control representa un elemento.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: 204e950fca74c4f7bd2c13dc8a8891152954c071
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166130"
---
# <a name="ui-automation-control-types-overview"></a><span data-ttu-id="770a9-103">Información general sobre tipos de control de UI Automation</span><span class="sxs-lookup"><span data-stu-id="770a9-103">UI Automation Control Types Overview</span></span>
> [!NOTE]
> <span data-ttu-id="770a9-104">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="770a9-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="770a9-105">Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="770a9-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="770a9-106">Los tipos de control de[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] son identificadores conocidos que se pueden usar para indicar qué tipo de control representa un elemento en concreto, como un cuadro combinado o un botón.</span><span class="sxs-lookup"><span data-stu-id="770a9-106">[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types are well-known identifiers that can be used to indicate what kind of control a particular element represents, such as a combo box or a button.</span></span>  
  
 <span data-ttu-id="770a9-107">El hecho de disponer de un identificador conocido ayuda a los dispositivos de tecnología de asistencia a determinar qué tipos de controles están disponibles en la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y cómo interactuar con los controles.</span><span class="sxs-lookup"><span data-stu-id="770a9-107">Having a well-known identifier makes it easier for assistive technology devices to determine what types of controls are available in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] and how to interact with the controls.</span></span>  
  
<a name="UI_Automation_Control_Type_Requisites"></a>
## <a name="ui-automation-control-type-requisites"></a><span data-ttu-id="770a9-108">Requisitos de los tipos de control de la automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="770a9-108">UI Automation Control Type Requisites</span></span>  
 <span data-ttu-id="770a9-109">Los tipos de control de[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] proporcionan un conjunto de condiciones que deben cumplir los proveedores.</span><span class="sxs-lookup"><span data-stu-id="770a9-109">[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types provide a set of conditions that providers must meet.</span></span> <span data-ttu-id="770a9-110">Cuando se cumplen estas condiciones, el control puede usar el nombre de tipo de control específico.</span><span class="sxs-lookup"><span data-stu-id="770a9-110">When these conditions are met, the control can use the specific control type name.</span></span> <span data-ttu-id="770a9-111">Cada tipo de control tiene condiciones para los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="770a9-111">Each control type has conditions for the following:</span></span>  
  
- <span data-ttu-id="770a9-112">Patrones de control de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : qué patrones de control deben ser compatibles, qué patrones de control son opcionales y qué patrones de control no deben ser compatibles con el control.</span><span class="sxs-lookup"><span data-stu-id="770a9-112">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns—which control patterns must be supported, which control patterns are optional, and which control patterns must not be supported by the control.</span></span>  
  
- <span data-ttu-id="770a9-113">Valores de propiedad de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : qué valores de propiedad son compatibles.</span><span class="sxs-lookup"><span data-stu-id="770a9-113">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values—which property values are supported.</span></span>  
  
- <span data-ttu-id="770a9-114">Estructura de árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria para el control.</span><span class="sxs-lookup"><span data-stu-id="770a9-114">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure—the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure for the control.</span></span>  
  
 <span data-ttu-id="770a9-115">Cuando un control cumple las condiciones de un tipo de control particular, el valor de la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> indicará ese tipo de control.</span><span class="sxs-lookup"><span data-stu-id="770a9-115">When a control meets the conditions for a particular control type, the <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> property value will indicate that control type.</span></span>  
  
<a name="Current_UI_Automation_Control_Types"></a>
## <a name="current-ui-automation-control-types"></a><span data-ttu-id="770a9-116">Tipos actuales de control de automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="770a9-116">Current UI Automation Control Types</span></span>  
 <span data-ttu-id="770a9-117">La siguiente lista contiene el conjunto actual de tipos de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="770a9-117">The following list contains the current set of [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] control types:</span></span>  
  
- [<span data-ttu-id="770a9-118">Compatibilidad de UI Automation para el tipo de control Button</span><span class="sxs-lookup"><span data-stu-id="770a9-118">UI Automation Support for the Button Control Type</span></span>](ui-automation-support-for-the-button-control-type.md)  
  
- [<span data-ttu-id="770a9-119">Compatibilidad de UI Automation para el tipo de control Calendar</span><span class="sxs-lookup"><span data-stu-id="770a9-119">UI Automation Support for the Calendar Control Type</span></span>](ui-automation-support-for-the-calendar-control-type.md)  
  
- [<span data-ttu-id="770a9-120">Compatibilidad de UI Automation para el tipo de control CheckBox</span><span class="sxs-lookup"><span data-stu-id="770a9-120">UI Automation Support for the CheckBox Control Type</span></span>](ui-automation-support-for-the-checkbox-control-type.md)  
  
- [<span data-ttu-id="770a9-121">Compatibilidad de UI Automation para el tipo de control ComboBox</span><span class="sxs-lookup"><span data-stu-id="770a9-121">UI Automation Support for the ComboBox Control Type</span></span>](ui-automation-support-for-the-combobox-control-type.md)  
  
- [<span data-ttu-id="770a9-122">Compatibilidad de UI Automation para el tipo de control DataGrid</span><span class="sxs-lookup"><span data-stu-id="770a9-122">UI Automation Support for the DataGrid Control Type</span></span>](ui-automation-support-for-the-datagrid-control-type.md)  
  
- [<span data-ttu-id="770a9-123">Compatibilidad de UI Automation para el tipo de control DataItem</span><span class="sxs-lookup"><span data-stu-id="770a9-123">UI Automation Support for the DataItem Control Type</span></span>](ui-automation-support-for-the-dataitem-control-type.md)  
  
- [<span data-ttu-id="770a9-124">Compatibilidad de UI Automation para el tipo de control Document</span><span class="sxs-lookup"><span data-stu-id="770a9-124">UI Automation Support for the Document Control Type</span></span>](ui-automation-support-for-the-document-control-type.md)  
  
- [<span data-ttu-id="770a9-125">Compatibilidad de UI Automation para el tipo de control Edit</span><span class="sxs-lookup"><span data-stu-id="770a9-125">UI Automation Support for the Edit Control Type</span></span>](ui-automation-support-for-the-edit-control-type.md)  
  
- [<span data-ttu-id="770a9-126">Compatibilidad de UI Automation para el tipo de control Group</span><span class="sxs-lookup"><span data-stu-id="770a9-126">UI Automation Support for the Group Control Type</span></span>](ui-automation-support-for-the-group-control-type.md)  
  
- [<span data-ttu-id="770a9-127">Compatibilidad de UI Automation para el tipo de control Header</span><span class="sxs-lookup"><span data-stu-id="770a9-127">UI Automation Support for the Header Control Type</span></span>](ui-automation-support-for-the-header-control-type.md)  
  
- [<span data-ttu-id="770a9-128">Compatibilidad de la UI Automation para el tipo de control HeaderItem</span><span class="sxs-lookup"><span data-stu-id="770a9-128">UI Automation Support for the HeaderItem Control Type</span></span>](ui-automation-support-for-the-headeritem-control-type.md)  
  
- [<span data-ttu-id="770a9-129">Compatibilidad de UI Automation para el tipo de control Hyperlink</span><span class="sxs-lookup"><span data-stu-id="770a9-129">UI Automation Support for the Hyperlink Control Type</span></span>](ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [<span data-ttu-id="770a9-130">Compatibilidad de UI Automation para el tipo de control Image</span><span class="sxs-lookup"><span data-stu-id="770a9-130">UI Automation Support for the Image Control Type</span></span>](ui-automation-support-for-the-image-control-type.md)  
  
- [<span data-ttu-id="770a9-131">Compatibilidad de UI Automation para el tipo de control List</span><span class="sxs-lookup"><span data-stu-id="770a9-131">UI Automation Support for the List Control Type</span></span>](ui-automation-support-for-the-list-control-type.md)  
  
- [<span data-ttu-id="770a9-132">Compatibilidad de UI Automation para el tipo de control ListItem</span><span class="sxs-lookup"><span data-stu-id="770a9-132">UI Automation Support for the ListItem Control Type</span></span>](ui-automation-support-for-the-listitem-control-type.md)  
  
- [<span data-ttu-id="770a9-133">Compatibilidad de UI Automation para el tipo de control Menu</span><span class="sxs-lookup"><span data-stu-id="770a9-133">UI Automation Support for the Menu Control Type</span></span>](ui-automation-support-for-the-menu-control-type.md)  
  
- [<span data-ttu-id="770a9-134">Compatibilidad de UI Automation para el tipo de control MenuBar</span><span class="sxs-lookup"><span data-stu-id="770a9-134">UI Automation Support for the MenuBar Control Type</span></span>](ui-automation-support-for-the-menubar-control-type.md)  
  
- [<span data-ttu-id="770a9-135">Compatibilidad de UI Automation para el tipo de control MenuItem</span><span class="sxs-lookup"><span data-stu-id="770a9-135">UI Automation Support for the MenuItem Control Type</span></span>](ui-automation-support-for-the-menuitem-control-type.md)  
  
- [<span data-ttu-id="770a9-136">Compatibilidad de UI Automation para el tipo de control Pane</span><span class="sxs-lookup"><span data-stu-id="770a9-136">UI Automation Support for the Pane Control Type</span></span>](ui-automation-support-for-the-pane-control-type.md)  
  
- [<span data-ttu-id="770a9-137">Compatibilidad de UI Automation para el tipo de control ProgressBar</span><span class="sxs-lookup"><span data-stu-id="770a9-137">UI Automation Support for the ProgressBar Control Type</span></span>](ui-automation-support-for-the-progressbar-control-type.md)  
  
- [<span data-ttu-id="770a9-138">Compatibilidad de UI Automation para el tipo de control RadioButton</span><span class="sxs-lookup"><span data-stu-id="770a9-138">UI Automation Support for the RadioButton Control Type</span></span>](ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [<span data-ttu-id="770a9-139">Compatibilidad de UI Automation para el tipo de control ScrollBar</span><span class="sxs-lookup"><span data-stu-id="770a9-139">UI Automation Support for the ScrollBar Control Type</span></span>](ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [<span data-ttu-id="770a9-140">Compatibilidad de UI Automation para el tipo de control Separator</span><span class="sxs-lookup"><span data-stu-id="770a9-140">UI Automation Support for the Separator Control Type</span></span>](ui-automation-support-for-the-separator-control-type.md)  
  
- [<span data-ttu-id="770a9-141">Compatibilidad de la UI Automation para el tipo de control Slider</span><span class="sxs-lookup"><span data-stu-id="770a9-141">UI Automation Support for the Slider Control Type</span></span>](ui-automation-support-for-the-slider-control-type.md)  
  
- [<span data-ttu-id="770a9-142">Compatibilidad de automatización de la IU para el tipo de control Spinner</span><span class="sxs-lookup"><span data-stu-id="770a9-142">UI Automation Support for the Spinner Control Type</span></span>](ui-automation-support-for-the-spinner-control-type.md)  
  
- [<span data-ttu-id="770a9-143">Compatibilidad de UI Automation para el tipo de control SplitButton</span><span class="sxs-lookup"><span data-stu-id="770a9-143">UI Automation Support for the SplitButton Control Type</span></span>](ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [<span data-ttu-id="770a9-144">Compatibilidad de UI Automation para el tipo de control StatusBar</span><span class="sxs-lookup"><span data-stu-id="770a9-144">UI Automation Support for the StatusBar Control Type</span></span>](ui-automation-support-for-the-statusbar-control-type.md)  
  
- [<span data-ttu-id="770a9-145">Compatibilidad de UI Automation para el tipo de control Tab</span><span class="sxs-lookup"><span data-stu-id="770a9-145">UI Automation Support for the Tab Control Type</span></span>](ui-automation-support-for-the-tab-control-type.md)  
  
- [<span data-ttu-id="770a9-146">Compatibilidad de UI Automation para el tipo de control TabItem</span><span class="sxs-lookup"><span data-stu-id="770a9-146">UI Automation Support for the TabItem Control Type</span></span>](ui-automation-support-for-the-tabitem-control-type.md)  
  
- [<span data-ttu-id="770a9-147">Compatibilidad de UI Automation para el tipo de control Table</span><span class="sxs-lookup"><span data-stu-id="770a9-147">UI Automation Support for the Table Control Type</span></span>](ui-automation-support-for-the-table-control-type.md)  
  
- [<span data-ttu-id="770a9-148">Compatibilidad de UI Automation para el tipo de control Text</span><span class="sxs-lookup"><span data-stu-id="770a9-148">UI Automation Support for the Text Control Type</span></span>](ui-automation-support-for-the-text-control-type.md)  
  
- [<span data-ttu-id="770a9-149">Compatibilidad de automatización de la interfaz de usuario para el tipo de control de posición</span><span class="sxs-lookup"><span data-stu-id="770a9-149">UI Automation Support for the Thumb Control Type</span></span>](ui-automation-support-for-the-thumb-control-type.md)  
  
- [<span data-ttu-id="770a9-150">Compatibilidad de UI Automation para el tipo de control TitleBar</span><span class="sxs-lookup"><span data-stu-id="770a9-150">UI Automation Support for the TitleBar Control Type</span></span>](ui-automation-support-for-the-titlebar-control-type.md)  
  
- [<span data-ttu-id="770a9-151">Compatibilidad de UI Automation para el tipo de control ToolBar</span><span class="sxs-lookup"><span data-stu-id="770a9-151">UI Automation Support for the ToolBar Control Type</span></span>](ui-automation-support-for-the-toolbar-control-type.md)  
  
- [<span data-ttu-id="770a9-152">Compatibilidad de UI Automation para el tipo de control ToolTip</span><span class="sxs-lookup"><span data-stu-id="770a9-152">UI Automation Support for the ToolTip Control Type</span></span>](ui-automation-support-for-the-tooltip-control-type.md)  
  
- [<span data-ttu-id="770a9-153">Compatibilidad de UI Automation para el tipo de control Tree</span><span class="sxs-lookup"><span data-stu-id="770a9-153">UI Automation Support for the Tree Control Type</span></span>](ui-automation-support-for-the-tree-control-type.md)  
  
- [<span data-ttu-id="770a9-154">Compatibilidad de UI Automation para el tipo de control TreeItem</span><span class="sxs-lookup"><span data-stu-id="770a9-154">UI Automation Support for the TreeItem Control Type</span></span>](ui-automation-support-for-the-treeitem-control-type.md)  
  
- [<span data-ttu-id="770a9-155">Compatibilidad de UI Automation para el tipo de control Window</span><span class="sxs-lookup"><span data-stu-id="770a9-155">UI Automation Support for the Window Control Type</span></span>](ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a><span data-ttu-id="770a9-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="770a9-156">See also</span></span>

- <xref:System.Windows.Automation.ControlType>
