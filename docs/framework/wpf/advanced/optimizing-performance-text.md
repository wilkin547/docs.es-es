---
title: 'Optimizar el rendimiento: Text'
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
ms.openlocfilehash: 4835fb42a8976d94be223d8306d1eb16e330f8f5
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68434007"
---
# <a name="optimizing-performance-text"></a>Optimizar el rendimiento: Text

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye compatibilidad para la presentación de contenido de texto mediante el uso de controles [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] completos. En general, puede dividir la representación de texto en tres capas:

1. Usar los <xref:System.Windows.Documents.Glyphs> objetos <xref:System.Windows.Media.GlyphRun> y directamente.

2. Usar el <xref:System.Windows.Media.FormattedText> objeto.

3. Usar controles de alto nivel, como los <xref:System.Windows.Controls.TextBlock> objetos y. <xref:System.Windows.Documents.FlowDocument>

En este tema se proporcionan recomendaciones de rendimiento para la representación de texto.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Representación de texto en el nivel de glifos

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona compatibilidad con texto avanzado, incluido el marcado de nivel de glifos con acceso directo a <xref:System.Windows.Documents.Glyphs> para los clientes que quieren interceptar y conservar el texto después de darle formato. Estas características ofrecen una compatibilidad fundamental para los distintos requisitos de representación de texto en cada uno de los siguientes escenarios.

- Presentación en pantalla de documentos de formato fijo.

- Escenarios de impresión.

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como un lenguaje de impresora del dispositivo.

  - [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)]

  - Controladores de impresora anteriores: salida de aplicaciones [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] al formato fijo.

  - Formato de cola de impresión.

- Representación de documentos de formato fijo, incluidos clientes de versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y otros dispositivos informáticos.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>y <xref:System.Windows.Media.GlyphRun> están diseñados para escenarios de impresión y presentación de documentos de formato fijo. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]proporciona varios elementos para el diseño general [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] y escenarios <xref:System.Windows.Controls.Label> como y <xref:System.Windows.Controls.TextBlock>. Para obtener más información sobre los escenarios de diseño y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], consulte [Tipografía en WPF](typography-in-wpf.md).

En los siguientes ejemplos se muestra cómo definir las propiedades <xref:System.Windows.Documents.Glyphs> de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]objeto en. El <xref:System.Windows.Documents.Glyphs> objeto representa la salida <xref:System.Windows.Media.GlyphRun> de en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. En los ejemplos se supone que las fuentes Arial, Courier New y Times New Roman están instaladas en la carpeta **C:\WINDOWS\Fonts** del equipo local.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Usar DrawGlyphRun

Si tiene un control personalizado y desea representar glifos, utilice el <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> método.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también proporciona servicios de nivel inferior para el formato de texto personalizado mediante el uso <xref:System.Windows.Media.FormattedText> del objeto. La forma más eficaz de representar texto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es mediante la generación de contenido de texto en el nivel de glifo mediante <xref:System.Windows.Documents.Glyphs> y <xref:System.Windows.Media.GlyphRun>. Sin embargo, el costo de esta eficacia es la pérdida de un formato de texto enriquecido fácil de usar, que son características integradas de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] controles, <xref:System.Windows.Controls.TextBlock> como y. <xref:System.Windows.Documents.FlowDocument>

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>Objeto FormattedText

El <xref:System.Windows.Media.FormattedText> objeto permite dibujar texto de varias líneas, en el que se puede dar formato a cada carácter del texto de forma individual. Para obtener más información, consulte [Dibujar texto con formato](drawing-formatted-text.md).

Para crear texto con formato, llame <xref:System.Windows.Media.FormattedText.%23ctor%2A> al constructor para crear <xref:System.Windows.Media.FormattedText> un objeto. Una vez que haya creado la cadena inicial de texto con formato, podrá aplicar una gama de estilos de formato. Si la aplicación desea implementar su propio diseño, el objeto es <xref:System.Windows.Media.FormattedText> una opción mejor que el uso de un control, <xref:System.Windows.Controls.TextBlock>como. Para obtener más información sobre <xref:System.Windows.Media.FormattedText> el objeto, vea [dibujar texto con formato](drawing-formatted-text.md) .

El <xref:System.Windows.Media.FormattedText> objeto proporciona funcionalidad de formato de texto de bajo nivel. Puede aplicar varios estilos de formato a uno o más caracteres. Por ejemplo, puede llamar a los <xref:System.Windows.Media.FormattedText.SetFontSize%2A> métodos y <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> para cambiar el formato de los cinco primeros caracteres del texto.

En el ejemplo de código siguiente <xref:System.Windows.Media.FormattedText> se crea un objeto y se representa.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>Controles FlowDocument, TextBlock y Label

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument afecta al rendimiento más que TextBlock o Label

En general, el <xref:System.Windows.Controls.TextBlock> elemento se debe usar cuando se requiere compatibilidad de texto limitada, como una frase breve en un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label>se puede usar cuando se requiere compatibilidad de texto mínima. El <xref:System.Windows.Documents.FlowDocument> elemento es un contenedor para documentos redistribuibles que admiten la presentación enriquecida de contenido y, por consiguiente, tiene un mayor impacto en el <xref:System.Windows.Controls.TextBlock> rendimiento <xref:System.Windows.Controls.Label> que el uso de los controles o.

Para obtener más información <xref:System.Windows.Documents.FlowDocument>sobre, vea [información general sobre documentos dinámicos](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Evitar el uso de TextBlock en FlowDocument

El <xref:System.Windows.Controls.TextBlock> elemento se deriva de <xref:System.Windows.UIElement>. El <xref:System.Windows.Documents.Run> elemento se deriva de <xref:System.Windows.Documents.TextElement>, que es menos costoso de usar que un <xref:System.Windows.UIElement>objeto derivado de. Cuando sea posible, <xref:System.Windows.Documents.Run> use <xref:System.Windows.Controls.TextBlock> en lugar de para mostrar el contenido <xref:System.Windows.Documents.FlowDocument>de texto en un.

En el ejemplo de marcado siguiente se muestran dos maneras de establecer el contenido <xref:System.Windows.Documents.FlowDocument>de texto dentro de un:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Evitar el uso de ejecución para establecer propiedades de texto

En general, el uso <xref:System.Windows.Documents.Run> de un <xref:System.Windows.Controls.TextBlock> en un es más intensivo en el rendimiento que <xref:System.Windows.Documents.Run> no usar un objeto explícito en absoluto. Si usa un <xref:System.Windows.Documents.Run> objeto para establecer las propiedades de texto, establezca esas propiedades directamente <xref:System.Windows.Controls.TextBlock> en en su lugar.

En el ejemplo de marcado siguiente se muestran estas dos maneras de establecer una propiedad de texto, en este <xref:System.Windows.Controls.TextBlock.FontWeight%2A> caso, la propiedad:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

En la tabla siguiente se muestra el costo de <xref:System.Windows.Controls.TextBlock> mostrar 1000 objetos con y sin <xref:System.Windows.Documents.Run>explícitamente.

|**Tipo TextBlock**|**Tiempo de creación (ms)**|**Tiempo de representación (ms)**|
|------------------------|------------------------------|----------------------------|
|Propiedades de texto de configuración de ejecución|146|540|
|Propiedades de texto de configuración de TextBlock|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Evitar el enlace de datos a la propiedad Label.Content

Imagine un escenario en el que tiene <xref:System.Windows.Controls.Label> un objeto que se actualiza con frecuencia <xref:System.String> desde un origen. Cuando el enlace de <xref:System.Windows.Controls.Label> datos de <xref:System.Windows.Controls.ContentControl.Content%2A> la propiedad del <xref:System.String> elemento al objeto de origen, puede experimentar un rendimiento deficiente. Cada vez que se <xref:System.String> actualiza el origen, se <xref:System.String> descarta el objeto anterior y se vuelve a <xref:System.String> crear un nuevo: dado que un <xref:System.String> objeto es inmutable, no se puede modificar. Esto, a su vez, hace <xref:System.Windows.Controls.ContentPresenter> que el <xref:System.Windows.Controls.Label> del objeto descarte su contenido anterior y vuelva a generar el nuevo contenido para mostrar <xref:System.String>el nuevo.

La solución a este problema es sencilla. <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Si no seestableceenunvalorpersonalizado,reemplaceporyelenlacededatosdesupropiedadalacadenadeorigen.<xref:System.Windows.Controls.Label>

|**Propiedad enlazada a datos**|**Tiempo de actualización (ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Hipervínculo

El <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico de nivel insertado que permite hospedar hipervínculos dentro del contenido dinámico.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Combinar hipervínculos en un solo objeto TextBlock

Puede optimizar el uso de varios <xref:System.Windows.Documents.Hyperlink> elementos si los agrupa juntos dentro de la misma. <xref:System.Windows.Controls.TextBlock> Esto ayuda a minimizar el número de objetos que crea en la aplicación. Por ejemplo, es posible que quiera mostrar varios hipervínculos, como los siguientes:

MSN inicio &#124; Mi MSN

En el ejemplo de marcación <xref:System.Windows.Controls.TextBlock> siguiente se muestran varios elementos usados para mostrar los hipervínculos:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

En el ejemplo de marcación siguiente se muestra una manera más eficaz de mostrar los hipervínculos, esta vez <xref:System.Windows.Controls.TextBlock>, con un solo:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Mostrar subrayado solo en hipervínculos de eventos MouseEnter

Un <xref:System.Windows.TextDecoration> objeto es un adorno visual que se puede Agregar al texto; sin embargo, puede tener un rendimiento intensivo en la creación de instancias. Si hace un uso intensivo de <xref:System.Windows.Documents.Hyperlink> los elementos, considere la posibilidad de mostrar un subrayado solo al desencadenar <xref:System.Windows.ContentElement.MouseEnter> un evento, como el evento. Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md).

En la imagen siguiente se muestra cómo el evento MouseEnter desencadena el hipervínculo subrayado:

![Hipervínculos que muestran TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

En el ejemplo de marcado siguiente <xref:System.Windows.Documents.Hyperlink> se muestra un definido con y sin subrayado:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

En la tabla siguiente se muestra el costo de rendimiento <xref:System.Windows.Documents.Hyperlink> de mostrar 1000 elementos con y sin subrayado.

|**Hyperlink**|**Tiempo de creación (ms)**|**Tiempo de representación (ms)**|
|-------------------|------------------------------|----------------------------|
|Con subrayado|289|1130|
|Sin subrayado|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Características de formato de texto

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona servicios de formato de texto enriquecido, como la división de palabras automática. Estos servicios pueden afectar al rendimiento de la aplicación y solo deben usarse cuando sea necesario.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Evitar el uso innecesario de la división de palabras

La división de palabras automática busca puntos de interrupción de guiones para líneas de texto y permite posiciones de <xref:System.Windows.Controls.TextBlock> salto <xref:System.Windows.Documents.FlowDocument> adicionales para las líneas de los objetos y. De forma predeterminada, la característica de división de palabras automática está deshabilitada en estos objetos. Puede habilitarla si establece la propiedad IsHyphenationEnabled del objeto en `true`. Sin embargo, la habilitación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de esta característica hace que inicie la interoperabilidad del modelo de objetos componentes (com), lo que puede afectar al rendimiento de la aplicación. Se recomienda que no se la división de palabras automática a menos que lo necesite.

### <a name="use-figures-carefully"></a>Usar figuras con cuidado

Un <xref:System.Windows.Documents.Figure> elemento representa una parte del contenido dinámico que puede tener una posición absoluta dentro de una página de contenido. En algunos casos, <xref:System.Windows.Documents.Figure> puede hacer que una página completa cambie de formato automáticamente si su posición entra en conflicto con el contenido que ya se ha diseñado. Puede minimizar la posibilidad de volver a formatear innecesariamente agrupando <xref:System.Windows.Documents.Figure> los elementos entre sí o declarándolos cerca de la parte superior del contenido en un escenario de tamaño de página fijo.

### <a name="optimal-paragraph"></a>Párrafo óptimo

La característica de párrafo óptimo del <xref:System.Windows.Documents.FlowDocument> objeto dispone los párrafos para que el espacio en blanco se distribuya lo más uniformemente posible. De forma predeterminada, la característica de párrafo óptimo está deshabilitada. Puede habilitar esta característica estableciendo la propiedad del <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> objeto en. `true` Sin embargo, habilitar esta característica afecta al rendimiento de la aplicación. Se recomienda que no use la característica de párrafo óptimo a menos que la necesite.

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
