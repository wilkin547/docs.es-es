---
title: Implementar el patrón de control TableItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: db94a1a4588c2f889da8adb1cb3e47e208ce1211
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393722"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a>Implementar el patrón de control TableItem de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presenta las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>, incluida la información sobre los eventos y propiedades. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El <xref:System.Windows.Automation.TableItemPattern> patrón de control se usa para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>. Acceso a la funcionalidad de la celda individual lo proporciona la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>. Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider> con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableItemProvider> debe exponer mediante programación la relación entre la celda individual y su información de fila y columna. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
  
-   Para la funcionalidad de elemento de cuadrícula relacionada, consulte [implementar el patrón de Control GridItem de UI Automation](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).  
  
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
 [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Patrones de control de Automatización de la interfaz de usuario para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Implementación del patrón de control Table de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [Implementación del patrón de control GridItem de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [Información general sobre el árbol de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Uso del almacenamiento en caché en la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
