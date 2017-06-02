---
title: "UI Automation Control Types Overview | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, control types"
  - "control types, UI Automation"
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# UI Automation Control Types Overview
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Los tipos de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] son identificadores conocidos que se pueden usar para indicar qué tipo de control representa un elemento en concreto, como un cuadro combinado o un botón.  
  
 El hecho de disponer de un identificador conocido ayuda a los dispositivos de tecnología de asistencia a determinar qué tipos de controles están disponibles en la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y cómo interactuar con los controles.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## Requisitos de los tipos de control de la automatización de la interfaz de usuario  
 Los tipos de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] proporcionan un conjunto de condiciones que deben cumplir los proveedores. Cuando se cumplen estas condiciones, el control puede usar el nombre de tipo de control específico. Cada tipo de control tiene condiciones para los siguientes elementos:  
  
-   Patrones de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: qué patrones de control deben ser compatibles, qué patrones de control son opcionales y qué patrones de control no deben ser compatibles con el control.  
  
-   Valores de propiedad de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: qué valores de propiedad son compatibles.  
  
-   Estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria para el control.  
  
 Cuando un control cumple las condiciones de un tipo de control particular, el valor de la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> indicará ese tipo de control.  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## Tipos actuales de control de automatización de la interfaz de usuario  
 La siguiente lista contiene el conjunto actual de tipos de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]:  
  
-   [UI Automation Support for the Button Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [UI Automation Support for the Calendar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [UI Automation Support for the CheckBox Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [UI Automation Support for the ComboBox Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [UI Automation Support for the DataGrid Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [UI Automation Support for the DataItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [UI Automation Support for the Document Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [UI Automation Support for the Edit Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [UI Automation Support for the Group Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [UI Automation Support for the Header Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [UI Automation Support for the HeaderItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [UI Automation Support for the Hyperlink Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [UI Automation Support for the Image Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [UI Automation Support for the List Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [UI Automation Support for the ListItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [UI Automation Support for the Menu Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [UI Automation Support for the MenuBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [UI Automation Support for the MenuItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [UI Automation Support for the Pane Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [UI Automation Support for the ProgressBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [UI Automation Support for the RadioButton Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [UI Automation Support for the ScrollBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [UI Automation Support for the Separator Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [UI Automation Support for the Slider Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [UI Automation Support for the Spinner Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [UI Automation Support for the SplitButton Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [UI Automation Support for the StatusBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [UI Automation Support for the Tab Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [UI Automation Support for the TabItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [UI Automation Support for the Table Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [UI Automation Support for the Text Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [UI Automation Support for the Thumb Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [UI Automation Support for the TitleBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [UI Automation Support for the ToolBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [UI Automation Support for the ToolTip Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [UI Automation Support for the Tree Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [UI Automation Support for the TreeItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [UI Automation Support for the Window Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## Vea también  
 <xref:System.Windows.Automation.ControlType>