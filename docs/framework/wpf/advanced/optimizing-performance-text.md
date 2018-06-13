---
title: 'Optimizar el rendimiento: Texto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: 177f42dfa1c1be2b12d7e9e5283cf57f14c0880c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548875"
---
# <a name="optimizing-performance-text"></a>Optimizar el rendimiento: Texto
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye compatibilidad para la presentación de contenido de texto mediante el uso de controles [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] completos. En general, puede dividir la representación de texto en tres capas:  
  
1.  Mediante el <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> objetos directamente.  
  
2.  Mediante la <xref:System.Windows.Media.FormattedText> objeto.  
  
3.  Usar controles de alto nivel, como el <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos.  
  
 En este tema se proporcionan recomendaciones de rendimiento para la representación de texto.  
  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Representación de texto en el nivel de glifos  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona compatibilidad con texto avanzado incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para clientes que desean interceptar y conservar el texto después de darle formato. Estas características ofrecen una compatibilidad fundamental para los distintos requisitos de representación de texto en cada uno de los siguientes escenarios.  
  
-   Presentación en pantalla de documentos de formato fijo.  
  
-   Escenarios de impresión.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como un lenguaje de impresora del dispositivo.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Controladores de impresora anteriores: salida de aplicaciones [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] al formato fijo.  
  
    -   Formato de cola de impresión.  
  
-   Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y otros dispositivos informáticos.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> están diseñadas para escenarios de impresión y presentación del documento de formato fijo. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona varios elementos de diseño general y [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] escenarios como <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre los escenarios de diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Los ejemplos siguientes muestran cómo definir las propiedades de un <xref:System.Windows.Documents.Glyphs> objeto [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El <xref:System.Windows.Documents.Glyphs> objeto representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en la carpeta **C:\WINDOWS\Fonts** del equipo local.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>Usar DrawGlyphRun  
 Si tiene un control personalizado y desea representar glifos, utilice el <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> método.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También proporciona servicios de bajo nivel para el texto personalizado de formato mediante el uso de la <xref:System.Windows.Media.FormattedText> objeto. La manera más eficaz de representación de texto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consiste en generar el contenido de texto en el nivel glifo con <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun>. Sin embargo, el costo de esta eficacia es la pérdida de fácil de usar formato de texto enriquecido, que son características integradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controles, como <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>Objeto FormattedText  
 La <xref:System.Windows.Media.FormattedText> objeto permite dibujar texto de varias líneas, en el que cada carácter en el texto puede aplicarse individualmente. Para obtener más información, consulte [Dibujar texto con formato](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Para crear texto con formato, llame a la <xref:System.Windows.Media.FormattedText.%23ctor%2A> constructor para crear un <xref:System.Windows.Media.FormattedText> objeto. Una vez que haya creado la cadena inicial de texto con formato, podrá aplicar una gama de estilos de formato. Si la aplicación desea implementar su propio diseño, el <xref:System.Windows.Media.FormattedText> objeto es más adecuado que usar un control, como <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre la <xref:System.Windows.Media.FormattedText> de objetos, consulte [texto con formato de dibujo](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 La <xref:System.Windows.Media.FormattedText> objeto proporciona capacidad de formato de texto de bajo nivel. Puede aplicar varios estilos de formato a uno o más caracteres. Por ejemplo, podría llamar tanto la <xref:System.Windows.Media.FormattedText.SetFontSize%2A> y <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> métodos para cambiar el formato de los cinco primeros caracteres del texto.  
  
 En el ejemplo de código siguiente se crea un <xref:System.Windows.Media.FormattedText> de objeto y lo representa.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>Controles FlowDocument, TextBlock y Label  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument afecta al rendimiento más que TextBlock o Label  
 En general, la <xref:System.Windows.Controls.TextBlock> deberían usar el elemento cuando se requiere, como una frase breve en compatibilidad con texto limitado un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> se puede usar cuando se requiere la compatibilidad de texto mínima. El <xref:System.Windows.Documents.FlowDocument> elemento es un contenedor de documentos dinámicos que admite presentación enriquecida de contenido y por lo tanto, tiene un mayor impacto en el rendimiento que el uso de la <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.Label> controles.  
  
 Para obtener más información sobre <xref:System.Windows.Documents.FlowDocument>, consulte [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Evitar el uso de TextBlock en FlowDocument  
 El <xref:System.Windows.Controls.TextBlock> elemento se deriva de <xref:System.Windows.UIElement>. El <xref:System.Windows.Documents.Run> elemento se deriva de <xref:System.Windows.Documents.TextElement>, que es menos costosa de usar que una <xref:System.Windows.UIElement>-objeto derivado. Cuando sea posible, utilice <xref:System.Windows.Documents.Run> en lugar de <xref:System.Windows.Controls.TextBlock> para mostrar el texto contenido en un <xref:System.Windows.Documents.FlowDocument>.  
  
 El siguiente ejemplo de marcado muestra dos maneras de establecer el contenido de texto dentro de un <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xaml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Evitar el uso de ejecución para establecer propiedades de texto  
 En general, el uso un <xref:System.Windows.Documents.Run> dentro de un <xref:System.Windows.Controls.TextBlock> es rendimiento más intensiva que no usa explícito <xref:System.Windows.Documents.Run> objeto en absoluto. Si usas un <xref:System.Windows.Documents.Run> para establecer las propiedades de texto, establecer las propiedades directamente en el <xref:System.Windows.Controls.TextBlock> en su lugar.  
  
 El ejemplo de marcado siguiente muestra estas dos maneras de establecer una propiedad de texto, en este caso, el <xref:System.Windows.Controls.TextBlock.FontWeight%2A> propiedad:  
  
 [!code-xaml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 La siguiente tabla muestra el costo de mostrar 1000 <xref:System.Windows.Controls.TextBlock> objetos con y sin explícito <xref:System.Windows.Documents.Run>.  
  
|**Tipo TextBlock**|**Tiempo de creación (ms)**|**Tiempo de representación (ms)**|  
|------------------------|------------------------------|----------------------------|  
|Propiedades de texto de configuración de ejecución|146|540|  
|Propiedades de texto de configuración de TextBlock|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitar el enlace de datos a la propiedad Label.Content  
 Imagine un escenario donde haya un <xref:System.Windows.Controls.Label> objeto que se actualiza con frecuencia desde un <xref:System.String> origen. Cuando el enlace de datos el <xref:System.Windows.Controls.Label> del elemento <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad a la <xref:System.String> objeto de origen, puede experimentar un rendimiento deficiente. Cada vez que el origen de <xref:System.String> se actualiza, la antigua <xref:System.String> objeto es descartados y un nuevo <xref:System.String> se vuelve a crear, porque una <xref:System.String> objeto es inmutable, no se puede modificar. Esto, a su vez, hace el <xref:System.Windows.Controls.ContentPresenter> de la <xref:System.Windows.Controls.Label> objeto descarte su contenido anterior y volver a generar el contenido nuevo para mostrar el nuevo <xref:System.String>.  
  
 La solución a este problema es sencilla. Si el <xref:System.Windows.Controls.Label> no está establecido en personalizado <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> valor, reemplace el <xref:System.Windows.Controls.Label> con un <xref:System.Windows.Controls.TextBlock> y enlazar los datos su <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad a la cadena de origen.  
  
|**Propiedad enlazada a datos**|**Tiempo de actualización (ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Hipervínculo  
 La <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinar hipervínculos en un solo objeto TextBlock  
 Puede optimizar el uso de varios <xref:System.Windows.Documents.Hyperlink> elementos agrupándolos dentro del mismo <xref:System.Windows.Controls.TextBlock>. Esto ayuda a minimizar el número de objetos que crea en la aplicación. Por ejemplo, es posible que quiera mostrar varios hipervínculos, como los siguientes:  
  
 MSN inicio &#124; Mi MSN  
  
 En el ejemplo de marcado siguiente se muestra varios <xref:System.Windows.Controls.TextBlock> elementos que se usan para mostrar los hipervínculos:  
  
 [!code-xaml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 En el ejemplo de marcado siguiente se muestra una forma más eficaz de mostrar los hipervínculos, esta vez, usando una sola <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xaml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Mostrar subrayado solo en hipervínculos de eventos MouseEnter  
 Un <xref:System.Windows.TextDecoration> objeto es un adorno visual que se puede agregar al texto; sin embargo, se puede mejorar el rendimiento al crear una instancia. Si realiza uso extenso de <xref:System.Windows.Documents.Hyperlink> elementos, considere la posibilidad de mostrar un subrayado únicamente al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos. Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Hipervínculo que aparece en MouseEnter  
  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Documents.Hyperlink> definido con y sin un subrayado:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 La siguiente tabla muestra el costo de rendimiento de mostrar 1000 <xref:System.Windows.Documents.Hyperlink> elementos con y sin un subrayado.  
  
|**Hyperlink**|**Tiempo de creación (ms)**|**Tiempo de representación (ms)**|  
|-------------------|------------------------------|----------------------------|  
|Con subrayado|289|1130|  
|Sin subrayado|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Características de formato de texto  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona servicios de formato de texto enriquecido, como la división de palabras automática. Estos servicios pueden afectar al rendimiento de la aplicación y solo deben usarse cuando sea necesario.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evitar el uso innecesario de la división de palabras  
 La división automática busca los puntos de interrupción de guión para las líneas de texto y permite posiciones de salto adicional a las líneas de <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos. De forma predeterminada, la característica de división de palabras automática está deshabilitada en estos objetos. Puede habilitarla si establece la propiedad IsHyphenationEnabled del objeto en `true`. Sin embargo, si se habilita esta característica, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inicia la interoperabilidad de [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], lo que puede afectar el rendimiento de la aplicación. Se recomienda que no se la división de palabras automática a menos que lo necesite.  
  
### <a name="use-figures-carefully"></a>Usar figuras con cuidado  
 Un <xref:System.Windows.Documents.Figure> elemento representa una parte del contenido del flujo que puede tener una posición absoluta dentro de una página de contenido. En algunos casos, un <xref:System.Windows.Documents.Figure> puede provocar una página completa volver a formatear automáticamente si está en conflicto con el contenido que ya se ha dispuesto en su posición. Puede minimizar la posibilidad de volver a formatear innecesarios por cualquier agrupación <xref:System.Windows.Documents.Figure> elementos junto a entre sí o declararlas cerca de la parte superior del contenido en un escenario de tamaño de página fijo.  
  
### <a name="optimal-paragraph"></a>Párrafo óptimo  
 La característica de párrafo óptimo de la <xref:System.Windows.Documents.FlowDocument> objeto dispone los párrafos para que el espacio en blanco se distribuya lo más uniformemente posible. De forma predeterminada, la característica de párrafo óptimo está deshabilitada. Puede habilitar esta característica estableciendo el objeto <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> propiedad `true`. Sin embargo, habilitar esta característica afecta al rendimiento de la aplicación. Se recomienda que no use la característica de párrafo óptimo a menos que la necesite.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
