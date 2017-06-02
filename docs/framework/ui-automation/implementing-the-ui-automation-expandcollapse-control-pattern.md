---
title: "Implementing the UI Automation ExpandCollapse Control Pattern | Microsoft Docs"
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
  - "UI Automation, ExpandCollapse control pattern"
  - "ExpandCollapse control pattern"
  - "control patterns, ExpandCollapse"
ms.assetid: 1dbabb8c-0d68-47c1-a35e-1c01cb01af26
caps.latest.revision: 25
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 25
---
# Implementing the UI Automation ExpandCollapse Control Pattern
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, incluida la información sobre propiedades, métodos y eventos. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.ExpandCollapsePattern> se usa para admitir controles que se expanden visualmente para mostrar más contenido y se contraen para ocultarlo. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Directrices y convenciones de implementación  
 Al implementar el patrón de control ExpandCollapse, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Los controles agregados, compilados con objetos secundarios que proporcionan la funcionalidad de expandir y contraer a la interfaz de usuario, deben ser compatibles con el patrón de control <xref:System.Windows.Automation.ExpandCollapsePattern>, mientras que sus elementos secundarios no tienen que serlo. Por ejemplo, se crea un control de cuadro combinado con una combinación de cuadro de lista, botón y controles de edición, pero solo el cuadro combinado primario debe ser compatible con el <xref:System.Windows.Automation.ExpandCollapsePattern>.  
  
    > [!NOTE]
    >  Una excepción es el control de menú, que es un agregado de objetos MenuItem individuales. Los objetos MenuItem son compatibles con el patrón de control <xref:System.Windows.Automation.ExpandCollapsePattern>, pero el control Menú primario no lo es. Se aplica una excepción similar a los controles Árbol y Elemento de árbol.  
  
-   Si el <xref:System.Windows.Automation.ExpandCollapseState> de un control se establece en <xref:System.Windows.Automation.ExpandCollapseState>, toda funcionalidad <xref:System.Windows.Automation.ExpandCollapsePattern> está actualmente inactiva para el control y la única información que se puede obtener mediante este patrón de control es <xref:System.Windows.Automation.ExpandCollapseState>. Si posteriormente se agrega cualquier objeto secundario, <xref:System.Windows.Automation.ExpandCollapseState> cambia y se activa la funcionalidad <xref:System.Windows.Automation.ExpandCollapsePattern>.  
  
-   <xref:System.Windows.Automation.ExpandCollapseState> hace referencia únicamente a la visibilidad de los objetos secundarios inmediatos, no a la visibilidad de todos los objetos descendientes.  
  
-   La funcionalidad de expandir y contraer es específica del control. A continuación se muestran ejemplos de este comportamiento.  
  
    -   El menú Personal de Office puede ser un MenuItem de tres estados \(<xref:System.Windows.Automation.ExpandCollapseState>, <xref:System.Windows.Automation.ExpandCollapseState> y <xref:System.Windows.Automation.ExpandCollapseState>\), donde el control especifica el estado que se debe adoptar cuando se llama a un <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>.  
  
    -   Llamar a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> en un objeto TreeItem puede hacer que se muestren todos los descendientes o solo los elementos secundarios inmediatos.  
  
    -   Si llamar a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> en un control mantiene el estado de sus descendientes, debería enviarse un evento de cambio de visibilidad, no un evento de cambio de estado. Si el control primario no mantiene el estado de sus descendientes cuando se contrae, el control podría destruir todos los descendientes que ya no estén visibles y generar un evento destruido; o podría cambiar la <xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A> de cada descendiente y generar un evento de cambio de visibilidad.  
  
-   Para garantizar la navegación, es deseable que un objeto esté en el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] \(con el estado de visibilidad adecuado\), independientemente de sus elementos primarios <xref:System.Windows.Automation.ExpandCollapseState>. Si los descendientes se generan a petición, solo pueden aparecer en el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] después de que se muestren por primera vez o solo mientras estén visibles.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## Miembros requeridos para IExpandCollapseProvider  
 Para implementar <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|-------------------------|---------------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>|Método|Ninguna|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|Evento|Este control no tiene ningún evento asociado; use este delegado genérico.|  
  
<a name="Exceptions"></a>   
## Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|-----------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> se llama cuando <xref:System.Windows.Automation.ExpandCollapseState> \= <xref:System.Windows.Automation.ExpandCollapseState>.|  
  
## Vea también  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Navigate Among UI Automation Elements with TreeWalker](../../../docs/framework/ui-automation/navigate-among-ui-automation-elements-with-treewalker.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)