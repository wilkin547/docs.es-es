---
title: "DataGrid | Microsoft Docs"
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
  - "controles [WPF], DataGrid"
  - "DataGrid [WPF], tareas comunes para"
  - "DataGrid [WPF], personalizar la apariencia de"
  - "DataGrid (tipos de columna) [WPF]"
  - "DataGrid (columnas) [WPF], utilizar"
  - "DataGrid (control) [WPF]"
  - "DataGrid (escenarios) [WPF]"
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DataGrid
El control <xref:System.Windows.Controls.DataGrid> le permite mostrar y editar datos de muchos orígenes diferentes como, por ejemplo, una base de datos SQL, una consulta LINQ o cualquier otro origen de datos enlazable.  Para obtener más información, vea [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Las columnas pueden mostrar texto, controles como <xref:System.Windows.Controls.ComboBox> o cualquier otro contenido de WPF, como imágenes, botones o cualquier contenido incluido en una plantilla.  Puede usar <xref:System.Windows.Controls.DataGridTemplateColumn> para mostrar datos definidos en una plantilla.  En la tabla siguiente se hace una lista de los tipos de columna que se proporcionan de manera predeterminada.  
  
|Tipo de columna generada|Tipo de datos|  
|------------------------------|-------------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 Se puede personalizar la apariencia de <xref:System.Windows.Controls.DataGrid>, como la fuente, el color y el tamaño.  <xref:System.Windows.Controls.DataGrid> admite toda la funcionalidad de estilos y plantillas de otros controles WPF.  <xref:System.Windows.Controls.DataGrid> también incluye comportamientos predeterminados y personalizables para la edición, ordenación y validación.  
  
 En la tabla siguiente se enumeran algunas de las tareas comunes para <xref:System.Windows.Controls.DataGrid> y cómo realizarlas.  Si se muestra la API relacionada, puede buscar más información y código de ejemplo.  
  
|Escenario|Método|  
|---------------|------------|  
|Colores de fondo alternos|Establezca la propiedad <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> en 2 o más y, a continuación, asigne <xref:System.Windows.Media.Brush> a las propiedades <xref:System.Windows.Controls.DataGrid.RowBackground%2A> y <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A>.|  
|Definir el comportamiento de la selección de celdas y filas|Establezca las propiedades <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> y <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Personalizar la apariencia visual de encabezados, celdas y filas|Aplique una nueva clase <xref:System.Windows.Style> a las propiedades <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A> o <xref:System.Windows.Controls.DataGrid.RowStyle%2A>.|  
|Establecer opciones de tamaño|Establezca las propiedades <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A> y <xref:System.Windows.FrameworkElement.MinWidth%2A>.  Para obtener más información, vea [Opciones de ajuste de tamaño en el control DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md).|  
|Tener acceso a elementos seleccionados|Compruebe la propiedad <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> para obtener las celdas seleccionadas y la propiedad <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> para obtener las filas seleccionadas.  Para obtener más información, vea <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Personalizar las interacciones del usuario final|Establezca las propiedades <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> y <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A>.|  
|Cancelar o cambiar las columnas generadas automáticamente|Controle el evento <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn>.|  
|Inmovilizar una columna|Establezca la propiedad <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> en 1 y mueva la columna a la posición situada más a la izquierda estableciendo la propiedad <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> en 0.|  
|Utilizar los datos XML como el origen de datos|Enlace la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.DataGrid> a la consulta XPath que representa la colección de elementos.  Cree cada columna en <xref:System.Windows.Controls.DataGrid>.  Enlace cada columna estableciendo el XPath del enlace en la consulta que obtiene la propiedad en el origen del elemento.  Para obtener un ejemplo, vea <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Tutorial: Mostrar los datos de una base de datos de SQL Server en un control DataGrid](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Describe cómo configurar un nuevo proyecto WPF, agregar un elemento de Entity Framework, establecer el origen y mostrar los datos en un control <xref:System.Windows.Controls.DataGrid>.|  
|[Cómo: Agregar detalles de fila a un control DataGrid](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|Describe cómo crear detalles de fila para <xref:System.Windows.Controls.DataGrid>.|  
|[Cómo: Implementar la validación con el control DataGrid](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|Describe cómo validar los valores de las celdas y filas de <xref:System.Windows.Controls.DataGrid>, y mostrar comentarios de validación.|  
|[Comportamiento predeterminado de teclado y mouse en el control DataGridView](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Describe cómo interactuar con el control <xref:System.Windows.Controls.DataGrid> a través del teclado y el mouse.|  
|[Cómo: Agrupar, ordenar y filtrar datos en el control DataGrid](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Describe cómo ver los datos de <xref:System.Windows.Controls.DataGrid> de maneras diferentes mediante su agrupación, ordenación y filtrado.|  
|[Opciones de ajuste de tamaño en el control DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|Describe cómo controlar el ajuste de tamaño absoluto y automático en <xref:System.Windows.Controls.DataGrid>.|  
  
## Vea también  
 <xref:System.Windows.Controls.DataGrid>   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)   
 [Controles](../../../../docs/framework/wpf/controls/index.md)   
 [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)