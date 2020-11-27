---
title: Implementar el patrón de control Window de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control window en la automatización de la interfaz de usuario. Conocer los miembros necesarios para la interfaz IWindowProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Window
- UI Automation, Window control pattern
- Window control pattern
ms.assetid: a28cb286-296e-4a62-b4cb-55ad636ebccc
ms.openlocfilehash: b43884393974e6f2863da6a4a5ca8f305e5a160c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286102"
---
# <a name="implementing-the-ui-automation-window-control-pattern"></a>Implementar el patrón de control Window de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>, incluida la información sobre las propiedades, los métodos y los eventos de <xref:System.Windows.Automation.WindowPattern> . Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El <xref:System.Windows.Automation.WindowPattern> patrón de control se usa para admitir controles que proporcionan la funcionalidad fundamental basada en ventanas dentro de una interfaz gráfica de usuario (GUI) tradicional. Entre los ejemplos de controles que deben implementar este patrón de control se incluyen las ventanas de aplicación de nivel superior, las ventanas secundarias de interfaz de múltiples documentos (MDI), los controles de panel de división de tamaño ajustable, los cuadros de diálogo modales y las ventanas de ayuda de globo.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  

 Al implementar el patrón de control Window, tenga en cuenta las siguientes directrices y convenciones:  
  
- Para admitir la capacidad de modificar el tamaño de la ventana y la posición de la pantalla mediante Automatización de la interfaz de usuario, un control debe implementar <xref:System.Windows.Automation.Provider.ITransformProvider> además de <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
- Los controles que contienen barras de título y elementos de barra de título que permiten que el control se mueva, cambie de tamaño, se maximice, minimice o se cierre son normalmente necesarios para implementar <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
- Los controles como los elementos emergentes de información sobre herramientas y las listas desplegables de menús o cuadros combinados normalmente no implementan <xref:System.Windows.Automation.Provider.IWindowProvider>.  
  
- Las ventanas de globo de ayuda se diferencian de los elementos emergentes de información sobre herramientas básicos en el aprovisionamiento de un botón de cierre de tipo ventana.  
  
- El modo de pantalla completa no es compatible con IWindowProvider, ya que es una característica específica de una aplicación y no es el comportamiento de ventana típico.  
  
<a name="Required_Members_for_IWindowProvider"></a>

## <a name="required-members-for-iwindowprovider"></a>Miembros necesarios para IWindowProvider  

 Para la interfaz de IWindowProvider, se requieren los siguientes métodos, eventos y propiedades.  
  
|Miembro requerido|Tipo de miembro|Notas|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.InteractionState%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsModal%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.IsTopmost%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Maximizable%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Minimizable%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.VisualState%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.Close%2A>|Método|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A>|Método|None|  
|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A>|Método|None|  
|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|Evento|None|  
|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|Evento|None|  
|<xref:System.Windows.Automation.WindowInteractionState>|Evento|No se garantiza que sea <xref:System.Windows.Automation.WindowInteractionState.ReadyForUserInteraction>|  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a>Excepciones  

 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IWindowProvider.SetVisualState%2A><br /><br /> : Cuando un control no admite un comportamiento solicitado.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IWindowProvider.WaitForInputIdle%2A><br /><br /> : Cuando el parámetro no es un número válido.|  
  
## <a name="see-also"></a>Vea también

- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
