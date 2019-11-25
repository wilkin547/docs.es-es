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
ms.openlocfilehash: 066e8c9ce1112399be8128d0821498f0d56a3dc3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283801"
---
# <a name="datagrid-styles-and-templates"></a>Estilos y plantillas de DataGrid
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.DataGrid>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="datagrid-parts"></a>Elementos DataGrid  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.DataGrid>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Fila que contiene los encabezados de columna.|  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.DataGrid>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.DataGrid>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
 La plantilla predeterminada para el <xref:System.Windows.Controls.DataGrid> contiene un control <xref:System.Windows.Controls.ScrollViewer>. Para obtener más información sobre las partes definidas por el <xref:System.Windows.Controls.ScrollViewer>, vea [estilos y plantillas de ScrollViewer](scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>Estados de DataGrid  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.DataGrid>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|Deshabilitado|CommonStates|El control está deshabilitado.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridcell-parts"></a>Elementos DataGridCell  
 El elemento <xref:System.Windows.Controls.DataGridCell> no tiene ninguna parte con nombre.  
  
## <a name="datagridcell-states"></a>Estados de DataGridCell  
 En la tabla siguiente se enumeran los Estados visuales del elemento <xref:System.Windows.Controls.DataGridCell>.  
  
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
|No seleccionado|SelectionStates|La celda no está seleccionada.|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida y no tiene el foco.|  
|Válido|ValidationStates|La celda es válida.|  
  
## <a name="datagridrow-parts"></a>Elementos DataGridRow  
 El elemento <xref:System.Windows.Controls.DataGridRow> no tiene ninguna parte con nombre.  
  
## <a name="datagridrow-states"></a>Estados de DataGridRow  
 En la tabla siguiente se enumeran los Estados visuales del elemento <xref:System.Windows.Controls.DataGridRow>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre la fila.|  
|MouseOver_Editing|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está en modo de edición.|  
|MouseOver_Selected|CommonStates|El puntero del mouse se coloca sobre la fila y se selecciona la fila.|  
|MouseOver_Unfocused_Editing|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver_Unfocused_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, se selecciona la fila y no tiene el foco.|  
|Normal_AlternatingRow|CommonStates|La fila es una fila alternativa.|  
|Normal_Editing|CommonStates|La fila está en modo de edición.|  
|Normal_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused_Editing|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridrowheader-parts"></a>Elementos DataGridRowHeader  
 En la tabla siguiente se enumeran las partes con nombre para el elemento <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se usa para cambiar el tamaño del encabezado de fila de la parte superior.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se usa para cambiar el tamaño del encabezado de fila de la parte inferior.|  
  
## <a name="datagridrowheader-states"></a>Estados de DataGridRowHeader  
 En la tabla siguiente se enumeran los Estados visuales del elemento <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre la fila.|  
|MouseOver_CurrentRow|CommonStates|El puntero del mouse se coloca sobre la fila y la fila es la fila actual.|  
|MouseOver_CurrentRow_Selected|CommonStates|El puntero del mouse se coloca sobre la fila y la fila es actual y está seleccionada.|  
|MouseOver_EditingRow|CommonStates|El puntero del mouse se coloca sobre la fila y la fila está en modo de edición.|  
|MouseOver_Selected|CommonStates|El puntero del mouse se coloca sobre la fila y se selecciona la fila.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, la fila es actual y está seleccionada, y no tiene el foco.|  
|MouseOver_Unfocused_EditingRow|CommonStates|El puntero del mouse se coloca sobre la fila, la fila está en modo de edición y no tiene el foco.|  
|MouseOver_Unfocused_Selected|CommonStates|El puntero del mouse se coloca sobre la fila, se selecciona la fila y no tiene el foco.|  
|Normal_CurrentRow|CommonStates|La fila es la fila actual.|  
|Normal_CurrentRow_Selected|CommonStates|La fila es la fila actual y está seleccionada.|  
|Normal_EditingRow|CommonStates|La fila está en modo de edición.|  
|Normal_Selected|CommonStates|La fila está seleccionada.|  
|Unfocused_CurrentRow_Selected|CommonStates|La fila es la fila actual, está seleccionada y no tiene el foco.|  
|Unfocused_EditingRow|CommonStates|La fila está en modo de edición y no tiene el foco.|  
|Unfocused_Selected|CommonStates|La fila está seleccionada y no tiene el foco.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>Elementos DataGridColumnHeadersPresenter  
 En la tabla siguiente se enumeran las partes con nombre para el elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Marcador de posición para los encabezados de columna.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>Estados de DataGridColumnHeadersPresenter  
 En la tabla siguiente se enumeran los Estados visuales del elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|InvalidFocused|ValidationStates|La celda no es válida y tiene el foco.|  
|InvalidUnfocused|ValidationStates|La celda no es válida y no tiene el foco.|  
|Válido|ValidationStates|La celda es válida.|  
  
## <a name="datagridcolumnheader-parts"></a>Elementos DataGridColumnHeader  
 En la tabla siguiente se enumeran las partes con nombre para el elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se usa para cambiar el tamaño del encabezado de columna de la izquierda.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Elemento que se usa para cambiar el tamaño del encabezado de columna de la derecha.|  
  
## <a name="datagridcolumnheader-states"></a>Estados de DataGridColumnHeader  
 En la tabla siguiente se enumeran los Estados visuales del elemento <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el control.|  
|Presionado|CommonStates|El control está presionado.|  
|SortAscending|SortStates|La columna se ordena en orden ascendente.|  
|SortDescending|SortStates|La columna se ordena en orden descendente.|  
|Sin ordenar|SortStates|La columna no está ordenada.|  
|InvalidFocused|ValidationStates|El control no es válido y tiene el foco.|  
|InvalidUnfocused|ValidationStates|El control no es válido y no tiene el foco.|  
|Válido|ValidationStates|El control es válido.|  
  
## <a name="datagrid-controltemplate-example"></a>Ejemplo de ControlTemplate de DataGrid  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.DataGrid> y sus tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
