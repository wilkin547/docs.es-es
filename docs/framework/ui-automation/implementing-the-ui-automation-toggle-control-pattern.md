---
title: "Implementing the UI Automation Toggle Control Pattern | Microsoft Docs"
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
  - "Toggle control pattern"
  - "control patterns, Toggle"
  - "UI Automation, Toggle control pattern"
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Implementing the UI Automation Toggle Control Pattern
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IToggleProvider>, incluida la información sobre métodos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.TogglePattern> se usa para admitir controles que pueden recorrer un conjunto de estados y mantener un estado una vez establecido. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## Directrices y convenciones de implementación  
 Al implementar el patrón de control Toggle, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Los controles que no mantienen el estado cuando se activan, como botones, botones de barra de herramientas e hipervínculos, deben implementar <xref:System.Windows.Automation.Provider.IInvokeProvider> en su lugar.  
  
-   Un control debe recorrer su <xref:System.Windows.Automation.ToggleState> en el siguiente orden: <xref:System.Windows.Automation.ToggleState>, <xref:System.Windows.Automation.ToggleState> y, si se admite, <xref:System.Windows.Automation.ToggleState>.  
  
-   <xref:System.Windows.Automation.TogglePattern> no ofrece un método SetState\(newState\) debido a problemas relacionados con la configuración directa de una CheckBox de tres estados sin recorrer su secuencia <xref:System.Windows.Automation.ToggleState> correspondiente.  
  
-   El control RadioButton no implementa <xref:System.Windows.Automation.Provider.IToggleProvider>, ya que no es capaz de recorrer sus estados válidos.  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## Miembros requeridos para IToggleProvider  
 Para implementar <xref:System.Windows.Automation.Provider.IToggleProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembro requerido|Tipo de miembro|Notas|  
|-----------------------|---------------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Propiedad|Ninguna|  
  
 Este patrón de control no tiene eventos asociados.  
  
<a name="Exceptions"></a>   
## Excepciones  
 Este patrón de control no tiene excepciones asociadas.  
  
## Vea también  
 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Support Control Patterns in a UI Automation Provider](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [UI Automation Control Patterns for Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Get the Toggle State of a Check Box Using UI Automation](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)