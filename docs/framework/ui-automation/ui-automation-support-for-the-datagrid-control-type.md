---
title: Compatibilidad de la automatización de la interfaz de usuario para el tipo de control DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- Data Grid control type
- control types, Data Grid
- UI Automation, Data Grid control type
ms.assetid: a3db4a3f-feb5-4e5f-9b42-aae7fa816e8a
ms.openlocfilehash: 6302a1d3d27ba9a32242cac6232fe495e8e6b4b9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741248"
---
# <a name="ui-automation-support-for-the-datagrid-control-type"></a>Compatibilidad de la automatización de la interfaz de usuario para el tipo de control DataGrid
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
 En este tema se ofrece información sobre la compatibilidad de [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] con el tipo de control DataGrid. En [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], un tipo de control es un conjunto de condiciones que un control debe cumplir para poder usar la propiedad `ControlType` . En las condiciones se incluyen instrucciones específicas para la estructura de árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , los patrones de control y los valores de propiedad de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 El tipo de control DataGrid permite a un usuario trabajar fácilmente con elementos que contienen metadatos representados en columnas. Los controles de cuadrícula de datos tienen filas de elementos y columnas de información sobre esos elementos. Un control List View en Microsoft Vista Explorer es un ejemplo que admite el tipo de control DataGrid.  
  
 En las secciones siguientes se definen la estructura del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , las propiedades, los patrones de control y los eventos necesarios para el tipo de control DataGrid. Los requisitos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] se aplican a todos los controles de cuadrícula de datos, ya sea [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="required-ui-automation-tree-structure"></a>Estructura de árbol de Automatización de la interfaz de usuario necesaria  
 En la tabla siguiente se detallan la vista de control y la vista de contenido del árbol [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece a los controles de cuadrícula de datos y se describe lo que puede incluirse en cada vista. Para más información sobre el árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vea [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : vista de control|Árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : vista de contenido|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataGrid<br /><br /> <ul><li>Header (0, 1 o 2)<br /><br /> <ul><li>HeaderItem (número de columnas o filas)</li></ul></li><li>DataItem (0 o más; se puede estructurar en jerarquía)</li></ul>|DataGrid<br /><br /> -DataItem (0 o más; se puede estructurar en la jerarquía)|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Propiedades de Automatización de la interfaz de usuario necesarias  
 En la tabla siguiente se muestran las propiedades que tienen un valor o una definición que es especialmente relevante para los controles de cuadrícula de datos. Para obtener más información sobre las propiedades de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|La propiedad|{2&gt;Value&lt;2}|Notas|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vea las notas.|El valor de esta propiedad debe ser único en todos los controles de una aplicación.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vea las notas.|El rectángulo exterior que contiene el control completo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vea las notas.|Se admite si hay un rectángulo delimitador. Si no todos los puntos que se encuentran dentro del rectángulo delimitador son seleccionables, y realiza pruebas de aciertos especializadas, invalide y ofrezca un punto en el que hacer clic.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataGrid|Este valor es el mismo para todos los marcos de trabajo de la interfaz de usuario.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Verdadero|El valor de esta propiedad siempre debe ser True. Esto significa que el control de cuadrícula de datos siempre debe estar en la vista de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|Verdadero|El valor de esta propiedad siempre debe ser True. Esto significa que el control de cuadrícula de datos siempre debe estar en la vista de control del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vea las notas.|Si el control puede recibir el foco del teclado, debe admitir esta propiedad.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vea las notas.|Si hay una etiqueta de texto estático, esta propiedad debe exponer una referencia a ese control.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"cuadrícula de datos"|Cadena localizada que corresponde al tipo de control DataGrid.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vea las notas.|El control de cuadrícula de datos normalmente obtiene el valor de su propiedad `Name` de una etiqueta de texto estático. Si no hay una etiqueta de texto estático, un desarrollador de aplicaciones debe asignar un valor a la propiedad `Name` . El valor de la propiedad `Name` nunca debe ser el contenido textual del control de edición.|  
  
## <a name="required-ui-automation-control-patterns"></a>Patrones de control de Automatización de la interfaz de usuario necesarios  
 En la tabla siguiente se muestran los patrones de control de necesarios para que todos los controles de cuadrícula de datos los admitan. Para más información sobre los patrones de control, vea [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Patrón de control|Compatibilidad con|Notas|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Sí|El propio control de cuadrícula de datos siempre admite el patrón de control Grid porque los elementos que contiene incluyen metadatos que se presentan en una cuadrícula.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Depende|La capacidad de desplazar la cuadrícula de datos depende del contenido y de si las barras de desplazamiento están presentes.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Depende|La capacidad de seleccionar la cuadrícula de datos depende del contenido.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Sí|El control de cuadrícula de datos siempre tiene un encabezado dentro de su subárbol, por lo que se debe admitir el patrón de control Table.|  
  
 Los elementos de datos dentro de los contenedores de la cuadrícula de datos admitirán como mínimo:  
  
- El patrón de control Selection Item (si la cuadrícula de datos es seleccionable)  
  
- El patrón de control Scroll Item (si la cuadrícula de datos es desplazable)  
  
- El patrón de control Table Item  
  
- Table Item (patrón de control)  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventos de Automatización de la interfaz de usuario necesarios  
 En la siguiente tabla se muestran los eventos de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que deben admitir todos los controles de cuadrícula de datos. Para más información sobre eventos, vea [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Compatibilidad con|Notas|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Requerido|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Depende|Ninguno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Requerido|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty> .|Depende|Ninguno|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Depende|Si el control admite el patrón Scroll, debe admitir este evento.|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Depende|Si el control admite el patrón Scroll, debe admitir este evento.|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Depende|Si el control admite el patrón Scroll, debe admitir este evento.|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Depende|Si el control admite el patrón Scroll, debe admitir este evento.|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Depende|Si el control admite el patrón Scroll, debe admitir este evento.|  
|Evento cambiado por propiedad<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Depende|Si el control admite el patrón Scroll, debe admitir este evento.|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Requerido|Ninguno|  
  
## <a name="date-grid-control-type-example"></a>Ejemplo de tipo de control Date Grid  
 En la imagen siguiente se muestra un control List View que implementa el tipo de control DataGrid.  
  
 ![Gráfico de un control de vista de lista con dos elementos de datos](./media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 Las vistas de control y de contenido del árbol de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] que pertenece al control List View se muestran a continuación. Los patrones de control de cada elemento de automatización se muestran entre paréntesis.  
  
|Árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : vista de control|Árbol de[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] : vista de contenido|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|<ul><li>DataGrid (Table, Grid, Selection)</li><li>Header<br /><br /> <ul><li>HeaderItem "Name" (Invoke)</li><li>HeaderItem "Date Modified" (Invoke)</li><li>HeaderItem "Size" (Invoke)</li></ul></li><li>Grupo "Contoso" (TableItem, GridItem, SelectionItem, Table *, Grid\*)<br /><br /> <ul><li>DataItem "Accounts Receivable. doc" (SelectionItem, Invoke, TableItem\*, GridItem\*)</li><li>DataItem "Accounts Payable. doc" (SelectionItem, Invoke, TableItem\*, GridItem\*)</li></ul></li></ul>|<ul><li>DataGrid (Table, Grid, Selection)</li><li>Grupo "Contoso" (TableItem, GridItem, SelectionItem, Table *, Grid\*)<br /><br /> <ul><li>DataItem "Accounts Receivable. doc" (SelectionItem, Invoke, TableItem\*, GridItem\*)</li><li>DataItem "Accounts Payable. doc" (SelectionItem, Invoke, TableItem\*, GridItem\*)</li></ul></li></ul>|  
  
 \* el ejemplo anterior muestra un control DataGrid que contiene varios niveles de controles. El control Group ("Contoso") contiene dos controles DataItem ("Accounts Receivable.doc" y "Accounts Payable.doc"). Un par de controles DataGrid/GridItem es independiente de un par en otro nivel. Los controles DataItem de un elemento Group también se pueden exponer como un tipo de control ListItem, lo que permite que se presenten más claramente como objetos seleccionables, en lugar de como elementos de datos simples. En este ejemplo no se incluyen los subelementos de los elementos de datos agrupados.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.ControlType.DataGrid>
- [Información general sobre tipos de control de Automatización de la interfaz de usuario](ui-automation-control-types-overview.md)
- [Información general sobre la Automatización de la interfaz de usuario](ui-automation-overview.md)
