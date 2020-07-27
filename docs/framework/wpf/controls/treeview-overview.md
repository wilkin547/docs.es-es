---
title: Introducción a TreeView
description: Aprenda cómo el control TreeView Windows Presentation Foundation muestra información en una estructura jerárquica mediante el uso de nodos, incluidos ejemplos sencillos.
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 6ef77febdd3facb7c7e1af566841c2a1aeaff810
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164534"
---
# <a name="treeview-overview"></a>Introducción a TreeView
El <xref:System.Windows.Controls.TreeView> control proporciona una manera de Mostrar información en una estructura jerárquica mediante el uso de nodos contraíbles. En este tema se presentan los <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeViewItem> controles y, y se proporcionan ejemplos sencillos de su uso.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>¿Qué es TreeView?  
 <xref:System.Windows.Controls.TreeView>es un <xref:System.Windows.Controls.ItemsControl> que anida los elementos mediante el uso de <xref:System.Windows.Controls.TreeViewItem> controles. En el ejemplo siguiente se crea un <xref:System.Windows.Controls.TreeView> .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Creación de un control TreeView  
 El <xref:System.Windows.Controls.TreeView> control contiene una jerarquía de <xref:System.Windows.Controls.TreeViewItem> controles. Un <xref:System.Windows.Controls.TreeViewItem> control es un <xref:System.Windows.Controls.HeaderedItemsControl> que tiene un <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> y una <xref:System.Windows.Controls.ItemsControl.Items%2A> colección.  
  
 Si va a definir un <xref:System.Windows.Controls.TreeView> mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , puede definir explícitamente el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenido de un <xref:System.Windows.Controls.TreeViewItem> control y los elementos que componen su colección. La ilustración anterior muestra este método.  
  
 También puede especificar <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> como origen de datos y, a continuación, especificar <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> y <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> para definir el <xref:System.Windows.Controls.TreeViewItem> contenido.  
  
 Para definir el diseño de un <xref:System.Windows.Controls.TreeViewItem> control, también puede utilizar <xref:System.Windows.HierarchicalDataTemplate> objetos. Para obtener más información y un ejemplo, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Si un elemento no es un <xref:System.Windows.Controls.TreeViewItem> control, se adjunta automáticamente a un <xref:System.Windows.Controls.TreeViewItem> control cuando <xref:System.Windows.Controls.TreeView> se muestra el control.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Expandir y contraer un control TreeViewItem  
 Si el usuario expande un <xref:System.Windows.Controls.TreeViewItem> , la <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> propiedad se establece en `true` . También puede expandir o contraer un <xref:System.Windows.Controls.TreeViewItem> sin ninguna acción de usuario directa si establece la <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> propiedad en `true` (expandir) o en `false` (contraer). Cuando esta propiedad cambia, <xref:System.Windows.Controls.TreeViewItem.Expanded> <xref:System.Windows.Controls.TreeViewItem.Collapsed> se produce un evento o.  
  
 Cuando <xref:System.Windows.FrameworkElement.BringIntoView%2A> se llama al método en un <xref:System.Windows.Controls.TreeViewItem> control, se <xref:System.Windows.Controls.TreeViewItem> expanden y sus controles primarios <xref:System.Windows.Controls.TreeViewItem> . Si un <xref:System.Windows.Controls.TreeViewItem> no es visible o parcialmente visible, se <xref:System.Windows.Controls.TreeView> desplaza para que sea visible.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Selección de TreeViewItem  
 Cuando un usuario hace clic en un <xref:System.Windows.Controls.TreeViewItem> control para seleccionarlo, <xref:System.Windows.Controls.TreeViewItem.Selected> se produce el evento y su <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> propiedad se establece en `true` . <xref:System.Windows.Controls.TreeViewItem>También se convierte en el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> del <xref:System.Windows.Controls.TreeView> control. Por el contrario, cuando la selección cambia de un <xref:System.Windows.Controls.TreeViewItem> control, <xref:System.Windows.Controls.TreeViewItem.Unselected> se produce su evento y su <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> propiedad se establece en `false` .  
  
 La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad en el <xref:System.Windows.Controls.TreeView> control es una propiedad de solo lectura; por lo tanto, no se puede establecer explícitamente. La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad se establece si el usuario hace clic en un <xref:System.Windows.Controls.TreeViewItem> control o si la <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> propiedad está establecida en `true` en el <xref:System.Windows.Controls.TreeViewItem> control.  
  
 Utilice la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad para especificar un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> de <xref:System.Windows.Controls.TreeView.SelectedItem%2A> . Para obtener más información, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Puede registrar un controlador de eventos en el <xref:System.Windows.Controls.TreeView.SelectedItemChanged> evento para determinar cuándo se ha realizado un <xref:System.Windows.Controls.TreeViewItem> cambio. El <xref:System.Windows.RoutedPropertyChangedEventArgs%601> que se proporciona al controlador de eventos especifica <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> , que es la selección anterior, y <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> , que es la selección actual. Cualquiera de los valores puede ser `null` si la aplicación o el usuario no han realizado una selección anterior o actual.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>Estilo de TreeView  
 El estilo predeterminado de un <xref:System.Windows.Controls.TreeView> control lo coloca dentro de un <xref:System.Windows.Controls.StackPanel> objeto que contiene un <xref:System.Windows.Controls.ScrollViewer> control. Cuando se establecen las <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> propiedades y de una <xref:System.Windows.Controls.TreeView> , estos valores se utilizan para ajustar el tamaño del <xref:System.Windows.Controls.StackPanel> objeto que muestra el <xref:System.Windows.Controls.TreeView> . Si el contenido que se va a mostrar es mayor que el área de visualización, se <xref:System.Windows.Controls.ScrollViewer> muestra automáticamente para que el usuario pueda desplazarse por el <xref:System.Windows.Controls.TreeView> contenido.  
  
 Para personalizar la apariencia de un <xref:System.Windows.Controls.TreeViewItem> control, establezca la <xref:System.Windows.FrameworkElement.Style%2A> propiedad en un personalizado <xref:System.Windows.Style> .  
  
 En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.Controls.Control.Foreground%2A> los <xref:System.Windows.Controls.Control.FontSize%2A> valores de las propiedades y de un <xref:System.Windows.Controls.TreeViewItem> control mediante <xref:System.Windows.FrameworkElement.Style%2A> .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Agregar imágenes y otro contenido a elementos TreeView  
 Puede incluir más de un objeto en el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenido de <xref:System.Windows.Controls.TreeViewItem> . Para incluir varios objetos en <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> el contenido, incluya los objetos dentro de un control de diseño, como <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.StackPanel> .  
  
 En el ejemplo siguiente se muestra cómo definir el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de un <xref:System.Windows.Controls.TreeViewItem> como <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.TextBlock> que están incluidos en un <xref:System.Windows.Controls.DockPanel> control.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.Image> y un <xref:System.Windows.Controls.TextBlock> que se incluyen en un <xref:System.Windows.Controls.DockPanel> control. Puede utilizar <xref:System.Windows.DataTemplate> para establecer <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> o <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> para <xref:System.Windows.Controls.TreeViewItem> .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Temas "Cómo..."](treeview-how-to-topics.md)
- [Modelo de contenido de WPF](wpf-content-model.md)
