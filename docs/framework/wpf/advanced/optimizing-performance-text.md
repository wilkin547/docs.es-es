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
ms.openlocfilehash: 3e729458538353499f27f95ea2ca37fea1335238
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740343"
---
# <a name="optimizing-performance-text"></a>Optimizar el rendimiento: Texto

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye compatibilidad para la presentación de contenido de texto mediante el uso de controles [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] completos. En general, puede dividir la representación de texto en tres capas:

1. Usar los objetos <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> directamente.

2. Usar el objeto <xref:System.Windows.Media.FormattedText>.

3. Usar controles de alto nivel, como los objetos <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument>.

En este tema se proporcionan recomendaciones de rendimiento para la representación de texto.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Representación de texto en el nivel de glifos

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona compatibilidad con texto avanzado, incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para los clientes que quieren interceptar y conservar el texto después de darle formato. Estas características ofrecen una compatibilidad fundamental para los distintos requisitos de representación de texto en cada uno de los siguientes escenarios.

- Presentación en pantalla de documentos de formato fijo.

- Escenarios de impresión.

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como un lenguaje de impresora del dispositivo.

  - Escritor de documentos XPS de Microsoft.

  - Controladores de impresora anteriores, que se envían desde aplicaciones Win32 al formato fijo.

  - Formato de cola de impresión.

- Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de Windows y otros dispositivos informáticos.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun> están diseñados para escenarios de impresión y presentación de documentos de formato fijo. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona varios elementos para el diseño general y escenarios de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] como <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre los escenarios de diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Tipografía en WPF](typography-in-wpf.md).

En los siguientes ejemplos se muestra cómo definir las propiedades de un objeto <xref:System.Windows.Documents.Glyphs> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El objeto <xref:System.Windows.Documents.Glyphs> representa la salida de un <xref:System.Windows.Media.GlyphRun> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en la carpeta **C:\WINDOWS\Fonts** del equipo local.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Usar DrawGlyphRun

Si tiene un control personalizado y desea representar glifos, utilice el método <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A>.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también proporciona servicios de nivel inferior para el formato de texto personalizado mediante el uso del objeto <xref:System.Windows.Media.FormattedText>. La forma más eficaz de representar texto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es mediante la generación de contenido de texto en el nivel de glifo mediante <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun>. Sin embargo, el costo de esta eficacia es la pérdida de un formato de texto enriquecido fácil de usar, que son características integradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controles, como <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument>.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>Objeto FormattedText

El objeto <xref:System.Windows.Media.FormattedText> permite dibujar texto de varias líneas, en el que se puede dar formato a cada carácter del texto de forma individual. Para obtener más información, consulte [Dibujar texto con formato](drawing-formatted-text.md).

Para crear texto con formato, llame al constructor <xref:System.Windows.Media.FormattedText.%23ctor%2A> para crear un objeto <xref:System.Windows.Media.FormattedText>. Una vez que haya creado la cadena inicial de texto con formato, podrá aplicar una gama de estilos de formato. Si la aplicación desea implementar su propio diseño, el objeto <xref:System.Windows.Media.FormattedText> es mejor opción que el uso de un control, como <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre el objeto <xref:System.Windows.Media.FormattedText>, vea [dibujar texto con formato](drawing-formatted-text.md) .

El objeto <xref:System.Windows.Media.FormattedText> proporciona funcionalidad de formato de texto de bajo nivel. Puede aplicar varios estilos de formato a uno o más caracteres. Por ejemplo, puede llamar a los métodos <xref:System.Windows.Media.FormattedText.SetFontSize%2A> y <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> para cambiar el formato de los cinco primeros caracteres del texto.

En el ejemplo de código siguiente se crea un objeto <xref:System.Windows.Media.FormattedText> y se representa.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>Controles FlowDocument, TextBlock y Label

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument afecta al rendimiento más que TextBlock o Label

En general, el elemento <xref:System.Windows.Controls.TextBlock> debe usarse cuando se requiere compatibilidad de texto limitada, como una frase breve en un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> se puede usar cuando se requiere compatibilidad de texto mínima. El elemento <xref:System.Windows.Documents.FlowDocument> es un contenedor para documentos redistribuibles que admiten la presentación enriquecida de contenido y, por consiguiente, tiene un mayor impacto en el rendimiento que el uso de los controles <xref:System.Windows.Controls.TextBlock> o <xref:System.Windows.Controls.Label>.

Para obtener más información sobre <xref:System.Windows.Documents.FlowDocument>, consulte [información general sobre documentos dinámicos](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Evitar el uso de TextBlock en FlowDocument

El elemento <xref:System.Windows.Controls.TextBlock> se deriva de <xref:System.Windows.UIElement>. El elemento <xref:System.Windows.Documents.Run> se deriva de <xref:System.Windows.Documents.TextElement>, que es menos costoso de usar que un objeto derivado de <xref:System.Windows.UIElement>. Cuando sea posible, use <xref:System.Windows.Documents.Run> en lugar de <xref:System.Windows.Controls.TextBlock> para mostrar el contenido de texto en un <xref:System.Windows.Documents.FlowDocument>.

En el ejemplo de marcado siguiente se muestran dos maneras de establecer el contenido de texto dentro de un <xref:System.Windows.Documents.FlowDocument>:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Evitar el uso de ejecución para establecer propiedades de texto

En general, el uso de un <xref:System.Windows.Documents.Run> dentro de un <xref:System.Windows.Controls.TextBlock> es más intensivo de rendimiento que no usar un objeto de <xref:System.Windows.Documents.Run> explícito. Si usa un <xref:System.Windows.Documents.Run> para establecer propiedades de texto, establezca esas propiedades directamente en el <xref:System.Windows.Controls.TextBlock> en su lugar.

En el ejemplo de marcado siguiente se muestran estas dos maneras de establecer una propiedad de texto, en este caso, la propiedad <xref:System.Windows.Controls.TextBlock.FontWeight%2A>:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

En la tabla siguiente se muestra el costo de mostrar 1000 objetos <xref:System.Windows.Controls.TextBlock> con y sin un <xref:System.Windows.Documents.Run>explícito.

|**Tipo TextBlock**|**Tiempo de creación (ms)**|**Tiempo de representación (ms)**|
|------------------------|------------------------------|----------------------------|
|Propiedades de texto de configuración de ejecución|146|540|
|Propiedades de texto de configuración de TextBlock|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitar el enlace de datos a la propiedad Label.Content

Imagine un escenario en el que tiene un objeto <xref:System.Windows.Controls.Label> que se actualiza con frecuencia desde un origen de <xref:System.String>. Cuando el enlace de datos de la propiedad <xref:System.Windows.Controls.ContentControl.Content%2A> del elemento de <xref:System.Windows.Controls.Label> al objeto de origen de <xref:System.String>, puede experimentar un rendimiento deficiente. Cada vez que se actualiza el <xref:System.String> de origen, se descarta el objeto de <xref:System.String> anterior y se vuelve a crear un nuevo <xref:System.String>, porque un objeto de <xref:System.String> es inmutable, no se puede modificar. Esto, a su vez, hace que el <xref:System.Windows.Controls.ContentPresenter> del objeto <xref:System.Windows.Controls.Label> deseche su contenido anterior y vuelva a generar el nuevo contenido para mostrar el nuevo <xref:System.String>.

La solución a este problema es sencilla. Si el <xref:System.Windows.Controls.Label> no se establece en un valor de <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> personalizado, reemplace el <xref:System.Windows.Controls.Label> por un <xref:System.Windows.Controls.TextBlock> y enlace de datos su <xref:System.Windows.Controls.TextBlock.Text%2A> propiedad a la cadena de origen.

|**Propiedad enlazada a datos**|**Tiempo de actualización (ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Hipervínculo

El objeto <xref:System.Windows.Documents.Hyperlink> es un elemento de contenido dinámico de nivel insertado que permite hospedar hipervínculos dentro del contenido dinámico.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinar hipervínculos en un solo objeto TextBlock

Puede optimizar el uso de varios elementos <xref:System.Windows.Documents.Hyperlink> si los agrupa juntos dentro de la misma <xref:System.Windows.Controls.TextBlock>. Esto ayuda a minimizar el número de objetos que crea en la aplicación. Por ejemplo, es posible que quiera mostrar varios hipervínculos, como los siguientes:

MSN inicio &#124; Mi MSN

En el ejemplo de marcación siguiente se muestran varios elementos <xref:System.Windows.Controls.TextBlock> usados para mostrar los hipervínculos:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

En el ejemplo de marcación siguiente se muestra una manera más eficaz de mostrar los hipervínculos, esta vez, con un solo <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Mostrar subrayado solo en hipervínculos de eventos MouseEnter

Un objeto <xref:System.Windows.TextDecoration> es un adorno visual que se puede Agregar al texto; sin embargo, el rendimiento puede ser intensivo en la creación de instancias. Si hace un uso intensivo de los elementos de <xref:System.Windows.Documents.Hyperlink>, considere la posibilidad de mostrar un subrayado solo al desencadenar un evento, como el evento <xref:System.Windows.ContentElement.MouseEnter>. Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md).

En la imagen siguiente se muestra cómo el evento MouseEnter desencadena el hipervínculo subrayado:

![Hipervínculos que muestran TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

En el ejemplo de marcado siguiente se muestra un <xref:System.Windows.Documents.Hyperlink> definido con y sin subrayado:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

En la tabla siguiente se muestra el costo de rendimiento de mostrar 1000 elementos <xref:System.Windows.Documents.Hyperlink> con y sin subrayado.

|**Hyperlink**|**Tiempo de creación (ms)**|**Tiempo de representación (ms)**|
|-------------------|------------------------------|----------------------------|
|Con subrayado|289|1130|
|Sin subrayado|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Características de formato de texto

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona servicios de formato de texto enriquecido, como la división de palabras automática. Estos servicios pueden afectar al rendimiento de la aplicación y solo deben usarse cuando sea necesario.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evitar el uso innecesario de la división de palabras

La división de palabras automática busca puntos de interrupción de guiones para líneas de texto y permite posiciones de salto adicionales para las líneas de <xref:System.Windows.Controls.TextBlock> y <xref:System.Windows.Documents.FlowDocument> objetos. De forma predeterminada, la característica de división de palabras automática está deshabilitada en estos objetos. Puede habilitarla si establece la propiedad IsHyphenationEnabled del objeto en `true`. Sin embargo, la habilitación de esta característica hace que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inicie la interoperabilidad del modelo de objetos componentes (COM), lo que puede afectar al rendimiento de la aplicación. Se recomienda que no se la división de palabras automática a menos que lo necesite.

### <a name="use-figures-carefully"></a>Usar figuras con cuidado

Un elemento <xref:System.Windows.Documents.Figure> representa una parte del contenido dinámico que puede tener una posición absoluta dentro de una página de contenido. En algunos casos, un <xref:System.Windows.Documents.Figure> puede hacer que una página completa cambie de formato automáticamente si su posición entra en conflicto con el contenido que ya se ha diseñado. Puede minimizar la posibilidad de volver a formatear innecesariamente agrupando <xref:System.Windows.Documents.Figure> elementos uno tras otro o declarándolos cerca de la parte superior del contenido en un escenario de tamaño de página fijo.

### <a name="optimal-paragraph"></a>Párrafo óptimo

La característica de párrafo óptimo del objeto <xref:System.Windows.Documents.FlowDocument> coloca los párrafos para que el espacio en blanco se distribuya lo más uniformemente posible. De forma predeterminada, la característica de párrafo óptimo está deshabilitada. Puede habilitar esta característica estableciendo la propiedad <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> del objeto en `true`. Sin embargo, habilitar esta característica afecta al rendimiento de la aplicación. Se recomienda que no use la característica de párrafo óptimo a menos que la necesite.

## <a name="see-also"></a>Vea también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de la aplicación](optimizing-performance-application-resources.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
