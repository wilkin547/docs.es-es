---
title: "Introducción a TreeView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e5f6b3d0a185754bc0d8d8ee726ca13443ccdc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="treeview-overview"></a>Introducción a TreeView
El <xref:System.Windows.Controls.TreeView> control proporciona una manera de mostrar información en una estructura jerárquica con nodos contraíbles. Este tema se presentan los <xref:System.Windows.Controls.TreeView> y <xref:System.Windows.Controls.TreeViewItem> controla y proporciona ejemplos sencillos de su uso.  
  
  
<a name="Simple_TreeView_Control"></a>   
## <a name="what-is-a-treeview"></a>¿Qué es TreeView?  
 <xref:System.Windows.Controls.TreeView>es un <xref:System.Windows.Controls.ItemsControl> que anida los elementos mediante el uso de <xref:System.Windows.Controls.TreeViewItem> controles. En el ejemplo siguiente se crea un <xref:System.Windows.Controls.TreeView>.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## <a name="creating-a-treeview"></a>Creación de un control TreeView  
 El <xref:System.Windows.Controls.TreeView> control contiene una jerarquía de <xref:System.Windows.Controls.TreeViewItem> controles. A <xref:System.Windows.Controls.TreeViewItem> control es un <xref:System.Windows.Controls.HeaderedItemsControl> que tiene un <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> y un <xref:System.Windows.Controls.ItemsControl.Items%2A> colección.  
  
 Si va a definir un <xref:System.Windows.Controls.TreeView> utilizando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede definir explícitamente el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenido de un <xref:System.Windows.Controls.TreeViewItem> control y los elementos que componen su colección. La ilustración anterior muestra este método.  
  
 También puede especificar un <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> como datos de origen y, a continuación, especifique un <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> y <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> para definir la <xref:System.Windows.Controls.TreeViewItem> contenido.  
  
 Para definir el diseño de un <xref:System.Windows.Controls.TreeViewItem> (control), también puede usar <xref:System.Windows.HierarchicalDataTemplate> objetos. Para obtener más información y un ejemplo, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Si un elemento no es un <xref:System.Windows.Controls.TreeViewItem> (control), se incluye automáticamente por un <xref:System.Windows.Controls.TreeViewItem> controlar cuándo el <xref:System.Windows.Controls.TreeView> se muestra el control.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Expandir y contraer un control TreeViewItem  
 Si el usuario expande un <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> propiedad está establecida en `true`. También puede expandir o contraer un <xref:System.Windows.Controls.TreeViewItem> sin intervención directa del usuario estableciendo la <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> propiedad `true` (expandir) o `false` (contraer). Cuando se cambia esta propiedad, un <xref:System.Windows.Controls.TreeViewItem.Expanded> o <xref:System.Windows.Controls.TreeViewItem.Collapsed> se produce el evento.  
  
 Cuando el <xref:System.Windows.FrameworkElement.BringIntoView%2A> método se llama en una <xref:System.Windows.Controls.TreeViewItem> (control), el <xref:System.Windows.Controls.TreeViewItem> y su elemento primario <xref:System.Windows.Controls.TreeViewItem> expandir controles. Si un <xref:System.Windows.Controls.TreeViewItem> no está visible o parcialmente visible, el <xref:System.Windows.Controls.TreeView> se desplaza para que sea visible.  
  
<a name="TreeViewItem_Selection"></a>   
## <a name="treeviewitem-selection"></a>Selección de TreeViewItem  
 Cuando un usuario hace clic en un <xref:System.Windows.Controls.TreeViewItem> control para seleccionarlo, el <xref:System.Windows.Controls.TreeViewItem.Selected> se produce el evento y su <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> propiedad está establecida en `true`. El <xref:System.Windows.Controls.TreeViewItem> también se convierte en el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de la <xref:System.Windows.Controls.TreeView> control. Por el contrario, cuando cambia la selección de un <xref:System.Windows.Controls.TreeViewItem> (control), su <xref:System.Windows.Controls.TreeViewItem.Unselected> se produce el evento y su <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> propiedad está establecida en `false`.  
  
 El <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad en el <xref:System.Windows.Controls.TreeView> control es una propiedad de solo lectura; por lo tanto, no puede establecerlo explícitamente. El <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad se establece si el usuario hace clic en un <xref:System.Windows.Controls.TreeViewItem> control o cuando el <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> propiedad está establecida en `true` en el <xref:System.Windows.Controls.TreeViewItem> control.  
  
 Use la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad para especificar un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> de un <xref:System.Windows.Controls.TreeView.SelectedItem%2A>. Para obtener más información, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Puede registrar un controlador de eventos en el <xref:System.Windows.Controls.TreeView.SelectedItemChanged> eventos con el fin de determinar cuándo un seleccionado <xref:System.Windows.Controls.TreeViewItem> cambios. El <xref:System.Windows.RoutedPropertyChangedEventArgs%601> proporcionadas para el evento controlador especifica la <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, que es la selección anterior y el <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, que es la selección actual. Cualquiera de los valores puede ser `null` si la aplicación o el usuario no han realizado una selección anterior o actual.  
  
<a name="TreeView_Style"></a>   
## <a name="treeview-style"></a>Estilo de TreeView  
 El estilo predeterminado para un <xref:System.Windows.Controls.TreeView> control lo coloca dentro de un <xref:System.Windows.Controls.StackPanel> objeto que contiene un <xref:System.Windows.Controls.ScrollViewer> control. Al establecer el <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades para un <xref:System.Windows.Controls.TreeView>, estos valores se usan para el tamaño de la <xref:System.Windows.Controls.StackPanel> objeto que muestra la <xref:System.Windows.Controls.TreeView>. Si el contenido que se muestra es mayor que el área de presentación, un <xref:System.Windows.Controls.ScrollViewer> muestra automáticamente para que el usuario puede desplazarse por la <xref:System.Windows.Controls.TreeView> contenido.  
  
 Para personalizar la apariencia de un <xref:System.Windows.Controls.TreeViewItem> de control, establezca la <xref:System.Windows.FrameworkElement.Style%2A> propiedad a una personalizada <xref:System.Windows.Style>.  
  
 En el ejemplo siguiente se muestra cómo establecer el <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontSize%2A> valores de propiedad para un <xref:System.Windows.Controls.TreeViewItem> control mediante el uso de un <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 [!code-xaml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## <a name="adding-images-and-other-content-to-treeview-items"></a>Agregar imágenes y otro contenido a elementos TreeView  
 Puede incluir más de un objeto en el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenido de un <xref:System.Windows.Controls.TreeViewItem>. Para incluir varios objetos en <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de contenido, escríbalo entre los objetos dentro de un control de diseño, como un <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.StackPanel>.  
  
 En el ejemplo siguiente se muestra cómo definir la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de un <xref:System.Windows.Controls.TreeViewItem> como un <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.TextBlock> que se incluyen en un <xref:System.Windows.Controls.DockPanel> control.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.Image> y un <xref:System.Windows.Controls.TextBlock> que se incluyen en un <xref:System.Windows.Controls.DockPanel> control. Puede usar un <xref:System.Windows.DataTemplate> para establecer el <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> o <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> para un <xref:System.Windows.Controls.TreeViewItem>.  
  
 [!code-xaml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)  
 [WPF Content Model](../../../../docs/framework/wpf/controls/wpf-content-model.md) (Modelo de contenido de WPF)
