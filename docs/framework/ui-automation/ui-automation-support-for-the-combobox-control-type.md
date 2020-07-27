---
title: Compatibilidad de UI Automation para el tipo de control ComboBox
description: Obtenga información sobre la compatibilidad de UI Automation para el tipo de control ComboBox. Obtenga información sobre la estructura de árbol necesaria, las propiedades, los patrones de control y los eventos.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Combo Box
- UI Automation, Combo Box control type
- ComboBox controls
ms.assetid: bb321126-4770-41da-983a-67b7b89d45dd
ms.openlocfilehash: c708de791056969e281ad1bc223e2a2233fa170b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166090"
---
# <a name="ui-automation-support-for-the-combobox-control-type"></a>Compatibilidad de UI Automation para el tipo de control ComboBox
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] con el tipo de control ComboBox. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Entre las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , patrones de control y eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Un cuadro combinado es un cuadro de lista combinado con un control estático o un control de edición que muestra el elemento seleccionado actualmente en la parte del cuadro de lista del cuadro combinado. La parte de cuadro de lista del control se muestra en todo momento o solo aparece cuando el usuario selecciona la flecha de lista desplegable (que es un botón de comando) junto al control. Si el campo de selección es un control de edición, el usuario puede escribir información que no esté en la lista; de lo contrario, el usuario solo puede seleccionar elementos de la lista.  
  
 En las secciones siguientes se definen la estructura del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , las propiedades, los patrones de control y los eventos necesarios para el tipo de control ComboBox. Los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisitos de se aplican a todos los controles de cuadro combinado, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 o Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se describe la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de cuadro combinado y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|ComboBox<br /><br /> -Edit (0 o 1)<br />-List (1)<br />-Elemento de lista (secundario de la lista; de 0 a varios)<br />-Button (1)|ComboBox<br /><br /> -Elemento de lista (de 0 a varios)|  
  
 El control de edición de la vista de control del cuadro combinado solo es necesario si el cuadro combinado se puede editar para aceptar cualquier entrada, como es el caso del cuadro combinado que se encuentra en el cuadro de diálogo Ejecutar.  
  
<a name="Required_UI_Automation_Properties"></a>
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen un valor o una definición que es especialmente relevante para los controles de cuadro combinado. Para más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Value|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables, y realiza pruebas de aciertos especializadas, invalide y ofrezca un punto en el que hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ComboBox|Este valor es el mismo para todos los marcos de trabajo [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vea las notas.|El texto de ayuda de los controles de cuadro combinado debe explicar por qué se le pide al usuario que elija una opción del cuadro combinado. El texto es similar a la información que se presenta mediante un elemento de información sobre herramientas. Por ejemplo, "Seleccione un elemento para establecer la resolución de pantalla del monitor".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Los controles de cuadro combinado siempre se incluyen en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Los controles de cuadro combinado siempre se incluyen en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Los controles de cuadro combinado exponen un conjunto de elementos de un contenedor de selección. El control de cuadro combinado puede recibir el foco del teclado, aunque cuando un cliente de Automatización de la interfaz de usuario establece el foco en un cuadro combinado, los elementos del subárbol del cuadro combinado pueden recibir el foco.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|Los controles de cuadro combinado suelen tener una etiqueta de texto estático a la que hace referencia esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"cuadro combinado"|Cadena localizada que corresponde al tipo de control ComboBox.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control del cuadro combinado suele recibir su nombre de un control de texto estático.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesarios para que todos los controles de cuadro combinado los admitan. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Soporte técnico|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Sí|El control de cuadro combinado siempre debe contener el botón de lista desplegable para se considere un cuadro combinado.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Sí|Muestra la selección actual en el cuadro combinado. Esta compatibilidad se delega en el cuadro de lista situado debajo del cuadro combinado.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Depende|Si el cuadro combinado tiene la capacidad de tomar valores de texto arbitrarios, se debe admitir el patrón Value. Este patrón ofrece la capacidad de establecer mediante programación el contenido de la cadena del cuadro combinado. Si no se admite el patrón Value, esto indica que el usuario debe realizar una selección de los elementos de lista dentro del subárbol del cuadro combinado.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Nunca|El patrón Scroll nunca se admite directamente en un cuadro combinado. Se admite si se puede desplazar un cuadro de lista contenido dentro de un cuadro combinado. Solo se admite cuando el cuadro de lista está visible en la pantalla.|  
  
<a name="Required_Events"></a>
## <a name="required-events"></a>Eventos necesarios  
 En la tabla siguiente se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que todos los controles de cuadro combinado deben admitir. Para más información sobre los eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obligatorio|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Requerido|None|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Depende|Si el control admite el patrón Value, debe admitir este evento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.ComboBox>
- [Información general sobre tipos de control de UI Automation](ui-automation-control-types-overview.md)
- [Información general sobre UI Automation](ui-automation-overview.md)
