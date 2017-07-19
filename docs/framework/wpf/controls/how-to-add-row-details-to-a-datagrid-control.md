---
title: "C&#243;mo: Agregar detalles de fila a un control DataGrid | Microsoft Docs"
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
  - "DataGrid [WPF], detalles de fila"
  - "DataTemplate [WPF], DataGrid"
  - "detalles de fila [WPF], DataGrid"
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Agregar detalles de fila a un control DataGrid
Cuando se usa el control <xref:System.Windows.Controls.DataGrid>, se puede personalizar la presentación de los datos agregando una sección de detalles de fila.  Agregar una sección de detalles de fila le permite agrupar algunos datos en una plantilla que está visible o contraída opcionalmente.  Por ejemplo, puede agregar detalles de fila a un control <xref:System.Windows.Controls.DataGrid> que presenta únicamente un resumen de los datos para cada fila del <xref:System.Windows.Controls.DataGrid>, pero presenta más campos de datos cuando el usuario selecciona una fila.  La plantilla para la sección de detalles de fila se define en la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  En la ilustración siguiente se muestra un ejemplo de una sección de detalles de fila.  
  
 ![DataGrid con detalles de filas](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP\_RowDetails")  
  
 La plantilla de detalles de fila se define como XAML alineado o como un recurso.  Ambos enfoques se muestran en los procedimientos siguientes.  Una plantilla de datos que se agrega como un recurso se puede usar en todo el proyecto sin volver a crear la plantilla.  Una plantilla de datos que se agrega como XAML alineado solo es accesible desde el control donde se define.  
  
### Para mostrar detalles de fila usando XAML alineado  
  
1.  Cree un control <xref:System.Windows.Controls.DataGrid> que muestre datos de un origen de datos.  
  
2.  En el elemento <xref:System.Windows.Controls.DataGrid>, agregue un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3.  Cree un objeto <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.  
  
     En el código XAML siguiente se muestra el control <xref:System.Windows.Controls.DataGrid> y cómo definir la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> alineada.  <xref:System.Windows.Controls.DataGrid> muestra tres valores en cada fila y tres valores más cuando la fila está seleccionada.  
  
     [!code-xml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     En el código siguiente se muestra la consulta que se emplea para seleccionar los datos que se muestran en <xref:System.Windows.Controls.DataGrid>.  En este ejemplo, la consulta selecciona los datos de una entidad que contiene información del cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### Para mostrar detalles de fila usando un recurso  
  
1.  Cree un control <xref:System.Windows.Controls.DataGrid> que muestre datos de un origen de datos.  
  
2.  Agregue un elemento <xref:System.Windows.FrameworkElement.Resources%2A> al elemento raíz, como un control <xref:System.Windows.Window> o un control <xref:System.Windows.Controls.Page>, o agregue un elemento <xref:System.Windows.Application.Resources%2A> a la clase <xref:System.Windows.Application> en el archivo App.xaml \(o Application.xaml\).  
  
3.  En el elemento Resources, cree un objeto <xref:System.Windows.DataTemplate> que defina la apariencia de la sección de detalles de fila.  
  
     En el código XAML siguiente se muestra la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definida en la clase <xref:System.Windows.Application>.  
  
     [!code-xml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  En <xref:System.Windows.DataTemplate>, establezca [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md) en un valor que identifique de manera única la plantilla de datos.  
  
5.  En el elemento <xref:System.Windows.Controls.DataGrid>, establezca la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> en el recurso definido en los pasos anteriores.  Asigne el recurso como un recurso estático.  
  
     En el código XAML siguiente se muestra la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> establecida en el recurso del ejemplo anterior.  
  
     [!code-xml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### Para establecer la visibilidad e impedir el desplazamiento horizontal de los detalles de fila  
  
1.  Si es necesario, establezca la propiedad <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> en un valor <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  
  
     De manera predeterminada, el valor se establece en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  Puede establecerlo en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> para mostrar los detalles de todas las filas o en <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> para ocultar los detalles de todas las filas.  
  
2.  Si es necesario, establezca la propiedad <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> en `true` para impedir que la sección de detalles de fila se desplace horizontalmente.