---
title: "Implementar el patr&#243;n de control GridItem de UI Automation | Microsoft Docs"
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
  - "patrones de control GridItem"
  - "patrón de control GridItem de UI Automation"
  - "GridItem (patrón de control)"
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Implementar el patr&#243;n de control GridItem de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a desarrolladores de .NET Framework que quieran usar los recursos administrados [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] clases definidas en el <xref:System.Windows.Automation> espacio de nombres. Para obtener la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presenta las directrices y convenciones de implementación <xref:System.Windows.Automation.Provider.IGridItemProvider>, incluida la información acerca de las propiedades. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El <xref:System.Windows.Automation.GridItemPattern> patrón de control se utiliza para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IGridProvider>. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar <xref:System.Windows.Automation.Provider.IGridProvider>, tenga en cuenta las directrices y convenciones siguientes:  
  
-   Las coordenadas de la cuadrícula son de base, donde la celda superior izquierda tiene las coordenadas (0, 0).  
  
-   Las celdas combinadas informarán sus <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> y <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> propiedades basan en su celda del anclaje subyacente definida por el proveedor de automatización de la interfaz de usuario. Normalmente, será la fila o columna superior izquierda.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider> no proporciona manipulación activa de la cuadrícula como combinar o dividir celdas.  
  
-   Controles que implementan <xref:System.Windows.Automation.Provider.IGridItemProvider> pueden recorrer normalmente (es decir, un cliente de automatización de la interfaz de usuario puede pasar a los controles adyacentes) mediante el teclado.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Miembros requeridos para IGridItemProvider  
 Los siguientes métodos y propiedades que son necesarios para implementar <xref:System.Windows.Automation.Provider.IGridItemProvider>.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Propiedad|Ninguna|  
  
 Este patrón de control no tiene métodos o propiedades asociados.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Este patrón de control no tiene excepciones asociadas.  
  
## <a name="see-also"></a>Vea también  
 [Patrones de Control UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Patrones de Control compatibles en un proveedor UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Patrones de Control UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Implementar el patrón de Control Grid UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)   
 [Información general sobre el árbol de automatización de interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Usar el almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)