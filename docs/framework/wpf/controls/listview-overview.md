---
title: "Informaci&#243;n general sobre ListView | Microsoft Docs"
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
  - "controles, ListView"
  - "ListView (controles) [WPF], acerca del control ListView"
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre ListView
El control <xref:System.Windows.Controls.ListView> proporciona la infraestructura necesaria para mostrar un conjunto de elementos de datos en distintos diseños o vistas.  Por ejemplo, un usuario puede desear mostrar los elementos de datos en una tabla y también ordenar sus columnas.  
  
   
  
<a name="WhatisaListView"></a>   
## ¿Qué es un control ListView?  
 El control <xref:System.Windows.Controls.ListView> es un <xref:System.Windows.Controls.ItemsControl> que se deriva de <xref:System.Windows.Controls.ListBox>.  Normalmente, sus elementos son miembros de una recolección de datos y se representan como objetos <xref:System.Windows.Controls.ListViewItem>.  <xref:System.Windows.Controls.ListViewItem> es un control <xref:System.Windows.Controls.ContentControl> que puede contener un solo elemento secundario.  Sin embargo, ese elemento secundario puede ser cualquier elemento visual.  
  
<a name="DefiningaListViewView"></a>   
## Definir un modo de vista para ListView  
 Para especificar un modo de vista para el contenido de un control <xref:System.Windows.Controls.ListView>, se establece la propiedad <xref:System.Windows.Controls.ListView.View%2A>.  Un modo de vista que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona es <xref:System.Windows.Controls.GridView>, que muestra una colección de elementos de datos en una tabla que tiene columnas personalizables.  
  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.GridView> para un control <xref:System.Windows.Controls.ListView> que muestra información de empleados.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la ilustración siguiente se muestra la presentación de los datos del ejemplo anterior.  
  
 ![ListView con resultado GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
 Puede crear un modo de vista personalizado mediante la definición de una clase que herede de la clase <xref:System.Windows.Controls.ViewBase>.  La clase <xref:System.Windows.Controls.ViewBase> proporciona la infraestructura necesaria para crear una vista personalizada.  Para obtener más información acerca de cómo crear una vista personalizada, vea [Crear un modo de vista personalizado para un control ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>   
## Enlazar datos a ListView  
 Use las propiedades <xref:System.Windows.Controls.ItemsControl.Items%2A> y <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para especificar los elementos para un control <xref:System.Windows.Controls.ListView>.  En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> en una recolección de datos que se denomina `EmployeeInfoDataSource`.  
  
 [!code-xml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 En <xref:System.Windows.Controls.GridView>, los objetos <xref:System.Windows.Controls.GridViewColumn> se enlazan a campos de datos específicos.  En el ejemplo siguiente se enlaza un objeto <xref:System.Windows.Controls.GridViewColumn> a un campo de datos al especificar <xref:System.Windows.Data.Binding> para la propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 También puede especificar <xref:System.Windows.Data.Binding> como parte de una definición <xref:System.Windows.DataTemplate> que se usa para definir el estilo de las celdas de una columna.  En el ejemplo siguiente, <xref:System.Windows.DataTemplate> que se identifica con <xref:System.Windows.ResourceKey> establece <xref:System.Windows.Data.Binding> para <xref:System.Windows.Controls.GridViewColumn>.  Observe que en este ejemplo no se define <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> porque, en ese caso, se invalidaría el enlace especificado por <xref:System.Windows.DataTemplate>.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## Aplicar estilos a un control ListView que implementa GridView  
 El control <xref:System.Windows.Controls.ListView> contiene objetos <xref:System.Windows.Controls.ListViewItem>, que representan los elementos de datos que se muestran.  Puede usar las propiedades siguientes para definir el contenido y estilo de los elementos de datos:  
  
-   En el control <xref:System.Windows.Controls.ListView>, use las propiedades <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> y <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.  
  
-   En el control <xref:System.Windows.Controls.ListViewItem>, use las propiedades <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> y <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>.  
  
 Para evitar problemas de alineación entre las celdas en <xref:System.Windows.Controls.GridView>, no utilice <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para establecer propiedades o agregar contenido que afecte al ancho de un elemento de <xref:System.Windows.Controls.ListView>.  Por ejemplo, puede producirse un problema de alineación al establecer la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> en <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>.  Para especificar propiedades o definir contenido que afecta al ancho de los elementos en <xref:System.Windows.Controls.GridView>, utilice las propiedades de la clase <xref:System.Windows.Controls.GridView> y sus clases relacionadas, como <xref:System.Windows.Controls.GridViewColumn>.  
  
 Para obtener más información sobre cómo utilizar <xref:System.Windows.Controls.GridView> y sus clases auxiliares, vea [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md).  
  
 Si define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para un control <xref:System.Windows.Controls.ListView> y también define <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, debe incluir un elemento <xref:System.Windows.Controls.ContentPresenter> en el estilo de manera que <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> funcione correctamente.  
  
 No use las propiedades <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> para contenido de <xref:System.Windows.Controls.ListView> que se muestre mediante <xref:System.Windows.Controls.GridView>.  Para especificar la alineación del contenido de una columna de <xref:System.Windows.Controls.GridView>, defina <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## Compartir el mismo modo de vista  
 Dos controles <xref:System.Windows.Controls.ListView> no pueden compartir al mismo tiempo el mismo modo de vista.  Si intenta utilizar el mismo modo de vista con más de un control <xref:System.Windows.Controls.ListView>, se producirá una excepción.  
  
 Para especificar un modo de vista que puedan usar varios controles <xref:System.Windows.Controls.ListView> simultáneamente, utilice plantillas o estilos.  Para obtener un ejemplo de cómo definir vistas como recursos \(<xref:System.Windows.FrameworkElement.Resources%2A>\), vea [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
<a name="CreatingaCustomView"></a>   
## Crear un modo de vista personalizado  
 Las vistas personalizadas como <xref:System.Windows.Controls.GridView> se derivan de la clase abstracta <xref:System.Windows.Controls.ViewBase>, que proporciona las herramientas necesarias para mostrar elementos de datos que se representan como objetos <xref:System.Windows.Controls.ListViewItem>.  
  
 Para obtener un ejemplo de un modo de vista personalizado, vea [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## Vea también  
 <xref:System.Windows.Controls.GridView>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Data.Binding>   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)