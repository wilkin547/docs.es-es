---
title: Eventos de UI Automation para clientes
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
ms.openlocfilehash: b56fc09b33a846fe94a52e19dc4b9c806d79c121
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044103"
---
# <a name="ui-automation-events-for-clients"></a>Eventos de UI Automation para clientes
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.  
  
 En este tema se describe cómo usan los clientes de UI Automation los eventos [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] permite que los clientes se suscriban a eventos de interés. Esta capacidad mejora el rendimiento eliminando la necesidad de sondear continuamente todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] del sistema para ver si ha cambiado cualquier información, estructura o estado.  
  
 La eficacia también mejora gracias a la capacidad para realizar escuchas de eventos que solo se encuentran dentro de un ámbito definido. Por ejemplo, un cliente puede estar a la escucha de eventos de cambio de foco en todos los elementos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] del árbol o solo en un elemento y sus descendientes.  
  
> [!NOTE]
> No dé por hecho que todos los eventos posibles los genera un proveedor de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]. Por ejemplo, no todos los cambios de propiedad provocan que los proveedores de proxy estándares generen eventos para los controles [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)].  
  
 Para obtener una vista más amplia [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] de los eventos, vea [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Las aplicaciones cliente se suscriben a eventos de un tipo determinado mediante el registro de un controlador de eventos, con uno de los métodos siguientes.  
  
|Método|Tipo de evento|Tipo de argumentos de evento|Tipo delegado|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Cambio de foco|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Cambio de propiedad|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Cambio de estructura|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Todos los demás eventos, identificados por un elemento <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> o <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Antes de llamar al método, debe crear un método delegado para controlar el evento. Si lo prefiere, puede controlar tipos diferentes de eventos en un solo método y pasar este método en varias llamadas a uno de los métodos de la tabla. Por ejemplo, es posible configurar un único elemento <xref:System.Windows.Automation.AutomationEventHandler> para controlar varios eventos de manera diferente, según el elemento <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
> Para procesar eventos de ventana cerrada, convierta el tipo de argumento que se pasa al controlador de eventos a <xref:System.Windows.Automation.WindowClosedEventArgs>. Como el elemento [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] para la ventana ya no es válido, no puede utilizar el parámetro `sender` para recuperar información; utilice <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> en su lugar.  
  
> [!CAUTION]
> Si la aplicación podría recibir eventos de su propia [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], no utilice el subproceso [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] de la aplicación para suscribirse a eventos o para cancelar la suscripción. Si lo hace, podría provocar un comportamiento imprevisible. Para obtener más información, consulta [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 Al apagar el equipo, o si los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ya no son de interés para la aplicación, los clientes de UI Automation deben llamar a uno de los métodos siguientes.  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Anula el registro de un controlador de eventos que se registró mediante <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Anula el registro de un controlador de eventos que se registró mediante <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Anula el registro de un controlador de eventos que se registró mediante <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Anula el registro de todos los controladores de eventos registrados.|  
  
 Para ver un ejemplo de código, vea [suscribirse a eventos de UI Automation](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Vea también

- [Suscripción a eventos de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)
- [Información general sobre eventos de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-events-overview.md)
- [Información general sobre las propiedades de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)
- [Ejemplo de TrackFocus](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FocusTracker)
