---
title: "Implementing the UI Automation Transform Control Pattern | Microsoft Docs"
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
  - "control patterns, Transform"
  - "Transform control pattern"
  - "UI Automation, Transform control pattern"
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
caps.latest.revision: 14
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 14
---
# Implementing the UI Automation Transform Control Pattern
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITransformProvider>, incluida la información sobre propiedades, métodos y eventos. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.TransformPattern> se utsa para admitir controles que se pueden mover, cambiar de tamaño o girar dentro de un espacio bidimensional. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Directrices y convenciones de implementación  
 Al implementar el patrón de control Transform, tenga en cuenta las siguientes directrices y convenciones:  
  
-   La compatibilidad con este patrón de control no se limita a los objetos del escritorio. Este patrón de control también lo admite los elementos secundarios de un objeto contenedor si los elementos secundarios se pueden mover, cambiar de tamaño o girar libremente dentro de los límites del contenedor.  
  
-   Un objeto no se puede mover, cambiar de tamaño o girar de manera que su ubicación en pantalla resultante quede completamente fuera de las coordenadas de su contenedor y que, por tanto, sea inaccesible para el teclado o el mouse \(por ejemplo, cuando una ventana de nivel superior se mueva fuera de la pantalla o un objeto secundario se mueva fuera de los límites de la ventanilla del contenedor\). En estos casos, el objeto se coloca lo más cerca posible de las coordenadas de pantalla solicitadas reemplazando las coordenadas superiores o izquierdas para que se encuentren dentro de los límites del contenedor.  
  
-   Para sistemas de varios monitores, si se mueve un objeto, cambia de tamaño o gira completamente fuera de las coordenadas de pantalla de escritorio combinadas, el objeto se coloca en el monitor principal lo más cerca posible de las coordenadas solicitadas.  
  
-   Todos los parámetros y los valores de propiedad son absolutos e independientes de la configuración regional.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## Miembros requeridos para ITransformProvider  
 Para implementar <xref:System.Windows.Automation.Provider.ITransformProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|-------------------------|---------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|Propiedad|Ninguno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|Método|Ninguna|  
  
 Este patrón de control no tiene eventos asociados.  
  
<a name="Exceptions"></a>   
## Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|-----------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> -   Si <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> es false.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> -   Si <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> es false.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> -   Si <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> es false.|  
  
## Vea también  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)