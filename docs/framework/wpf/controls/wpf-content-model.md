---
title: "Modelo de contenido de WPF | Microsoft Docs"
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
  - "clases con contenido arbitrario [WPF], modelo de contenido"
  - "presentación de contenido [WPF], controles"
  - "modelo de contenido [WPF], controles"
  - "ContentControl (clase) [WPF], mostrar contenido"
  - "controles [WPF], mostrar texto"
  - "controles [WPF], aplicar formato a texto"
  - "mostrar contenido [WPF]"
  - "UIElement (clase) [WPF], mostrar contenido"
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Modelo de contenido de WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es una plataforma de presentación que proporciona muchos controles y tipos similares cuyo propósito principal es mostrar distintos tipos de contenido.  Para determinar qué control se debe usar o de qué control hay que derivar, debe entender los tipos de objetos que un control determinado puede mostrar mejor.  
  
 En este tema se resume el modelo de contenido para el control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y los tipos similares.  El modelo de contenido describe qué contenido se puede utilizar en un control. Este tema también incluye las propiedades de contenido para cada modelo de contenido.  Una propiedad de contenido es aquélla que se utiliza para almacenar el contenido del objeto.  
  
   
  
<a name="classes_that_contain_arbitrary_content"></a>   
## Clases que incluyen contenido arbitrario  
 Algunos controles pueden contener un objeto de cualquier tipo, como una cadena, un objeto <xref:System.DateTime> o un <xref:System.Windows.UIElement> que es un contenedor para elementos adicionales.  Por ejemplo, un <xref:System.Windows.Controls.Button> puede contener una imagen y algún texto; o <xref:System.Windows.Controls.CheckBox> puede contener el valor de <xref:System.DateTime.Now%2A?displayProperty=fullName>.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene cuatro clases que pueden incluir contenido arbitrario.  En la tabla siguiente se enumeran las clases que heredan de <xref:System.Windows.Controls.Control>.  
  
|Clases que incluyen contenido arbitrario|Content|  
|----------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Un único objeto arbitrario.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Un encabezado y un único elemento; los dos son objetos arbitrarios.|  
|<xref:System.Windows.Controls.ItemsControl>|Una colección de objetos arbitrarios.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Un encabezado y una colección de elementos; todos son objetos arbitrarios.|  
  
 Los controles que heredan de estas clases pueden incluir el mismo tipo de contenido y tratar el contenido de la misma manera.  En la ilustración siguiente se muestra un control de cada modelo de contenido que contiene una imagen y texto.  
  
 ![Elementos Button, GroupBox, Listbox, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")  
  
### Controles que contienen un único objeto arbitrario  
 La clase <xref:System.Windows.Controls.ContentControl> contiene una parte única de contenido arbitrario.  Su propiedad de contenido es <xref:System.Windows.Controls.ContentControl.Content%2A>.  Los siguientes controles heredan de <xref:System.Windows.Controls.ContentControl> y usan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 En la ilustración se muestran cuatro botones cuya propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> está establecida en una cadena, un objeto <xref:System.DateTime>, un <xref:System.Windows.Shapes.Rectangle> y un <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>.  
  
 ![Cuatro botones](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.png "ControlContentModelButtons")  
Cuatro botones que tienen distintos tipos de contenido  
  
 Para obtener un ejemplo de cómo establecer la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>, vea <xref:System.Windows.Controls.ContentControl>.  
  
### Controles que contienen un encabezado y un único objeto arbitrario  
 La clase <xref:System.Windows.Controls.HeaderedContentControl> hereda de <xref:System.Windows.Controls.ContentControl> y muestra contenido con un encabezado.  Hereda la propiedad de contenido, <xref:System.Windows.Controls.ContentControl.Content%2A>, de <xref:System.Windows.Controls.ContentControl> y define la propiedad <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> que es del tipo <xref:System.Object>; en consecuencia, ambos pueden ser un objeto arbitrario.  
  
 Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedContentControl> y usan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 En la ilustración siguiente se muestran dos objetos <xref:System.Windows.Controls.TabItem>.  El primer <xref:System.Windows.Controls.TabItem> tiene objetos <xref:System.Windows.UIElement> como <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A>.  <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> está establecido en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>.  <xref:System.Windows.Controls.ContentControl.Content%2A> está establecido en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.Label>.  El segundo <xref:System.Windows.Controls.TabItem> tiene una cadena en <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y un <xref:System.Windows.Controls.TextBlock> en <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")  
TabControl que usa tipos diferentes en la propiedad Header  
  
 Para obtener un ejemplo de cómo crear objetos <xref:System.Windows.Controls.TabItem>, vea <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### Controles que contienen una colección de objetos arbitrarios  
 La clase <xref:System.Windows.Controls.ItemsControl> hereda de <xref:System.Windows.Controls.Control> y puede contener varios elementos, como cadenas, objetos u otros elementos.  Sus propiedades de contenido son <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> y <xref:System.Windows.Controls.ItemsControl.Items%2A>.  <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> se suele usar para rellenar <xref:System.Windows.Controls.ItemsControl> con una recolección de datos.  Si no desea emplear una colección para rellenar el <xref:System.Windows.Controls.ItemsControl>, puede agregar elementos mediante la propiedad <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 Los siguientes controles heredan de <xref:System.Windows.Controls.ItemsControl> y usan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 En la ilustración siguiente se muestra un control <xref:System.Windows.Controls.ListBox> que contiene estos tipos de elementos:  
  
-   Una cadena.  
  
-   Un objeto <xref:System.DateTime>.  
  
-   Un <xref:System.Windows.UIElement>.  
  
-   Un <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>.  
  
 ![ListBox con cuatro tipos de contenido](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")  
ListBox que contiene varios tipos de objetos  
  
### Controles que contienen un encabezado y una colección de objetos arbitrarios  
 La clase <xref:System.Windows.Controls.HeaderedItemsControl> hereda de <xref:System.Windows.Controls.ItemsControl> y puede contener varios elementos, como cadenas, objetos u otros elementos, y un encabezado.  Hereda las propiedades de contenido de <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>y <xref:System.Windows.Controls.ItemsControl.Items%2A>, y define la propiedad <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> que puede ser un objeto arbitrario.  
  
 Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedItemsControl> y usan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## Clases que contienen una colección de objetos UIElement  
 La clase <xref:System.Windows.Controls.Panel> coloca y organiza los objetos <xref:System.Windows.UIElement> secundarios.  Su propiedad de contenido es <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Las clases siguientes heredan de la clase <xref:System.Windows.Controls.Panel> y usan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 Para obtener más información, vea [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## Clases que afectan a la apariencia de un objeto UIElement  
 La clase <xref:System.Windows.Controls.Decorator> aplica efectos visuales a un único objeto <xref:System.Windows.UIElement> secundario o alrededor del mismo.  Su propiedad de contenido es <xref:System.Windows.Controls.Decorator.Child%2A>.  Las clases siguientes heredan de <xref:System.Windows.Controls.Decorator> y usan su modelo de contenido:  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 En la ilustración siguiente se muestra un objeto <xref:System.Windows.Controls.TextBox> que tiene \(está decorado con\) un objeto <xref:System.Windows.Controls.Border> alrededor.  
  
 ![TextBox con borde negro](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout\_Border\_around\_TextBox")  
TextBlock que tiene un borde  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## Clases que proporcionan comentarios visuales sobre un objeto UIElement  
 La clase <xref:System.Windows.Documents.Adorner> proporciona indicaciones visuales a un usuario.  Por ejemplo, use un <xref:System.Windows.Documents.Adorner> para agregar controladores funcionales a los elementos o proporcionar información de estado sobre un control.  La clase <xref:System.Windows.Documents.Adorner> proporciona un marco para que pueda crear sus propios adornos.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona ningún adorno implementado.  Para obtener más información, vea [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## Clases que permiten a los usuarios introducir texto  
 WPF proporciona tres controles primarios que permiten a los usuarios introducir texto.  Cada control muestra el texto de manera diferente.  En la tabla siguiente se enumeran estos tres controles relacionados con texto, sus capacidades cuando muestran texto y sus propiedades que contienen el texto del control.  
  
|Control|El texto se muestra como|Propiedad de contenido|  
|-------------|------------------------------|----------------------------|  
|<xref:System.Windows.Controls.TextBox>|Texto sin formato|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Texto con formato|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Texto oculto \(se enmascaran los caracteres\)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## Clases que muestran su texto  
 Se pueden usar varias clases para mostrar texto sin formato o con formato.  Puede emplear <xref:System.Windows.Controls.TextBlock> para mostrar cantidades pequeñas de texto.  Si desea mostrar grandes cantidades de texto, use los controles <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer> o <xref:System.Windows.Controls.FlowDocumentPageViewer>.  
  
 <xref:System.Windows.Controls.TextBlock> tiene dos propiedades de contenido: <xref:System.Windows.Controls.TextBlock.Text%2A> y <xref:System.Windows.Controls.TextBlock.Inlines%2A>.  Cuando se desea mostrar texto que usa un formato coherente, la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> suele ser la mejor opción.  Si piensa usar formato diferente a lo largo del texto, emplee la propiedad <xref:System.Windows.Controls.TextBlock.Inlines%2A>.  La propiedad <xref:System.Windows.Controls.TextBlock.Inlines%2A> es una colección de objetos <xref:System.Windows.Documents.Inline> que especifican cómo se va a dar formato al texto.  
  
 En la siguiente tabla se hace una lista de la propiedad de contenido para <xref:System.Windows.Controls.FlowDocumentReader>, las clases <xref:System.Windows.Controls.FlowDocumentScrollViewer> y <xref:System.Windows.Controls.FlowDocumentPageViewer>.  
  
|Control|Propiedad de contenido|Tipo de propiedad de contenido|  
|-------------|----------------------------|------------------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Documento|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
  
 <xref:System.Windows.Documents.FlowDocument> implementa la interfaz <xref:System.Windows.Documents.IDocumentPaginatorSource>; por tanto, las tres clases pueden tomar un objeto <xref:System.Windows.Documents.FlowDocument> como contenido.  
  
<a name="classes_that_format_text"></a>   
## Clases que dan formato al texto  
 <xref:System.Windows.Documents.TextElement> y sus clases relacionadas le permiten dar formato al texto.  Los objetos <xref:System.Windows.Documents.TextElement> contienen y dan formato al texto de objetos <xref:System.Windows.Documents.FlowDocument> y <xref:System.Windows.Controls.TextBlock>.  Los dos tipos principales de objetos <xref:System.Windows.Documents.TextElement> son elementos <xref:System.Windows.Documents.Block> y <xref:System.Windows.Documents.Inline>.  Un elemento <xref:System.Windows.Documents.Block> representa un bloque de texto, como un párrafo o una lista.  Un elemento <xref:System.Windows.Documents.Inline> representa una parte de texto de un bloque.  Muchas clases <xref:System.Windows.Documents.Inline> especifican el formato para el texto al que se aplican.  Cada <xref:System.Windows.Documents.TextElement> tiene su propio modelo de contenido.  Para obtener más información, vea [Información general sobre el modelo de contenido de TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).  
  
## Vea también  
 [Avanzadas](../../../../docs/framework/wpf/advanced/index.md)