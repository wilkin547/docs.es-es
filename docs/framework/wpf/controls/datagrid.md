---
title: DataGrid
description: Obtenga información sobre cómo el control DataGrid le permite mostrar y editar datos de distintos orígenes, como una base de datos, una consulta LINQ o cualquier otro origen de datos enlazable.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: 3db49c12fcb363ef7f99e5c69beae09ab05addcf
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168312"
---
# <a name="datagrid"></a>DataGrid
El <xref:System.Windows.Controls.DataGrid> control permite mostrar y editar datos de muchos orígenes diferentes, como una base de datos SQL, una consulta LINQ o cualquier otro origen de datos enlazable. Para obtener más información, vea [información general sobre orígenes de enlace](../data/binding-sources-overview.md).  
  
 Las columnas pueden mostrar texto, controles, como <xref:System.Windows.Controls.ComboBox> , o cualquier otro contenido de WPF, como imágenes, botones o cualquier contenido incluido en una plantilla. Puede utilizar un <xref:System.Windows.Controls.DataGridTemplateColumn> para mostrar los datos definidos en una plantilla. En la tabla siguiente se enumeran los tipos de columna que se proporcionan de forma predeterminada.  
  
|Tipo de columna generado|Tipo de datos|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>puede personalizarse en apariencia, como la fuente, el color y el tamaño de la celda. <xref:System.Windows.Controls.DataGrid>admite toda la funcionalidad de estilos y plantillas de otros controles de WPF. <xref:System.Windows.Controls.DataGrid>también incluye comportamientos predeterminados y personalizables para editar, ordenar y validar.  
  
 En la tabla siguiente se enumeran algunas de las tareas comunes de <xref:System.Windows.Controls.DataGrid> y cómo realizarlas. Al ver la API relacionada, puede encontrar más información y código de ejemplo.  
  
|Escenario|Enfoque|  
|--------------|--------------|  
|Colores de fondo alternativos|Establezca la <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> propiedad en 2 o más y, a continuación, asigne un <xref:System.Windows.Media.Brush> a las <xref:System.Windows.Controls.DataGrid.RowBackground%2A> <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> propiedades y.|  
|Definir el comportamiento de la selección de celdas y filas|Establezca las propiedades <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> y <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Personalizar el aspecto visual de los encabezados, celdas y filas|Aplique un nuevo <xref:System.Windows.Style> a las <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A> propiedades,, <xref:System.Windows.Controls.DataGrid.CellStyle%2A> o <xref:System.Windows.Controls.DataGrid.RowStyle%2A> .|  
|Establecer opciones de ajuste de tamaño|Establezca las <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> propiedades,, <xref:System.Windows.FrameworkElement.MinHeight%2A> , <xref:System.Windows.FrameworkElement.Width%2A> , <xref:System.Windows.FrameworkElement.MaxWidth%2A> o <xref:System.Windows.FrameworkElement.MinWidth%2A> . Para obtener más información, consulte [Opciones de ajuste de tamaño en el control DataGrid](sizing-options-in-the-datagrid-control.md).|  
|Acceder a los elementos seleccionados|Compruebe la <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> propiedad para obtener las celdas seleccionadas y la <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> propiedad para obtener las filas seleccionadas. Para más información, consulte <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Personalización de interacciones del usuario final|Establezca las <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A> propiedades,, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> ,, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> y <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> .|  
|Cancelar o cambiar columnas generadas automáticamente|Controle el <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> evento.|  
|Inmovilizar una columna|Establezca la <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> propiedad en 1 y mueva la columna a la posición situada más a la izquierda estableciendo la <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> propiedad en 0.|  
|Usar datos XML como origen de datos|Enlace el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> en <xref:System.Windows.Controls.DataGrid> a la consulta XPath que representa la colección de elementos. Cree cada columna en <xref:System.Windows.Controls.DataGrid> . Enlazar cada columna estableciendo el XPath en el enlace con la consulta que obtiene la propiedad en el origen del elemento. Para obtener un ejemplo, consulte <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Describe cómo configurar un nuevo proyecto de WPF, agregar un elemento Entity Framework, establecer el origen y mostrar los datos en un <xref:System.Windows.Controls.DataGrid> .|  
|[Procedimiento para agregar detalles de fila a un control DataGrid](how-to-add-row-details-to-a-datagrid-control.md)|Describe cómo crear detalles de fila para un <xref:System.Windows.Controls.DataGrid> .|  
|[Procedimiento para implementar la validación con el control DataGrid](how-to-implement-validation-with-the-datagrid-control.md)|Describe cómo validar valores en <xref:System.Windows.Controls.DataGrid> celdas y filas, y cómo mostrar comentarios de validación.|  
|[Comportamiento predeterminado de teclado y mouse en el control DataGridView](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Describe cómo interactuar con el <xref:System.Windows.Controls.DataGrid> control mediante el teclado y el mouse.|  
|[Procedimiento para agrupar, ordenar y filtrar datos en el control DataGrid](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Describe cómo ver los datos de de <xref:System.Windows.Controls.DataGrid> diferentes maneras mediante la agrupación, ordenación y filtrado de los datos.|  
|[Opciones de ajuste de tamaño en el control DataGrid](sizing-options-in-the-datagrid-control.md)|Describe cómo controlar el ajuste de tamaño absoluto y automático en <xref:System.Windows.Controls.DataGrid> .|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.DataGrid>
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Controles](index.md)
- [Modelo de contenido de WPF](wpf-content-model.md)
