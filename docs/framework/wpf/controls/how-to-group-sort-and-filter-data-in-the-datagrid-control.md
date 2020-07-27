---
title: 'Cómo: agrupar, ordenar y filtrar datos en el control DataGrid'
description: Obtenga información sobre cómo enlazar un control DataGrid de Windows Presentation Foundation a una CollectionView que admita la agrupación, ordenación y filtrado de datos en las vistas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 072e5a104a91faa40bb54f2a3fc4ed6188e1112e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167666"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Cómo: agrupar, ordenar y filtrar datos en el control DataGrid

A menudo resulta útil ver los datos de una <xref:System.Windows.Controls.DataGrid> forma diferente mediante la agrupación, ordenación y filtrado de los datos. Para agrupar, ordenar y filtrar los datos de un <xref:System.Windows.Controls.DataGrid> , debe enlazarlos a un <xref:System.Windows.Data.CollectionView> que admita estas funciones. Después, puede trabajar con los datos de <xref:System.Windows.Data.CollectionView> sin que afecte a los datos de origen subyacentes. Los cambios en la vista de colección se reflejan en la <xref:System.Windows.Controls.DataGrid> interfaz de usuario (UI).

La <xref:System.Windows.Data.CollectionView> clase proporciona funcionalidad de agrupación y ordenación para un origen de datos que implementa la <xref:System.Collections.IEnumerable> interfaz. La <xref:System.Windows.Data.CollectionViewSource> clase le permite establecer las propiedades de <xref:System.Windows.Data.CollectionView> desde XAML.

En este ejemplo, una colección de `Task` objetos se enlaza a un objeto <xref:System.Windows.Data.CollectionViewSource> . <xref:System.Windows.Data.CollectionViewSource>Se utiliza como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para <xref:System.Windows.Controls.DataGrid> . La agrupación, ordenación y filtrado se realizan en <xref:System.Windows.Data.CollectionViewSource> y se muestran en la <xref:System.Windows.Controls.DataGrid> interfaz de usuario.

![Datos agrupados en un control DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Datos agrupados en un control DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Usar un CollectionViewSource como ItemsSource

Para agrupar, ordenar y filtrar los datos de un <xref:System.Windows.Controls.DataGrid> control, puede enlazar <xref:System.Windows.Controls.DataGrid> a un <xref:System.Windows.Data.CollectionView> que admita estas funciones. En este ejemplo, <xref:System.Windows.Controls.DataGrid> se enlaza a un <xref:System.Windows.Data.CollectionViewSource> objeto que proporciona estas funciones para una <xref:System.Collections.Generic.List%601> de `Task` objetos.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Para enlazar un control DataGrid a un CollectionViewSource

1. Cree una colección de datos que implemente la <xref:System.Collections.IEnumerable> interfaz.

    Si usa <xref:System.Collections.Generic.List%601> para crear la colección, debe crear una nueva clase que herede de en <xref:System.Collections.Generic.List%601> lugar de crear instancias de una instancia de <xref:System.Collections.Generic.List%601> . Esto permite enlazar datos a la colección en XAML.

    > [!NOTE]
    > Los objetos de la colección deben implementar la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz cambiada y la <xref:System.ComponentModel.IEditableObject> interfaz para que el objeto <xref:System.Windows.Controls.DataGrid> pueda responder correctamente a los cambios de propiedad y a las ediciones. Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. En XAML, cree una instancia de la clase de colección y establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md).

3. En XAML, cree una instancia de la <xref:System.Windows.Data.CollectionViewSource> clase, establezca la [Directiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)y establezca la instancia de la clase de colección como <xref:System.Windows.Data.CollectionViewSource.Source%2A> .

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Cree una instancia de la <xref:System.Windows.Controls.DataGrid> clase y establezca la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad en <xref:System.Windows.Data.CollectionViewSource> .

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Para obtener acceso a <xref:System.Windows.Data.CollectionViewSource> desde el código, utilice el <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> método para obtener una referencia a <xref:System.Windows.Data.CollectionViewSource> .

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Agrupar elementos en un control DataGrid

Para especificar cómo se agrupan los elementos en una <xref:System.Windows.Controls.DataGrid> , utilice el <xref:System.Windows.Data.PropertyGroupDescription> tipo para agrupar los elementos en la vista de código fuente.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Para agrupar elementos en un control DataGrid mediante XAML

1. Cree un <xref:System.Windows.Data.PropertyGroupDescription> que especifica la propiedad por la que se va a agrupar. Puede especificar la propiedad en XAML o en el código.

   1. En XAML, establezca <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> en el nombre de la propiedad por la que se va a agrupar.

   2. En el código, pase el nombre de la propiedad que se va a agrupar por en el constructor.

2. Agregue <xref:System.Windows.Data.PropertyGroupDescription> a la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> colección.

3. Agregue instancias adicionales de <xref:System.Windows.Data.PropertyGroupDescription> a la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección para agregar más niveles de agrupación.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Para quitar un grupo, quite <xref:System.Windows.Data.PropertyGroupDescription> de la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección.

5. Para quitar todos los grupos, llame al <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> método de la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Cuando los elementos se agrupan en <xref:System.Windows.Controls.DataGrid> , puede definir un <xref:System.Windows.Controls.GroupStyle> que especifique la apariencia de cada grupo. <xref:System.Windows.Controls.GroupStyle>Para aplicar, agréguelo a la <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> colección de DataGrid. Si tiene varios niveles de agrupación, puede aplicar distintos estilos a cada nivel de grupo. Los estilos se aplican en el orden en el que se definen. Por ejemplo, si define dos estilos, el primero se aplicará a los grupos de filas de nivel superior. El segundo estilo se aplicará a todos los grupos de filas en el segundo nivel y en el inferior. <xref:System.Windows.FrameworkElement.DataContext%2A>De <xref:System.Windows.Controls.GroupStyle> es el <xref:System.Windows.Data.CollectionViewGroup> que el grupo representa.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Para cambiar la apariencia de los encabezados de grupo de filas

1. Cree un <xref:System.Windows.Controls.GroupStyle> que defina la apariencia del grupo de filas.

2. Coloque <xref:System.Windows.Controls.GroupStyle> dentro de las `<DataGrid.GroupStyle>` etiquetas.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Ordenar elementos en un control DataGrid

Para especificar cómo se ordenan los elementos en una <xref:System.Windows.Controls.DataGrid> , utilice el <xref:System.ComponentModel.SortDescription> tipo para ordenar los elementos en la vista de código fuente.

### <a name="to-sort-items-in-a-datagrid"></a>Para ordenar los elementos de un control DataGrid

1. Cree un <xref:System.ComponentModel.SortDescription> que especifique la propiedad por la que se va a ordenar. Puede especificar la propiedad en XAML o en el código.

    1. En XAML, establezca <xref:System.ComponentModel.SortDescription.PropertyName%2A> en el nombre de la propiedad por la que se va a ordenar.

    2. En el código, pase el nombre de la propiedad que se va a ordenar por y el <xref:System.ComponentModel.ListSortDirection> al constructor.

2. Agregue <xref:System.ComponentModel.SortDescription> a la <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> colección.

3. Agregue instancias adicionales de <xref:System.ComponentModel.SortDescription> a la <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> colección para ordenarlas por propiedades adicionales.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtrar elementos en un control DataGrid

Para filtrar los elementos de un <xref:System.Windows.Controls.DataGrid> mediante <xref:System.Windows.Data.CollectionViewSource> , debe proporcionar la lógica de filtrado en el controlador del <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.

### <a name="to-filter-items-in-a-datagrid"></a>Para filtrar elementos en un control DataGrid

1. Agregue un controlador para el <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.

2. En el <xref:System.Windows.Data.CollectionViewSource.Filter> controlador de eventos, defina la lógica de filtrado.

    El filtro se aplicará cada vez que se actualice la vista.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

Como alternativa, puede filtrar elementos en un <xref:System.Windows.Controls.DataGrid> creando un método que proporcione la lógica de filtrado y estableciendo la <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> propiedad para aplicar el filtro. Para ver un ejemplo de este método, vea [filtrar datos en una vista](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo agrupar, ordenar y filtrar `Task` los datos en un <xref:System.Windows.Data.CollectionViewSource> y mostrar los datos agrupados, ordenados y filtrados `Task` en un <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Data.CollectionViewSource>Se utiliza como <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para <xref:System.Windows.Controls.DataGrid> . La agrupación, ordenación y filtrado se realizan en <xref:System.Windows.Data.CollectionViewSource> y se muestran en la <xref:System.Windows.Controls.DataGrid> interfaz de usuario.

Para probar este ejemplo, tendrá que ajustar el nombre de DGGroupSortFilterExample para que coincida con el nombre del proyecto. Si está utilizando Visual Basic, deberá cambiar el nombre de clase de por <xref:System.Windows.Window> lo siguiente.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Crear y enlazar a un ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtrar datos en una vista](../data/how-to-filter-data-in-a-view.md)
- [Ordenar datos en una vista](../data/how-to-sort-data-in-a-view.md)
- [Ordenar y agrupar datos mediante una vista en XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
