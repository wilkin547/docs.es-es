---
title: Compatibilidad de automatización de la IU para el tipo de control Spinner
description: Obtenga información sobre la compatibilidad de UI Automation para el tipo de control Spinner. Obtenga información sobre la estructura de árbol necesaria, las propiedades, los patrones de control y los eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Spinner control type
- Spinner control type
- control types, Spinner
ms.assetid: 3a29d185-65d8-42e3-bcc3-7f43e96f40c5
ms.openlocfilehash: 13469f7852ffa58d36f4b1fecb1ed93afcdb5fb0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269579"
---
# <a name="ui-automation-support-for-the-spinner-control-type"></a>Compatibilidad de automatización de la IU para el tipo de control Spinner

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control Spinner. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . En las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los controles Spinner se usan para seleccionar desde un dominio de elementos o un intervalo de números.  
  
 En las secciones siguientes se define la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control Spinner. Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos de se aplican a todos los controles de número, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 o Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  

 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenecen a controles de número cuando admite el valor del intervalo, el valor controla cuándo admiten los patrones de control Range Value, Value y Selection, y se describe lo que se puede incluir en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 **Patrón de control Range Value o Value**  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|Spinner<br /><br /> -Edit (0 o 1)<br />-Botón (2)|Spinner|  
  
 **Selection (patrón de control)**  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|Spinner<br /><br /> -Edit (0 o 1)<br />-Botón (2)<br />-Elemento de lista (0 o más)|Spinner<br /><br /> -ListItem (0 o más)|  
  
 Para garantizar que los dos botones del subárbol de la vista de control se pueden distinguir por herramientas de pruebas automatizadas, asigne `SmallIncrement` o `SmallDecrement` `AutomationId` , según corresponda. Para algunas implementaciones, el control Edit asociado puede ser del mismo nivel que el control Spinner.  
  
<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  

 En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para los controles de número. Para obtener más información sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] las propiedades, vea [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valor|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|El punto en el que se puede hacer clic del control de número enfoca la parte de edición del control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control de número suele recibir su nombre de una etiqueta de texto estático.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|Los controles de número tienen una etiqueta de texto estático.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Spinner|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"control de número"|Cadena localizada que corresponde al tipo de control Spinner.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de número siempre debe ser contenido.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de número siempre debe ser un control.|  
  
<a name="Required_UI_Automation_Control_Patterns_and_Properties"></a>

## <a name="required-ui-automation-control-patterns-and-properties"></a>Propiedades y patrones de control de Automatización de la interfaz de usuario necesarios  

 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de número. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control/Propiedad de patrón|Soporte técnico/valor|Notas|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Depende|Los controles de número que tienen una lista de elementos que se van a seleccionar deben admitir este patrón.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|False|Los controles de número siempre son contenedores de selección única.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Depende|Los controles de número  que abarcan un intervalo numérico pueden admitir este patrón.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Depende|Los controles de número que abarcan un conjunto discreto de opciones o números pueden admitir este patrón.|  
  
<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  

 En la tabla siguiente se muestran los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de número. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> .|Depende|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.Spinner>
- [Información general sobre tipos de control de UI Automation](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
