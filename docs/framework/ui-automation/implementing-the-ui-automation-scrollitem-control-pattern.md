---
title: Implementar el patrón de control ScrollItem de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 3a0647ab98dcb86306573a0e9826fa7232fa9ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180138"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a>Implementar el patrón de control ScrollItem de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IScrollItemProvider>, incluida la información sobre propiedades, métodos y eventos. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.ScrollItemPattern> se usa para admitir controles secundarios individuales de contenedores que implementan <xref:System.Windows.Automation.Provider.IScrollProvider>. Este patrón de control actúa como canal de comunicación entre un control secundario y su contenedor para garantizar que el contenedor puede cambiar el contenido (o región) visible en ese momento dentro de su ventanilla para mostrar el control secundario. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Scroll Item, tenga en cuenta las siguientes directrices y convenciones:  
  
- Los elementos que se incluye en un control Window o Canvas no tienen que implementar la interfaz de IScrollItemProvider. Sin embargo, como alternativa, deben exponer una ubicación válida para <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>. Esto permitirá que una aplicación cliente de UI Automation use los métodos de patrón de control <xref:System.Windows.Automation.ScrollPattern> en el contenedor para que muestre el elemento secundario.  
  
<a name="Required_Members_for_IScrollItemProvider"></a>
## <a name="required-members-for-iscrollitemprovider"></a>Miembros requeridos para IScrollItemProvider  
 El siguiente método es necesario para implementar la interfaz de IScrollProvider.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|- Método|None|  
  
 Este patrón de control no tiene eventos o propiedades asociados.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Si no se puede desplazar un elemento en la vista:<br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a>Consulte también

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
