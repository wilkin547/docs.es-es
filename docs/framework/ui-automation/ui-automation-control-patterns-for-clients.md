---
title: Patrones de controles de UI Automation para clientes
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
ms.openlocfilehash: 1ee0df5b133f08ec3cf6ba617c80c480e207ddf6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179960"
---
# <a name="ui-automation-control-patterns-for-clients"></a>Patrones de controles de UI Automation para clientes
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 Este tema es una introducción a los patrones de control para clientes de automatización de la interfaz de usuario. Incluye información que explica cómo un cliente de automatización de la interfaz de usuario puede usar los patrones de control para tener acceso a la información sobre [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].  
  
 Los patrones de control proporcionan una manera de categorizar y exponer la funcionalidad de un control independientemente de su tipo o apariencia. Los clientes de automatización de la interfaz de usuario pueden examinar un <xref:System.Windows.Automation.AutomationElement> para determinar qué patrones de control son compatibles y estar seguros del comportamiento del control.  
  
 Para obtener una lista completa de los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>
## <a name="getting-control-patterns"></a>Obtener patrones de control  
 Los clientes recuperan un patrón de control de un <xref:System.Windows.Automation.AutomationElement> mediante una llamada a <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> o <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 Los clientes pueden usar el método <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> o una propiedad `IsPatternAvailable` individual (por ejemplo, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) para determinar si se admite un patrón o un grupo de patrones en el <xref:System.Windows.Automation.AutomationElement>. Sin embargo, resulta más eficaz intentar obtener el patrón de control y comprobar si hay una referencia `null` que comprobar las propiedades compatibles y recuperar el patrón de control, ya que se generan menos llamadas entre procesos.  
  
 En el siguiente ejemplo se muestra cómo obtener un patrón de control <xref:System.Windows.Automation.TextPattern> de un <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>
## <a name="retrieving-properties-on-control-patterns"></a>Recuperar propiedades en patrones de control  
 Para recuperar los valores de propiedad en los patrones de control, los clientes pueden llamar a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> o <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> y convertir el objeto devuelto al tipo apropiado. Para obtener [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] más información sobre las propiedades, vea Propiedades de automatización de la interfaz de usuario [para clientes](ui-automation-properties-for-clients.md).  
  
 Además `GetPropertyValue` de los métodos, los valores de propiedad se pueden recuperar [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] a través de los descriptores de acceso de Common Language Runtime (CLR) para tener acceso a las propiedades de un patrón.  
  
<a name="uiautomation_with_variable_patterns"></a>
## <a name="controls-with-variable-patterns"></a>Controles con patrones variables  
 Algunos tipos de controles admiten patrones diferentes en función de su estado o de la manera en la que se usan. Ejemplos de controles que pueden tener patrones variables son vistas de lista (miniaturas, mosaicos, iconos, lista, detalles), gráficos de Microsoft Excel (Pie, Línea, Barra, Valor de celda con una fórmula), área de documento de Microsoft Word (Normal, Diseño web, Esquema, Diseño de impresión, Imprimir Vista previa) y aspectos del Reproductor de Microsoft Windows Media.  
  
 Los controles que implementan tipos de controles personalizados pueden tener cualquier conjunto de patrones de control que sea necesario para representar su funcionalidad.  
  
## <a name="see-also"></a>Consulte también

- [Patrones de control de UI Automation](ui-automation-control-patterns.md)
- [Modelo de texto de UI Automation](ui-automation-text-pattern.md)
- [Invocación de un control mediante Automatización de la interfaz de usuario](invoke-a-control-using-ui-automation.md)
- [Obtener el estado de alternancia de una casilla mediante UI Automation](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [Asignación de patrones de controles para clientes de UI Automation](control-pattern-mapping-for-ui-automation-clients.md)
- [TextPattern Insertar muestra de texto](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [Ejemplo de búsqueda y selección de TextPattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FindText)
- [InvokePattern, ExpandCollapsePattern y TogglePattern Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
