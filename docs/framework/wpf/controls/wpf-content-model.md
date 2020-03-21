---
title: Modelo de contenido
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
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187402"
---
# <a name="wpf-content-model"></a>Modelo de contenido de WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es una plataforma de presentación que proporciona muchos controles y tipos semejantes a controles cuyo propósito principal es mostrar diferentes tipos de contenido. Para determinar qué control usar o de qué control derivar, debe entender los tipos de objetos que un control determinado puede mostrar mejor.  
  
 En este tema se resume el modelo de contenido para controles y tipos semejantes a controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El modelo de contenido describe el contenido que se puede utilizar en un control. En este tema también se incluyen las propiedades de contenido para cada modelo de contenido. Una propiedad de contenido es aquella que se utiliza para almacenar el contenido del objeto.  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a>Clases que incluyen contenido arbitrario  
 Algunos controles pueden contener un objeto de cualquier <xref:System.DateTime> tipo, como <xref:System.Windows.UIElement> una cadena, un objeto o un que es un contenedor para elementos adicionales. Por ejemplo, <xref:System.Windows.Controls.Button> a puede contener una imagen y algún texto; o <xref:System.Windows.Controls.CheckBox> una puede contener <xref:System.DateTime.Now%2A?displayProperty=nameWithType>el valor de .  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene cuatro clases que pueden incluir contenido arbitrario. En la tabla siguiente se <xref:System.Windows.Controls.Control>enumeran las clases, que heredan de .  
  
|Clase que incluye contenido arbitrario|Contenido|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Un único objeto arbitrario.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Un encabezado y un único elemento; ambos son objetos arbitrarios.|  
|<xref:System.Windows.Controls.ItemsControl>|Una colección de objetos arbitrarios.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Un encabezado y una colección de elementos; todos ellos son objetos arbitrarios.|  
  
 Los controles que heredan de estas clases pueden incluir el mismo tipo de contenido y tratarlo de la misma manera. En la ilustración siguiente se muestra un control de cada modelo de contenido que contiene una imagen y texto:  
  
 ![Captura de pantalla que muestra cuatro controles diferentes, uno de cada modelo de contenido.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Controles que incluyen un único objeto arbitrario  
 La <xref:System.Windows.Controls.ContentControl> clase contiene una sola pieza de contenido arbitrario. Su propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>content es . Los siguientes controles <xref:System.Windows.Controls.ContentControl> heredan de su modelo de contenido y los usan:  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 La siguiente ilustración <xref:System.Windows.Controls.ContentControl.Content%2A> muestra cuatro botones <xref:System.DateTime> cuyo se <xref:System.Windows.Shapes.Rectangle>establece <xref:System.Windows.Controls.Panel> en una <xref:System.Windows.Shapes.Ellipse> cadena, un objeto, un , y un que contiene un y un <xref:System.Windows.Controls.TextBlock>:  
  
 ![Captura de pantalla que muestra cuatro botones con diferentes tipos de contenido.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Para obtener un ejemplo <xref:System.Windows.Controls.ContentControl.Content%2A> de cómo <xref:System.Windows.Controls.ContentControl>establecer la propiedad, vea .  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Controles que incluyen un encabezado y un único objeto arbitrario  
 La <xref:System.Windows.Controls.HeaderedContentControl> clase hereda y <xref:System.Windows.Controls.ContentControl> muestra contenido con un encabezado. Hereda la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A>content, <xref:System.Windows.Controls.ContentControl> , <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> from y define <xref:System.Object>la propiedad que es de tipo ; por lo tanto, ambos pueden ser un objeto arbitrario.  
  
 Los siguientes controles <xref:System.Windows.Controls.HeaderedContentControl> heredan de su modelo de contenido y los usan:  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 En la ilustración siguiente se muestran dos <xref:System.Windows.Controls.TabItem> objetos. El <xref:System.Windows.Controls.TabItem> primero <xref:System.Windows.UIElement> tiene <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> objetos <xref:System.Windows.Controls.ContentControl.Content%2A>como el y el . El <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> se establece <xref:System.Windows.Controls.StackPanel> en <xref:System.Windows.Shapes.Ellipse> un <xref:System.Windows.Controls.TextBlock>que contiene un y un . El <xref:System.Windows.Controls.ContentControl.Content%2A> se establece <xref:System.Windows.Controls.StackPanel> en <xref:System.Windows.Controls.TextBlock> un <xref:System.Windows.Controls.Label>que contiene un y un . El <xref:System.Windows.Controls.TabItem> segundo tiene una <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> cadena <xref:System.Windows.Controls.TextBlock> en <xref:System.Windows.Controls.ContentControl.Content%2A>el y a en el .  
  
 ![TabControl que usa tipos diferentes en el Header propiedad.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Para obtener un ejemplo <xref:System.Windows.Controls.TabItem> de <xref:System.Windows.Controls.HeaderedContentControl>cómo crear objetos, consulte .  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Controles que incluyen una colección de objetos arbitrarios  
 La <xref:System.Windows.Controls.ItemsControl> clase hereda y <xref:System.Windows.Controls.Control> puede contener varios elementos, como cadenas, objetos u otros elementos. Sus propiedades <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.ItemsControl.Items%2A>contenido son y . <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>normalmente se usa <xref:System.Windows.Controls.ItemsControl> para rellenar con una colección de datos. Si no desea usar una colección <xref:System.Windows.Controls.ItemsControl>para rellenar el , <xref:System.Windows.Controls.ItemsControl.Items%2A> puede agregar elementos mediante la propiedad.  
  
 Los siguientes controles <xref:System.Windows.Controls.ItemsControl> heredan de su modelo de contenido y los usan:  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 En la ilustración siguiente se muestra un <xref:System.Windows.Controls.ListBox> que contiene estos tipos de elementos:  
  
- Una cadena.  
  
- Objeto <xref:System.DateTime> .  
  
- <xref:System.Windows.UIElement>.  
  
- A <xref:System.Windows.Controls.Panel> que <xref:System.Windows.Shapes.Ellipse> contiene <xref:System.Windows.Controls.TextBlock>un y un .  
  
 ![Captura de pantalla que muestra un ListBox con cuatro tipos de contenido.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Controles que incluyen un encabezado y una colección de objetos arbitrarios  
 La <xref:System.Windows.Controls.HeaderedItemsControl> clase hereda <xref:System.Windows.Controls.ItemsControl> y puede contener varios elementos, como cadenas, objetos u otros elementos, y un encabezado. Hereda las <xref:System.Windows.Controls.ItemsControl> propiedades <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>de <xref:System.Windows.Controls.ItemsControl.Items%2A>contenido , , <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> y , y define la propiedad que puede ser un objeto arbitrario.  
  
 Los siguientes controles <xref:System.Windows.Controls.HeaderedItemsControl> heredan de su modelo de contenido y los usan:  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Clases que incluyen una colección de objetos UIElement  
 La <xref:System.Windows.Controls.Panel> clase posiciona y <xref:System.Windows.UIElement> organiza los objetos secundarios. Su propiedad <xref:System.Windows.Controls.Panel.Children%2A>content es .  
  
 Las clases siguientes <xref:System.Windows.Controls.Panel> heredan de la clase y utilizan su modelo de contenido:  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 Para más información, consulte [Información general sobre elementos Panel](panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>Clases que afectan a la apariencia de un objeto UIElement  
 La <xref:System.Windows.Controls.Decorator> clase aplica efectos visuales <xref:System.Windows.UIElement>sobre o alrededor de un solo elemento secundario. Su propiedad <xref:System.Windows.Controls.Decorator.Child%2A>content es . Las clases <xref:System.Windows.Controls.Decorator> siguientes heredan y usan su modelo de contenido:  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 La siguiente ilustración muestra un <xref:System.Windows.Controls.TextBox> que <xref:System.Windows.Controls.Border> tiene (está decorado con) un a su alrededor.  
  
 ![TextBox con borde negro](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
TextBlock con borde  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Clases que proporcionan comentarios visuales sobre un objeto UIElement  
 La <xref:System.Windows.Documents.Adorner> clase proporciona indicaciones visuales a un usuario. Por ejemplo, <xref:System.Windows.Documents.Adorner> utilice un para agregar identificadores funcionales a los elementos o proporcionar información de estado sobre un control. La <xref:System.Windows.Documents.Adorner> clase proporciona un marco de trabajo para que pueda crear sus propios adornos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no proporciona ningún adorno implementado. Para más información, consulte [Información general sobre adornos](adorners-overview.md).  
  
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
 Se pueden usar varias clases para mostrar texto sin formato o con él. Puede utilizar <xref:System.Windows.Controls.TextBlock> para mostrar pequeñas cantidades de texto. Si desea mostrar grandes cantidades de <xref:System.Windows.Controls.FlowDocumentReader>texto, utilice los controles , <xref:System.Windows.Controls.FlowDocumentPageViewer>o . <xref:System.Windows.Controls.FlowDocumentScrollViewer>  
  
 Tiene <xref:System.Windows.Controls.TextBlock> dos propiedades <xref:System.Windows.Controls.TextBlock.Text%2A> de <xref:System.Windows.Controls.TextBlock.Inlines%2A>contenido: y . Cuando desea mostrar texto que usa <xref:System.Windows.Controls.TextBlock.Text%2A> un formato coherente, la propiedad suele ser su mejor opción. Si planea usar un formato diferente en <xref:System.Windows.Controls.TextBlock.Inlines%2A> todo el texto, utilice la propiedad. La <xref:System.Windows.Controls.TextBlock.Inlines%2A> propiedad es <xref:System.Windows.Documents.Inline> una colección de objetos, que especifican cómo dar formato al texto.  
  
 En la tabla siguiente <xref:System.Windows.Controls.FlowDocumentReader>se <xref:System.Windows.Controls.FlowDocumentPageViewer>muestra <xref:System.Windows.Controls.FlowDocumentScrollViewer> la propiedad content para , , y clases.  
  
|Control|Propiedad de contenido|Tipo de propiedad de contenido|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Documento|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Documento|<xref:System.Windows.Documents.FlowDocument>|  
  
 Implementa <xref:System.Windows.Documents.FlowDocument> la <xref:System.Windows.Documents.IDocumentPaginatorSource> interfaz; por lo tanto, las <xref:System.Windows.Documents.FlowDocument> tres clases pueden tomar un como contenido.  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a>Clases que dan formato al texto  
 <xref:System.Windows.Documents.TextElement>y sus clases relacionadas le permiten dar formato al texto. <xref:System.Windows.Documents.TextElement>objetos contienen <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> da formato al texto y a los objetos. Los dos tipos <xref:System.Windows.Documents.TextElement> principales <xref:System.Windows.Documents.Block> de <xref:System.Windows.Documents.Inline> objetos son elementos y elementos. Un <xref:System.Windows.Documents.Block> elemento representa un bloque de texto, como un párrafo o una lista. Un <xref:System.Windows.Documents.Inline> elemento representa una parte del texto de un bloque. Muchas <xref:System.Windows.Documents.Inline> clases especifican el formato del texto al que se aplican. Cada <xref:System.Windows.Documents.TextElement> uno tiene su propio modelo de contenido. Para más información, consulte [Información general sobre el modelo de contenido de TextElement](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>Consulte también

- [Avanzadas](../advanced/index.md)
