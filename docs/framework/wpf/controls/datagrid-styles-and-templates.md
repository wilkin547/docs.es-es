---
title: "Estilos y plantillas de DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], DataGrid"
  - "DataGrid [WPF], estilos y plantillas"
  - "partes [WPF], DataGrid"
  - "estados [WPF], DataGrid"
  - "estilos [WPF], DataGrid"
  - "plantillas [WPF], DataGrid"
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Estilos y plantillas de DataGrid
En este tema, se describen los estilos y plantillas del control <xref:System.Windows.Controls.DataGrid>.  Puede modificar la plantilla <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar un aspecto único al control.  Para obtener más información, vea [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Elementos de DataGrid  
 En la siguiente tabla, se muestran los elementos con nombre del control <xref:System.Windows.Controls.DataGrid>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Fila que contiene los encabezados de columna.|  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.DataGrid>, la plantilla puede contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>.  \(El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.DataGrid>; el <xref:System.Windows.Controls.ScrollViewer> permite el desplazamiento dentro del control\).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe asignar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
 La plantilla predeterminada para <xref:System.Windows.Controls.DataGrid> contiene un control <xref:System.Windows.Controls.ScrollViewer>.  Para obtener más información sobre los elementos definidos por <xref:System.Windows.Controls.ScrollViewer>, vea [Estilos y plantillas de ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md).  
  
## Estados de DataGrid  
 En la tabla siguiente se muestran los estados visuales del control <xref:System.Windows.Controls.DataGrid>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|Disabled|CommonStates|El control está deshabilitado.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido ni tiene el foco.|  
|Valid|ValidationStates|El control es válido.|  
  
## Elementos de DataGridCell  
 El elemento <xref:System.Windows.Controls.DataGridCell> no tiene ningún elemento con nombre.  
  
## Estados de DataGridCell  
 En la tabla siguiente se muestran los estados visuales del elemento <xref:System.Windows.Controls.DataGridCell>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre la celda.|  
|Focused|FocusStates|La celda tiene el foco.|  
|Unfocused|FocusStates|La celda no tiene el foco.|  
|Actual|CurrentStates|La celda es la celda actual.|  
|Estándar|CurrentStates|La celda no es la celda actual.|  
|Display|InteractionStates|La celda está en modo de presentación.|  
|Edición|InteractionStates|La celda está en modo de edición.|  
|Seleccionado|SelectionStates|La celda está seleccionada.|  
|No seleccionado|SelectionStates|La celda no está seleccionada.|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida ni tiene el foco.|  
|Valid|ValidationStates|La celda es válida.|  
  
## Elementos de DataGridRow  
 El elemento <xref:System.Windows.Controls.DataGridRow> no tiene ningún elemento con nombre.  
  
## Estados de DataGridRow  
 En la tabla siguiente se muestran los estados visuales del elemento <xref:System.Windows.Controls.DataGridRow>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre la fila.|  
|MouseOver\_Editing|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está en modo de edición.|  
|MouseOver\_Selected|CommonStates|El puntero del mouse está colocado sobre la fila y la fila está seleccionada.|  
|MouseOver\_Unfocused\_Editing|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver\_Unfocused\_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está seleccionada y no tiene el foco.|  
|Normal\_AlternatingRow|CommonStates|La fila es una fila alterna.|  
|Normal\_Editing|CommonStates|La fila está en modo de edición.|  
|Normal\_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused\_Editing|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused\_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido ni tiene el foco.|  
|Valid|ValidationStates|El control es válido.|  
  
## Elementos de DataGridRowHeader  
 En la siguiente tabla se muestran los elementos con nombre del elemento <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se utiliza para cambiar el tamaño del encabezado de fila de la parte superior.|  
|PART\_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se utiliza para cambiar el tamaño del encabezado de fila de la parte inferior.|  
  
## Estados de DataGridRowHeader  
 En la tabla siguiente se muestran los estados visuales del elemento <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está colocado sobre la fila.|  
|MouseOver\_CurrentRow|CommonStates|El puntero del mouse se coloca sobre la fila y la fila es la fila actual.|  
|MouseOver\_CurrentRow\_Selected|CommonStates|El puntero del mouse está colocado sobre la fila y la fila es la actual y está seleccionada.|  
|MouseOver\_EditingRow|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está en modo de edición.|  
|MouseOver\_Selected|CommonStates|El puntero del mouse está colocado sobre la fila y la fila está seleccionada.|  
|MouseOver\_Unfocused\_CurrentRow\_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila es la actual y está seleccionada, y no tiene el foco.|  
|MouseOver\_Unfocused\_EditingRow|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver\_Unfocused\_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está seleccionada y no tiene el foco.|  
|Normal\_CurrentRow|CommonStates|La fila es la fila actual.|  
|Normal\_CurrentRow\_Selected|CommonStates|La fila es la fila actual y está seleccionada.|  
|Normal\_EditingRow|CommonStates|La fila está en modo de edición.|  
|Normal\_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused\_CurrentRow\_Selected|CommonStates|La fila es la fila actual, está seleccionada y no tiene el foco.|  
|Unfocused\_EditingRow|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused\_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido ni tiene el foco.|  
|Valid|ValidationStates|El control es válido.|  
  
## Elementos de DataGridColumnHeadersPresenter  
 En la siguiente tabla se muestran los elementos con nombre del elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Marcador de posición para encabezados de columna.|  
  
## Estados de DataGridColumnHeadersPresenter  
 En la tabla siguiente se muestran los estados visuales del elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida ni tiene el foco.|  
|Valid|ValidationStates|La celda es válida.|  
  
## Elementos de DataGridColumnHeader  
 En la siguiente tabla se muestran los elementos con nombre del elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
||||  
|-|-|-|  
|Parte|Tipo|Descripción|  
|PART\_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se utiliza para cambiar el tamaño del encabezado de columna de la izquierda.|  
|PART\_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se utiliza para cambiar el tamaño del encabezado de columna de la derecha.|  
  
## Estados de DataGridColumnHeader  
 En la tabla siguiente se muestran los estados visuales del elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
||||  
|-|-|-|  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|Normal|CommonStates|Estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse está situado sobre el control.|  
|Pressed|CommonStates|El control está presionado.|  
|SortAscending|SortStates|La columna está ordenada de manera ascendente.|  
|SortDescending|SortStates|La columna está ordenada de manera descendente.|  
|Unsorted|SortStates|La columna no está ordenada.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido ni tiene el foco.|  
|Valid|ValidationStates|El control es válido.|  
  
## Ejemplo de ControlTemplate de DataGrid  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.DataGrid> y sus tipos asociados.  
  
 [!code-xml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 El ejemplo anterior utiliza uno o más de los siguientes recursos.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para obtener el ejemplo completo, vea          [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) .  
  
## Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Personalizar la apariencia de un control existente creando una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)