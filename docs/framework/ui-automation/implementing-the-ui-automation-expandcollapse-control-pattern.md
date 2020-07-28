---
title: Implementar el patrón de control ExpandCollapse de UI Automation
description: Obtenga información sobre las directrices y convenciones de implementación del patrón de control ExpandCollapse en la automatización de la interfaz de usuario. Sepa cómo implementar IExpandCollapseProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, ExpandCollapse control pattern
- ExpandCollapse control pattern
- control patterns, ExpandCollapse
ms.assetid: 1dbabb8c-0d68-47c1-a35e-1c01cb01af26
ms.openlocfilehash: 525b57816071ba2d879036676201a0506d1a29db
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165865"
---
# <a name="implementing-the-ui-automation-expandcollapse-control-pattern"></a>Implementar el patrón de control ExpandCollapse de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).

En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, incluida la información sobre propiedades, métodos y eventos. Al final de la información general se proporcionan vínculos a referencias adicionales.

El patrón de control <xref:System.Windows.Automation.ExpandCollapsePattern> se usa para admitir controles que se expanden visualmente para mostrar más contenido y se contraen para ocultarlo. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).

<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación

Al implementar el patrón de control ExpandCollapse, tenga en cuenta las siguientes directrices y convenciones:

- Los controles agregados, compilados con objetos secundarios que proporcionan la funcionalidad de expandir y contraer a la interfaz de usuario, deben ser compatibles con el patrón de control <xref:System.Windows.Automation.ExpandCollapsePattern> , mientras que sus elementos secundarios no tienen que serlo. Por ejemplo, se crea un control de cuadro combinado con una combinación de cuadro de lista, botón y controles de edición, pero solo el cuadro combinado primario debe ser compatible con el <xref:System.Windows.Automation.ExpandCollapsePattern>.

  > [!NOTE]
  > Una excepción es el control de menú, que es un agregado de objetos MenuItem individuales. Los objetos MenuItem son compatibles con el patrón de control <xref:System.Windows.Automation.ExpandCollapsePattern> , pero el control Menú primario no lo es. Se aplica una excepción similar a los controles Árbol y Elemento de árbol.

- Si el <xref:System.Windows.Automation.ExpandCollapseState> de un control se establece en <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>, toda funcionalidad <xref:System.Windows.Automation.ExpandCollapsePattern> está actualmente inactiva para el control y la única información que se puede obtener mediante este patrón de control es <xref:System.Windows.Automation.ExpandCollapseState>. Si posteriormente se agrega cualquier objeto secundario, <xref:System.Windows.Automation.ExpandCollapseState> cambia y se activa la funcionalidad <xref:System.Windows.Automation.ExpandCollapsePattern> .

- <xref:System.Windows.Automation.ExpandCollapseState> hace referencia únicamente a la visibilidad de los objetos secundarios inmediatos, no a la visibilidad de todos los objetos descendientes.

- La funcionalidad de expandir y contraer es específica del control. A continuación se muestran ejemplos de este comportamiento.

  - El menú Personal de Office puede ser un MenuItem de tres estados (<xref:System.Windows.Automation.ExpandCollapseState.Expanded>, <xref:System.Windows.Automation.ExpandCollapseState.Collapsed> y <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>), donde el control especifica el estado que se debe adoptar cuando se llama a un <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> .

  - Llamar a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> en un objeto TreeItem puede hacer que se muestren todos los descendientes o solo los elementos secundarios inmediatos.

  - Si llamar a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> en un control mantiene el estado de sus descendientes, debería enviarse un evento de cambio de visibilidad, no un evento de cambio de estado. Si el control primario no mantiene el estado de sus descendientes cuando se contrae, el control podría destruir todos los descendientes que ya no estén visibles y generar un evento destruido; o podría cambiar la <xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A> de cada descendiente y generar un evento de cambio de visibilidad.

- Para garantizar la navegación, es deseable que un objeto esté en el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (con el estado de visibilidad adecuado), independientemente de sus elementos primarios <xref:System.Windows.Automation.ExpandCollapseState>. Si los descendientes se generan a petición, solo pueden aparecer en el árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] después de que se muestren por primera vez o solo mientras estén visibles.

<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-iexpandcollapseprovider"></a>Miembros requeridos para IExpandCollapseProvider

Para implementar <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, se requieren las siguientes propiedades y métodos.

|Miembros requeridos|Tipo de miembro|Notas|
|----------------------|-----------------|-----------|
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Propiedad.|None|
|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>|Método|None|
|<xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>|Método|None|
|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|Evento|Este control no tiene ningún evento asociado; use este delegado genérico.|

<a name="Exceptions"></a>

## <a name="exceptions"></a>Excepciones

Los proveedores deben producir las siguientes excepciones.

|Tipo de excepción|Condición|
|--------------------|---------------|
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> Se llama a o cuando <xref:System.Windows.Automation.ExpandCollapseState>  =  <xref:System.Windows.Automation.ExpandCollapseState.LeafNode> .|

## <a name="see-also"></a>Consulte también

- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Navegar entre elementos de UI Automation con TreeWalker](navigate-among-ui-automation-elements-with-treewalker.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
