---
title: Información general sobre el control Expander
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: abcc7c48c602aee742959b39bb5244563eaf4d5d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="expander-overview"></a>Información general sobre el control Expander
Un <xref:System.Windows.Controls.Expander> control proporciona una manera de proporcionar contenido en un área ampliable que se parece a una ventana e incluye un encabezado.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>Crear un control Expander simple  
 En el ejemplo siguiente se muestra cómo crear un sencillo <xref:System.Windows.Controls.Expander> control. Este ejemplo se crea un <xref:System.Windows.Controls.Expander> que parece que la ilustración anterior.  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 El <xref:System.Windows.Controls.ContentControl.Content%2A> y <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> de un <xref:System.Windows.Controls.Expander> también puede incluir contenido complejo, como <xref:System.Windows.Controls.RadioButton> y <xref:System.Windows.Controls.Image> objetos.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Establecer la dirección del área de contenido de expansión  
 Puede establecer el área de contenido de un <xref:System.Windows.Controls.Expander> control para expandir en una de las cuatro direcciones (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, o <xref:System.Windows.Controls.ExpandDirection.Right>) mediante el uso de la <xref:System.Windows.Controls.ExpandDirection> propiedad. Cuando se contrae el área de contenido, solo el <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y su botón de alternancia aparece. Un <xref:System.Windows.Controls.Button> control que muestra una flecha se utiliza como un botón de alternancia para expandir o contraer el área de contenido. Expandido, el <xref:System.Windows.Controls.Expander> intenta mostrar todo su contenido en un área de la ventana.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Controlar el tamaño de un control Expander en un panel  
 Si un <xref:System.Windows.Controls.Expander> control está dentro de un control de diseño que hereda de <xref:System.Windows.Controls.Panel>, como <xref:System.Windows.Controls.StackPanel>, no se especifica un <xref:System.Windows.FrameworkElement.Height%2A> en el <xref:System.Windows.Controls.Expander> cuando el <xref:System.Windows.Controls.Expander.ExpandDirection%2A> propiedad está establecida en <xref:System.Windows.Controls.ExpandDirection.Down> o <xref:System.Windows.Controls.ExpandDirection.Up>. De igual forma, no especifique un <xref:System.Windows.FrameworkElement.Width%2A> en el <xref:System.Windows.Controls.Expander> cuando el <xref:System.Windows.Controls.Expander.ExpandDirection%2A> propiedad está establecida en <xref:System.Windows.Controls.ExpandDirection.Left> o <xref:System.Windows.Controls.ExpandDirection.Right>.  
  
 Cuando se define una dimensión de tamaño en un <xref:System.Windows.Controls.Expander> control en la dirección que se muestra el contenido expandido, el <xref:System.Windows.Controls.Expander> toma el control del área que se utiliza en el contenido y muestra un borde alrededor de ella. El borde se muestra aunque el contenido se contraiga. Para establecer el tamaño del área de contenido expandido, establezca las dimensiones de tamaño del contenido de la <xref:System.Windows.Controls.Expander>, o si desea desplazar la capacidad, en el <xref:System.Windows.Controls.ScrollViewer> que incluye el contenido.  
  
 Cuando un <xref:System.Windows.Controls.Expander> control es el último elemento en una <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] establece automáticamente el <xref:System.Windows.Controls.Expander> dimensiones en el área restante de la <xref:System.Windows.Controls.DockPanel>. Para evitar que este comportamiento predeterminado, establezca el <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> propiedad en el <xref:System.Windows.Controls.DockPanel> el objeto a `false`, o asegúrese de que el <xref:System.Windows.Controls.Expander> no es el último elemento en un <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>Crear contenido desplazable  
 Si el contenido es demasiado grande para el tamaño del área de contenido, puede ajustar el contenido de un <xref:System.Windows.Controls.Expander> en un <xref:System.Windows.Controls.ScrollViewer> con el fin de proporcionar contenido desplazable. El <xref:System.Windows.Controls.Expander> control no proporciona automáticamente la capacidad de desplazamiento. La siguiente ilustración muestra un <xref:System.Windows.Controls.Expander> control que contiene un <xref:System.Windows.Controls.ScrollViewer> control.  
  
 **Control Expander en un control ScrollViewer**  
  
 ![Control Expander con ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 Cuando coloca un <xref:System.Windows.Controls.Expander> controlar en un <xref:System.Windows.Controls.ScrollViewer>, establezca el <xref:System.Windows.Controls.ScrollViewer> dimensión propiedad que corresponde a la dirección en la que el <xref:System.Windows.Controls.Expander> contenido se abre en el tamaño de la <xref:System.Windows.Controls.Expander> área de contenido. Por ejemplo, si establece la <xref:System.Windows.Controls.Expander.ExpandDirection%2A> propiedad en el <xref:System.Windows.Controls.Expander> a <xref:System.Windows.Controls.ExpandDirection.Down> (se abre el área de contenido hacia abajo), establezca el <xref:System.Windows.FrameworkElement.Height%2A> propiedad en el <xref:System.Windows.Controls.ScrollViewer> control a la altura requerida para el área de contenido. Si se establece en su lugar, la dimensión de altura en el contenido en Sí, <xref:System.Windows.Controls.ScrollViewer> no reconoce este valor y por lo tanto, no proporciona contenido desplazable.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.Expander> control de contenido complejo que contiene un <xref:System.Windows.Controls.ScrollViewer> control. Este ejemplo se crea un <xref:System.Windows.Controls.Expander> que es similar de la ilustración al principio de esta sección.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>Usar propiedades de alineación  
 Puede alinear el contenido estableciendo la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> y <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> propiedades en el <xref:System.Windows.Controls.Expander> control. Al establecer estas propiedades, la alineación se aplica al encabezado y también al contenido ampliado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
