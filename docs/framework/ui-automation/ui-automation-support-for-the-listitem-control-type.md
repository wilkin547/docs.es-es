---
title: Compatibilidad de UI Automation para el tipo de control ListItem
ms.date: 03/30/2017
helpviewer_keywords:
- control types, List
- List Item control type
- UI Automation, List Item control type
ms.assetid: 34f533bf-fc14-4e78-8fee-fb7107345fab
ms.openlocfilehash: 245f9030897d54a2f1c95d5ce6369b67d23cb319
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179700"
---
# <a name="ui-automation-support-for-the-listitem-control-type"></a>Compatibilidad de UI Automation para el tipo de control ListItem
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control <xref:System.Windows.Automation.ControlType.ListItem> . En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . En las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Los controles de elemento de lista son un ejemplo de controles que implementan el tipo de control ListItem.  
  
 En las secciones siguientes se definen la estructura de árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control ListItem. Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos se aplican [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]a todos los controles de lista, ya sea , Win32 o Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de elemento de lista y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|ListItem<br /><br /> - Imagen (0 o más)<br />- Texto (0 o más)<br />- Editar (0 o más)|ListItem|  
  
 Los elementos secundarios de un control de elemento de lista en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] siempre deben ser "0". Si la estructura del control es tal que otros elementos están contenidos debajo del elemento de lista, debe seguir los requisitos para la compatibilidad con automatización de la interfaz de usuario para el tipo de control De tipo de [control TreeItem.](ui-automation-support-for-the-treeitem-control-type.md)  
  
<a name="Required_UI_Automation_Properties"></a>
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para los controles de elemento de lista. Para obtener [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] más información sobre las propiedades, vea Propiedades de automatización de la interfaz de usuario [para clientes](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Value|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El valor de esta propiedad debe incluir el área del contenido de imagen y texto del elemento de lista.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Depende|Si el control de lista tiene un punto interactivo (un punto en el que puede hacer clic para que la lista reciba el enfoque), ese punto se debe exponer a través de esta propiedad. Si los elementos de lista descendientes abarcan completamente el control de lista, este generará una <xref:System.Windows.Automation.NoClickablePointException> para indicar que el cliente debe solicitar un elemento dentro del control de lista para un punto donde hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El valor de la propiedad del nombre de un control de elemento de lista procede del contenido del texto del elemento.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|Si hay una etiqueta de texto estático, esta propiedad debe exponer una referencia a ese control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ListItem|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"elemento de lista"|Cadena localizada que corresponde al tipo de control ListItem.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de lista siempre se incluye en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de lista siempre se incluye en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Si el contenedor puede aceptar la entrada de teclado, este valor de propiedad debe ser verdadero.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|""|El texto de ayuda para los controles de lista debe explicar por qué se le solicita al usuario que elija una opción en una lista de opciones, que es normalmente el mismo tipo de información presentada a través de una información sobre herramientas. Por ejemplo, "Seleccione un elemento para establecer la resolución de pantalla del monitor".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|Depende|Esta propiedad se debe exponer para los controles de elemento de lista que representan un objeto subyacente. Estos controles de elemento de lista suelen tener un icono asociado al control que los usuarios se asocian con el objeto subyacente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>|Depende|Esta propiedad debe devolver un valor para si el elemento de lista se desplaza actualmente en la vista dentro del contenedor primario que implementa el patrón de control Scroll.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por los controles de elemento de lista. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Soporte técnico|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Sí|El control de elemento de lista debe implementar este patrón de control. Esto permite que los controles de elementos de lista transmitan cuando se seleccionan.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Depende|Si el elemento de lista se incluye dentro de un contenedor que se puede desplazar, se debe implementar este patrón de control.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Depende|Si el elemento de lista se puede activar y la acción no realiza un cambio de estado de la selección, se debe implementar este patrón de control.|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Depende|Si el elemento se puede manipular para mostrar u ocultar información, se debe implementar este patrón de control.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Depende|Si se puede editar el elemento, se debe implementar este patrón de control. Los cambios realizados al control de elemento de lista provocarán cambios en los valores de <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>y <xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Depende|Si se admite la navegación espacial de un elemento a otro dentro del contenedor de lista y el contenedor está organizado en filas y columnas, se debe implementar el patrón de control de elemento de cuadrícula.|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Depende|Si el elemento tiene un comando que se puede ejecutar en él, independiente de la selección, se debe implementar este patrón. Se trata normalmente de una acción asociada a hacer doble clic en el control de elemento de lista. Ejemplos serían iniciar un documento desde el Explorador de Microsoft Windows o reproducir un archivo de música en el Reproductor de Microsoft Windows Media.|  
  
<a name="Required_UI_Automation_Events"></a>
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  
 En la siguiente tabla se muestra los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que se deben admitir por todos los controles de elemento de lista. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Depende|None|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Obligatorio|None|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Obligatorio|None|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Obligatorio|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Depende|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Automation.ControlType.ListItem>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
