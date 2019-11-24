---
title: Compatibilidad de UI Automation para el tipo de control Menu
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu
- UI Automation, Menu control type
- Menu control type
ms.assetid: 016323cb-f800-4938-b77b-2eb25d646090
ms.openlocfilehash: f09438d9941f2abb49cae8f7542efe84f44e81dc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446744"
---
# <a name="ui-automation-support-for-the-menu-control-type"></a>Compatibilidad de UI Automation para el tipo de control Menu
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con el tipo de control Menu. Describe la estructura de árbol de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] de control y ofrece las propiedades y los patrones de control para escenarios de control concretos.  
  
 Un control de menú permite organizar jerárquicamente los elementos asociados a comandos y controladores de eventos. In a typical Microsoft Windows application, a menu bar contains several menu buttons (such as **File**, **Edit**, and **Window**), and each menu button displays a menu. Un menú contiene una colección de elementos de menú (como **Nuevo**, **Abrir**y **Cerrar**), que se puede expandir para mostrar elementos de menú adicionales o realizar una acción específica cuando se haga clic en ellos.  
  
 En las secciones siguientes se definen la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] necesaria, las propiedades, los patrones de control y los eventos para el tipo de control Menu. Los requisitos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de lista, ya sean [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de automatización de interfaz de usuario necesaria  
 En la tabla siguiente se describen la vista de control y la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de menú y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Vista de control|Vista de contenido|  
|------------------|------------------|  
|Menú<br /><br /> -   MenuItem (1 or many)|No aplicable (a menos que el control de menú sea un menú contextual que sea un elemento primario de un objeto que no sea un elemento de menú)<br /><br /> -   MenuItem (1 or many)|  
  
 Los controles de menú siempre aparecen en las vistas de control y contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Los tipos de control de menú deben aparecer en el control al que hace referencia su información. Los clientes de Automatización de la interfaz de usuario deben estar a la escucha de `MenuOpenedEvent` para asegurarse de que obtienen de forma coherente la información que transmiten los controles de menú. Los controles de menú contextual son un caso especial. Aparecen como elementos secundarios del escritorio.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que tienen un valor o una definición que es especialmente relevante para el tipo de control Menu. For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Propiedad[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valor|Notas|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|No admitido|El control de menú no requiere que se establezca una propiedad Name.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|No se espera ninguna etiqueta con un control de menú típico.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Menú|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|False|El control de menú no se incluye en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|El control de menú siempre se incluye en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Patrones de control necesarios para la automatización de la interfaz de usuario  
 No hay ningún patrón de control necesario para el tipo de control Menu.  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de automatización de la interfaz de usuario necesarios  
 Los controles de menú deben generar el evento `MenuOpenedEvent` cuando aparecen en la pantalla. El evento `MenuOpenedEvent` incluirá el texto del control. El evento `MenuClosedEvent` debe generarse cuando un menú desaparece de la pantalla.  
  
 En la siguiente tabla se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir todos los controles de menú. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Soporte técnico/valor|Notas|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.MenuOpenedEvent>|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.MenuClosedEvent>|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|Ninguno|  
|Evento de cambio de propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguno|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.Menu>
- [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](ui-automation-control-patterns-overview.md)
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
