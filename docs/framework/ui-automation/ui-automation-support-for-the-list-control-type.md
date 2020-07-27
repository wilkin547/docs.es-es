---
title: Compatibilidad de UI Automation para el tipo de control List
description: Obtenga información sobre la compatibilidad de UI Automation para el tipo de control List. Obtenga información sobre la estructura de árbol necesaria, las propiedades, los patrones de control y los eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, List
- List control type
- UI Automation, List control type
ms.assetid: 0e959fcb-50f2-413b-948d-7167d279bc11
ms.openlocfilehash: 01827250ac216dbcb57a8a139637e7c48d59566d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166081"
---
# <a name="ui-automation-support-for-the-list-control-type"></a>Compatibilidad de UI Automation para el tipo de control List
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control List. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . En las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 El tipo de control List ofrece una manera de organizar uno o varios grupos planos de elementos y permite al usuario seleccionar uno o varios de esos elementos. El tipo de control List tiene una restricción flexible respecto a los tipos de elementos secundarios que puede contener. Esto permite que los proveedores de Automatización de la interfaz de usuario admitan un elemento conocido para los contenedores de selección.  
  
 Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos de las secciones siguientes se aplican a todos los controles que implementan el tipo de control List, ya sea [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 o Windows Forms. Los controles de contenedor de List son un ejemplo de controles que implementan el tipo de control List.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se describen las dos vistas del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenecen a los controles de lista y se describe lo que puede incluirse en cada vista. La vista de control solo contiene elementos que son controles y la vista de contenido quita información redundante del árbol. Por ejemplo, un control de texto utilizado para etiquetar un cuadro combinado se expondrá como el elemento `ComboBox NameProperty`. Como ya se expone el control de texto de esta manera a través de la vista de control, no es necesario que se exponga dos veces; por lo tanto, se quita de la vista de contenido. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|Contiene los elementos que corresponden a los controles.|Quita la información redundante del árbol para que las tecnologías de asistencia trabajen con el conjunto más pequeño de información significativa para el usuario final.|  
|List<br /><br /> -DataItem (0 o más)<br />-ListItem (0 o más)<br />-Group (0 o más)<br />-ScrollBar (0, 1 o 2)|List<br /><br /> -DataItem (0 o más)<br />-ListItem (0 o más)<br />-Group (0 o más)|  
  
 La vista de control de un control que implementa el tipo de control List (por ejemplo, un control de lista) consta de:  
  
- Cero o más elementos dentro del control de lista (los elementos pueden basarse en el elemento de lista o en los tipos de control de elemento de datos).
  
- Cero o más controles de grupo dentro de un control de lista.
  
- Cero, uno o dos controles de barra de desplazamiento.
  
La vista de contenido de un control que implementa el tipo de control List (por ejemplo, un control de lista) consta de:  
  
- Cero o más elementos dentro del control de lista (los elementos pueden basarse en el elemento de lista o en los tipos de control de elemento de datos).
  
- Cero o más grupos dentro del control de lista.

Un control de lista no debe disponer de elementos que tengan una relación jerárquica que no sea estar agrupados. Si los elementos tienen elementos secundarios en el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , el contenedor de lista debe basarse en el tipo de control Tree.  
  
 Los elementos seleccionables dentro del control de lista estarán disponibles en los descendientes del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] del control de lista. Todos los elementos dentro del control de lista deben pertenecer al mismo grupo de selección. Los elementos seleccionables de la lista se deben exponer como tipos de control ListItem (en lugar de DataItem).  
  
<a name="Required_UI_Automation_Properties"></a>
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] cuyo valor o definición es especialmente relevante para los controles de lista. Para obtener más información sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] las propiedades, vea [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Value|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Si el control de lista tiene un punto interactivo (un punto en el que puede hacer clic para que la lista reciba el foco), dicho punto se debe exponer a través de esta propiedad.<br /><br /> Si el valor de la `IsOffScreen` propiedad es true, se producirá la <xref:System.Windows.Automation.NoClickablePointException> excepción.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El valor de propiedad Name de un control de lista debe indicar la categoría de opciones de la que se solicita que el usuario seleccione. Esta propiedad suele recibir su nombre de una etiqueta de texto estático. Si no hay ninguna etiqueta de texto estático, el desarrollador de aplicaciones debe exponer un valor para la propiedad Name.<br /><br /> La única vez que esta propiedad no es necesaria para los controles de lista es si el control se utiliza dentro del subárbol de otro control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|Si hay una etiqueta de texto estático, esta propiedad debe exponer una referencia a ese control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|List|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"lista"|Cadena localizada que corresponde al tipo de control List.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|El control de lista siempre se incluye en la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de lista siempre se incluye en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Si el contenedor puede aceptar la entrada de teclado, este valor de propiedad debe ser verdadero.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vea las notas.|El texto de ayuda para los controles de lista debe explicar por qué se solicita al usuario que realice una selección de una lista de opciones. Por ejemplo, "Seleccione un elemento de esta lista para establecer la resolución de pantalla del monitor".|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>
## <a name="required-ui-automation-control-patterns-and-properties"></a>Propiedades y patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir los controles de lista. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control/Propiedad de patrón|Soporte técnico/valor|Notas|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Obligatorio|Todos los controles que admiten el tipo de control List deben implementar `ISelectionProvider` cuando se mantiene el estado de la selección entre los elementos contenidos en el control. Si los elementos dentro del contenedor no son seleccionables, debe utilizarse el tipo de control Group.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Depende|Los controles List no siempre requieren que se seleccione un elemento.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Depende|Los controles List pueden ser contenedores de selección única o múltiple.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Depende|Implemente este patrón de control si el desplazamiento entre los elementos del contenedor es posible.|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Depende|Implemente este patrón si la navegación en cuadrícula debe estar disponible de elemento en elemento.|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Depende|Implemente este patrón de control si el control puede admitir varias vistas de los elementos del contenedor.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Nunca|`ITableProvider` nunca se admite para el tipo de control List. Si el control debe admitir este patrón de control, el control debe basarse en el tipo de control Data Grid.|  
  
<a name="Required_UI_Automation_Events"></a>
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que todos los controles de edición deben admitir. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico/valor|Notas|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Depende|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Depende|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Depende|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obligatorio|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.List>
- [Información general sobre tipos de control de UI Automation](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
