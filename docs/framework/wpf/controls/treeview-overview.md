---
title: "Introducci&#243;n a TreeView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Control (clase), TreeView"
  - "expandir nodo"
  - "TreeView (control), acerca del control TreeView"
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Introducci&#243;n a TreeView
El control <xref:System.Windows.Controls.TreeView> proporciona una manera de mostrar información en una estructura jerárquica con nodos contraíbles.  En este tema se presentan los controles <xref:System.Windows.Controls.TreeView> y <xref:System.Windows.Controls.TreeViewItem> y se proporcionan ejemplos sencillos de su uso.  
  
   
  
<a name="Simple_TreeView_Control"></a>   
## ¿Qué es un control TreeView?  
 <xref:System.Windows.Controls.TreeView> es un control <xref:System.Windows.Controls.ItemsControl> que anida los elementos mediante controles <xref:System.Windows.Controls.TreeViewItem>.  En el ejemplo siguiente se crea un control <xref:System.Windows.Controls.TreeView>.  
  
 [!code-xml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## Crear un control TreeView  
 El control <xref:System.Windows.Controls.TreeView> contiene una jerarquía de controles <xref:System.Windows.Controls.TreeViewItem>.  Un control <xref:System.Windows.Controls.TreeViewItem> es un control <xref:System.Windows.Controls.HeaderedItemsControl> que tiene una colección de propiedades <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 Si va a definir <xref:System.Windows.Controls.TreeView> mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede definir explícitamente el contenido de <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de un control <xref:System.Windows.Controls.TreeViewItem> y los elementos que forman su colección.  En la ilustración anterior se muestra este método.  
  
 También puede especificar <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> como origen de datos y, a continuación, especificar <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> e <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> para definir el contenido de <xref:System.Windows.Controls.TreeViewItem>.  
  
 Para definir el diseño de un control <xref:System.Windows.Controls.TreeViewItem>, puede utilizar también objetos <xref:System.Windows.HierarchicalDataTemplate>.  Para obtener más información y un ejemplo, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Si un elemento no es un control <xref:System.Windows.Controls.TreeViewItem>, se incluye automáticamente en un control <xref:System.Windows.Controls.TreeViewItem> cuando se muestra el control <xref:System.Windows.Controls.TreeView>.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## Expandir y contraer un elemento TreeViewItem  
 Si el usuario expande <xref:System.Windows.Controls.TreeViewItem>, la propiedad <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> se establece en `true`.  También se puede expandir o contraer <xref:System.Windows.Controls.TreeViewItem> sin que el usuario realice ninguna acción directa; para ello, establezca la propiedad <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> en `true` \(para expandir\) o en `false` \(para contraer\).  Cuando esta propiedad cambia, se produce un evento <xref:System.Windows.Controls.TreeViewItem.Expanded> o <xref:System.Windows.Controls.TreeViewItem.Collapsed>.  
  
 Cuando se llama al método <xref:System.Windows.FrameworkElement.BringIntoView%2A> en un control <xref:System.Windows.Controls.TreeViewItem>, éste y sus controles <xref:System.Windows.Controls.TreeViewItem> primarios se expanden.  Si <xref:System.Windows.Controls.TreeViewItem> no está total o parcialmente visible, <xref:System.Windows.Controls.TreeView> se desplaza para hacerlo visible.  
  
<a name="TreeViewItem_Selection"></a>   
## Selección de TreeViewItem  
 Cuando un usuario hace clic en un control <xref:System.Windows.Controls.TreeViewItem> para seleccionarlo, se produce el evento <xref:System.Windows.Controls.TreeViewItem.Selected> y se establece su propiedad <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> en `true`.  Además, <xref:System.Windows.Controls.TreeViewItem> se convierte en el elemento seleccionado \(<xref:System.Windows.Controls.TreeView.SelectedItem%2A>\) del control <xref:System.Windows.Controls.TreeView>.  A la inversa, cuando cambia la selección de un control <xref:System.Windows.Controls.TreeViewItem>, se produce su evento <xref:System.Windows.Controls.TreeViewItem.Unselected> y su propiedad <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> se establece en `false`.  
  
 La propiedad <xref:System.Windows.Controls.TreeView.SelectedItem%2A> del control <xref:System.Windows.Controls.TreeView> es de sólo lectura; por lo tanto, no puede establecerse explícitamente.  La propiedad <xref:System.Windows.Controls.TreeView.SelectedItem%2A> se establece si el usuario hace clic en un control <xref:System.Windows.Controls.TreeViewItem> o cuando la propiedad <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> se establece en `true` en el control <xref:System.Windows.Controls.TreeViewItem>.  
  
 Utilice la propiedad <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> para especificar la propiedad <xref:System.Windows.Controls.TreeView.SelectedValue%2A> de un control <xref:System.Windows.Controls.TreeView.SelectedItem%2A>.  Para obtener más información, vea [Usar SelectedValue, SelectedValuePath y SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Puede registrar un controlador de eventos en el evento <xref:System.Windows.Controls.TreeView.SelectedItemChanged> para determinar cuándo cambia un elemento <xref:System.Windows.Controls.TreeViewItem> seleccionado.  La clase <xref:System.Windows.RoutedPropertyChangedEventArgs%601> que se proporciona al controlador de eventos especifica la propiedad <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, que es la selección anterior, y la propiedad <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, que es la selección actual.  Cualquiera de estos valores puede ser `null` si la aplicación o el usuario no han realizado una selección anterior o actual.  
  
<a name="TreeView_Style"></a>   
## Estilo de TreeView  
 El estilo predeterminado de un control <xref:System.Windows.Controls.TreeView> lo coloca dentro de un objeto <xref:System.Windows.Controls.StackPanel> que contiene un control <xref:System.Windows.Controls.ScrollViewer>.  Cuando se establecen las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> para <xref:System.Windows.Controls.TreeView>, estos valores se utilizan para cambiar el tamaño del objeto <xref:System.Windows.Controls.StackPanel> que muestra el control <xref:System.Windows.Controls.TreeView>.  Si el contenido que se desea mostrar es mayor que el área de presentación, se muestra automáticamente un control <xref:System.Windows.Controls.ScrollViewer>, para que el usuario pueda desplazarse por el contenido de <xref:System.Windows.Controls.TreeView>.  
  
 Para personalizar la apariencia de un control <xref:System.Windows.Controls.TreeViewItem>, establezca la propiedad <xref:System.Windows.FrameworkElement.Style%2A> en un estilo <xref:System.Windows.Style> personalizado.  
  
 En el ejemplo siguiente se muestra cómo establecer los valores de propiedad <xref:System.Windows.Controls.Control.Foreground%2A> y <xref:System.Windows.Controls.Control.FontSize%2A> para un control <xref:System.Windows.Controls.TreeViewItem> mediante <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 [!code-xml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## Agregar imágenes y otro contenido a los elementos de TreeView  
 Puede incluir más de un objeto en el contenido de <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de un elemento <xref:System.Windows.Controls.TreeViewItem>.  Para incluir varios objetos en el contenido de <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>, encierre los objetos en un control de diseño, como <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.StackPanel>.  
  
 En el ejemplo siguiente se muestra cómo definir la propiedad <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de <xref:System.Windows.Controls.TreeViewItem> como una clase <xref:System.Windows.Controls.CheckBox> y una clase <xref:System.Windows.Controls.TextBlock> incluidas en un control <xref:System.Windows.Controls.DockPanel>.  
  
 [!code-xml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 En el ejemplo siguiente se muestra cómo definir una clase <xref:System.Windows.DataTemplate> que contiene un control <xref:System.Windows.Controls.Image> y un control <xref:System.Windows.Controls.TextBlock> incluidos en un control <xref:System.Windows.Controls.DockPanel>.  Puede utilizar <xref:System.Windows.DataTemplate> para establecer <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> o <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> para un elemento <xref:System.Windows.Controls.TreeViewItem>.  
  
 [!code-xml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## Vea también  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)   
 [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)