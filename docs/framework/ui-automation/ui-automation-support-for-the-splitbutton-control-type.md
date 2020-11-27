---
title: Compatibilidad de UI Automation para el tipo de control SplitButton
description: Obtenga información sobre la compatibilidad de UI Automation para el tipo de control SplitButton. Obtenga información sobre la estructura de árbol necesaria, las propiedades, los patrones de control y los eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- Split Button control type
- control types, Split Button
- UI Automation, Split Button control type
ms.assetid: 14b05ccf-bcd8-4045-9bae-f7679cd98711
ms.openlocfilehash: bd230afbc69e2d8b29adae43cb93a8399b4ea085
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269566"
---
# <a name="ui-automation-support-for-the-splitbutton-control-type"></a>Compatibilidad de UI Automation para el tipo de control SplitButton

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control SplitButton. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . En las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 El control de botón de expansión permite la capacidad de realizar una acción en un control y expandir el control para ver una lista de otras acciones posibles que se pueden realizar.  
  
 En las secciones siguientes se definen la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control SplitButton. Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos se aplican a todos los controles de botón de expansión, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 o Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  

 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de botón de expansión y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|SplitButton<br /><br /> <ul><li>Image (0 o 1)</li><li>Text (0 o 1)</li><li>Button (1 o 2)<br /><br /> <ul><li>Menu (0 o 1; aparece como elemento secundario del botón que admite el patrón ExpandCollapse)</li><li>MenuItem (1 o varios)</li></ul></li></ul>|SplitButton<br /><br /> -MenuItem (1 a varios)|  
  
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  

 En la tabla siguiente se muestran las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen un valor o una definición que es especialmente relevante para los controles de botón de expansión. Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valor|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables, y realiza pruebas de aciertos especializadas, invalide y ofrezca un punto en el que hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|"Atrás"|El nombre del control de botón de expansión se muestra en el botón.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Null|Los controles de botón de expansión no tienen una etiqueta de texto estático.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|SplitButton|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"botón de expansión"|Cadena localizada que corresponde al tipo de control SplitButton.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vea las notas.|El texto de ayuda puede indicar el resultado de la activación del botón de división, que normalmente es el mismo tipo de información que se presenta mediante un elemento de información sobre herramientas.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de botón de división contiene información para el usuario final.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de botón de división es visible para el usuario final.|  
  
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  

 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que es necesario que todos los controles de botón de expansión admitan. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Soporte técnico|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Obligatorio|Los botones de expansión siempre tienen una acción predeterminada asociada a Invoke.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Requerido|Los botones de expansión siempre tienen la capacidad de expandir una lista de opciones.|  
  
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  

 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que todos los controles de botón de expansión deben admitir. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Requerido|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|  
  
## <a name="splitbutton-control-example"></a>Ejemplo de control SplitButton  

 En la imagen siguiente se muestra un tipo de control SplitButton en un control de cuadrícula de datos.  
  
 ![Botón de expansión](./media/uiauto-splitbutton-detailed.gif "uiauto_splitbutton_detailed")  
  
 A continuación se muestran la vista de control y la vista de contenido del árbol de Automatización de la interfaz de usuario que pertenece a los controles de botón de división y de cuadrícula de datos. Los patrones de control de cada elemento de automatización se muestran entre paréntesis.  
  
|Árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : vista de control|Árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : vista de contenido|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|<ul><li>SplitButton "Nombre" (Invoke, ExpandCollapse)</li><li>Button "Más opciones" (Invoke)<br /><br /> <ul><li>Menú</li><li>MenuItem</li><li>…</li></ul></li></ul>|<ul><li>SplitButton "Nombre" (Invoke, ExpandCollapse)</li><li>Button "Más opciones" (Invoke)<br /><br /> <ul><li>Menú</li><li>MenuItem</li><li>…</li></ul></li></ul>|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.SplitButton>
- [Información general sobre tipos de control de UI Automation](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
