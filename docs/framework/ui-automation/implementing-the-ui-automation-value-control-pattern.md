---
title: Implementar el patrón de control Value de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
ms.openlocfilehash: cccaf1afa55d786e43863e094a9745a0a1d00870
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174959"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a>Implementar el patrón de control Value de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IValueProvider>y se incluye información sobre eventos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.ValuePattern> se utiliza para admitir controles que tienen un valor intrínseco que no abarca un intervalo y que se puede representar como una cadena. Esta cadena puede ser editable, dependiendo del control y su configuración. Para obtener ejemplos de controles que implementan este patrón, vea [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  
 Al implementar el patrón de control Value, tenga en cuenta las siguientes directrices y convenciones:  
  
-   Los controles como <xref:System.Windows.Automation.ControlType.ListItem> y <xref:System.Windows.Automation.ControlType.TreeItem> deben admitir <xref:System.Windows.Automation.ValuePattern> si el valor de cualquiera de los elementos es modificable, sin tener en cuenta el modo de edición actual del control. El control primario también debe admitir <xref:System.Windows.Automation.ValuePattern> si los elementos secundarios son modificables.  
  
 ![Elemento de lista modificable. ](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")  
Ejemplo de un elemento de lista modificable  
  
-   Los controles de edición de línea única admiten el acceso mediante programación a su contenido a través de la implementación de <xref:System.Windows.Automation.Provider.IValueProvider>. Sin embargo, los controles de edición multilínea no implementan <xref:System.Windows.Automation.Provider.IValueProvider>; en su lugar, proporcionan acceso a su contenido mediante la implementación de <xref:System.Windows.Automation.Provider.ITextProvider>.  
  
-   Para recuperar el contenido textual de un control de edición de multilínea, el control debe implementar <xref:System.Windows.Automation.Provider.ITextProvider>. Sin embargo, <xref:System.Windows.Automation.Provider.ITextProvider> no admite establecer el valor de un control.  
  
-   <xref:System.Windows.Automation.Provider.IValueProvider> no se admite la recuperación de información de formato ni valores de subcadena. Implemente <xref:System.Windows.Automation.Provider.ITextProvider> en estos escenarios.  
  
-   <xref:System.Windows.Automation.Provider.IValueProvider> debe implementarse mediante controles, como el **selector de colores** control de selección de [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (se muestra a continuación), que admite la asignación de cadena entre un valor de color (por ejemplo, "amarillo") y un equivalente interno[!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)]estructura.  
  
 ![Selector de color con amarillo resaltado. ](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Ejemplo de asignación de cadena de muestrario de colores  
  
-   Un control debe tener el valor de su <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> establecido en `true` y el valor de <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> establecido en `false` antes de permitir una llamada a <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a>Miembros requeridos para IValueProvider  
 Para implementar <xref:System.Windows.Automation.Provider.IValueProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembros requeridos|Tipo de miembro|Notas|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|Propiedad|Ninguna|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|Método|Ninguna|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Excepciones  
 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> -Si la información específica de la configuración regional se pasa a un control en un formato incorrecto, como una fecha con formato incorrecto.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> -Si no se puede convertir un nuevo valor de una cadena a un formato en el control reconoce.|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> -Cuando se realiza un intento de manipular un control que no está habilitado.|  
  
## <a name="see-also"></a>Vea también

- [Información general acerca de los patrones de control de UI Automation](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [ValuePattern Insert Text Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [Información general sobre el árbol de la UI Automation](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
