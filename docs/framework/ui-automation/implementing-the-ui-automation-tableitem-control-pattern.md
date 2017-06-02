---
title: "Implementar el patr&#243;n de control TableItem de UI Automation | Microsoft Docs"
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
  - "patrones de control de elemento de tabla"
  - "Automatización de interfaz de usuario, el patrón de control TableItem"
  - "TableItem (patrón de control)"
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
caps.latest.revision: 14
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 14
---
# Implementar el patr&#243;n de control TableItem de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que quieran usar los recursos administrados [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clases definidas en el <xref:System.Windows.Automation> espacio de nombres. Para obtener la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presenta las directrices y convenciones de implementación <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluida la información sobre los eventos y propiedades. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El <xref:System.Windows.Automation.TableItemPattern> patrón de control se utiliza para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>. Acceso a la funcionalidad de la celda individual es proporcionado por la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>. Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider> con la diferencia de que cualquier control que implementa <xref:System.Windows.Automation.Provider.ITableItemProvider> mediante programación debe exponer la relación entre la celda individual y su información de fila y columna. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
  
-   Para la funcionalidad del elemento de cuadrícula relacionados, consulte [implementar el patrón de Control GridItem de UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a>Miembros requeridos para ITableItemProvider  
  
|Miembro requerido|Tipo de miembro|Notas|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|Método|Ninguna|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|Método|Ninguna|  
  
 Este patrón de control no tiene eventos o propiedades asociados.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Este patrón de control no tiene excepciones asociadas.  
  
## <a name="see-also"></a>Vea también  
 [Patrones de Control UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Patrones de Control compatibles en un proveedor UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Patrones de Control UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Implementar el patrón de Control Table UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)   
 [Implementar el patrón de Control GridItem UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)   
 [Información general sobre el árbol de automatización de interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Usar el almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)