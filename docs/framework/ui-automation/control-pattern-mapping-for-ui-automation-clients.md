---
title: Asignación de patrones de controles para clientes de UI Automation
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 64c3dccac61ceb2934904c5d03fc96d961976d6b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932626"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Asignación de patrones de controles para clientes de UI Automation
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener la información más [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]reciente acerca [de, consulte API de automatización de Windows: Automatización](https://go.microsoft.com/fwlink/?LinkID=156746)de la interfaz de usuario.  
  
 En este tema se muestran los tipos de control y sus patrones de control asociados.  
  
 En la siguiente tabla se organizan los patrones de control en las siguientes categorías:  
  
- Se admite. El control debe admitir este patrón de control.  
  
- Compatibilidad condicional. El control puede admitir este patrón de control según el estado del control.  
  
- No compatible. El control no admite este patrón de control; los controles personalizados pueden admitir este patrón de control.  
  
> [!NOTE]
> Algunos controles tienen compatibilidad condicional con varios patrones de control, en función de la funcionalidad del control. Por ejemplo, el control de elemento de menú tiene compatibilidad condicional con el patrón de control <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> , en función de su función en el control de menú.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Patrones de controles de UI Automation para clientes  
  
|Tipo de control|Compatible|Compatibilidad condicional|No admitido|  
|------------------|---------------|-------------------------|-------------------|  
|Botón|None|Invoke, Toggle, Expand Collapse|None|  
|Calendario|Grid, Table|Selection, Scroll|Valor|  
|Casilla|Alternar|None|None|  
|Cuadro combinado|Expandir o contraer|Selection, Value|Scroll|  
|Data Grid|Cuadrícula|Scroll, Selection, Table|None|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|None|  
|Documento|Text|Scroll, Value|None|  
|Editar|None|Text, Range Value, Value|None|  
|Grupo|None|Expandir o contraer|None|  
|Encabezado|None|Transformación|None|  
|Header Item|None|Transform, Invoke|None|  
|Hipervínculo|Invocar|Valor|None|  
|Image|None|Grid Item, Table Item|Invoke, Selection Item|  
|Enumerar|None|Grid, Multiple View, Scroll, Selection|Tabla|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|None|  
|Menú|None|None|None|  
|Barra de menús|None|Expand Collapse, Dock, Transform|None|  
|Elemento de menú|None|Expand Collapse, Invoke, Selection Item, Toggle|None|  
|Panel|None|Dock Scroll, Transform|Ventana|  
|ProgressBar|None|Range Value, Value|None|  
|Radio Button|Selection Item|None|Alternar|  
|Scroll Bar|None|RangeValue|Scroll|  
|Separador|None|None|None|  
|Slider|Ninguna|Range Value, Selection, Value|None|  
|Spinner|None|Range Value, Selection, Value|None|  
|Botón de expansión|Invoke, Expand Collapse|None|None|  
|Barra de estado|None|Cuadrícula|None|  
|Tab|Número de selección|Scroll|None|  
|Tab Item|Selection Item|None|Invocar|  
|Tabla|Grid, Grid Item, Table, Table Item|None|None|  
|Text|None|Grid Item, Table Item, Text|Valor|  
|Thumb|Transformación|None|None|  
|Barra de título|None|None|None|  
|Tool Bar|None|Dock, Expand Collapse, Transform|None|  
|Tool Tip|None|Text, Window|None|  
|Árbol|None|Scroll, Selection|None|  
|Tree Item|Expandir o contraer|Invoke, Scroll Item, Selection Item, Toggle|None|  
|Ventana|Transform, Window|Acoplar|None|  
  
> [!NOTE]
> Si un tipo de control no muestra patrones de control compatibles enumerados pero tiene uno o más patrones de control que admitidos condicionalmente, se admitirá en todo momento uno de esos patrones de control condicionales.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la Automatización de la interfaz de usuario](../../../docs/framework/ui-automation/ui-automation-overview.md)
