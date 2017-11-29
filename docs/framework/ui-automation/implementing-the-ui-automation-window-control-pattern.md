---
title: "Implementar el patrón de control Window de UI Automation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
caps.latest.revision: "21"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 9e8d83c3ef40ccc6e97ba3128cab5d88a5af5305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a>Implementar el patrón de control Window de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>, incluida la información sobre las propiedades, los métodos y los eventos de <xref:System.Windows.Automation.WindowPattern> . Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.WindowPattern> se utiliza para admitir controles que ofrecen funcionalidad fundamental basada dentro de una [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)]tradicional. Entre los ejemplos de controles que deben implementar este patrón de control se incluyen las ventanas de la aplicación de nivel superior, las ventanas secundarias de [!INCLUDE[TLA#tla_mdi](../../../includes/tlasharptla-mdi-md.md)] , los controles de panel de división que se pueden cambiar de tamaño, los cuadros de diálogo modales y las ventanas de globo de ayuda.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Window, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Para admitir la capacidad de modificar el tamaño de la ventana y la posición de la pantalla mediante Automatización de la interfaz de usuario, un control debe implementar <xref:System.Windows.Automation.Provider.ITransformProvider> además de <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
-   Los controles que contienen barras de título y elementos de barra de título que permiten que el control se mueva, cambie de tamaño, se maximice, minimice o se cierre son normalmente necesarios para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
-   Los controles como los elementos emergentes de información sobre herramientas y las listas desplegables de menús o cuadros combinados normalmente no implementan <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
-   Las ventanas de globo de ayuda se diferencian de los elementos emergentes de información sobre herramientas básicos en el aprovisionamiento de un botón de cierre de tipo ventana.  
  
-   El modo de pantalla completa no es compatible con IWindowProvider, ya que es una característica específica de una aplicación y no es el comportamiento de ventana típico.  
  
<a name="Required_Members_for_IWindowProvider"></a>   
## <a name="required-members-for-iwindowprovider"></a>Miembros necesarios para IWindowProvider  
 Para la interfaz de IWindowProvider, se requieren los siguientes métodos, eventos y propiedades.  
  
|Miembro requerido|Tipo de miembro|Notas|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|Método|Ninguna|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|Evento|Ninguno|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|Evento|Ninguno|  
|<xref:System.Windows.Automation.WindowInteractionState>|Evento|No se garantiza que sea <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction>|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> -Cuando un control no admite un comportamiento solicitado.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> -Cuando el parámetro no es un número válido.|  
  
## <a name="see-also"></a>Vea también  
 [Información general del patrones de Control UI Automation](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Patrones de Control compatibles en un proveedor de UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Patrones de Control UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Información general sobre el árbol de automatización de interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Usar almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
