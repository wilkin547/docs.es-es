---
title: Implementar el patrón de control TableItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
ms.openlocfilehash: 4374666ba5e03720413614c63b00ba987f81f58f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447085"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a>Implementar el patrón de control TableItem de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ITableItemProvider>y se incluye información sobre eventos y propiedades. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.TableItemPattern> se usa para admitir controles secundarios de contenedores que implementan <xref:System.Windows.Automation.Provider.ITableProvider>. El acceso a la funcionalidad de celda individual lo proporciona la implementación simultánea necesaria de <xref:System.Windows.Automation.Provider.IGridItemProvider>. Este patrón de control es análogo a <xref:System.Windows.Automation.Provider.IGridItemProvider>, con la diferencia de que cualquier control que implemente <xref:System.Windows.Automation.Provider.ITableItemProvider> debe exponer mediante programación la relación entre la celda individual y su información de fila y columna. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
  
- Para obtener la funcionalidad de elemento de cuadrícula relacionada, vea [implementar el patrón de control GridItem de UI Automation](implementing-the-ui-automation-griditem-control-pattern.md).  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a>Miembros requeridos para ITableItemProvider  
  
|Miembro requerido|Tipo de miembro|Notas|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|Método|Ninguno|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|Método|Ninguno|  
  
 Este patrón de control no tiene eventos o propiedades asociados.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Este patrón de control no tiene excepciones asociadas.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario](support-control-patterns-in-a-ui-automation-provider.md)
- [UI Automation Control Patterns for Clients](ui-automation-control-patterns-for-clients.md)
- [Implementación del patrón de control Table de Automatización de la interfaz de usuario](implementing-the-ui-automation-table-control-pattern.md)
- [Implementación del patrón de control GridItem de Automatización de la interfaz de usuario](implementing-the-ui-automation-griditem-control-pattern.md)
- [Información general sobre el árbol de la Automatización de la interfaz de usuario](ui-automation-tree-overview.md)
- [Uso del almacenamiento en caché en la Automatización de la interfaz de usuario](use-caching-in-ui-automation.md)
