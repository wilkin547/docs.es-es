---
title: 'Cómo: agrupar, ordenar y filtrar datos en el control DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 622b64fd7738b02cd72131e7e9fe91c04314b1d0
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559479"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Cómo: agrupar, ordenar y filtrar datos en el control DataGrid

A menudo resulta útil ver los datos de una <xref:System.Windows.Controls.DataGrid> de maneras diferentes mediante la agrupación, ordenación y filtrado de los datos. Para agrupar, ordenar y filtrar los datos de un <xref:System.Windows.Controls.DataGrid>, debe enlazarlos a un <xref:System.Windows.Data.CollectionView> que admita estas funciones. Después, puede trabajar con los datos en el <xref:System.Windows.Data.CollectionView> sin que ello afecte a los datos de origen subyacentes. Los cambios en la vista de colección se reflejan en la <xref:System.Windows.Controls.DataGrid> interfaz de usuario (UI).

La clase <xref:System.Windows.Data.CollectionView> proporciona funcionalidad de agrupación y ordenación para un origen de datos que implementa la interfaz <xref:System.Collections.IEnumerable>. La clase <xref:System.Windows.Data.CollectionViewSource> permite establecer las propiedades de un <xref:System.Windows.Data.CollectionView> desde XAML.

En este ejemplo, una colección de objetos `Task` se enlaza a un <xref:System.Windows.Data.CollectionViewSource>. El <xref:System.Windows.Data.CollectionViewSource> se utiliza como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.DataGrid>. La agrupación, ordenación y filtrado se realizan en el <xref:System.Windows.Data.CollectionViewSource> y se muestran en la interfaz de usuario de <xref:System.Windows.Controls.DataGrid>.

![Datos agrupados en un control DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Datos agrupados en un control DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Usar un CollectionViewSource como ItemsSource

Para agrupar, ordenar y filtrar los datos de un control <xref:System.Windows.Controls.DataGrid>, enlace el <xref:System.Windows.Controls.DataGrid> a una <xref:System.Windows.Data.CollectionView> que admita estas funciones. En este ejemplo, el <xref:System.Windows.Controls.DataGrid> se enlaza a una <xref:System.Windows.Data.CollectionViewSource> que proporciona estas funciones para un <xref:System.Collections.Generic.List%601> de objetos `Task`.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Para enlazar un control DataGrid a un CollectionViewSource

1. Cree una colección de datos que implemente la interfaz <xref:System.Collections.IEnumerable>.

    Si usa <xref:System.Collections.Generic.List%601> para crear la colección, debe crear una nueva clase que herede de <xref:System.Collections.Generic.List%601> en lugar de crear una instancia de <xref:System.Collections.Generic.List%601>. Esto permite enlazar datos a la colección en XAML.

    > [!NOTE]
    > Los objetos de la colección deben implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> cambiado y la interfaz <xref:System.ComponentModel.IEditableObject> para que el <xref:System.Windows.Controls.DataGrid> responda correctamente a los cambios de propiedad y a las ediciones. Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. En XAML, cree una instancia de la clase de colección y establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md).

3. En XAML, cree una instancia de la clase <xref:System.Windows.Data.CollectionViewSource>, establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)y establezca la instancia de la clase de colección como <xref:System.Windows.Data.CollectionViewSource.Source%2A>.

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Cree una instancia de la clase <xref:System.Windows.Controls.DataGrid> y establezca la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> en el <xref:System.Windows.Data.CollectionViewSource>.

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Para tener acceso al <xref:System.Windows.Data.CollectionViewSource> desde el código, utilice el método <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> para obtener una referencia a la <xref:System.Windows.Data.CollectionViewSource>.

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Agrupar elementos en un control DataGrid

Para especificar cómo se agrupan los elementos en un <xref:System.Windows.Controls.DataGrid>, use el tipo de <xref:System.Windows.Data.PropertyGroupDescription> para agrupar los elementos en la vista de código fuente.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Para agrupar elementos en un control DataGrid mediante XAML

1. Cree una <xref:System.Windows.Data.PropertyGroupDescription> que especifique la propiedad por la que se va a agrupar. Puede especificar la propiedad en XAML o en el código.

   1. En XAML, establezca el <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> en el nombre de la propiedad por la que se va a agrupar.

   2. En el código, pase el nombre de la propiedad que se va a agrupar por en el constructor.

2. Agregue el <xref:System.Windows.Data.PropertyGroupDescription> a la colección de <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType>.

3. Agregue instancias adicionales de <xref:System.Windows.Data.PropertyGroupDescription> a la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> para agregar más niveles de agrupación.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Para quitar un grupo, quite el <xref:System.Windows.Data.PropertyGroupDescription> de la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.

5. Para quitar todos los grupos, llame al método <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> de la colección <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Cuando los elementos se agrupan en el <xref:System.Windows.Controls.DataGrid>, puede definir una <xref:System.Windows.Controls.GroupStyle> que especifique la apariencia de cada grupo. Para aplicar el <xref:System.Windows.Controls.GroupStyle>, agréguelo a la colección <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> de DataGrid. Si tiene varios niveles de agrupación, puede aplicar distintos estilos a cada nivel de grupo. Los estilos se aplican en el orden en el que se definen. Por ejemplo, si define dos estilos, el primero se aplicará a los grupos de filas de nivel superior. El segundo estilo se aplicará a todos los grupos de filas en el segundo nivel y en el inferior. El <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.GroupStyle> es el <xref:System.Windows.Data.CollectionViewGroup> que representa el grupo.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Para cambiar la apariencia de los encabezados de grupo de filas

1. Cree una <xref:System.Windows.Controls.GroupStyle> que defina la apariencia del grupo de filas.

2. Coloque el <xref:System.Windows.Controls.GroupStyle> dentro de las etiquetas de `<DataGrid.GroupStyle>`.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Ordenar elementos en un control DataGrid

Para especificar cómo se ordenan los elementos en un <xref:System.Windows.Controls.DataGrid>, use el tipo de <xref:System.ComponentModel.SortDescription> para ordenar los elementos en la vista de código fuente.

### <a name="to-sort-items-in-a-datagrid"></a>Para ordenar los elementos de un control DataGrid

1. Cree una <xref:System.ComponentModel.SortDescription> que especifique la propiedad por la que se va a ordenar. Puede especificar la propiedad en XAML o en el código.

    1. En XAML, establezca el <xref:System.ComponentModel.SortDescription.PropertyName%2A> en el nombre de la propiedad por la que se va a ordenar.

    2. En el código, pase el nombre de la propiedad que se va a ordenar por y el <xref:System.ComponentModel.ListSortDirection> al constructor.

2. Agregue el <xref:System.ComponentModel.SortDescription> a la colección de <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType>.

3. Agregue instancias adicionales de <xref:System.ComponentModel.SortDescription> a la colección <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> para ordenarlas por propiedades adicionales.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtrar elementos en un control DataGrid

Para filtrar los elementos de un <xref:System.Windows.Controls.DataGrid> mediante un <xref:System.Windows.Data.CollectionViewSource>, debe proporcionar la lógica de filtrado en el controlador del evento <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType>.

### <a name="to-filter-items-in-a-datagrid"></a>Para filtrar elementos en un control DataGrid

1. Agregue un controlador para el evento <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType>.

2. En el controlador de eventos <xref:System.Windows.Data.CollectionViewSource.Filter>, defina la lógica de filtrado.

    El filtro se aplicará cada vez que se actualice la vista.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

Como alternativa, puede filtrar los elementos de un <xref:System.Windows.Controls.DataGrid> creando un método que proporcione la lógica de filtrado y estableciendo la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> para aplicar el filtro. Para ver un ejemplo de este método, vea [filtrar datos en una vista](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo agrupar, ordenar y filtrar `Task` datos en un <xref:System.Windows.Data.CollectionViewSource> y mostrar los datos agrupados, ordenados y `Task` filtrados en un <xref:System.Windows.Controls.DataGrid>. El <xref:System.Windows.Data.CollectionViewSource> se utiliza como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.DataGrid>. La agrupación, ordenación y filtrado se realizan en el <xref:System.Windows.Data.CollectionViewSource> y se muestran en la interfaz de usuario de <xref:System.Windows.Controls.DataGrid>.

Para probar este ejemplo, tendrá que ajustar el nombre de DGGroupSortFilterExample para que coincida con el nombre del proyecto. Si está utilizando Visual Basic, deberá cambiar el nombre de clase de <xref:System.Windows.Window> por lo siguiente.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Crear y enlazar a una colección ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtrar datos en una vista](../data/how-to-filter-data-in-a-view.md)
- [Ordenar datos en una vista](../data/how-to-sort-data-in-a-view.md)
- [Ordenar y agrupar datos mediante una vista en XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
