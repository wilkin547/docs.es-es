---
title: Información general sobre ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 5a7e640b7398c2034933688ea6356ef14692f8f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557386"
---
# <a name="listview-overview"></a>Información general sobre ListView
El <xref:System.Windows.Controls.ListView> control proporciona la infraestructura necesaria para mostrar un conjunto de elementos de datos en distintos diseños o vistas. Por ejemplo, es posible que un usuario quiera mostrar elementos de datos en una tabla y, además, ordenar las columnas.  
  
  
<a name="WhatisaListView"></a>   
## <a name="what-is-a-listview"></a>¿Qué es ListView?  
 El <xref:System.Windows.Controls.ListView> control es un <xref:System.Windows.Controls.ItemsControl> que se deriva de <xref:System.Windows.Controls.ListBox>. Normalmente, sus elementos son miembros de una recolección de datos y se representan como <xref:System.Windows.Controls.ListViewItem> objetos. A <xref:System.Windows.Controls.ListViewItem> es un <xref:System.Windows.Controls.ContentControl> y puede contener sólo un único elemento secundario. Sin embargo, el elemento secundario puede ser cualquier elemento visual.  
  
<a name="DefiningaListViewView"></a>   
## <a name="defining-a-view-mode-for-a-listview"></a>Definición de un modo de vista para ListView  
 Para especificar un modo de vista para el contenido de un <xref:System.Windows.Controls.ListView> (control), establecer el <xref:System.Windows.Controls.ListView.View%2A> propiedad. Modo de una vista que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona es <xref:System.Windows.Controls.GridView>, que muestra una colección de elementos de datos en una tabla que tiene columnas personalizables.  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.GridView> para un <xref:System.Windows.Controls.ListView> control que muestra información de los empleados.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la ilustración siguiente se muestra cómo aparecen los datos en el ejemplo anterior.  
  
 ![ListView con salida de GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
 Puede crear un modo de vista personalizada definiendo una clase que hereda de la <xref:System.Windows.Controls.ViewBase> clase. La <xref:System.Windows.Controls.ViewBase> clase proporciona la infraestructura que necesita para crear una vista personalizada. Para más información sobre cómo crear una vista personalizada, consulte [Creación de un modo de vista personalizada para un control ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## <a name="binding-data-to-a-listview"></a>Enlace de datos a un control ListView  
 Use la <xref:System.Windows.Controls.ItemsControl.Items%2A> y <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedades para especificar elementos para una <xref:System.Windows.Controls.ListView> control. El ejemplo siguiente se establece la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad a una recopilación de datos que se denomina `EmployeeInfoDataSource`.  
  
 [!code-xaml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 En un <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> enlazan objetos a los campos de datos especificado. En el ejemplo siguiente se enlaza un <xref:System.Windows.Controls.GridViewColumn> objeto a un campo de datos mediante la especificación de un <xref:System.Windows.Data.Binding> para el <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 También puede especificar un <xref:System.Windows.Data.Binding> como parte de una <xref:System.Windows.DataTemplate> definición que utiliza para definir el estilo de las celdas de una columna. En el ejemplo siguiente, la <xref:System.Windows.DataTemplate> que se identifica con un <xref:System.Windows.ResourceKey> establece la <xref:System.Windows.Data.Binding> para un <xref:System.Windows.Controls.GridViewColumn>. Tenga en cuenta que este ejemplo no define la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> porque al hacerlo por lo que invalida el enlace especificado por <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## <a name="styling-a-listview-that-implements-a-gridview"></a>Aplicación de un estilo a un control ListView que implementa GridView  
 El <xref:System.Windows.Controls.ListView> control contiene <xref:System.Windows.Controls.ListViewItem> objetos que representan los elementos de datos que se muestran. Puede usar las propiedades siguientes para definir el contenido y el estilo de los elementos de datos:  
  
-   En el <xref:System.Windows.Controls.ListView> de control, use la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>, y <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> propiedades.  
  
-   En el <xref:System.Windows.Controls.ListViewItem> de control, use la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> propiedades.  
  
 Para evitar problemas de alineación entre las celdas de un <xref:System.Windows.Controls.GridView>, no utilice la <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para establecer propiedades o agregar contenido que afecta al ancho de un elemento en un <xref:System.Windows.Controls.ListView>. Por ejemplo, puede producirse un problema de alineación al establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Para especificar propiedades o definir contenido que afecta al ancho de los elementos de un <xref:System.Windows.Controls.GridView>, utilice las propiedades de la <xref:System.Windows.Controls.GridView> clase y sus clases relacionadas, como <xref:System.Windows.Controls.GridViewColumn>.  
  
 Para obtener más información sobre cómo usar <xref:System.Windows.Controls.GridView> y sus clases auxiliares, vea el artículo [GridView Overview](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 Si define un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para un <xref:System.Windows.Controls.ListView> controlar y que también definen un <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, debe incluir un <xref:System.Windows.Controls.ContentPresenter> en el estilo en orden para el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> funcione correctamente.  
  
 No utilice la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> propiedades de <xref:System.Windows.Controls.ListView> contenido que se muestra mediante el uso de un <xref:System.Windows.Controls.GridView>. Para especificar la alineación del contenido de una columna de un <xref:System.Windows.Controls.GridView>, defina un <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## <a name="sharing-the-same-view-mode"></a>Uso compartido del mismo modo de vista  
 Dos <xref:System.Windows.Controls.ListView> controles no pueden compartir el mismo modo de vista al mismo tiempo. Si intenta usar el mismo modo de vista con más de una <xref:System.Windows.Controls.ListView> de control, se produce una excepción.  
  
 Para especificar un modo de vista que puede usarse simultáneamente más de un <xref:System.Windows.Controls.ListView>, utilice plantillas o estilos. Para obtener un ejemplo de cómo definir vistas como <xref:System.Windows.FrameworkElement.Resources%2A>, consulte [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
<a name="CreatingaCustomView"></a>   
## <a name="creating-a-custom-view-mode"></a>Creación de un modo de vista personalizado  
 Personalizar vistas como <xref:System.Windows.Controls.GridView> se derivan de la <xref:System.Windows.Controls.ViewBase> clase, que proporciona las herramientas para mostrar los elementos de datos que se representan como abstracta <xref:System.Windows.Controls.ListViewItem> objetos.  
  
 Para ver un ejemplo de un modo de vista personalizada, consulte [Ejemplo de ListView con varias vistas](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GridView>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Data.Binding>  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
