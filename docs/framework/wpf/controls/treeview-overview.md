---
title: Introducción a TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 267e870e13d26439e4fbcbba3c5741ff84cabe3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187373"
---
# <a name="treeview-overview"></a>Introducción a TreeView
El <xref:System.Windows.Controls.TreeView> control proporciona una manera de mostrar información en una estructura jerárquica mediante el uso de nodos contraíbles. En este tema <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeViewItem> se presentan los controles y y se proporcionan ejemplos sencillos de su uso.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>¿Qué es TreeView?  
 <xref:System.Windows.Controls.TreeView>es <xref:System.Windows.Controls.ItemsControl> un que anida los <xref:System.Windows.Controls.TreeViewItem> elementos mediante el uso de controles. En el ejemplo <xref:System.Windows.Controls.TreeView>siguiente se crea un archivo .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Creación de un control TreeView  
 El <xref:System.Windows.Controls.TreeView> control contiene <xref:System.Windows.Controls.TreeViewItem> una jerarquía de controles. Un <xref:System.Windows.Controls.TreeViewItem> control <xref:System.Windows.Controls.HeaderedItemsControl> es un <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> que <xref:System.Windows.Controls.ItemsControl.Items%2A> tiene un y una colección.  
  
 Si está definiendo <xref:System.Windows.Controls.TreeView> un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]mediante , puede <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> definir explícitamente el contenido de un <xref:System.Windows.Controls.TreeViewItem> control y los elementos que componen su colección. La ilustración anterior muestra este método.  
  
 También puede especificar <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> un como origen de <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> datos y, a continuación, especificar a y para definir el <xref:System.Windows.Controls.TreeViewItem> contenido.  
  
 Para definir el <xref:System.Windows.Controls.TreeViewItem> diseño de un <xref:System.Windows.HierarchicalDataTemplate> control, también puede utilizar objetos. Para obtener más información y un ejemplo, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Si un elemento <xref:System.Windows.Controls.TreeViewItem> no es un control, <xref:System.Windows.Controls.TreeViewItem> se desencierra automáticamente por un control cuando se muestra el <xref:System.Windows.Controls.TreeView> control.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Expandir y contraer un control TreeViewItem  
 Si el usuario <xref:System.Windows.Controls.TreeViewItem>expande <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> un , `true`la propiedad se establece en . También puede expandir o <xref:System.Windows.Controls.TreeViewItem> contraer a sin <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> ninguna `true` acción directa `false` del usuario estableciendo la propiedad en (expandir) o (contraer). Cuando esta propiedad <xref:System.Windows.Controls.TreeViewItem.Expanded> cambia, se produce un evento o. <xref:System.Windows.Controls.TreeViewItem.Collapsed>  
  
 Cuando <xref:System.Windows.FrameworkElement.BringIntoView%2A> se llama al <xref:System.Windows.Controls.TreeViewItem> método <xref:System.Windows.Controls.TreeViewItem> en un <xref:System.Windows.Controls.TreeViewItem> control, los controles primarios y los se expanden. Si <xref:System.Windows.Controls.TreeViewItem> a no es visible <xref:System.Windows.Controls.TreeView> o parcialmente visible, los desplazamientos para hacerlo visible.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Selección de TreeViewItem  
 Cuando un usuario <xref:System.Windows.Controls.TreeViewItem> hace clic en <xref:System.Windows.Controls.TreeViewItem.Selected> un control para <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> seleccionarlo, `true`se produce el evento y su propiedad se establece en . El <xref:System.Windows.Controls.TreeViewItem> también se <xref:System.Windows.Controls.TreeView.SelectedItem%2A> convierte <xref:System.Windows.Controls.TreeView> en el control. Por el contrario, cuando la <xref:System.Windows.Controls.TreeViewItem> selección <xref:System.Windows.Controls.TreeViewItem.Unselected> cambia de <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> un control, `false`se produce su evento y su propiedad se establece en .  
  
 La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad <xref:System.Windows.Controls.TreeView> del control es una propiedad de solo lectura; por lo tanto, no se puede establecer explícitamente. La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad se establece si el <xref:System.Windows.Controls.TreeViewItem> usuario hace <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> clic en `true` un <xref:System.Windows.Controls.TreeViewItem> control o cuando la propiedad se establece en el control.  
  
 Utilice <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> la propiedad <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para <xref:System.Windows.Controls.TreeView.SelectedItem%2A>especificar un archivo . Para obtener más información, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Puede registrar un controlador <xref:System.Windows.Controls.TreeView.SelectedItemChanged> de eventos en el <xref:System.Windows.Controls.TreeViewItem> evento para determinar cuándo cambia un seleccionado. El <xref:System.Windows.RoutedPropertyChangedEventArgs%601> que se proporciona al controlador <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>de eventos especifica el <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, que es la selección anterior, y el , que es la selección actual. Cualquiera de los valores puede ser `null` si la aplicación o el usuario no han realizado una selección anterior o actual.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>Estilo de TreeView  
 El estilo predeterminado <xref:System.Windows.Controls.TreeView> de un <xref:System.Windows.Controls.StackPanel> control lo <xref:System.Windows.Controls.ScrollViewer> coloca dentro de un objeto que contiene un control. Al establecer <xref:System.Windows.FrameworkElement.Width%2A> las <xref:System.Windows.FrameworkElement.Height%2A> propiedades <xref:System.Windows.Controls.TreeView>y de un , <xref:System.Windows.Controls.StackPanel> estos valores <xref:System.Windows.Controls.TreeView>se utilizan para ajustar el tamaño del objeto que muestra el archivo . Si el contenido que se va a <xref:System.Windows.Controls.ScrollViewer> mostrar es mayor que el <xref:System.Windows.Controls.TreeView> área de visualización, se muestra automáticamente para que el usuario pueda desplazarse por el contenido.  
  
 Para personalizar la <xref:System.Windows.Controls.TreeViewItem> apariencia de <xref:System.Windows.FrameworkElement.Style%2A> un control, <xref:System.Windows.Style>establezca la propiedad en un archivo .  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.Control.Foreground%2A> se <xref:System.Windows.Controls.Control.FontSize%2A> muestra cómo <xref:System.Windows.Controls.TreeViewItem> establecer los <xref:System.Windows.FrameworkElement.Style%2A>valores y de propiedad de un control mediante un archivo .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Agregar imágenes y otro contenido a elementos TreeView  
 Puede incluir más de un <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> objeto <xref:System.Windows.Controls.TreeViewItem>en el contenido de un archivo . Para incluir varios <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> objetos en el contenido, encierre <xref:System.Windows.Controls.Panel> los <xref:System.Windows.Controls.StackPanel>objetos dentro de un control de diseño, como a o .  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> se <xref:System.Windows.Controls.TreeViewItem> muestra <xref:System.Windows.Controls.CheckBox> cómo <xref:System.Windows.Controls.TextBlock> definir el de <xref:System.Windows.Controls.DockPanel> a como a y que están encerrados en un control.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 En el ejemplo siguiente <xref:System.Windows.DataTemplate> se muestra <xref:System.Windows.Controls.Image> cómo <xref:System.Windows.Controls.TextBlock> definir un que <xref:System.Windows.Controls.DockPanel> contiene un y un que se incluyen en un control. Puede utilizar <xref:System.Windows.DataTemplate> a para <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> establecer <xref:System.Windows.Controls.TreeViewItem>el archivo o para un archivo .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Temas de información](treeview-how-to-topics.md)
- [Modelo de contenido de WPF](wpf-content-model.md)
