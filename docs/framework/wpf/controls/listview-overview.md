---
title: Información general sobre ListView
description: Obtenga información sobre el control Windows Presentation Foundation ListView, que proporciona la infraestructura para mostrar los elementos de datos en diferentes diseños o vistas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ListView
- ListView controls [WPF], about ListView control
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
ms.openlocfilehash: 419c6216f0af696ec71e7607c79c2db637caa785
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164567"
---
# <a name="listview-overview"></a>Información general sobre ListView
El <xref:System.Windows.Controls.ListView> control proporciona la infraestructura para mostrar un conjunto de elementos de datos en diferentes diseños o vistas. Por ejemplo, es posible que un usuario quiera mostrar elementos de datos en una tabla y, además, ordenar las columnas.  

<a name="WhatisaListView"></a>
## <a name="what-is-a-listview"></a>¿Qué es ListView?  
 El <xref:System.Windows.Controls.ListView> control es un <xref:System.Windows.Controls.ItemsControl> que se deriva de <xref:System.Windows.Controls.ListBox> . Normalmente, sus elementos son miembros de una recopilación de datos y se representan como <xref:System.Windows.Controls.ListViewItem> objetos. Un <xref:System.Windows.Controls.ListViewItem> es un <xref:System.Windows.Controls.ContentControl> y solo puede contener un elemento secundario. Sin embargo, el elemento secundario puede ser cualquier elemento visual.  
  
<a name="DefiningaListViewView"></a>
## <a name="defining-a-view-mode-for-a-listview"></a>Definición de un modo de vista para ListView  
 Para especificar un modo de vista para el contenido de un <xref:System.Windows.Controls.ListView> control, establezca la <xref:System.Windows.Controls.ListView.View%2A> propiedad. Un modo de vista que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona es <xref:System.Windows.Controls.GridView> , que muestra una colección de elementos de datos de una tabla que tiene columnas personalizables.  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.GridView> para un <xref:System.Windows.Controls.ListView> control que muestra información de empleado.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 En la ilustración siguiente se muestra cómo aparecen los datos en el ejemplo anterior.  
  
 ![Captura de pantalla que muestra un control ListView con resultados de GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
 Puede crear un modo de vista personalizado definiendo una clase que herede de la <xref:System.Windows.Controls.ViewBase> clase. La <xref:System.Windows.Controls.ViewBase> clase proporciona la infraestructura que necesita para crear una vista personalizada. Para más información sobre cómo crear una vista personalizada, consulte [Creación de un modo de vista personalizada para un control ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="BindingDatatoaListView"></a>
## <a name="binding-data-to-a-listview"></a>Enlace de datos a un control ListView  
 Utilice las <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedades y para especificar los elementos de un <xref:System.Windows.Controls.ListView> control. En el ejemplo siguiente se establece la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad en una colección de datos a la que se llama `EmployeeInfoDataSource` .  
  
 [!code-xaml[ListViewCode#ItemsSource](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 En <xref:System.Windows.Controls.GridView> , <xref:System.Windows.Controls.GridViewColumn> los objetos se enlazan a los campos de datos especificados. En el ejemplo siguiente se enlaza un <xref:System.Windows.Controls.GridViewColumn> objeto a un campo de datos especificando un <xref:System.Windows.Data.Binding> para la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xaml[ListViewCode#GridViewColumnProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 También puede especificar <xref:System.Windows.Data.Binding> como parte de una <xref:System.Windows.DataTemplate> definición que se utiliza para aplicar estilo a las celdas de una columna. En el ejemplo siguiente, el <xref:System.Windows.DataTemplate> que se identifica con <xref:System.Windows.ResourceKey> establece el <xref:System.Windows.Data.Binding> para un <xref:System.Windows.Controls.GridViewColumn> . Tenga en cuenta que en este ejemplo no se define <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> porque al hacerlo se invalida el enlace especificado por <xref:System.Windows.DataTemplate> .  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>
## <a name="styling-a-listview-that-implements-a-gridview"></a>Aplicación de un estilo a un control ListView que implementa GridView  
 El <xref:System.Windows.Controls.ListView> control contiene <xref:System.Windows.Controls.ListViewItem> objetos, que representan los elementos de datos que se muestran. Puede usar las propiedades siguientes para definir el contenido y el estilo de los elementos de datos:  
  
- En el <xref:System.Windows.Controls.ListView> control, utilice las <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> propiedades, y <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> .  
  
- En el <xref:System.Windows.Controls.ListViewItem> control, use las <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> propiedades y.  
  
 Para evitar problemas de alineación entre las celdas de un <xref:System.Windows.Controls.GridView> , no use <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para establecer propiedades ni para agregar contenido que afecte al ancho de un elemento de <xref:System.Windows.Controls.ListView> . Por ejemplo, puede producirse un problema de alineación al establecer la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad en <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . Para especificar las propiedades o definir el contenido que afecta al ancho de los elementos de un <xref:System.Windows.Controls.GridView> , utilice las propiedades de la <xref:System.Windows.Controls.GridView> clase y sus clases relacionadas, como <xref:System.Windows.Controls.GridViewColumn> .  
  
 Para obtener más información sobre cómo usar <xref:System.Windows.Controls.GridView> y sus clases auxiliares, vea [información general sobre GridView](gridview-overview.md).  
  
 Si define un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para un <xref:System.Windows.Controls.ListView> control y también define <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , debe incluir un <xref:System.Windows.Controls.ContentPresenter> en el estilo para <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> que funcione correctamente.  
  
 No use las <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propiedades y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> para el <xref:System.Windows.Controls.ListView> contenido que se muestra mediante <xref:System.Windows.Controls.GridView> . Para especificar la alineación del contenido de una columna de <xref:System.Windows.Controls.GridView> , defina un <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> .  
  
<a name="UsingtheSameViewMoreThanOnce"></a>
## <a name="sharing-the-same-view-mode"></a>Uso compartido del mismo modo de vista  
 Dos <xref:System.Windows.Controls.ListView> controles no pueden compartir el mismo modo de vista al mismo tiempo. Si intenta usar el mismo modo de vista con más de un <xref:System.Windows.Controls.ListView> control, se produce una excepción.  
  
 Para especificar un modo de vista que pueda ser utilizado simultáneamente por más de un <xref:System.Windows.Controls.ListView> , utilice plantillas o estilos.
  
<a name="CreatingaCustomView"></a>
## <a name="creating-a-custom-view-mode"></a>Creación de un modo de vista personalizado  
 Las vistas personalizadas como <xref:System.Windows.Controls.GridView> se derivan de la <xref:System.Windows.Controls.ViewBase> clase abstracta, que proporciona las herramientas para mostrar los elementos de datos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos.
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.GridView>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Data.Binding>
- [Información general sobre GridView](gridview-overview.md)
- [Temas "Cómo..."](listview-how-to-topics.md)
- [Controles](../advanced/optimizing-performance-controls.md)
