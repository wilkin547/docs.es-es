---
title: Implementar el patrón de control Selection de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- Selection control pattern
- UI Automation, Selection control pattern
- control patterns, Selection
ms.assetid: 449c3068-a5d6-4f66-84c6-1bcc7dd4d209
ms.openlocfilehash: 0b468c7fd88c7b79ca069553af0740e84ae9d05b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649508"
---
# <a name="implementing-the-ui-automation-selection-control-pattern"></a>Implementar el patrón de control Selection de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.ISelectionProvider>, incluida la información sobre eventos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.SelectionPattern> se usa para admitir controles que actúan como contenedores para una colección de elementos secundarios seleccionables. Los elementos secundarios de este elemento deben implementar <xref:System.Windows.Automation.Provider.ISelectionItemProvider>. Para obtener ejemplos de controles que implementan este patrón de control, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Selection, tenga en cuenta las siguientes directrices y convenciones:  
  
- Los controles que implementan <xref:System.Windows.Automation.Provider.ISelectionProvider> permiten la selección de elementos secundarios únicos o múltiples. Por ejemplo, el cuadro de lista, la vista de lista y la vista de árbol admiten varias selecciones mientras que el cuadro combinado, el control deslizante y el grupo de botones de radio admiten la selección única.  
  
- Los controles que tienen un intervalo mínimo, máximo y continuo, como el control deslizante **Volumen** , deben implementar <xref:System.Windows.Automation.Provider.IRangeValueProvider> en lugar de <xref:System.Windows.Automation.Provider.ISelectionProvider>.  
  
- Los controles de selección única que administran los controles secundarios que implementan <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, como el control deslizante de **Resolución de pantalla** del cuadro de diálogo de **Propiedades de pantalla** o el control de selección **Selector de color** de [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (se muestra a continuación), deben implementar <xref:System.Windows.Automation.Provider.ISelectionProvider>; sus elementos secundarios deben implementar tanto <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> como <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
 ![Selector de color con amarillo resaltado. ](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Ejemplo de asignación de cadena de muestrario de colores  
  
- Los menús no admiten <xref:System.Windows.Automation.SelectionPattern>. Si está trabajando con elementos de menú que incluyen tanto gráficos como texto (como los elementos del **panel de vista previa** del menú **Ver** [!INCLUDE[TLA#tla_outlook](../../../includes/tlasharptla-outlook-md.md)]) y necesita transmitir el estado, debe implementar <xref:System.Windows.Automation.Provider.IToggleProvider>.  
  
<a name="Required_Members_for_ISelectionProvider"></a>   
## <a name="required-members-for-iselectionprovider"></a>Miembros requeridos para ISelectionProvider  
 Para la interfaz de <xref:System.Windows.Automation.Provider.ISelectionProvider> , se requieren las siguientes propiedades, métodos y eventos.  
  
|Miembros requeridos|Tipo|Notas|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Propiedad|Debe admitir eventos de cambio de propiedad mediante <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> y <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Propiedad|Debe admitir eventos de cambio de propiedad mediante <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> y <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Método|Ninguna|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|evento|Se produce cuando una selección de un contenedor ha cambiado de manera considerable y requiere el envío de más eventos de adición y eliminación de lo que permite la constante <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> .|  
  
 Las propiedades <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> y <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> pueden ser dinámicas. Por ejemplo, es posible que el estado inicial de un control no tenga elementos seleccionados de forma predeterminada, lo que indica que <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> es `false`. Sin embargo, cuando se haya seleccionado un elemento, el control siempre debe tener al menos un elemento seleccionado. Del mismo modo, en raras ocasiones, un control podría permitir la selección de varios elementos en la inicialización pero solo permitir posteriormente la realización de selecciones únicas.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|Si el control no está habilitado.|  
|<xref:System.InvalidOperationException>|Si el control está oculto.|  
  
## <a name="see-also"></a>Vea también

- [Información general sobre los patrones de control de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de control de Automatización de la interfaz de usuario para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Implementación del patrón de control SelectionItem de Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/implementing-the-ui-automation-selectionitem-control-pattern.md)
- [Información general sobre el árbol de la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Uso del almacenamiento en caché en la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
