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
ms.openlocfilehash: 2f336d1eb8dcdfec3c3c8059ba865147c6b6c825
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187519"
---
# <a name="listview-overview"></a>Información general sobre ListView
El <xref:System.Windows.Controls.ListView> control proporciona la infraestructura para mostrar un conjunto de elementos de datos en diferentes diseños o vistas. Por ejemplo, es posible que un usuario quiera mostrar elementos de datos en una tabla y, además, ordenar las columnas.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>¿Qué es ListView?  
 El <xref:System.Windows.Controls.ListView> control <xref:System.Windows.Controls.ItemsControl> es un que <xref:System.Windows.Controls.ListBox>se deriva de . Normalmente, sus elementos son miembros de <xref:System.Windows.Controls.ListViewItem> una colección de datos y se representan como objetos. A <xref:System.Windows.Controls.ListViewItem> es <xref:System.Windows.Controls.ContentControl> un y puede contener solo un único elemento secundario. Sin embargo, el elemento secundario puede ser cualquier elemento visual.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Definición de un modo de vista para ListView  
 Para especificar un modo de <xref:System.Windows.Controls.ListView> vista para el <xref:System.Windows.Controls.ListView.View%2A> contenido de un control, establezca la propiedad. Un modo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] de <xref:System.Windows.Controls.GridView>vista que proporciona es , que muestra una colección de elementos de datos en una tabla que tiene columnas personalizables.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.GridView> se <xref:System.Windows.Controls.ListView> muestra cómo definir un parador que muestra información de empleados.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la ilustración siguiente se muestra cómo aparecen los datos en el ejemplo anterior.  
  
 ![Captura de pantalla que muestra un ListView con salida GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 Puede crear un modo de vista personalizado definiendo <xref:System.Windows.Controls.ViewBase> una clase que herede de la clase. La <xref:System.Windows.Controls.ViewBase> clase proporciona la infraestructura que necesita para crear una vista personalizada. Para más información sobre cómo crear una vista personalizada, consulte [Creación de un modo de vista personalizada para un control ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Enlace de datos a un control ListView  
 Utilice <xref:System.Windows.Controls.ItemsControl.Items%2A> las <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedades y para <xref:System.Windows.Controls.ListView> especificar elementos para un control. En el ejemplo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> siguiente se establece la `EmployeeInfoDataSource`propiedad en una colección de datos a la que se llama .  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 En <xref:System.Windows.Controls.GridView>un <xref:System.Windows.Controls.GridViewColumn> , los objetos se enlazan a campos de datos especificados. En el ejemplo <xref:System.Windows.Controls.GridViewColumn> siguiente se enlaza un objeto <xref:System.Windows.Data.Binding> a <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> un campo de datos especificando a para la propiedad.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 También puede especificar <xref:System.Windows.Data.Binding> como parte <xref:System.Windows.DataTemplate> de una definición que utilice para aplicar estilo a las celdas de una columna. En el ejemplo <xref:System.Windows.DataTemplate> siguiente, el <xref:System.Windows.ResourceKey> que <xref:System.Windows.Data.Binding> se <xref:System.Windows.Controls.GridViewColumn>identifica con un establece el for a . Tenga en cuenta que <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> este ejemplo no define el porque <xref:System.Windows.DataTemplate>al hacerlo invalida el enlace especificado por .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Aplicación de un estilo a un control ListView que implementa GridView  
 El <xref:System.Windows.Controls.ListView> control <xref:System.Windows.Controls.ListViewItem> contiene objetos, que representan los elementos de datos que se muestran. Puede usar las propiedades siguientes para definir el contenido y el estilo de los elementos de datos:  
  
- En <xref:System.Windows.Controls.ListView> el control, <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>utilice <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> las propiedades , , y .  
  
- En <xref:System.Windows.Controls.ListViewItem> el control, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> use las propiedades y.  
  
 Para evitar problemas de <xref:System.Windows.Controls.GridView>alineación entre <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> celdas en un , no utilice el <xref:System.Windows.Controls.ListView>para establecer propiedades o agregar contenido que afecta al ancho de un elemento en un archivo . Por ejemplo, puede producirse un <xref:System.Windows.FrameworkElement.Margin%2A> problema de <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>alineación al establecer la propiedad en el archivo . Para especificar propiedades o definir contenido que <xref:System.Windows.Controls.GridView>afecte al ancho <xref:System.Windows.Controls.GridView> de los elementos <xref:System.Windows.Controls.GridViewColumn>de un , utilice las propiedades de la clase y sus clases relacionadas, como .  
  
 Para obtener más información <xref:System.Windows.Controls.GridView> sobre cómo usar y sus clases auxiliares, vea [Información general sobre GridView](gridview-overview.md).  
  
 Si define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> un <xref:System.Windows.Controls.ListView> control para un <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>control y <xref:System.Windows.Controls.ContentPresenter> también define un , <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> debe incluir un en el estilo para que el funcione correctamente.  
  
 No utilice <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> las <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> propiedades <xref:System.Windows.Controls.ListView> y para el contenido <xref:System.Windows.Controls.GridView>que se muestra mediante un archivo . Para especificar la alineación del <xref:System.Windows.Controls.GridView>contenido en <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>una columna de un , defina un archivo .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Uso compartido del mismo modo de vista  
 Dos <xref:System.Windows.Controls.ListView> controles no pueden compartir el mismo modo de vista al mismo tiempo. Si intenta utilizar el mismo modo de <xref:System.Windows.Controls.ListView> vista con más de un control, se produce una excepción.  
  
 Para especificar un modo de vista que <xref:System.Windows.Controls.ListView>pueda ser utilizado simultáneamente por más de uno, utilice plantillas o estilos.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Creación de un modo de vista personalizado  
 Las vistas <xref:System.Windows.Controls.GridView> personalizadas como <xref:System.Windows.Controls.ViewBase> se derivan de la clase abstracta, que <xref:System.Windows.Controls.ListViewItem> proporciona las herramientas para mostrar los elementos de datos que se representan como objetos.
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Información general sobre GridView](gridview-overview.md)
- [Temas de información](listview-how-to-topics.md)
- [Controles](../advanced/optimizing-performance-controls.md)
