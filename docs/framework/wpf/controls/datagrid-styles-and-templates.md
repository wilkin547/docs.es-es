---
title: Estilos y plantillas de DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: 582179d8469cabc3551e1bed53c87e045f26e7cf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366080"
---
# <a name="datagrid-styles-and-templates"></a>Estilos y plantillas de DataGrid
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.DataGrid> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datagrid-parts"></a>Elementos de DataGrid  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.DataGrid> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|La fila que contiene los encabezados de columna.|  
  
 Cuando creas un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.DataGrid>, la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento en el <xref:System.Windows.Controls.DataGrid>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> el nombre, `ItemsPresenter`.  
  
 La plantilla predeterminada para el <xref:System.Windows.Controls.DataGrid> contiene un <xref:System.Windows.Controls.ScrollViewer> control. Para obtener más información acerca de los elementos definidos por el <xref:System.Windows.Controls.ScrollViewer>, consulte [ScrollViewer Styles and Templates](scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Estados del control DataGrid  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.DataGrid> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridcell-parts"></a>DataGridCell partes  
 El <xref:System.Windows.Controls.DataGridCell> elemento no tiene elementos con nombre.  
  
## <a name="datagridcell-states"></a>Estados de DataGridCell  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.DataGridCell> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|Se coloca el puntero del mouse sobre la celda.|  
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
  
## <a name="datagridrow-parts"></a>DataGridRow partes  
 El <xref:System.Windows.Controls.DataGridRow> elemento no tiene elementos con nombre.  
  
## <a name="datagridrow-states"></a>Estados de DataGridRow  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.DataGridRow> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|Se coloca el puntero del mouse sobre la fila.|  
|MouseOver_Editing|CommonStates|Se coloca el puntero del mouse sobre la fila y la fila está en modo de edición.|  
|MouseOver_Selected|CommonStates|Se coloca el puntero del mouse sobre la fila y la fila está seleccionada.|  
|MouseOver_Unfocused_Editing|CommonStates|Se coloca el puntero del mouse sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver_Unfocused_Selected|CommonStates|Se coloca el puntero del mouse sobre la fila, la fila está seleccionada y no tiene el foco.|  
|Normal_AlternatingRow|CommonStates|La fila es una fila alterna.|  
|Normal_Editing|CommonStates|La fila está en modo de edición.|  
|Normal_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused_Editing|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridrowheader-parts"></a>DataGridRowHeader partes  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de fila en la parte superior.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de fila en la parte inferior.|  
  
## <a name="datagridrowheader-states"></a>Estados de DataGridRowHeader  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DataGridRowHeader> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|Se coloca el puntero del mouse sobre la fila.|  
|MouseOver_CurrentRow|CommonStates|Se coloca el puntero del mouse sobre la fila y la fila es la fila actual.|  
|MouseOver_CurrentRow_Selected|CommonStates|Se coloca el puntero del mouse sobre la fila y la fila está seleccionado y actual.|  
|MouseOver_EditingRow|CommonStates|Se coloca el puntero del mouse sobre la fila y la fila está en modo de edición.|  
|MouseOver_Selected|CommonStates|Se coloca el puntero del mouse sobre la fila y la fila está seleccionada.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|Se coloca el puntero del mouse sobre la fila, la fila está actualizada y seleccionado y no tiene el foco.|  
|MouseOver_Unfocused_EditingRow|CommonStates|Se coloca el puntero del mouse sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver_Unfocused_Selected|CommonStates|Se coloca el puntero del mouse sobre la fila, la fila está seleccionada y no tiene el foco.|  
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
  
## <a name="datagridcolumnheaderspresenter-parts"></a>DataGridColumnHeadersPresenter partes  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|El marcador de posición para los encabezados de columna.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Estados de DataGridColumnHeadersPresenter  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> elemento.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida y no tiene el foco.|  
|Válido|ValidationStates|La celda es válida.|  
  
## <a name="datagridcolumnheader-parts"></a>DataGridColumnHeader partes  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de columna de la izquierda.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|El elemento que se usa para cambiar el tamaño del encabezado de columna de la derecha.|  
  
## <a name="datagridcolumnheader-states"></a>Estados de DataGridColumnHeader  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> elemento.  
  
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
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.DataGrid> control y sus tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
