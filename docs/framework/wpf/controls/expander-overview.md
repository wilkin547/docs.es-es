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
ms.openlocfilehash: 892d972a5704d50e91d04e05d6fdea7180a3155d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187112"
---
# <a name="expander-overview"></a>Información general sobre el control Expander
Un <xref:System.Windows.Controls.Expander> control proporciona una manera de proporcionar contenido en un área expandible que se asemeja a una ventana e incluye un encabezado.  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>Crear un control Expander simple  
 En el ejemplo siguiente se <xref:System.Windows.Controls.Expander> muestra cómo crear un control simple. En este <xref:System.Windows.Controls.Expander> ejemplo se crea un aspecto similar a la ilustración anterior.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 El <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y <xref:System.Windows.Controls.Expander> de un también puede <xref:System.Windows.Controls.RadioButton> contener <xref:System.Windows.Controls.Image> contenido complejo, como y objetos.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Establecer la dirección del área de contenido de expansión  
 Puede establecer el área <xref:System.Windows.Controls.Expander> de contenido de un control<xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up>para <xref:System.Windows.Controls.ExpandDirection.Left>expandirse en una de las cuatro direcciones ( , , , o <xref:System.Windows.Controls.ExpandDirection.Right>) mediante la <xref:System.Windows.Controls.ExpandDirection> propiedad. Cuando el área de contenido <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> está contraída, solo aparece el botón de alternancia y el botón de alternancia. Un <xref:System.Windows.Controls.Button> control que muestra una flecha direccional se utiliza como un botón de alternancia para expandir o contraer el área de contenido. Cuando se expande, intenta <xref:System.Windows.Controls.Expander> mostrar todo su contenido en un área similar a una ventana.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Controlar el tamaño de un control Expander en un panel  
 Si <xref:System.Windows.Controls.Expander> un control está dentro de <xref:System.Windows.Controls.Panel>un control <xref:System.Windows.Controls.StackPanel>de diseño <xref:System.Windows.FrameworkElement.Height%2A> que <xref:System.Windows.Controls.Expander> hereda <xref:System.Windows.Controls.Expander.ExpandDirection%2A> de , <xref:System.Windows.Controls.ExpandDirection.Down> <xref:System.Windows.Controls.ExpandDirection.Up>como , no especifique a en el momento en que la propiedad se establece en o . De forma similar, <xref:System.Windows.FrameworkElement.Width%2A> no <xref:System.Windows.Controls.Expander> especifique <xref:System.Windows.Controls.Expander.ExpandDirection%2A> a en <xref:System.Windows.Controls.ExpandDirection.Left> <xref:System.Windows.Controls.ExpandDirection.Right>el momento en que la propiedad se establece en o .  
  
 Cuando se establece una <xref:System.Windows.Controls.Expander> dimensión de tamaño en un control en <xref:System.Windows.Controls.Expander> la dirección en la que se muestra el contenido expandido, el toma el control del área que utiliza el contenido y muestra un borde alrededor de él. El borde se muestra aunque el contenido se contraiga. Para establecer el tamaño del área de contenido expandida, <xref:System.Windows.Controls.Expander>establezca las dimensiones de tamaño <xref:System.Windows.Controls.ScrollViewer> en el contenido de la función de desplazamiento , o si desea que se encierre el contenido.  
  
 Cuando <xref:System.Windows.Controls.Expander> un control es el <xref:System.Windows.Controls.DockPanel> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] último elemento <xref:System.Windows.Controls.Expander> de un , establece <xref:System.Windows.Controls.DockPanel>automáticamente las dimensiones para que sea igual al área restante del archivo . Para evitar este comportamiento <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> predeterminado, <xref:System.Windows.Controls.DockPanel> establezca `false`la propiedad del <xref:System.Windows.Controls.Expander> objeto en , o <xref:System.Windows.Controls.DockPanel>asegúrese de que no es el último elemento de un archivo .  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>Crear contenido desplazable  
 Si el contenido es demasiado grande para el tamaño del área <xref:System.Windows.Controls.Expander> de <xref:System.Windows.Controls.ScrollViewer> contenido, puede ajustar el contenido de un en un para proporcionar contenido desplazable. El <xref:System.Windows.Controls.Expander> control no proporciona automáticamente la capacidad de desplazamiento. En la ilustración siguiente se muestra un <xref:System.Windows.Controls.Expander> control que contiene un <xref:System.Windows.Controls.ScrollViewer> control.  
  
 **Control Expander en un control ScrollViewer**  
  
 ![Captura de pantalla que muestra un expansor con ScrollBar.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 Al colocar <xref:System.Windows.Controls.Expander> un control <xref:System.Windows.Controls.ScrollViewer>en <xref:System.Windows.Controls.ScrollViewer> un , establezca la propiedad de <xref:System.Windows.Controls.Expander> dimensión que corresponde <xref:System.Windows.Controls.Expander> a la dirección en la que se abre el contenido al tamaño del área de contenido. Por ejemplo, si <xref:System.Windows.Controls.Expander.ExpandDirection%2A> establece la <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.ExpandDirection.Down> propiedad en el valor (el área de contenido se abre hacia abajo), establezca la <xref:System.Windows.FrameworkElement.Height%2A> propiedad en el <xref:System.Windows.Controls.ScrollViewer> control en el alto necesario para el área de contenido. Si, en su lugar, establece <xref:System.Windows.Controls.ScrollViewer> la dimensión de altura en el propio contenido, no reconoce esta configuración y, por lo tanto, no proporciona contenido desplazable.  
  
 En el ejemplo siguiente <xref:System.Windows.Controls.Expander> se muestra cómo crear un <xref:System.Windows.Controls.ScrollViewer> control que tiene contenido complejo y que contiene un control. En este <xref:System.Windows.Controls.Expander> ejemplo se crea un que es como la ilustración al principio de esta sección.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>Usar propiedades de alineación  
 Puede alinear el contenido <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> estableciendo <xref:System.Windows.Controls.Expander> las propiedades y las propiedades del control. Al establecer estas propiedades, la alineación se aplica al encabezado y también al contenido ampliado.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [Temas de información](expander-how-to-topics.md)
