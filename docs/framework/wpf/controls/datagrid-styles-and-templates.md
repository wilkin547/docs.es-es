---
title: Estilos y plantillas de DataGrid
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b2dd7e47454cdfa806ce025d905073468f70f7cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="datagrid-styles-and-templates"></a>Estilos y plantillas de DataGrid
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.DataGrid> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).  
  
## <a name="datagrid-parts"></a>Partes de DataGrid  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.DataGrid> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|La fila que contiene los encabezados de columna.|  
  
 Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.DataGrid>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.DataGrid>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
 La plantilla predeterminada para la <xref:System.Windows.Controls.DataGrid> contiene un <xref:System.Windows.Controls.ScrollViewer> control. Para obtener más información sobre los elementos definidos por el <xref:System.Windows.Controls.ScrollViewer>, consulte [ScrollViewer estilos y plantillas](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Estados de DataGrid  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.DataGrid> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridcell-parts"></a>Partes de DataGridCell  
 El <xref:System.Windows.Controls.DataGridCell> elemento no tiene los elementos con nombre.  
  
## <a name="datagridcell-states"></a>Estados de DataGridCell  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.DataGridCell> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre la celda.|  
|Con foco|FocusStates|La celda tiene el foco.|  
|Sin foco|FocusStates|La celda no tiene el foco|  
|Current|CurrentStates|La celda es la celda actual.|  
|Estándar|CurrentStates|La celda no es la celda actual.|  
|Pantalla|InteractionStates|La celda está en modo de presentación.|  
|Editar|InteractionStates|La celda está en modo de edición.|  
|Seleccionado|SelectionStates|La celda está seleccionada.|  
|No seleccionado|SelectionStates|No se selecciona la celda.|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida y no tiene el foco.|  
|Válido|ValidationStates|La celda es válida.|  
  
## <a name="datagridrow-parts"></a>Partes de DataGridRow  
 El <xref:System.Windows.Controls.DataGridRow> elemento no tiene los elementos con nombre.  
  
## <a name="datagridrow-states"></a>Estados de DataGridRow  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.DataGridRow> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre la fila.|  
|MouseOver_Editing|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está en modo de edición.|  
|MouseOver_Selected|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está seleccionada.|  
|MouseOver_Unfocused_Editing|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver_Unfocused_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está seleccionada y no tiene el foco.|  
|Normal_AlternatingRow|CommonStates|La fila es una fila alterno.|  
|Normal_Editing|CommonStates|La fila está en modo de edición.|  
|Normal_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused_Editing|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridrowheader-parts"></a>Partes de DataGridRowHeader  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de fila de la parte superior.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de fila de la parte inferior.|  
  
## <a name="datagridrowheader-states"></a>Estados de DataGridRowHeader  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre la fila.|  
|MouseOver_CurrentRow|CommonStates|El puntero del mouse se coloca sobre la fila y la fila es la fila actual.|  
|MouseOver_CurrentRow_Selected|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está actualizada y seleccionado.|  
|MouseOver_EditingRow|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está en modo de edición.|  
|MouseOver_Selected|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está seleccionada.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila es actual y está seleccionada y no tiene el foco.|  
|MouseOver_Unfocused_EditingRow|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver_Unfocused_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está seleccionada y no tiene el foco.|  
|Normal_CurrentRow|CommonStates|La fila es la fila actual.|  
|Normal_CurrentRow_Selected|CommonStates|La fila es la fila actual y se selecciona.|  
|Normal_EditingRow|CommonStates|La fila está en modo de edición.|  
|Normal_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused_CurrentRow_Selected|CommonStates|La fila es la fila actual, está seleccionada y no tiene el foco.|  
|Unfocused_EditingRow|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>Partes de DataGridColumnHeadersPresenter  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|El marcador de posición para los encabezados de columna.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Estados de DataGridColumnHeadersPresenter  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida y no tiene el foco.|  
|Válido|ValidationStates|La celda es válida.|  
  
## <a name="datagridcolumnheader-parts"></a>Partes de DataGridColumnHeader  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de columna de la izquierda.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de columna de la derecha.|  
  
## <a name="datagridcolumnheader-states"></a>Estados de DataGridColumnHeader  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|  
|Presionado|CommonStates|El control está presionado.|  
|SortAscending|SortStates|La columna está ordenada en orden ascendente.|  
|SortDescending|SortStates|La columna está ordenada en orden descendente.|  
|Sin ordenar|SortStates|La columna no está ordenada.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagrid-controltemplate-example"></a>Ejemplo de ControlTemplate de DataGrid  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.DataGrid> control y sus tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
