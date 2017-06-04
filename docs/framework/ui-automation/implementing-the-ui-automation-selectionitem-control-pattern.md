---
title: "Implementing the UI Automation SelectionItem Control Pattern | Microsoft Docs"
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
  - "Selection Item control pattern"
  - "UI Automation, Selection Item control pattern"
  - "control patterns, Selection Item"
ms.assetid: 76b0949a-5b23-4cfc-84cc-154f713e2e12
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# Implementing the UI Automation SelectionItem Control Pattern
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, incluida la información sobre propiedades, métodos y eventos. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.SelectionItemPattern> se usa para admitir controles que actúan como elementos secundarios individuales y seleccionables de controles de contenedor que implementan <xref:System.Windows.Automation.Provider.ISelectionProvider>. Para obtener ejemplos de controles que implementan el patrón de control SelectionItem, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Directrices y convenciones de implementación  
 Al implementar el patrón de control Selection Item, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Los controles de selección única que administran los controles secundarios que implementan <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, como el control deslizante de **Resolución de pantalla** del cuadro de diálogo de **Propiedades de pantalla**, deben implementar <xref:System.Windows.Automation.Provider.ISelectionProvider> y sus elementos secundarios deben implementar tanto <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> como <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## Miembros requeridos para ISelectionItemProvider  
 Para implementar <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, se requieren las siguientes propiedades, métodos y eventos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|-------------------------|---------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Método|Ninguna|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Evento|Se produce cuando una selección de un contenedor ha cambiado de manera considerable y requiere el envío de más eventos <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> y <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> de lo que permite la constante <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit>.|  
  
-   Si el resultado de <xref:System.Windows.Automation.SelectionItemPattern.Select%2A>, <xref:System.Windows.Automation.SelectionItemPattern.AddToSelection%2A> o <xref:System.Windows.Automation.SelectionItemPattern.RemoveFromSelection%2A> es un elemento seleccionado único, se debe generar un <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>; en caso contrario, envíe <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>\/<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> según sea adecuado.  
  
<a name="Exceptions"></a>   
## Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|-----------------------|---------------|  
|<xref:System.InvalidOperationException>|Cuando se intenten cualquiera de las siguientes opciones:<br /><br /> -   Se llama a <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> en un contenedor de selección única donde <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> \= `true` y ya hay un elemento seleccionado.<br />-   Se llama a <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> en un contenedor de selección múltiple donde <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> \= `true` y solo hay un elemento seleccionado.<br />-   Se llama a <xref:System.Windows.Automation.Provider.ISelectionItemProvider.AddToSelection%2A> en un contenedor de selección única donde <xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty> \= `false` y ya hay otro elemento seleccionado.|  
  
## Vea también  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Implementing the UI Automation Selection Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-selection-control-pattern.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [Fragment Provider Sample](http://msdn.microsoft.com/es-es/778ef1bc-8610-4bc9-886e-aeff94a8a13e)