---
title: "Optimizar el rendimiento: Texto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "representar texto"
  - "hipervínculos"
  - "texto con formato [WPF]"
  - "texto, rendimiento"
  - "glifos"
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Optimizar el rendimiento: Texto
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]incluye compatibilidad para la presentación del contenido de texto mediante el uso de características [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] controles. En general, puede dividir la representación de texto en tres capas:  
  
1.  Mediante la <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> objetos directamente.  
  
2.  Mediante la <xref:System.Windows.Media.FormattedText> objeto.  
  
3.  Utilizar controles de alto nivel, como el <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos.  
  
 Este tema proporciona recomendaciones de rendimiento de la representación de texto.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Representación de texto en el nivel de glifos  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona compatibilidad con texto avanzado incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para clientes que desean interceptar y conservar el texto después de darle formato. Estas características ofrecen compatibilidad fundamental para el texto diferentes requisitos de representación en cada uno de los siguientes escenarios.  
  
-   Presentación en pantalla de documentos de formato fijo.  
  
-   Escenarios de impresión.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]como un lenguaje de impresora del dispositivo.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]Operador  
  
    -   Controladores de impresora anteriores, salidos de [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] aplicaciones al formato fijo.  
  
    -   Formato de la cola de impresión.  
  
-   Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y otros dispositivos informáticos.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> están diseñadas para escenarios de impresión y presentación de documentos de formato fijo. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona varios elementos para el diseño general y [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] escenarios como <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre el diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] escenarios, consulte el [tipografía en WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Los ejemplos siguientes muestran cómo definir las propiedades de un <xref:System.Windows.Documents.Glyphs> objeto en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El <xref:System.Windows.Documents.Glyphs> objeto representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en el **C:\WINDOWS\Fonts** carpeta en el equipo local.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>Uso de DrawGlyphRun  
 Si tiene un control personalizado y desea representar glifos, utilice la <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> método.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]También proporciona servicios de nivel inferior para el texto personalizado de formato mediante el uso de la <xref:System.Windows.Media.FormattedText> objeto. La forma más eficaz de representación de texto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] está generando el contenido de texto en el nivel glifos mediante <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun>. Sin embargo, el costo de esta eficacia es la pérdida de fácil de usar formato de texto enriquecido, que son características integradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controles, como <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>Objeto FormattedText  
 El <xref:System.Windows.Media.FormattedText> objeto permite dibujar texto de varias líneas, en el que cada carácter en el texto puede formatearse individualmente. Para obtener más información, consulte [texto con formato de dibujo](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Para crear texto con formato, llame a la <xref:System.Windows.Media.FormattedText.%23ctor%2A> constructor para crear un <xref:System.Windows.Media.FormattedText> objeto. Una vez haya creado la cadena de texto con formato inicial, puede aplicar una gama de estilos de formato. Si desea que la aplicación implemente su propio diseño, el <xref:System.Windows.Media.FormattedText> objeto es más adecuado que usar un control, como <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre la <xref:System.Windows.Media.FormattedText> de objeto, vea [texto con formato de dibujo](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 El <xref:System.Windows.Media.FormattedText> objeto proporciona capacidad de formato de texto de bajo nivel. Puede aplicar varios estilos de formato a uno o más caracteres. Por ejemplo, podría llamar tanto la <xref:System.Windows.Media.FormattedText.SetFontSize%2A> y <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> métodos para cambiar el formato de los cinco primeros caracteres del texto.  
  
 En el ejemplo de código siguiente se crea un <xref:System.Windows.Media.FormattedText> objeto y lo representa.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock y controles de etiqueta  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument afecta al rendimiento más que TextBlock o Label  
 En general, la <xref:System.Windows.Controls.TextBlock> deberían usar el elemento cuando se requiere, como una frase breve en la compatibilidad de texto limitada un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> se puede usar cuando se requiere la compatibilidad de texto mínima. El <xref:System.Windows.Documents.FlowDocument> elemento es un contenedor para documentos dinámicos que admite presentación enriquecida de contenido y por lo tanto, tiene un mayor impacto de rendimiento que el uso de la <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.Label> controles.  
  
 Para obtener más información sobre <xref:System.Windows.Documents.FlowDocument>, consulte [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Evite el uso de TextBlock en FlowDocument  
 El <xref:System.Windows.Controls.TextBlock> se deriva de elemento <xref:System.Windows.UIElement>. El <xref:System.Windows.Documents.Run> se deriva de elemento <xref:System.Windows.Documents.TextElement>, que es menos costoso de usar que un <xref:System.Windows.UIElement>-objeto derivado. Cuando sea posible, use <xref:System.Windows.Documents.Run> en lugar de <xref:System.Windows.Controls.TextBlock> para mostrar el texto contenido en una <xref:System.Windows.Documents.FlowDocument>.  
  
 En el ejemplo de marcado siguiente se muestra dos maneras de establecer contenido de texto dentro de un <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Evite el uso de ejecución para establecer las propiedades de texto  
 En general, utilizando un <xref:System.Windows.Documents.Run> dentro de un <xref:System.Windows.Controls.TextBlock> es más rendimiento intensivo que no utiliza explícita <xref:System.Windows.Documents.Run> en todos los objetos. Si está utilizando un <xref:System.Windows.Documents.Run> con el fin de establecer las propiedades de texto, establezca las propiedades directamente en el <xref:System.Windows.Controls.TextBlock> en su lugar.  
  
 En el ejemplo de marcado siguiente se muestra estas dos maneras de establecer una propiedad de texto, en este caso, el <xref:System.Windows.Controls.TextBlock.FontWeight%2A> propiedad:  
  
 [!code-xml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 La siguiente tabla muestra el costo de mostrar 1000 <xref:System.Windows.Controls.TextBlock> objetos con y sin explícita <xref:System.Windows.Documents.Run>.  
  
|**Tipo de TextBlock**|**Hora de creación (ms)**|**Tiempo (ms) de representación**|  
|------------------------|------------------------------|----------------------------|  
|Ejecute establecer las propiedades de texto|146|540|  
|Propiedades de texto de configuración de TextBlock|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitar el enlace de datos a la propiedad Label.Content  
 Imagine un escenario en el que tiene un <xref:System.Windows.Controls.Label> objeto que se actualiza con frecuencia de un <xref:System.String> origen. Cuando el enlace de datos el <xref:System.Windows.Controls.Label> del elemento <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad a la <xref:System.String> objeto de origen, puede experimentar un rendimiento deficiente. Cada vez que el origen de <xref:System.String> se actualiza, la antigua <xref:System.String> objeto es descartados y un nuevo <xref:System.String> se vuelve a crear, porque una <xref:System.String> objeto es inmutable, no se puede modificar. Esto, a su vez, hace el <xref:System.Windows.Controls.ContentPresenter> de la <xref:System.Windows.Controls.Label> objeto descarte su contenido anterior y volver a generar el contenido nuevo para mostrar el nuevo <xref:System.String>.  
  
 La solución a este problema es simple. Si el <xref:System.Windows.Controls.Label> no está establecido en personalizado <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> valor, reemplace la <xref:System.Windows.Controls.Label> con una <xref:System.Windows.Controls.TextBlock> y enlazar los datos su <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad en la cadena de origen.  
  
|**Propiedad enlazan a datos**|**Tiempo de actualización (ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Hipervínculo  
 El <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinar hipervínculos en un solo objeto TextBlock  
 Puede optimizar el uso de varios <xref:System.Windows.Documents.Hyperlink> elementos agrupándolos dentro del mismo <xref:System.Windows.Controls.TextBlock>. Esto ayuda a minimizar el número de objetos que cree en la aplicación. Por ejemplo, puede mostrar varios hipervínculos, como los siguientes:  
  
 Página principal de MSN | Mi MSN  
  
 En el ejemplo de marcado siguiente se muestra varios <xref:System.Windows.Controls.TextBlock> elementos utilizados para mostrar los hipervínculos:  
  
 [!code-xml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 En el ejemplo de marcado siguiente se muestra una manera más eficaz de mostrar los hipervínculos, esta vez, usando una sola <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Mostrar hipervínculos en los eventos MouseEnter subrayados  
 Un <xref:System.Windows.TextDecoration> objeto es un adorno visual que se puede agregar al texto; sin embargo, puede mejorar el rendimiento al crear una instancia. Si hace un uso intensivo de <xref:System.Windows.Documents.Hyperlink> elementos, considere la posibilidad de mostrar un subrayado únicamente al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos. Para obtener más información, consulte [especificar un hipervínculo subrayado](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Hipervínculo que aparece al desencadenar MouseEnter  
  
 El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Documents.Hyperlink> definido con y sin subrayado:  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 La siguiente tabla muestra el costo de rendimiento de mostrar 1000 <xref:System.Windows.Documents.Hyperlink> elementos con y sin subrayado.  
  
|**Hipervínculo**|**Hora de creación (ms)**|**Tiempo (ms) de representación**|  
|-------------------|------------------------------|----------------------------|  
|Con subrayado|289|1130|  
|Sin subrayado|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Características de formato de texto  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Proporciona los servicios, como los guiones de división automática de formato de texto enriquecido. Estos servicios pueden afectar al rendimiento de la aplicación y sólo deben utilizarse cuando sea necesario.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evite el uso innecesario de guiones  
 La división automática busca los puntos de interrupción de guión para las líneas de texto y permite posiciones de salto de línea adicional a las líneas de <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos. De forma predeterminada, la característica de división automática está deshabilitada en estos objetos. Puede habilitar esta característica estableciendo la propiedad IsHyphenationEnabled del objeto en `true`. Sin embargo, si se habilita esta característica, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para iniciar [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] interoperabilidad, lo que puede afectar el rendimiento de la aplicación. Se recomienda que no utilice la división automática a menos que lo necesite.  
  
### <a name="use-figures-carefully"></a>Utilice las cifras con cuidado  
 Un <xref:System.Windows.Documents.Figure> elemento representa una parte de contenido dinámico que puede tener una posición absoluta dentro de una página de contenido. En algunos casos, un <xref:System.Windows.Documents.Figure> puede provocar una página entera a formatear automáticamente si entra en conflicto con el contenido que ya se ha dispuesto en su posición. Puede minimizar la posibilidad de que cualquier agrupación de formato innecesarios <xref:System.Windows.Documents.Figure> elementos juntos, o declararlas cerca de la parte superior del contenido en un escenario de tamaño de página fijo.  
  
### <a name="optimal-paragraph"></a>Párrafo óptimo  
 La característica de párrafo óptimo de la <xref:System.Windows.Documents.FlowDocument> objeto dispone los párrafos para que el espacio en blanco se distribuya lo más uniformemente posible. De forma predeterminada, la característica de párrafo óptimo está deshabilitada. Puede habilitar esta característica estableciendo el objeto <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> propiedad `true`. Sin embargo, habilitar esta característica afecta al rendimiento de la aplicación. Se recomienda que no utilice la característica de párrafo óptimo a menos que lo necesite.  
  
## <a name="see-also"></a>Vea también  
 [Optimizar el rendimiento de la aplicación de WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear el rendimiento de la aplicación](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Para aprovechar el Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Creación de imágenes y gráficos&2;D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)