---
title: "C&#243;mo: Agrupar, ordenar y filtrar datos en el control DataGrid | Microsoft Docs"
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
  - "DataGrid [WPF], filtro"
  - "DataGrid [WPF], grupo"
  - "DataGrid [WPF], ordenar"
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Agrupar, ordenar y filtrar datos en el control DataGrid
A menudo es útil ver los datos de un control <xref:System.Windows.Controls.DataGrid> de maneras diferentes, agrupándolos, ordenándolos y filtrándolos.  Para agrupar, ordenar y filtrar los datos de una <xref:System.Windows.Controls.DataGrid>, enlácela a una <xref:System.Windows.Data.CollectionView> que admita estas características.  A continuación, puede trabajar con los datos de la <xref:System.Windows.Data.CollectionView> sin que afecte a los datos de origen subyacentes.  Los cambios en la vista de colección se reflejan en la interfaz de usuario de <xref:System.Windows.Controls.DataGrid>.  
  
 La clase <xref:System.Windows.Data.CollectionView> proporciona la funcionalidad de agrupación y ordenación para un origen de datos que implemente la interfaz <xref:System.Collections.IEnumerable>.  La clase <xref:System.Windows.Data.CollectionViewSource> permite establecer las propiedades de una <xref:System.Windows.Data.CollectionView> a partir del XAML.  
  
 En este ejemplo, una colección de objetos `Task` se enlaza a un <xref:System.Windows.Data.CollectionViewSource>.  <xref:System.Windows.Data.CollectionViewSource> se usa como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.DataGrid>.  La agrupación, ordenación y filtrado se realizan en <xref:System.Windows.Data.CollectionViewSource> y se muestran en la interfaz de usuario de <xref:System.Windows.Controls.DataGrid>.  
  
 ![Datos agrupados en una clase DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF\_DataGridGroups")  
Datos agrupados en una DataGrid  
  
## Usar un CollectionViewSource como un ItemsSource  
 Para agrupar, ordenar y filtrar los datos de un control <xref:System.Windows.Controls.DataGrid>, enlace la <xref:System.Windows.Controls.DataGrid> a una <xref:System.Windows.Data.CollectionView> que admita estas características.  En este ejemplo, <xref:System.Windows.Controls.DataGrid> se enlaza a un objeto <xref:System.Windows.Data.CollectionViewSource> que proporciona estas funciones para una colección <xref:System.Collections.Generic.List%601> de objetos `Task`.  
  
#### Para enlazar un DataGrid a un CollectionViewSource  
  
1.  Cree una colección de datos que implemente la interfaz <xref:System.Collections.IEnumerable>.  
  
     Si utiliza <xref:System.Collections.Generic.List%601> para crear la colección, debe crear una nueva clase que herede de <xref:System.Collections.Generic.List%601> en lugar de crear una instancia de <xref:System.Collections.Generic.List%601>.  Esto permite el enlace de datos a la colección en XAML.  
  
    > [!NOTE]
    >  Los objetos de la colección deben implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> y la interfaz <xref:System.ComponentModel.IEditableObject> para que <xref:System.Windows.Controls.DataGrid> responda correctamente a los cambios y ediciones de propiedad.  Para obtener más información, consulte [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  En XAML, cree una instancia de la clase de colección y establezca la [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md).  
  
3.  En XAML, cree una instancia de la clase <xref:System.Windows.Data.CollectionViewSource>, establezca la [x:Key \(Directiva\)](../../../../docs/framework/xaml-services/x-key-directive.md), y establezca la instancia de la clase de colección como el <xref:System.Windows.Data.CollectionViewSource.Source%2A>.  
  
     [!code-xml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  Cree una instancia de la clase <xref:System.Windows.Controls.DataGrid> y establezca la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> en el <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-xml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  Para tener acceso al <xref:System.Windows.Data.CollectionViewSource> desde el código, utilice el método <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> para obtener una referencia al <xref:System.Windows.Data.CollectionViewSource>.  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## Agrupación de elementos en DataGrid  
 Para especificar cómo se agrupan los elementos de <xref:System.Windows.Controls.DataGrid>, se usa el tipo <xref:System.Windows.Data.PropertyGroupDescription> para agrupar los elementos en la vista de origen.  
  
#### Para agrupar los elementos en un DataGrid mediante XAML  
  
1.  Cree una <xref:System.Windows.Data.PropertyGroupDescription> que especifique la propiedad por la que desea agrupar.  Puede especificar la propiedad en XAML o en el código.  
  
    1.  En XAML, establezca el <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> en el nombre de la propiedad por la que desea agrupar.  
  
    2.  En el código, pase el nombre de la propiedad por la que desea agrupar al constructor.  
  
2.  Agregue el objeto <xref:System.Windows.Data.PropertyGroupDescription> a la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=fullName>.  
  
3.  Agregue más instancias de <xref:System.Windows.Data.PropertyGroupDescription> a la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> para aumentar el número de niveles de agrupación.  
  
     [!code-xml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  Para quitar un grupo, quite la <xref:System.Windows.Data.PropertyGroupDescription> de la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.  
  
5.  Para quitar todos los grupos, llame al método <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> de la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 Cuando los elementos se agrupan en la <xref:System.Windows.Controls.DataGrid>, puede definir un <xref:System.Windows.Controls.GroupStyle> que especifique el aspecto de cada grupo.  Aplique el <xref:System.Windows.Controls.GroupStyle> agregándolo a la colección <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> del control DataGrid.  Si dispone de varios niveles de agrupación, puede aplicar estilos diferentes a cada nivel de grupo.  Los estilos se aplican en el orden en que se definen.  Por ejemplo, si define dos estilos, el primero se aplicará a los grupos de fila de nivel superior.  El segundo estilo se aplicará a todos los grupos de filas del segundo nivel y niveles inferiores.  El <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.GroupStyle> es el <xref:System.Windows.Data.CollectionViewGroup> que el grupo representa.  
  
#### Para cambiar la apariencia del encabezado de grupo de filas  
  
1.  Cree un <xref:System.Windows.Controls.GroupStyle> que defina la apariencia del grupo de filas.  
  
2.  Coloque <xref:System.Windows.Controls.GroupStyle> dentro de las etiquetas `<DataGrid.GroupStyle>`.  
  
     [!code-xml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## Ordenación de elementos en DataGrid  
 Para especificar cómo se ordenan los elementos de <xref:System.Windows.Controls.DataGrid>, se usa el tipo <xref:System.ComponentModel.SortDescription> para ordenar los elementos en la vista de origen.  
  
#### Para ordenar elementos en DataGrid  
  
1.  Cree una <xref:System.ComponentModel.SortDescription> que especifique la propiedad por la que desea ordenar.  Puede especificar la propiedad en XAML o en el código.  
  
    1.  En XAML, establezca el <xref:System.ComponentModel.SortDescription.PropertyName%2A> en el nombre de la propiedad por la que desea ordenar.  
  
    2.  En el código, pase el nombre de la propiedad por la que desea ordenar y la <xref:System.ComponentModel.ListSortDirection> al constructor.  
  
2.  Agregue la <xref:System.ComponentModel.SortDescription> a la colección <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=fullName>.  
  
3.  Agregue más instancias de <xref:System.ComponentModel.SortDescription> a la colección <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> para ordenar por otras propiedades.  
  
     [!code-xml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## Filtrado de elementos en DataGrid  
 Para filtrar los elementos de una <xref:System.Windows.Controls.DataGrid> mediante un <xref:System.Windows.Data.CollectionViewSource>, proporcione la lógica de filtrado del controlador del evento <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=fullName>.  
  
#### Para filtrar elementos en DataGrid  
  
1.  Agregue un controlador para el evento <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=fullName>.  
  
2.  En el controlador de eventos <xref:System.Windows.Data.CollectionViewSource.Filter>, defina la lógica de filtrado.  
  
     El filtro se aplicará cada vez que se actualice la vista.  
  
     [!code-xml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 O bien, puede filtrar los elementos de una <xref:System.Windows.Controls.DataGrid> creando un método que proporcione la lógica de filtrado y estableciendo la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=fullName> para aplicar el filtro.  Para ver un ejemplo de este método, consulte [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agrupar, ordenar y filtrar los datos `Task` en un <xref:System.Windows.Data.CollectionViewSource> y cómo mostrar los datos `Task` agrupados, ordenados y filtrados en una <xref:System.Windows.Controls.DataGrid>.  <xref:System.Windows.Data.CollectionViewSource> se usa como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.DataGrid>.  La agrupación, ordenación y filtrado se realizan en <xref:System.Windows.Data.CollectionViewSource> y se muestran en la interfaz de usuario de <xref:System.Windows.Controls.DataGrid>.  
  
 Para probar este ejemplo, deberá ajustar el nombre DGGroupSortFilterExample para que coincida con el nombre de proyecto.  Si utiliza Visual Basic, deberá cambiar el nombre de clase de <xref:System.Windows.Window> por el siguiente.  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## Compilar el código  
  
## Programación eficaz  
  
## Seguridad de .NET Framework  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Crear y enlazar a una colección ObservableCollection](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)   
 [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)