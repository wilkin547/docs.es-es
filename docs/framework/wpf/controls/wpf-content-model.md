---
title: Modelo de contenido de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: 4f866e0366a7781c287b3ebae7b668c2b296a5cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134613"
---
# <a name="wpf-content-model"></a>Modelo de contenido de WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es una plataforma de presentación que proporciona muchos controles y tipos semejantes a controles cuyo propósito principal es mostrar diferentes tipos de contenido. Para determinar qué control usar o de qué control derivar, debe entender los tipos de objetos que un control determinado puede mostrar mejor.  
  
 En este tema se resume el modelo de contenido para controles y tipos semejantes a controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El modelo de contenido describe el contenido que se puede utilizar en un control. En este tema también se incluyen las propiedades de contenido para cada modelo de contenido. Una propiedad de contenido es aquella que se utiliza para almacenar el contenido del objeto.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>Clases que incluyen contenido arbitrario  
 Algunos controles pueden contener un objeto de cualquier tipo, como una cadena, un <xref:System.DateTime> objeto, o un <xref:System.Windows.UIElement> que es un contenedor para elementos adicionales. Por ejemplo, un <xref:System.Windows.Controls.Button> puede contener una imagen y algo de texto; o un <xref:System.Windows.Controls.CheckBox> puede contener el valor de <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene cuatro clases que pueden incluir contenido arbitrario. La tabla siguiente enumeran las clases que heredan de <xref:System.Windows.Controls.Control>.  
  
|Clase que incluye contenido arbitrario|Contenido|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Un único objeto arbitrario.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Un encabezado y un único elemento; ambos son objetos arbitrarios.|  
|<xref:System.Windows.Controls.ItemsControl>|Una colección de objetos arbitrarios.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Un encabezado y una colección de elementos; todos ellos son objetos arbitrarios.|  
  
 Los controles que heredan de estas clases pueden incluir el mismo tipo de contenido y tratarlo de la misma manera. La siguiente ilustración muestra un control de cada modelo de contenido que contiene una imagen y texto:  
  
 ![Captura de pantalla que muestra cuatro controles diferentes, uno de cada modelo de contenido.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Controles que incluyen un único objeto arbitrario  
 La <xref:System.Windows.Controls.ContentControl> clase contiene un único fragmento de contenido arbitrario. Su propiedad de contenido es <xref:System.Windows.Controls.ContentControl.Content%2A>. Los siguientes controles heredan de <xref:System.Windows.Controls.ContentControl> y utilizan su modelo de contenido:  
  
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
  
 La siguiente ilustración muestra cuatro botones cuya propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> está establecida en una cadena, un <xref:System.DateTime> objeto, un <xref:System.Windows.Shapes.Rectangle>y un <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>:  
  
 ![Captura de pantalla que muestra cuatro botones con diferentes tipos de contenido.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Para obtener un ejemplo de cómo establecer el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad, vea <xref:System.Windows.Controls.ContentControl>.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Controles que incluyen un encabezado y un único objeto arbitrario  
 El <xref:System.Windows.Controls.HeaderedContentControl> clase hereda de <xref:System.Windows.Controls.ContentControl> y muestra contenido con un encabezado. Hereda la propiedad de contenido, <xref:System.Windows.Controls.ContentControl.Content%2A>, desde <xref:System.Windows.Controls.ContentControl> y define la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> propiedad que es de tipo <xref:System.Object>; por lo tanto, ambos pueden ser un objeto arbitrario.  
  
 Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedContentControl> y utilizan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 La siguiente ilustración muestra dos <xref:System.Windows.Controls.TabItem> objetos. La primera <xref:System.Windows.Controls.TabItem> tiene <xref:System.Windows.UIElement> objetos como el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y <xref:System.Windows.Controls.ContentControl.Content%2A>. El <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> está establecido en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>. El <xref:System.Windows.Controls.ContentControl.Content%2A> está establecido en un <xref:System.Windows.Controls.StackPanel> que contiene un <xref:System.Windows.Controls.TextBlock> y un <xref:System.Windows.Controls.Label>. El segundo <xref:System.Windows.Controls.TabItem> tiene una cadena el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y un <xref:System.Windows.Controls.TextBlock> en el <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![TabControl que usa tipos diferentes en la propiedad de encabezado.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Para obtener un ejemplo de cómo crear <xref:System.Windows.Controls.TabItem> objetos, vea <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Controles que incluyen una colección de objetos arbitrarios  
 El <xref:System.Windows.Controls.ItemsControl> clase hereda de <xref:System.Windows.Controls.Control> y puede contener varios elementos, como cadenas, objetos u otros elementos. Sus propiedades de contenido son <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> y <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Normalmente se usa para rellenar el <xref:System.Windows.Controls.ItemsControl> con una colección de datos. Si no desea usar una colección para rellenar el <xref:System.Windows.Controls.ItemsControl>, puede agregar elementos mediante el <xref:System.Windows.Controls.ItemsControl.Items%2A> propiedad.  
  
 Los siguientes controles heredan de <xref:System.Windows.Controls.ItemsControl> y utilizan su modelo de contenido:  
  
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
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.ListBox> que contiene estos tipos de elementos:  
  
-   Una cadena.  
  
-   Objeto <xref:System.DateTime>.  
  
-   Objeto <xref:System.Windows.UIElement>.  
  
-   Un <xref:System.Windows.Controls.Panel> que contiene un <xref:System.Windows.Shapes.Ellipse> y un <xref:System.Windows.Controls.TextBlock>.  
  
 ![Captura de pantalla que muestra un control ListBox con cuatro tipos de contenido.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Controles que incluyen un encabezado y una colección de objetos arbitrarios  
 El <xref:System.Windows.Controls.HeaderedItemsControl> clase hereda de <xref:System.Windows.Controls.ItemsControl> y puede contener varios elementos, como cadenas, objetos, o un encabezado y otros elementos. Hereda el <xref:System.Windows.Controls.ItemsControl> propiedades, del contenido <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, y <xref:System.Windows.Controls.ItemsControl.Items%2A>, y define la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad que puede ser un objeto arbitrario.  
  
 Los siguientes controles heredan de <xref:System.Windows.Controls.HeaderedItemsControl> y utilizan su modelo de contenido:  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Clases que incluyen una colección de objetos UIElement  
 El <xref:System.Windows.Controls.Panel> clase coloca y organiza secundarios <xref:System.Windows.UIElement> objetos. Su propiedad de contenido es <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Las siguientes clases heredan de la <xref:System.Windows.Controls.Panel> clase y utilizan su modelo de contenido:  
  
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
  
 Para más información, consulte [Información general sobre elementos Panel](panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>Clases que afectan a la apariencia de un objeto UIElement  
 El <xref:System.Windows.Controls.Decorator> clase aplica efectos visuales en o alrededor de un único elemento secundario <xref:System.Windows.UIElement>. Su propiedad de contenido es <xref:System.Windows.Controls.Decorator.Child%2A>. Las siguientes clases heredan de <xref:System.Windows.Controls.Decorator> y utilizan su modelo de contenido:  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.TextBox> que tiene (está decorado con) un <xref:System.Windows.Controls.Border> alrededor de ella.  
  
 ![TextBox con borde negro](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
TextBlock con borde  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Clases que proporcionan comentarios visuales sobre un objeto UIElement  
 La <xref:System.Windows.Documents.Adorner> clase proporciona indicaciones visuales a un usuario. Por ejemplo, use un <xref:System.Windows.Documents.Adorner> para agregar controladores funcionales a elementos o proporcionar información de estado sobre un control. La <xref:System.Windows.Documents.Adorner> clase proporciona un marco para que pueda crear sus propios adornos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona ningún adorno implementado. Para más información, consulte [Información general sobre adornos](adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a>Clases que permiten a los usuarios escribir texto  
 WPF proporciona tres controles principales que permiten a los usuarios escribir texto. Cada control muestra el texto de forma diferente. En la tabla siguiente, se muestran estos tres controles relacionados con el texto, sus funcionalidades cuando muestran texto y las propiedades que contienen el texto del control.  
  
|Control|El texto se muestra como|Propiedad de contenido|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|Texto sin formato|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Texto con formato|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Texto oculto (se enmascaran los caracteres)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a>Clases que muestran el texto  
 Se pueden usar varias clases para mostrar texto sin formato o con él. Puede usar <xref:System.Windows.Controls.TextBlock> para mostrar pequeñas cantidades de texto. Si desea mostrar grandes cantidades de texto, use la <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, o <xref:System.Windows.Controls.FlowDocumentScrollViewer> controles.  
  
 El <xref:System.Windows.Controls.TextBlock> tiene dos propiedades de contenido: <xref:System.Windows.Controls.TextBlock.Text%2A> y <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Cuando desea mostrar el texto que usa un formato coherente, la <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad suele ser la mejor opción. Si piensa utilizar formatos diferentes en todo el texto, utilice el <xref:System.Windows.Controls.TextBlock.Inlines%2A> propiedad. El <xref:System.Windows.Controls.TextBlock.Inlines%2A> propiedad es una colección de <xref:System.Windows.Documents.Inline> objetos, que especifican cómo dar formato al texto.  
  
 La tabla siguiente muestra la propiedad de contenido para <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, y <xref:System.Windows.Controls.FlowDocumentScrollViewer> clases.  
  
|Control|Propiedad de contenido|Tipo de propiedad de contenido|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Documento|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
  
 El <xref:System.Windows.Documents.FlowDocument> implementa el <xref:System.Windows.Documents.IDocumentPaginatorSource> interfaz; así pues, pueden realizar las tres clases un <xref:System.Windows.Documents.FlowDocument> como contenido.  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>Clases que dan formato al texto  
 <xref:System.Windows.Documents.TextElement> y sus clases relacionadas permiten aplicar formato al texto. <xref:System.Windows.Documents.TextElement> los objetos contienen y dar formato al texto en <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos. Los dos tipos principales de <xref:System.Windows.Documents.TextElement> son objetos <xref:System.Windows.Documents.Block> elementos y <xref:System.Windows.Documents.Inline> elementos. Un <xref:System.Windows.Documents.Block> elemento representa un bloque de texto, como un párrafo o una lista. Un <xref:System.Windows.Documents.Inline> elemento representa una parte del texto en un bloque. Muchos <xref:System.Windows.Documents.Inline> clases especifican el formato del texto al que se aplican. Cada <xref:System.Windows.Documents.TextElement> tiene su propio modelo de contenido. Para más información, consulte [Información general sobre el modelo de contenido de TextElement](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Avanzadas](../advanced/index.md)
