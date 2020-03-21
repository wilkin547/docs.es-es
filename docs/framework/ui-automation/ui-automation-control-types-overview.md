---
title: Información general sobre tipos de control de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: 643c89e8f6c5e34aa1fb3c5c7c6c750c72046277
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179934"
---
# <a name="ui-automation-control-types-overview"></a>Información general sobre tipos de control de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Los tipos de control de[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] son identificadores conocidos que se pueden usar para indicar qué tipo de control representa un elemento en concreto, como un cuadro combinado o un botón.  
  
 El hecho de disponer de un identificador conocido ayuda a los dispositivos de tecnología de asistencia a determinar qué tipos de controles están disponibles en la [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] y cómo interactuar con los controles.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>
## <a name="ui-automation-control-type-requisites"></a>Requisitos de los tipos de control de la automatización de la interfaz de usuario  
 Los tipos de control de[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] proporcionan un conjunto de condiciones que deben cumplir los proveedores. Cuando se cumplen estas condiciones, el control puede usar el nombre de tipo de control específico. Cada tipo de control tiene condiciones para los siguientes elementos:  
  
- Patrones de control de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : qué patrones de control deben ser compatibles, qué patrones de control son opcionales y qué patrones de control no deben ser compatibles con el control.  
  
- Valores de propiedad de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : qué valores de propiedad son compatibles.  
  
- Estructura de árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria para el control.  
  
 Cuando un control cumple las condiciones de un tipo de control particular, el valor de la propiedad <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> indicará ese tipo de control.  
  
<a name="Current_UI_Automation_Control_Types"></a>
## <a name="current-ui-automation-control-types"></a>Tipos actuales de control de automatización de la interfaz de usuario  
 La siguiente lista contiene el conjunto actual de tipos de control de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :  
  
- [Compatibilidad de UI Automation para el tipo de control Button](ui-automation-support-for-the-button-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Calendar](ui-automation-support-for-the-calendar-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control CheckBox](ui-automation-support-for-the-checkbox-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control ComboBox](ui-automation-support-for-the-combobox-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control DataGrid](ui-automation-support-for-the-datagrid-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control DataItem](ui-automation-support-for-the-dataitem-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Document](ui-automation-support-for-the-document-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Edit](ui-automation-support-for-the-edit-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Group](ui-automation-support-for-the-group-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Header](ui-automation-support-for-the-header-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control HeaderItem](ui-automation-support-for-the-headeritem-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Hyperlink](ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Image](ui-automation-support-for-the-image-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control List](ui-automation-support-for-the-list-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control ListItem](ui-automation-support-for-the-listitem-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Menu](ui-automation-support-for-the-menu-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control MenuBar](ui-automation-support-for-the-menubar-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control MenuItem](ui-automation-support-for-the-menuitem-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Pane](ui-automation-support-for-the-pane-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control ProgressBar](ui-automation-support-for-the-progressbar-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control RadioButton](ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control ScrollBar](ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Separator](ui-automation-support-for-the-separator-control-type.md)  
  
- [Compatibilidad de la UI Automation para el tipo de control Slider](ui-automation-support-for-the-slider-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Spinner](ui-automation-support-for-the-spinner-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control SplitButton](ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control StatusBar](ui-automation-support-for-the-statusbar-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Tab](ui-automation-support-for-the-tab-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control TabItem](ui-automation-support-for-the-tabitem-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Table](ui-automation-support-for-the-table-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Text](ui-automation-support-for-the-text-control-type.md)  
  
- [Compatibilidad de automatización de la interfaz de usuario para el tipo de control de posición](ui-automation-support-for-the-thumb-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control TitleBar](ui-automation-support-for-the-titlebar-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control ToolBar](ui-automation-support-for-the-toolbar-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control ToolTip](ui-automation-support-for-the-tooltip-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control Tree](ui-automation-support-for-the-tree-control-type.md)  
  
- [Compatibilidad de UI Automation para el tipo de control TreeItem](ui-automation-support-for-the-treeitem-control-type.md)  
  
- [Compatibilidad de Automatización de la interfaz de usuario para el tipo de control Window](ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Automation.ControlType>
