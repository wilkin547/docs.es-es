---
title: Asignación de patrones de controles para clientes de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 48298cb8d89958c701d7150aeb497e82d565bde1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433859"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Asignación de patrones de controles para clientes de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se muestran los tipos de control y sus patrones de control asociados.  
  
 En la siguiente tabla se organizan los patrones de control en las siguientes categorías:  
  
- Se admite. El control debe admitir este patrón de control.  
  
- Compatibilidad condicional. El control puede admitir este patrón de control según el estado del control.  
  
- No se admite. El control no admite este patrón de control; los controles personalizados pueden admitir este patrón de control.  
  
> [!NOTE]
> Algunos controles tienen compatibilidad condicional con varios patrones de control, en función de la funcionalidad del control. Por ejemplo, el control de elemento de menú tiene compatibilidad condicional con el patrón de control <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> , en función de su función en el control de menú.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Patrones de controles de UI Automation para clientes  
  
|Tipo de control|Compatible|Compatibilidad condicional|No admitido|  
|------------------|---------------|-------------------------|-------------------|  
|Botón|Ninguno|Invoke, Toggle, Expand Collapse|Ninguno|  
|Calendario|Grid, Table|Selection, Scroll|Valor|  
|Casilla|Alternar|Ninguno|Ninguno|  
|Cuadro combinado|Expandir o contraer|Selection, Value|Scroll|  
|Data Grid|Cuadrícula|Scroll, Selection, Table|Ninguno|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|Ninguno|  
|Documento|Text|Scroll, Value|Ninguno|  
|Editar|Ninguno|Text, Range Value, Value|Ninguno|  
|Agrupar|Ninguno|Expandir o contraer|Ninguno|  
|Header|Ninguno|Transform|Ninguno|  
|Header Item|Ninguno|Transform, Invoke|Ninguno|  
|Hipervínculo|Invocar|Valor|Ninguno|  
|Imagen|Ninguno|Grid Item, Table Item|Invoke, Selection Item|  
|Lista|Ninguno|Grid, Multiple View, Scroll, Selection|Table|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|Ninguno|  
|Menú|Ninguno|Ninguno|Ninguno|  
|Barra de menús|Ninguno|Expand Collapse, Dock, Transform|Ninguno|  
|Elemento de menú|Ninguno|Expand Collapse, Invoke, Selection Item, Toggle|Ninguno|  
|Panel|Ninguno|Dock Scroll, Transform|Ventana|  
|ProgressBar|Ninguno|Range Value, Value|Ninguno|  
|Radio Button|Selection Item|Ninguno|Alternar|  
|Scroll Bar|Ninguno|RangeValue|Scroll|  
|Separador|Ninguno|Ninguno|Ninguno|  
|Slider|Ninguno|Range Value, Selection, Value|Ninguno|  
|Spinner|Ninguno|Range Value, Selection, Value|Ninguno|  
|Botón de expansión|Invoke, Expand Collapse|Ninguno|Ninguno|  
|Barra de estado|Ninguno|Cuadrícula|Ninguno|  
|Tab|Selección|Scroll|Ninguno|  
|Tab Item|Selection Item|Ninguno|Invocar|  
|Table|Grid, Grid Item, Table, Table Item|Ninguno|Ninguno|  
|Text|Ninguno|Grid Item, Table Item, Text|Valor|  
|Thumb|Transform|Ninguno|Ninguno|  
|Barra de título|Ninguno|Ninguno|Ninguno|  
|Tool Bar|Ninguno|Dock, Expand Collapse, Transform|Ninguno|  
|Tool Tip|Ninguno|Text, Window|Ninguno|  
|Árbol|Ninguno|Scroll, Selection|Ninguno|  
|Tree Item|Expandir o contraer|Invoke, Scroll Item, Selection Item, Toggle|Ninguno|  
|Ventana|Transform, Window|Acoplar|Ninguno|  
  
> [!NOTE]
> Si un tipo de control no muestra patrones de control compatibles enumerados pero tiene uno o más patrones de control que admitidos condicionalmente, se admitirá en todo momento uno de esos patrones de control condicionales.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
