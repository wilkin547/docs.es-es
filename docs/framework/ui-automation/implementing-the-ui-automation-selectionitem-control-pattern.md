---
title: Implementación del patrón de control SelectionItem de UI Automation
description: Consulte directrices y convenciones para implementar el patrón de control SelectionItem en la automatización de la interfaz de usuario. Conocer los miembros necesarios para la interfaz ISelectionItemProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- Selection Item control pattern
- UI Automation, Selection Item control pattern
- control patterns, Selection Item
ms.assetid: 76b0949a-5b23-4cfc-84cc-154f713e2e12
ms.openlocfilehash: 441417aa370563a9ce8b513be6ca4507b21e1e4a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163547"
---
# <a name="implementing-the-ui-automation-selectionitem-control-pattern"></a>Implementación del patrón de control SelectionItem de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, incluida la información sobre propiedades, métodos y eventos. Al final de la información general se proporcionan vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.SelectionItemPattern> se usa para admitir controles que actúan como elementos secundarios individuales y seleccionables de controles de contenedor que implementan <xref:System.Windows.Automation.Provider.ISelectionProvider>. Para obtener ejemplos de controles que implementan el patrón de control SelectionItem, vea [asignación de patrones de control para clientes de UI Automation](control-pattern-mapping-for-ui-automation-clients.md) .  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Selection Item, tenga en cuenta las siguientes directrices y convenciones:  
  
- Los controles de selección única que administran los controles secundarios que implementan <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, como el control deslizante de **Resolución de pantalla** del cuadro de diálogo de **Propiedades de pantalla** , deben implementar <xref:System.Windows.Automation.Provider.ISelectionProvider> y sus elementos secundarios deben implementar tanto <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> como <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-iselectionitemprovider"></a>Miembros requeridos para ISelectionItemProvider  
 Para implementar <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, se requieren las siguientes propiedades, métodos y eventos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Propiedad.|None|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Propiedad.|None|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Método|None|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Evento|Se produce cuando una selección de un contenedor ha cambiado de manera considerable y requiere el envío de más eventos <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> y <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> de lo que permite la constante <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> .|  
  
- Si el resultado de <xref:System.Windows.Automation.SelectionItemPattern.Select%2A>, <xref:System.Windows.Automation.SelectionItemPattern.AddToSelection%2A>o <xref:System.Windows.Automation.SelectionItemPattern.RemoveFromSelection%2A> es un elemento seleccionado único, se debe generar un <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> ; en caso contrario, envíe <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>/ <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> según sea adecuado.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Cuando se intenten cualquiera de las siguientes opciones:<br /><br /> -   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> en un contenedor de selección única donde <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` y ya hay un elemento seleccionado.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> en un contenedor de selección múltiple donde <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` y solo hay un elemento seleccionado.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.AddToSelection%2A> en un contenedor de selección única donde <xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty> = `false` y ya hay otro elemento seleccionado.|  
  
## <a name="see-also"></a>Consulte también

- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Implementar el patrón de control Selection de UI Automation](implementing-the-ui-automation-selection-control-pattern.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
- [Ejemplo de proveedor de fragmentos](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771502(v=vs.90))
