---
title: Eventos de UI Automation para clientes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
caps.latest.revision: "32"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 8486f8c8eaa586f6f81ea895fd22c96801b3594b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ui-automation-events-for-clients"></a>Eventos de UI Automation para clientes
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se describe cómo usan los clientes de UI Automation los eventos [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)].  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]permite a los clientes para suscribirse a eventos de interés. Esta capacidad mejora el rendimiento eliminando la necesidad de sondear continuamente todos los [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementos en el sistema para ver si ha cambiado cualquier información, estructura o estado.  
  
 La eficacia también mejora gracias a la capacidad para realizar escuchas de eventos que solo se encuentran dentro de un ámbito definido. Por ejemplo, un cliente puede escuchar eventos de cambio de foco en todos los [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elementos en el árbol, o en un solo elemento y sus descendientes.  
  
> [!NOTE]
>  No se da por supuesto que todos los posibles eventos generados por un [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] proveedor. Por ejemplo, no todos los cambios de propiedad hacen que se provoquen con los proveedores de proxy estándar para eventos [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] y [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controles.  
  
 Para obtener una vista más amplia de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] los eventos, vea [información general sobre eventos de UI Automation](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Suscripción a eventos  
 Las aplicaciones cliente se suscriben a eventos de un tipo determinado mediante el registro de un controlador de eventos, con uno de los métodos siguientes.  
  
|Método|Tipo de evento|Tipo de argumentos de evento|Tipo delegado|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Cambio de foco|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Cambio de propiedad|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Cambio de estructura|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Todos los demás eventos, identificados por un<xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> o <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Antes de llamar al método, debe crear un método delegado para controlar el evento. Si lo prefiere, puede controlar tipos diferentes de eventos en un solo método y pasar este método en varias llamadas a uno de los métodos de la tabla. Por ejemplo, una sola <xref:System.Windows.Automation.AutomationEventHandler> puede configurarse para controlar varios eventos de forma diferente según el <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Para procesar eventos de ventana cerrada, convierta el tipo de argumento que se pasa al controlador de eventos como <xref:System.Windows.Automation.WindowClosedEventArgs>. Porque el [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] elemento de la ventana ya no es válido, no se puede usar el `sender` parámetro para recuperar información; utilice <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> en su lugar.  
  
> [!CAUTION]
>  Si la aplicación puede recibir eventos desde su propio [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], no use la aplicación [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] subproceso para suscribirse a eventos o para cancelar la suscripción. Si lo hace, podría provocar un comportamiento imprevisible. Para obtener más información, consulta [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 Al apagar el equipo, o si los eventos [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ya no son de interés para la aplicación, los clientes de UI Automation deben llamar a uno de los métodos siguientes.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Anula el registro de un controlador de eventos que se registró mediante <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Anula el registro de un controlador de eventos que se registró mediante <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Anula el registro de un controlador de eventos que se registró mediante <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Anula el registro de todos los controladores de eventos registrados.|  
  
 Por ejemplo de código, vea [suscribirse a eventos de automatización de interfaz de usuario](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Vea también  
 [Suscripción a eventos de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [Información general sobre eventos de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [Información general sobre las propiedades de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [Ejemplo de TrackFocus](http://msdn.microsoft.com/library/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
