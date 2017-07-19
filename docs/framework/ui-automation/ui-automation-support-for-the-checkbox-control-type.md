---
title: "UI Automation Support for the CheckBox Control Type | Microsoft Docs"
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
  - "CheckBox control type"
  - "control types, CheckBox"
  - "UI Automation, CheckBox control type"
ms.assetid: 9c2a0e70-3a39-4ba9-96ea-a7fe531fae9f
caps.latest.revision: 31
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 31
---
# UI Automation Support for the CheckBox Control Type
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con el tipo de control CheckBox. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que debe cumplir un control para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>. Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 Una casilla es un objeto que se usa para indicar un estado con el que los usuarios pueden interactuar para recorrer cíclicamente dicho estado. Las casillas le presentan al usuario una opción binaria \(Sí\/No\), \(Activado\/Desactivado\) o terciaria \(Activado, Desactivado, Indeterminado\).  
  
 En las secciones siguientes se definen la estructura del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], las propiedades, los patrones de control y los eventos necesarios para el tipo de control CheckBox. Los requisitos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de casilla, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de casilla y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|----------------------|------------------------|  
|CheckBox|CheckBox|  
  
> [!NOTE]
>  Las casillas nunca tienen elementos secundarios en el control ni en la vista de contenido. Si el control no necesita contener elementos secundarios, quiere decir que se debe usar otro tipo de control.  
  
### Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen un valor o una definición que es especialmente relevante para los controles de casilla. Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vea [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Propiedad [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valor|Notas|  
|-------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables y realiza pruebas de aciertos especializadas, reemplace y ofrezca un punto en el que hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|CheckBox|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El valor de esta propiedad siempre debe ser True. Esto significa que el control de casilla siempre debe incluirse en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El valor de esta propiedad siempre debe ser True. Esto significa que el control de cuadrícula de datos siempre debe estar en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Las casillas son controles que se etiquetan automáticamente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"casilla"|Cadena localizada que corresponde al tipo de control CheckBox.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El valor de la propiedad `Name` del control de casilla es el texto que se muestra junto al cuadro que mantiene el estado de alternancia.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## Patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesarios para que todos los controles de casilla los admitan. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Compatibilidad|Notas|  
|-----------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Requerido|Permite que la casilla se recorra cíclicamente por sus estados internos mediante programación.|  
  
<a name="Required_UI_Automation_Events"></a>   
## Eventos de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que todos los controles de casilla deben admitir. Para más información sobre eventos, vea [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|Evento [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Compatibilidad|Notas|  
|----------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguna|  
|Evento cambiado por propiedad <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.|Obligatorio|Ninguna|  
|Evento cambiado por propiedad <xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>.|Obligatorio|Ninguna|  
|Evento cambiado por propiedad <xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>.|Obligatorio|Ninguna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguna|  
|Evento de cambio de propiedad <xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>.|Obligatorio|Ninguna|  
  
<a name="Default_Action"></a>   
## Acción predeterminada  
 La acción predeterminada de la casilla es hacer que un botón de radio reciba el foco y alterne su estado actual. Como se mencionó con anterioridad, las casillas le presentan al usuario una decisión binaria \(Sí\/No\), \(Activado\/Desactivado\) o terciaria \(Activado, Desactivado, Indeterminado\). Si la casilla es binaria, la acción predeterminada hace que el estado "activado" se convierta en "desactivado" o que el estado "desactivado" pase a "activado". En una casilla de estado terciaria la acción predeterminada recorre cíclicamente los estados de la casilla en el mismo orden que si el usuario hubiera enviado sucesivos clics del mouse al control.  
  
## Vea también  
 <xref:System.Windows.Automation.ControlType.CheckBox>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)