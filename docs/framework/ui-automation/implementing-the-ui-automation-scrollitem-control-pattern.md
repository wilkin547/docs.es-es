---
title: "Implementar el patr&#243;n de control ScrollItem de UI Automation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "patrones de control de elemento de desplazamiento"
  - "Automatización de interfaz de usuario, el patrón de control ScrollItem"
  - "Scroll Item (patrón de control)"
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
caps.latest.revision: 16
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 16
---
# Implementar el patr&#243;n de control ScrollItem de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que quieran usar los recursos administrados [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clases definidas en el <xref:System.Windows.Automation> espacio de nombres. Para obtener la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presenta las directrices y convenciones de implementación de la <xref:System.Windows.Automation.Provider.IScrollItemProvider>, incluida información sobre las propiedades, métodos y eventos. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El <xref:System.Windows.Automation.ScrollItemPattern> patrón de control se utiliza para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IScrollProvider>. Este patrón de control actúa como canal de comunicación entre un control secundario y su contenedor para garantizar que el contenedor puede cambiar el contenido (o región) visible en ese momento dentro de su ventanilla para mostrar el control secundario. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Scroll Item, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Los elementos que se incluye en un control Window o Canvas no tienen que implementar la interfaz de IScrollItemProvider. Como alternativa, sin embargo, deben exponer una ubicación válida para la <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>. Esto permitirá que una aplicación de cliente de automatización de la interfaz de usuario para usar el <xref:System.Windows.Automation.ScrollPattern> controlar métodos del modelo en el contenedor para mostrar el elemento secundario.  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a>Miembros requeridos para IScrollItemProvider  
 El siguiente método es necesario para implementar la interfaz de IScrollProvider.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|-(Método)|Ninguna|  
  
 Este patrón de control no tiene eventos o propiedades asociados.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Si no se puede desplazar un elemento en la vista:<br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a>Vea también  
 [Patrones de Control UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Patrones de Control compatibles en un proveedor UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Patrones de Control UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Información general sobre el árbol de automatización de interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Usar el almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)