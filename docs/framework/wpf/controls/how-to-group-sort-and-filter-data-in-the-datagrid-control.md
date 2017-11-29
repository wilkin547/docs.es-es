---
title: "Cómo: Agrupar, ordenar y filtrar datos en el control DataGrid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3c8afacfafbe14794bf17a4e9a4df7c175a3668
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="61e76-102">Cómo: Agrupar, ordenar y filtrar datos en el control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="61e76-103">A menudo resulta útil ver los datos en un <xref:System.Windows.Controls.DataGrid> de maneras diferentes, agrupar, ordenar y filtrar los datos.</span><span class="sxs-lookup"><span data-stu-id="61e76-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="61e76-104">Para agrupar, ordenar y filtrar los datos en un <xref:System.Windows.Controls.DataGrid>, enlazarlo a un <xref:System.Windows.Data.CollectionView> que es compatible con estas funciones.</span><span class="sxs-lookup"><span data-stu-id="61e76-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="61e76-105">A continuación, puede trabajar con los datos en el <xref:System.Windows.Data.CollectionView> sin que afecte a los datos de origen subyacentes.</span><span class="sxs-lookup"><span data-stu-id="61e76-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="61e76-106">Los cambios en la vista de colección se reflejan en el <xref:System.Windows.Controls.DataGrid> interfaz de usuario (UI).</span><span class="sxs-lookup"><span data-stu-id="61e76-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="61e76-107">El <xref:System.Windows.Data.CollectionView> clase proporciona agrupar y ordenar funcionalidad para un origen de datos que implementa el <xref:System.Collections.IEnumerable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="61e76-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="61e76-108">El <xref:System.Windows.Data.CollectionViewSource> clase le permite establecer las propiedades de un <xref:System.Windows.Data.CollectionView> de XAML.</span><span class="sxs-lookup"><span data-stu-id="61e76-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="61e76-109">En este ejemplo, una colección de `Task` objetos está enlazado a un <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="61e76-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="61e76-110">El <xref:System.Windows.Data.CollectionViewSource> se utiliza como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="61e76-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="61e76-111">Agrupación, ordenación y filtrado se realizan en el <xref:System.Windows.Data.CollectionViewSource> y se muestran en la <xref:System.Windows.Controls.DataGrid> interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="61e76-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="61e76-112">![Agrupar datos en un control DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="61e76-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="61e76-113">Datos agrupados en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="61e76-114">Usar un CollectionViewSource como ItemsSource</span><span class="sxs-lookup"><span data-stu-id="61e76-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="61e76-115">Grupo, ordenar y filtrar los datos en un <xref:System.Windows.Controls.DataGrid> (control), enlazar la <xref:System.Windows.Controls.DataGrid> a un <xref:System.Windows.Data.CollectionView> que es compatible con estas funciones.</span><span class="sxs-lookup"><span data-stu-id="61e76-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="61e76-116">En este ejemplo, el <xref:System.Windows.Controls.DataGrid> está enlazado a un <xref:System.Windows.Data.CollectionViewSource> que proporciona estas funciones para un <xref:System.Collections.Generic.List%601> de `Task` objetos.</span><span class="sxs-lookup"><span data-stu-id="61e76-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="61e76-117">Para enlazar un control DataGrid a una CollectionViewSource</span><span class="sxs-lookup"><span data-stu-id="61e76-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="61e76-118">Crear una colección de datos que implementa el <xref:System.Collections.IEnumerable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="61e76-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="61e76-119">Si usa <xref:System.Collections.Generic.List%601> para crear la colección, debe crear una nueva clase que hereda de <xref:System.Collections.Generic.List%601> en lugar de crear instancias de una instancia de <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="61e76-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="61e76-120">Esto le permite enlazar los datos a la colección en XAML.</span><span class="sxs-lookup"><span data-stu-id="61e76-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61e76-121">Deben implementar los objetos de la colección el <xref:System.ComponentModel.INotifyPropertyChanged> interfaz modificado y la <xref:System.ComponentModel.IEditableObject> interfaz en orden para el <xref:System.Windows.Controls.DataGrid> responder correctamente a los cambios de propiedad y modificaciones.</span><span class="sxs-lookup"><span data-stu-id="61e76-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="61e76-122">Para más información, consulte [Cómo: Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="61e76-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="61e76-123">En XAML, cree una instancia de la clase de colección y establecer el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="61e76-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="61e76-124">En XAML, cree una instancia de la <xref:System.Windows.Data.CollectionViewSource> clase, establezca el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md)y establezca la instancia de la clase de colección como el <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="61e76-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="61e76-125">Cree una instancia de la <xref:System.Windows.Controls.DataGrid> clase y establezca la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad a la <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="61e76-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="61e76-126">Para tener acceso a la <xref:System.Windows.Data.CollectionViewSource> desde el código, utilice la <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> método para obtener una referencia a la <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="61e76-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="61e76-127">Agrupar elementos en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="61e76-128">Para especificar cómo se agrupan los elementos en una <xref:System.Windows.Controls.DataGrid>, usa el <xref:System.Windows.Data.PropertyGroupDescription> tipo para agrupar los elementos en la vista del origen.</span><span class="sxs-lookup"><span data-stu-id="61e76-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="61e76-129">Para agrupar elementos en un control DataGrid con XAML</span><span class="sxs-lookup"><span data-stu-id="61e76-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="61e76-130">Crear un <xref:System.Windows.Data.PropertyGroupDescription> que especifica la propiedad para realizar la agrupación.</span><span class="sxs-lookup"><span data-stu-id="61e76-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="61e76-131">Puede especificar la propiedad en XAML o en código.</span><span class="sxs-lookup"><span data-stu-id="61e76-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="61e76-132">En XAML, establezca la <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> para el nombre de la propiedad para realizar la agrupación.</span><span class="sxs-lookup"><span data-stu-id="61e76-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="61e76-133">En el código, pase el nombre de la propiedad para agrupar por para el constructor.</span><span class="sxs-lookup"><span data-stu-id="61e76-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="61e76-134">Agregar el <xref:System.Windows.Data.PropertyGroupDescription> a la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> colección.</span><span class="sxs-lookup"><span data-stu-id="61e76-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="61e76-135">Agregar instancias adicionales de <xref:System.Windows.Data.PropertyGroupDescription> a la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección para agregar más niveles de agrupación.</span><span class="sxs-lookup"><span data-stu-id="61e76-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="61e76-136">Para quitar un grupo, quite el <xref:System.Windows.Data.PropertyGroupDescription> desde el <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="61e76-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="61e76-137">Para quitar todos los grupos, llame a la <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> método de la <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="61e76-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="61e76-138">Cuando se agrupan los elementos en el <xref:System.Windows.Controls.DataGrid>, puede definir un <xref:System.Windows.Controls.GroupStyle> que especifica la apariencia de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="61e76-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="61e76-139">Aplicar el <xref:System.Windows.Controls.GroupStyle> agregándolo a la <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> colección del control DataGrid.</span><span class="sxs-lookup"><span data-stu-id="61e76-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="61e76-140">Si tiene varios niveles de agrupación, puede aplicar diferentes estilos a cada nivel de grupo.</span><span class="sxs-lookup"><span data-stu-id="61e76-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="61e76-141">Se aplican los estilos en el orden en que se definen.</span><span class="sxs-lookup"><span data-stu-id="61e76-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="61e76-142">Por ejemplo, si define dos estilos, la primera se aplicarán a los grupos de fila de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="61e76-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="61e76-143">El segundo estilo será aplicada a todos los grupos de filas en el segundo nivel e inferior.</span><span class="sxs-lookup"><span data-stu-id="61e76-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="61e76-144">El <xref:System.Windows.FrameworkElement.DataContext%2A> de la <xref:System.Windows.Controls.GroupStyle> es el <xref:System.Windows.Data.CollectionViewGroup> que representa el grupo.</span><span class="sxs-lookup"><span data-stu-id="61e76-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="61e76-145">Para cambiar la apariencia de los encabezados de grupo de filas</span><span class="sxs-lookup"><span data-stu-id="61e76-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="61e76-146">Crear un <xref:System.Windows.Controls.GroupStyle> que define el aspecto del grupo de filas.</span><span class="sxs-lookup"><span data-stu-id="61e76-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="61e76-147">Coloque el <xref:System.Windows.Controls.GroupStyle> dentro de la `<DataGrid.GroupStyle>` etiquetas.</span><span class="sxs-lookup"><span data-stu-id="61e76-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="61e76-148">Ordenar elementos en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="61e76-149">Para especificar cómo se ordenan los elementos en una <xref:System.Windows.Controls.DataGrid>, usa el <xref:System.ComponentModel.SortDescription> tipo para ordenar los elementos en la vista del origen.</span><span class="sxs-lookup"><span data-stu-id="61e76-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="61e76-150">Para ordenar los elementos en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="61e76-151">Crear un <xref:System.ComponentModel.SortDescription> que especifica la propiedad para ordenar por.</span><span class="sxs-lookup"><span data-stu-id="61e76-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="61e76-152">Puede especificar la propiedad en XAML o en código.</span><span class="sxs-lookup"><span data-stu-id="61e76-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="61e76-153">En XAML, establezca la <xref:System.ComponentModel.SortDescription.PropertyName%2A> para el nombre de la propiedad para ordenar por.</span><span class="sxs-lookup"><span data-stu-id="61e76-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="61e76-154">En el código, pase el nombre de la propiedad para ordenar por y <xref:System.ComponentModel.ListSortDirection> al constructor.</span><span class="sxs-lookup"><span data-stu-id="61e76-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="61e76-155">Agregar el <xref:System.ComponentModel.SortDescription> a la <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> colección.</span><span class="sxs-lookup"><span data-stu-id="61e76-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="61e76-156">Agregar instancias adicionales de <xref:System.ComponentModel.SortDescription> a la <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> colección para ordenar por propiedades adicionales.</span><span class="sxs-lookup"><span data-stu-id="61e76-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="61e76-157">Filtrado de elementos en un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="61e76-158">Para filtrar los elementos en una <xref:System.Windows.Controls.DataGrid> con un <xref:System.Windows.Data.CollectionViewSource>, proporcionar la lógica de filtrado en el controlador para el <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="61e76-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="61e76-159">Para filtrar los elementos de un control DataGrid</span><span class="sxs-lookup"><span data-stu-id="61e76-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="61e76-160">Agregue un controlador para el <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> eventos.</span><span class="sxs-lookup"><span data-stu-id="61e76-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="61e76-161">En el <xref:System.Windows.Data.CollectionViewSource.Filter> controlador de eventos, definir la lógica de filtrado.</span><span class="sxs-lookup"><span data-stu-id="61e76-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="61e76-162">El filtro se aplicará cada vez que se actualice la vista.</span><span class="sxs-lookup"><span data-stu-id="61e76-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="61e76-163">Como alternativa, puede filtrar los elementos de un <xref:System.Windows.Controls.DataGrid> mediante la creación de un método que proporciona la lógica de filtrado y la configuración de la <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> propiedad que se va a aplicar el filtro.</span><span class="sxs-lookup"><span data-stu-id="61e76-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="61e76-164">Para ver un ejemplo de este método, consulte [filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="61e76-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61e76-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61e76-165">Example</span></span>  
 <span data-ttu-id="61e76-166">En el ejemplo siguiente se muestra cómo agrupar, ordenar y filtrar `Task` datos en un <xref:System.Windows.Data.CollectionViewSource> y mostrar agrupados, ordenar y filtrar `Task` datos en un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="61e76-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="61e76-167">El <xref:System.Windows.Data.CollectionViewSource> se utiliza como el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para el <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="61e76-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="61e76-168">Agrupación, ordenación y filtrado se realizan en el <xref:System.Windows.Data.CollectionViewSource> y se muestran en la <xref:System.Windows.Controls.DataGrid> interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="61e76-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="61e76-169">Para probar este ejemplo, debe ajustar el nombre DGGroupSortFilterExample para que coincida con el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="61e76-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="61e76-170">Si está utilizando Visual Basic, debe cambiar el nombre de clase <xref:System.Windows.Window> al siguiente.</span><span class="sxs-lookup"><span data-stu-id="61e76-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61e76-171">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="61e76-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="61e76-172">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="61e76-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="61e76-173">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="61e76-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e76-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="61e76-174">See Also</span></span>  
 [<span data-ttu-id="61e76-175">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="61e76-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="61e76-176">Crear y enlazar a una colección ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="61e76-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="61e76-177">Filtrar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="61e76-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="61e76-178">Ordenar datos en una vista</span><span class="sxs-lookup"><span data-stu-id="61e76-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="61e76-179">Ordenar y agrupar datos mediante una vista en XAML</span><span class="sxs-lookup"><span data-stu-id="61e76-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
