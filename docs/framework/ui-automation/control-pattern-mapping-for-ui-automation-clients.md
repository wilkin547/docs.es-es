---
title: Asignación de patrones de controles para clientes de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 689e649343c93d0670c6870098a09f61097f4fb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180228"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Asignación de patrones de controles para clientes de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se muestran los tipos de control y sus patrones de control asociados.  
  
 En la siguiente tabla se organizan los patrones de control en las siguientes categorías:  
  
- Compatible. El control debe admitir este patrón de control.  
  
- Compatibilidad condicional. El control puede admitir este patrón de control según el estado del control.  
  
- No compatible. El control no admite este patrón de control; los controles personalizados pueden admitir este patrón de control.  
  
> [!NOTE]
> Algunos controles tienen compatibilidad condicional con varios patrones de control, en función de la funcionalidad del control. Por ejemplo, el control de elemento de menú tiene compatibilidad condicional con el patrón de control <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> , en función de su función en el control de menú.  
  
<a name="control_mapping_clients"></a>
## <a name="ui-automation-control-patterns-for-clients"></a>Patrones de controles de UI Automation para clientes  
  
|Tipo de control|Compatible|Compatibilidad condicional|No compatible|  
|------------------|---------------|-------------------------|-------------------|  
|Botón|None|Invoke, Toggle, Expand Collapse|None|  
|Calendario|Grid, Table|Selection, Scroll|Value|  
|Casilla|Alternar|None|None|  
|Cuadro combinado|Expandir o contraer|Selection, Value|Scroll|  
|Cuadrícula de datos|Cuadrícula|Scroll, Selection, Table|None|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|None|  
|Documento|Texto|Scroll, Value|None|  
|Editar|None|Text, Range Value, Value|None|  
|Grupo|None|Expandir o contraer|None|  
|Encabezado|None|Transformación|None|  
|Header Item|None|Transform, Invoke|None|  
|Hyperlink|Invocar|Value|None|  
|Imagen|None|Grid Item, Table Item|Invoke, Selection Item|  
|List|None|Grid, Multiple View, Scroll, Selection|Tabla|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|None|  
|Menú|None|None|None|  
|Barra de menús|None|Expand Collapse, Dock, Transform|None|  
|Elemento de menú|None|Expand Collapse, Invoke, Selection Item, Toggle|None|  
|Panel|None|Dock Scroll, Transform|Periodo|  
|ProgressBar|None|Range Value, Value|None|  
|Radio Button|Selection Item|None|Alternar|  
|Scroll Bar|None|RangeValue|Scroll|  
|Separador|None|None|None|  
|Control deslizante|None|Range Value, Selection, Value|None|  
|Spinner|None|Range Value, Selection, Value|None|  
|Botón de expansión|Invoke, Expand Collapse|None|None|  
|Barra de estado|None|Cuadrícula|None|  
|Pestaña|Número de selección|Scroll|None|  
|Tab Item|Selection Item|None|Invocar|  
|Tabla|Grid, Grid Item, Table, Table Item|None|None|  
|Texto|None|Grid Item, Table Item, Text|Value|  
|Thumb|Transformación|None|None|  
|Barra de título|None|None|None|  
|Tool Bar|None|Dock, Expand Collapse, Transform|None|  
|Tool Tip|None|Text, Window|None|  
|Árbol|None|Scroll, Selection|None|  
|Tree Item|Expandir o contraer|Invoke, Scroll Item, Selection Item, Toggle|None|  
|Periodo|Transform, Window|Acoplar|None|  
  
> [!NOTE]
> Si un tipo de control no muestra patrones de control compatibles enumerados pero tiene uno o más patrones de control que admitidos condicionalmente, se admitirá en todo momento uno de esos patrones de control condicionales.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre UI Automation](ui-automation-overview.md)
