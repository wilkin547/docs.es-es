---
title: Procedimiento Agrupar, ordenar y filtrar los datos en el control DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 81fdb0a6d5602f612c55d7e790ca9a0fe56c144e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771103"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Procedimiento Agrupar, ordenar y filtrar datos en el control DataGrid

A menudo resulta útil ver los datos en un <xref:System.Windows.Controls.DataGrid> de maneras diferentes mediante la agrupación, ordenación y filtrado de los datos. Para agrupar, ordenar y filtrar los datos en un <xref:System.Windows.Controls.DataGrid>, enlazarlo a un <xref:System.Windows.Data.CollectionView> que admite estas funciones. A continuación, puede trabajar con los datos en el <xref:System.Windows.Data.CollectionView> sin que afecte a los datos de origen subyacente. Los cambios en la vista de colección se reflejan en el <xref:System.Windows.Controls.DataGrid> interfaz de usuario (UI).

El <xref:System.Windows.Data.CollectionView> clase proporciona agrupación y ordenación de la funcionalidad para un origen de datos que implementa el <xref:System.Collections.IEnumerable> interfaz. El <xref:System.Windows.Data.CollectionViewSource> clase le permite establecer las propiedades de un <xref:System.Windows.Data.CollectionView> desde XAML.

En este ejemplo, una colección de `Task` objetos está enlazado a un <xref:System.Windows.Data.CollectionViewSource>. El <xref:System.Windows.Data.CollectionViewSource> se utiliza como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.DataGrid>. Agrupación, ordenación y filtrado se realizan en el <xref:System.Windows.Data.CollectionViewSource> y se muestran en el <xref:System.Windows.Controls.DataGrid> la interfaz de usuario.

![Datos agrupados en un control DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") datos agrupados en un control DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Uso de CollectionViewSource como ItemsSource

Para agrupar, ordenar y filtrar datos en un <xref:System.Windows.Controls.DataGrid> control, enlaza el <xref:System.Windows.Controls.DataGrid> a un <xref:System.Windows.Data.CollectionView> que admite estas funciones. En este ejemplo, el <xref:System.Windows.Controls.DataGrid> está enlazado a un <xref:System.Windows.Data.CollectionViewSource> que proporciona estas funciones para un <xref:System.Collections.Generic.List%601> de `Task` objetos.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Para enlazar un control DataGrid a CollectionViewSource

1. Cree una recopilación de datos que implementa el <xref:System.Collections.IEnumerable> interfaz.

    Si usas <xref:System.Collections.Generic.List%601> para crear la colección, debe crear una nueva clase que hereda de <xref:System.Collections.Generic.List%601> en lugar de una instancia de <xref:System.Collections.Generic.List%601>. Esto le permite enlazar los datos a la colección en XAML.

    > [!NOTE]
    > Deben implementar los objetos de la colección el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz modificado y el <xref:System.ComponentModel.IEditableObject> interfaz en orden para el <xref:System.Windows.Controls.DataGrid> responder correctamente a los cambios de propiedad y modificaciones. Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. En XAML, cree una instancia de la clase de colección y establezca el [Directiva x: Key](../../xaml-services/x-key-directive.md).

3. En XAML, cree una instancia de la <xref:System.Windows.Data.CollectionViewSource> clase, establezca el [Directiva x: Key](../../xaml-services/x-key-directive.md)y establece la instancia de la clase de colección como el <xref:System.Windows.Data.CollectionViewSource.Source%2A>.

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Cree una instancia de la <xref:System.Windows.Controls.DataGrid> clase y establezca el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad a la <xref:System.Windows.Data.CollectionViewSource>.

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Para tener acceso a la <xref:System.Windows.Data.CollectionViewSource> desde el código, utilice el <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> método para obtener una referencia a la <xref:System.Windows.Data.CollectionViewSource>.

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Agrupar elementos en un control DataGrid

Para especificar cómo se agrupan los elementos en un <xref:System.Windows.Controls.DataGrid>, usa el <xref:System.Windows.Data.PropertyGroupDescription> tipo para agrupar los elementos en la vista del origen.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Para agrupar elementos en un DataGrid mediante XAML

1. Crear un <xref:System.Windows.Data.PropertyGroupDescription> que especifica la propiedad en Agrupar por. Puede especificar la propiedad en XAML o en código.

   1. En XAML, establezca la <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> al nombre de la propiedad en Agrupar por.

   2. En el código, pase el nombre de la propiedad para agruparla al constructor.

2. Agregar el <xref:System.Windows.Data.PropertyGroupDescription> a la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> colección.

3. Agregar instancias adicionales de <xref:System.Windows.Data.PropertyGroupDescription> a la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección para agregar más niveles de agrupación.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Para quitar un grupo, quite el <xref:System.Windows.Data.PropertyGroupDescription> desde el <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección.

5. Para quitar todos los grupos, llame a la <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> método de la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Cuando se agrupan los elementos en el <xref:System.Windows.Controls.DataGrid>, puede definir un <xref:System.Windows.Controls.GroupStyle> que especifica la apariencia de cada grupo. Aplica el <xref:System.Windows.Controls.GroupStyle> agregándolo a la <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> colección del control DataGrid. Si tiene varios niveles de agrupación, puede aplicar estilos diferentes para cada nivel de grupo. Los estilos se aplican en el orden en el que se definen. Por ejemplo, si define dos estilos, la primera se aplicará a los grupos de fila de nivel superior. El segundo estilo será aplicada a todos los grupos de filas en el segundo nivel e inferior. El <xref:System.Windows.FrameworkElement.DataContext%2A> de la <xref:System.Windows.Controls.GroupStyle> es el <xref:System.Windows.Data.CollectionViewGroup> que representa el grupo.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Para cambiar la apariencia de los encabezados de grupo de fila

1. Crear un <xref:System.Windows.Controls.GroupStyle> que define la apariencia del grupo de filas.

2. Coloque el <xref:System.Windows.Controls.GroupStyle> dentro de la `<DataGrid.GroupStyle>` etiquetas.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Ordenar elementos en un control DataGrid

Para especificar cómo se ordenan los elementos en un <xref:System.Windows.Controls.DataGrid>, usa el <xref:System.ComponentModel.SortDescription> tipo para ordenar los elementos en la vista del origen.

### <a name="to-sort-items-in-a-datagrid"></a>Para ordenar los elementos de un control DataGrid

1. Crear un <xref:System.ComponentModel.SortDescription> que especifica la propiedad para ordenar por. Puede especificar la propiedad en XAML o en código.

    1. En XAML, establezca el <xref:System.ComponentModel.SortDescription.PropertyName%2A> en el nombre de la propiedad para ordenar por.

    2. En el código, pase el nombre de la propiedad para ordenar por y <xref:System.ComponentModel.ListSortDirection> al constructor.

2. Agregar el <xref:System.ComponentModel.SortDescription> a la <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> colección.

3. Agregar instancias adicionales de <xref:System.ComponentModel.SortDescription> a la <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> colección para ordenar por propiedades adicionales.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtrar elementos en un control DataGrid

Para filtrar los elementos en un <xref:System.Windows.Controls.DataGrid> mediante un <xref:System.Windows.Data.CollectionViewSource>, proporcionan la lógica de filtrado en el controlador para el <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> eventos.

### <a name="to-filter-items-in-a-datagrid"></a>Para filtrar los elementos de un control DataGrid

1. Agregar un controlador para el <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> eventos.

2. En el <xref:System.Windows.Data.CollectionViewSource.Filter> controlador de eventos, definir la lógica de filtrado.

    El filtro se aplicará cada vez que se actualice la vista.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

Como alternativa, puede filtrar los elementos de un <xref:System.Windows.Controls.DataGrid> mediante la creación de un método que proporciona la lógica de filtrado y configuración de la <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> propiedad para aplicar el filtro. Para ver un ejemplo de este método, consulte [filtrar los datos en una vista](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra la agrupación, ordenación y filtrado `Task` datos en un <xref:System.Windows.Data.CollectionViewSource> y mostrar agrupados, ordenar y filtrar `Task` datos en un <xref:System.Windows.Controls.DataGrid>. El <xref:System.Windows.Data.CollectionViewSource> se utiliza como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.DataGrid>. Agrupación, ordenación y filtrado se realizan en el <xref:System.Windows.Data.CollectionViewSource> y se muestran en el <xref:System.Windows.Controls.DataGrid> la interfaz de usuario.

Para probar este ejemplo, deberá ajustar el nombre DGGroupSortFilterExample para que coincida con el nombre del proyecto. Si utiliza Visual Basic, deberá cambiar el nombre de clase <xref:System.Windows.Window> al siguiente.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Crear y enlazar a una colección ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtrar datos en una vista](../data/how-to-filter-data-in-a-view.md)
- [Ordenar datos en una vista](../data/how-to-sort-data-in-a-view.md)
- [Ordenar y agrupar datos mediante una vista en XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
