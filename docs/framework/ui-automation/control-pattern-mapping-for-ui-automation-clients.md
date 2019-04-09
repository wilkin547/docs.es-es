---
title: Asignación de patrones de controles para clientes de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 829df66f49d5df5f5c8cf8d2b6cfa74f0a2172dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101138"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Asignación de patrones de controles para clientes de UI Automation
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 En este tema se muestran los tipos de control y sus patrones de control asociados.  
  
 En la siguiente tabla se organizan los patrones de control en las siguientes categorías:  
  
-   Se admite. El control debe admitir este patrón de control.  
  
-   Compatibilidad condicional. El control puede admitir este patrón de control según el estado del control.  
  
-   No se admite. El control no admite este patrón de control; los controles personalizados pueden admitir este patrón de control.  
  
> [!NOTE]
>  Algunos controles tienen compatibilidad condicional con varios patrones de control, en función de la funcionalidad del control. Por ejemplo, el control de elemento de menú tiene compatibilidad condicional con el patrón de control <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> , en función de su función en el control de menú.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Patrones de controles de UI Automation para clientes  
  
|Tipo de control|Compatible|Compatibilidad condicional|No admitido|  
|------------------|---------------|-------------------------|-------------------|  
|Botón|Ninguna|Invoke, Toggle, Expand Collapse|Ninguna|  
|Calendario|Grid, Table|Selection, Scroll|Valor|  
|Casilla|Alternar|Ninguna|Ninguna|  
|Cuadro combinado|Expandir o contraer|Selection, Value|Scroll|  
|Data Grid|Cuadrícula|Scroll, Selection, Table|Ninguna|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|Ninguna|  
|Documento|Texto|Scroll, Value|Ninguna|  
|Editar|Ninguna|Text, Range Value, Value|Ninguna|  
|Agrupar|Ninguna|Expandir o contraer|Ninguna|  
|Encabezado|Ninguna|Transformación|Ninguna|  
|Header Item|Ninguna|Transform, Invoke|Ninguna|  
|Hipervínculo|Invocar|Valor|Ninguna|  
|Imagen|Ninguna|Grid Item, Table Item|Invoke, Selection Item|  
|Lista|Ninguna|Grid, Multiple View, Scroll, Selection|Tabla|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|Ninguna|  
|Menú|Ninguna|Ninguna|Ninguna|  
|Barra de menús|Ninguna|Expand Collapse, Dock, Transform|Ninguna|  
|Elemento de menú|Ninguna|Expand Collapse, Invoke, Selection Item, Toggle|Ninguna|  
|Panel|Ninguna|Dock Scroll, Transform|Ventana|  
|ProgressBar|Ninguna|Range Value, Value|Ninguna|  
|Radio Button|Selection Item|Ninguna|Alternar|  
|Scroll Bar|Ninguna|RangeValue|Scroll|  
|Separador|Ninguna|Ninguna|Ninguna|  
|Slider|Ninguna|Range Value, Selection, Value|Ninguna|  
|Spinner|Ninguna|Range Value, Selection, Value|Ninguna|  
|Botón de expansión|Invoke, Expand Collapse|Ninguna|Ninguna|  
|Barra de estado|Ninguna|Cuadrícula|Ninguna|  
|Tab|Selección|Scroll|Ninguna|  
|Tab Item|Selection Item|Ninguna|Invocar|  
|Tabla|Grid, Grid Item, Table, Table Item|Ninguna|Ninguna|  
|Texto|Ninguna|Grid Item, Table Item, Text|Valor|  
|Thumb|Transformación|Ninguna|Ninguna|  
|Barra de título|Ninguna|Ninguna|Ninguna|  
|Tool Bar|Ninguna|Dock, Expand Collapse, Transform|Ninguna|  
|Tool Tip|Ninguna|Text, Window|Ninguna|  
|Árbol|Ninguna|Scroll, Selection|Ninguna|  
|Tree Item|Expandir o contraer|Invoke, Scroll Item, Selection Item, Toggle|Ninguna|  
|Ventana|Transform, Window|Acoplar|Ninguna|  
  
> [!NOTE]
>  Si un tipo de control no muestra patrones de control compatibles enumerados pero tiene uno o más patrones de control que admitidos condicionalmente, se admitirá en todo momento uno de esos patrones de control condicionales.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre UI Automation](../../../docs/framework/ui-automation/ui-automation-overview.md)
