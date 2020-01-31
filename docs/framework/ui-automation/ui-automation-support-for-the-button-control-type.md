---
title: Compatibilidad de la automatización de la interfaz de usuario para el tipo de control Button
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Button
- UI Automation, Button control type
- Button control type
ms.assetid: 057c983a-da83-4c50-86c7-26fe381076a6
ms.openlocfilehash: e17a5d9278a235a5c25bb53c68f15b95d1d9177f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789596"
---
# <a name="ui-automation-support-for-the-button-control-type"></a>Compatibilidad de la automatización de la interfaz de usuario para el tipo de control Button
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control Button. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , patrones de control y eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Un botón es un objeto con el que un usuario interactúa para realizar una acción, como por ejemplo los botones **Aceptar** y **Cancelar** de un cuadro de diálogo. El control de botón es un control simple de exponer porque se asigna a un único comando que el usuario quiere realizar.  
  
 En las secciones siguientes se definen la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control Button. Los requisitos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de botón, ya sea [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 o Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de botón y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista Contenido|  
|------------------|------------------|  
|Botón<br /><br /> -Image (0 o más)<br />-Text (0 o más)|Botón|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la siguiente tabla se enumeran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen un valor o una definición que son especialmente relevantes para los controles que implementan el tipo de control Button (como los controles de botón). Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|{2&gt;Value&lt;2}|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>|Vea las notas.|El control Button normalmente debe admitir una tecla de aceleración para permitir que los usuarios finales realicen la acción que representa rápidamente desde el teclado.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables, y realiza pruebas de aciertos especializadas, invalide y ofrezca un punto en el que hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Botón|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vea las notas.|El texto de ayuda puede indicar cuál será el resultado final de la activación del botón. Suele ser el mismo tipo de información que se presenta mediante un elemento de información sobre herramientas.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Verdadero|El control Button siempre debe ser contenido.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Verdadero|El control Button siempre debe ser un control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Los controles de botón se etiquetan automáticamente con su contenido.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"botón"|Cadena localizada que corresponde al tipo de control Button.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El nombre del control de botón es el texto que se utiliza para etiquetarlo. Cada vez que se utiliza una imagen para etiquetar un botón, debe proporcionar texto alternativo para la propiedad Name del botón.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que es necesario que todos los controles de botón de radio admitan. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Compatibilidad con|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Vea las notas.|Todos los botones deben admitir el patrón de control Invoke o el patrón de control Toggle. Invoke se admite cuando el botón ejecuta un comando a petición del usuario. Este comando se asigna a una única operación, como cortar, copiar, pegar o eliminar.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Vea las notas.|Todos los botones deben admitir el patrón de control Invoke o el patrón de control Toggle. Toggle se admite si el botón puede pasar cíclicamente por una serie de hasta tres estados. Normalmente, se considera como un conmutador de encendido y apagado para características específicas.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Vea las notas.|Cuando un botón se hospeda como elemento secundario de un botón de expansión, el botón secundario puede admitir el patrón ExpandCollapse en lugar de Invoke o Toggle. El patrón ExpandCollapse se puede usar para abrir o cerrar un menú u otra subestructura asociada con el elemento de botón.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que todos los controles de botón deben admitir. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Compatibilidad con|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguno|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depende|Si el control admite el patrón de control Invoke, debe admitir este evento.|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Depende|Si el control admite el patrón de control Toggle, debe admitir este evento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.Button>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
