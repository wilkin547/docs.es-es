---
title: Implementación del patrón de control Scroll de UI Automation
description: Revise las directrices y convenciones para implementar el patrón de control scroll en la automatización de la interfaz de usuario. Consulte los miembros necesarios para la interfaz IScrollProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll control pattern
- control patterns, Scroll
- Scroll control pattern
ms.assetid: 73d64242-6cbb-424c-92dd-dc69530b7899
ms.openlocfilehash: 4069772530d8b4db817aa1b7a9be86a3ee83881e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239268"
---
# <a name="implementing-the-ui-automation-scroll-control-pattern"></a>Implementación del patrón de control Scroll de UI Automation

> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se presentan las directrices y convenciones para implementar <xref:System.Windows.Automation.Provider.IScrollProvider>, incluida la información sobre eventos y propiedades. Al final del tema se ofrecen vínculos a referencias adicionales.  
  
 El patrón de control <xref:System.Windows.Automation.ScrollPattern> se usa para admitir un control que actúe como contenedor desplazable para una colección de objetos secundarios. No se requiere el control para el uso de barras de desplazamiento para admitir la funcionalidad de desplazamiento, aunque lo hace habitualmente.  
  
 ![Control Scroll sin barras de desplazamiento.](./media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")  
Ejemplo de un control de desplazamiento que no use barras de desplazamiento  
  
 Para obtener ejemplos de controles que implementan este control, vea [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Directrices y convenciones de implementación  

 Al implementar el patrón de control Scroll, tenga en cuenta las siguientes directrices y convenciones:  
  
- Los elementos secundarios de este control deben implementar <xref:System.Windows.Automation.Provider.IScrollItemProvider>.  
  
- Las barras de desplazamiento de un control de contenedor no admiten el patrón de control <xref:System.Windows.Automation.ScrollPattern> . Deben admitir el patrón de control <xref:System.Windows.Automation.RangeValuePattern> en su lugar.  
  
- Cuando el desplazamiento se mide en porcentajes, todos los valores o cantidades relacionadas con la graduación del desplazamiento deben normalizarse a un intervalo de 0 a 100.  
  
- Las propiedades<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> y <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> son independientes de la propiedad <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.  
  
- Si <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` , <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> debe establecerse en el 100 % y <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> debe establecerse en <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. De igual modo, si <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` , <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> debe establecerse en el 100 por ciento y <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> debe establecerse en <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. Esto permite que un cliente de la automatización de la interfaz de usuario use estos valores de propiedad del método <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> a la vez que se evita una [condición de carrera](https://support.microsoft.com/default.aspx?scid=kb;en-us;317723) si se activa una dirección que al cliente no le interesa para desplazamiento.  
  
- <xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> es específica de la configuración regional. La configuración de HorizontalScrollPercent = 100,0 debe establecer la ubicación de desplazamiento del control en el equivalente de su posición que se encuentra situada más a la derecha para idiomas como el inglés que se leen de izquierda a derecha. Otra alternativa, para idiomas como el árabe que se leen de derecha a izquierda, la configuración de HorizontalScrollPercent = 100,0 debe establecer la ubicación de desplazamiento a la posición que se encuentra más a la izquierda.  
  
<a name="Required_Members_for_IScrollProvider"></a>

## <a name="required-members-for-iscrollprovider"></a>Miembros requeridos para IScrollProvider  

 Para implementar <xref:System.Windows.Automation.Provider.IScrollProvider>, se requieren las siguientes propiedades y métodos.  
  
|Miembro requerido|Tipo de miembro|Notas|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalScrollPercent%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalViewSize%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalViewSize%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontallyScrollable%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticallyScrollable%2A>|Propiedad|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>|Método|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>|Método|None|  
  
 Este patrón de control no tiene eventos asociados.  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a>Excepciones  

 Los proveedores deben producir las siguientes excepciones.  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> genera esta excepción si un control admite valores <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> exclusivamente para el desplazamiento horizontal o vertical, pero se pasa un valor <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> .|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> genera esta excepción cuando se pasa un valor que no se puede convertir a un tipo double.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> genera esta excepción cuando se pasa un valor superior a 100 o menor de 0 (excepto -1, que equivale a <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>).|  
|<xref:System.InvalidOperationException>|Tanto <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> como <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> generan esta excepción cuando se intenta un desplazamiento en una dirección no admitida.|  
  
## <a name="see-also"></a>Vea también

- [Información general acerca de los patrones de control de UI Automation](ui-automation-control-patterns-overview.md)
- [Patrones de control compatibles en un proveedor de UI Automation](support-control-patterns-in-a-ui-automation-provider.md)
- [Patrones de controles de UI Automation para clientes](ui-automation-control-patterns-for-clients.md)
- [Información general sobre el árbol de la UI Automation](ui-automation-tree-overview.md)
- [Utilizar el almacenamiento en caché en la UI Automation](use-caching-in-ui-automation.md)
