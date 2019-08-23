---
title: Información general sobre características bidireccionales en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: b009c2503c7cbf6aca847fc7318135842a060f69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965037"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Información general sobre características bidireccionales en WPF
A diferencia de cualquier otra plataforma de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] desarrollo, tiene muchas características que admiten el desarrollo rápido de contenido bidireccional, por ejemplo, mixto de izquierda a derecha y de derecha a izquierda en el mismo documento. Al mismo tiempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea una excelente experiencia para los usuarios que requieren características bidireccionales como los usuarios de habla árabe y hebreo.  
  
 En las siguientes secciones se explican muchas características bidireccionales, junto con ejemplos que muestran cómo conseguir la mejor visualización de contenido bidireccional. La mayoría de los ejemplos [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]usan, aunque puede aplicar fácilmente los conceptos a C# o a Microsoft Visual Basic código.  

<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 La propiedad básica que define la dirección del flujo de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en una <xref:System.Windows.FrameworkElement.FlowDirection%2A>aplicación es. Esta propiedad se puede establecer en uno de los dos valores de <xref:System.Windows.FlowDirection.LeftToRight> enumeración, o <xref:System.Windows.FlowDirection.RightToLeft>. La propiedad está disponible para todos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] los elementos que heredan de. <xref:System.Windows.FrameworkElement>  
  
 En los siguientes ejemplos se establece la dirección de <xref:System.Windows.Controls.TextBox> flujo de un elemento.  
  
 **Dirección del flujo de izquierda a derecha**  
  
 [!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Dirección del flujo de derecha a izquierda**  
  
 [!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 En el gráfico siguiente se muestra cómo se representa el código anterior.  
    
 ![Gráfico que muestra las distintas direcciones de flujo.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)  
  
 Un elemento dentro de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] un árbol <xref:System.Windows.FrameworkElement.FlowDirection%2A> heredará de su contenedor. En el ejemplo siguiente, <xref:System.Windows.Controls.TextBlock> está dentro de <xref:System.Windows.Controls.Grid>, que reside en <xref:System.Windows.Window>. <xref:System.Windows.FrameworkElement.FlowDirection%2A> Establecer <xref:System.Windows.Controls.TextBlock> para<xref:System.Windows.Controls.Grid> implica establecerlo también para y. <xref:System.Windows.Window>  
  
 En el ejemplo siguiente se <xref:System.Windows.FrameworkElement.FlowDirection%2A>muestra la configuración de.  
  
 [!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 El nivel <xref:System.Windows.Window> superior tiene un <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, por lo que todos los elementos contenidos en él también <xref:System.Windows.FrameworkElement.FlowDirection%2A>heredan el mismo. Para que un elemento invalide <xref:System.Windows.FrameworkElement.FlowDirection%2A> un especificado, debe agregar un cambio de dirección explícito como <xref:System.Windows.Controls.TextBlock> el segundo del ejemplo anterior que cambia <xref:System.Windows.FlowDirection.LeftToRight>a. Cuando no <xref:System.Windows.FrameworkElement.FlowDirection%2A> se define, se aplica <xref:System.Windows.FlowDirection.LeftToRight> el valor predeterminado.  
  
 En el gráfico siguiente se muestra la salida del ejemplo anterior:

 ![Gráfico que muestra el cambio de dirección de flujo explícito.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)  

<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Muchas plataformas de desarrollo como HTML [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y Java proporcionan compatibilidad especial para el desarrollo de contenido bidireccional. Los lenguajes de marcado, como HTML, proporcionan a los escritores de contenido el marcado necesario para mostrar texto en cualquier dirección requerida, por ejemplo, la etiqueta HTML 4,0, "dir" que toma "RTL" o "LTR" como valores. Esta etiqueta es similar a la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad, pero la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad funciona de forma más avanzada para el diseño del contenido textual y se puede usar para contenido que no sea texto.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un <xref:System.Windows.Documents.FlowDocument> es un elemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] versátil que puede hospedar una combinación de texto, tablas, imágenes y otros elementos. Los ejemplos de las secciones siguientes usan este elemento.  
  
 Agregar texto a un <xref:System.Windows.Documents.FlowDocument> puede realizarse de forma más unidireccional. Una manera sencilla de hacerlo es a través de <xref:System.Windows.Documents.Paragraph> , que es un elemento de nivel de bloque usado para agrupar contenido como texto. Para agregar texto a los elementos en el nivel insertado, <xref:System.Windows.Documents.Span> los <xref:System.Windows.Documents.Run>ejemplos usan y. <xref:System.Windows.Documents.Span>es un elemento de contenido dinámico de nivel insertado que se utiliza para agrupar otros elementos insertados <xref:System.Windows.Documents.Run> , mientras que es un elemento de contenido dinámico de nivel insertado diseñado para contener una ejecución de texto sin formato. Un <xref:System.Windows.Documents.Span> elemento puede contener <xref:System.Windows.Documents.Run> varios elementos.  
  
 El primer ejemplo de documento contiene un documento que tiene un número de nombres de recurso compartido de red; por ejemplo `\\server1\folder\file.ext`,. Tanto si tiene este vínculo de red en un documento en árabe como en inglés, siempre quiere que aparezca de la misma manera. En el gráfico siguiente se ilustra el uso del elemento span y se muestra el vínculo <xref:System.Windows.FlowDirection.RightToLeft> en un documento árabe:

 ![Gráfico que ilustra el uso del elemento span.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")  
  
 Dado que el texto <xref:System.Windows.FlowDirection.RightToLeft>es, todos los caracteres especiales, como "\\", separan el texto de derecha a izquierda. Esto hace que el vínculo no se muestre en el orden correcto, por lo que para resolver el problema, el texto debe estar incrustado para <xref:System.Windows.Documents.Run> conservar <xref:System.Windows.FlowDirection.LeftToRight>un flujo diferente. En lugar de tener una independiente <xref:System.Windows.Documents.Run> para cada idioma, una mejor manera de resolver el problema es insertar el texto en inglés que se usa con menos frecuencia en <xref:System.Windows.Documents.Span>un árabe más grande.  
  
 En el gráfico siguiente se ilustra esto mediante el elemento Run insertado en un elemento span:

 ![Gráfico que muestra el elemento de ejecución incrustado en un elemento span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)  
  
 En el siguiente ejemplo se <xref:System.Windows.Documents.Run> muestra <xref:System.Windows.Documents.Span> el uso de los elementos y en documentos.  
  
 [!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Elementos Span  
 El <xref:System.Windows.Documents.Span> elemento funciona como un separador de límites entre textos con diferentes direcciones de flujo.  Incluso <xref:System.Windows.Documents.Span> se considera que los elementos con la misma dirección de flujo tienen ámbitos bidireccionales diferentes <xref:System.Windows.FlowDirection>, <xref:System.Windows.Documents.Span> lo que significa que los elementos se ordenan en el contenedor, <xref:System.Windows.Documents.Span> solo el contenido dentro del elemento. <xref:System.Windows.FlowDirection> sigue<xref:System.Windows.Documents.Span>a la de.  
  
 En el gráfico siguiente se muestra la dirección del <xref:System.Windows.Controls.TextBlock> flujo de varios elementos.  
    
 ![Gráfico que ilustra los bloques de texto con diferentes direcciones de flujo.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)  
  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Windows.Documents.Span> los <xref:System.Windows.Documents.Run> elementos y para generar los resultados que se muestran en el gráfico anterior.  
  
 [!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 En los <xref:System.Windows.Controls.TextBlock> elementos del ejemplo, los <xref:System.Windows.Documents.Span> elementos se colocan según la <xref:System.Windows.FlowDirection> propiedad de sus elementos primarios, pero el texto <xref:System.Windows.Documents.Span> dentro de cada elemento fluye según <xref:System.Windows.FlowDirection>su propio. Esto es aplicable a los idiomas latín y árabe, o a cualquier otro idioma.  
  
### <a name="adding-xmllang"></a>Agregar xml:lang  
 En `"200.0+21.4=221.4"`el gráfico siguiente se muestra otro ejemplo que usa números y expresiones aritméticas, como. Observe que solo <xref:System.Windows.FlowDirection> se establece.  
    
 ![Gráfico que muestra números usando solo FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)  
  
 Los usuarios de esta aplicación estarán decepcionados por la salida, aunque el <xref:System.Windows.FlowDirection> sea correcto, los números no tienen la forma de que los números arábigos tengan forma.  
  
 Los elementos XAML pueden incluir [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] un atributo`xml:lang`() que define el idioma de cada elemento. XAML también admite un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] `xml:lang` principio de lenguaje en el que los elementos secundarios usan los valores que se aplican a los elementos primarios del árbol. En el ejemplo anterior, dado que no se definió un lenguaje <xref:System.Windows.Documents.Run> para el elemento o alguno de sus elementos de nivel superior `xml:lang` , se usaba el valor `en-US` predeterminado, que es para XAML. El algoritmo de forma de número interno [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] de selecciona números en el idioma correspondiente (en este caso, Inglés). Para que los números arábigos se `xml:lang` representen correctamente, es necesario establecer.  
  
 En el gráfico siguiente se muestra el `xml:lang` ejemplo de agregado.  
    
 ![Gráfico que muestra números árabes que fluyen de derecha a izquierda.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)  
  
 En el ejemplo siguiente `xml:lang` se agrega a la aplicación.  
  
 [!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Tenga en cuenta que muchos idiomas tienen `xml:lang` valores diferentes en función de la región de destino, por `"ar-SA"` ejemplo `"ar-EG"` , y representan dos variaciones de árabe. En los ejemplos anteriores se muestra que debe definir los `xml:lang` valores y. <xref:System.Windows.FlowDirection>  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementos no textuales  
 <xref:System.Windows.FlowDirection>define no solo cómo fluye el texto en un elemento de texto sino también la dirección de flujo de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] casi todos los demás elementos. En el gráfico siguiente se <xref:System.Windows.Controls.ToolBar> muestra un que usa <xref:System.Windows.Media.LinearGradientBrush> una horizontal para dibujar su fondo con un degradado de izquierda a derecha.  

 ![Gráfico que muestra una barra de herramientas con un degradado de izquierda a derecha.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)  
  
 Después de establecer <xref:System.Windows.FlowDirection> en <xref:System.Windows.FlowDirection.RightToLeft>, no solo los <xref:System.Windows.Controls.ToolBar> botones se organizan <xref:System.Windows.Media.LinearGradientBrush> de derecha a izquierda, sino que también se realinean sus desplazamientos para fluir de derecha a izquierda.  
  
 En el gráfico siguiente se muestra la realineación <xref:System.Windows.Media.LinearGradientBrush>del.  
    
 ![Gráfico que muestra una barra de herramientas con un degradado de derecha a izquierda.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)  
  
 En el ejemplo siguiente se <xref:System.Windows.FlowDirection.RightToLeft>dibuja un. <xref:System.Windows.Controls.ToolBar> (Para dibujarlo <xref:System.Windows.Controls.ToolBar>de izquierda a derecha, quite <xref:System.Windows.FlowDirection> el atributo en.  
  
 [!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>Excepciones de FlowDirection  
 Hay algunos casos en los que <xref:System.Windows.FlowDirection> no se comporta de la manera esperada. En esta sección se describen dos de estas excepciones.  
  
 **Image**  
  
 Un <xref:System.Windows.Controls.Image> representa un control que muestra una imagen. En [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] , se puede utilizar con una <xref:System.Windows.Controls.Image.Source%2A> propiedad <xref:System.Windows.Controls.Image> que define el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] del que se va a mostrar.  
  
 A diferencia <xref:System.Windows.FlowDirection> de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] otros elementos <xref:System.Windows.Controls.Image> , no hereda del contenedor. Sin embargo, si <xref:System.Windows.FlowDirection> se establece explícitamente <xref:System.Windows.FlowDirection.RightToLeft>en, <xref:System.Windows.Controls.Image> se muestra volteada horizontalmente. Se implementa como una práctica característica para los desarrolladores de contenido bidireccional, porque el volteo horizontal de la imagen muestra el efecto deseado en algunos casos.  
  
 En el gráfico siguiente se muestra un <xref:System.Windows.Controls.Image>volteo.  
    
 ![Gráfico que muestra una imagen volteada.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)  
  
 En el ejemplo siguiente se muestra <xref:System.Windows.Controls.Image> que no puede <xref:System.Windows.FlowDirection> heredar de <xref:System.Windows.Controls.StackPanel> la que lo contiene. **Nota:** Debe tener un archivo denominado **ms_logo. jpg** en C:\ para ejecutar este ejemplo.  
  
 [!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Nota:** En los archivos de descarga se incluye un archivo **ms_logo. jpg** . En el código, se supone que el archivo .jpg no está dentro del proyecto, sino en alguna ubicación de la unidad C:\. Debe copiar el archivo .jpg de los archivos del proyecto en la unidad C:\ o cambiar el código para buscar el archivo dentro del proyecto. Para realizar este cambio `Source="file://c:/ms_logo.jpg"` en `Source="ms_logo.jpg"`.  
  
 **Rutas de acceso**  
  
 Además <xref:System.Windows.Controls.Image>de, otro elemento interesante es <xref:System.Windows.Shapes.Path>. Patch es un objeto que puede dibujar una serie de líneas y curvas conectadas. Se comporta de forma similar a un <xref:System.Windows.Controls.Image> con respecto a su <xref:System.Windows.FlowDirection>; por ejemplo <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> , es un reflejo horizontal de su <xref:System.Windows.FlowDirection.LeftToRight> . Sin embargo, a diferencia <xref:System.Windows.Controls.Image>de <xref:System.Windows.Shapes.Path> , hereda su <xref:System.Windows.FlowDirection> del contenedor y no es necesario especificarlo explícitamente.  
  
 En el ejemplo siguiente se dibuja una flecha simple mediante 3 líneas. La primera flecha hereda la <xref:System.Windows.FlowDirection.RightToLeft> dirección del flujo <xref:System.Windows.Controls.StackPanel> de para que sus puntos inicial y final se midan desde una raíz en el lado derecho. La segunda flecha que tiene explícitamente <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> también se inicia en el lado derecho. Sin embargo, la tercera flecha tiene su raíz de inicio en el lado izquierdo. Para obtener más información acerca del <xref:System.Windows.Media.LineGeometry> dibujo <xref:System.Windows.Media.GeometryGroup>, vea y.  
  
 [!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 En el gráfico siguiente se muestra la salida del ejemplo anterior con las flechas dibujadas mediante el `Path` elemento:

 ![Gráfico que muestra las flechas dibujadas mediante el elemento path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)  
  
 Y son dos ejemplos de cómo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] usa <xref:System.Windows.FlowDirection>. <xref:System.Windows.Shapes.Path> <xref:System.Windows.Controls.Image> Junto a <xref:System.Windows.Controls.InkPresenter> la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] disposición de los elementos en una dirección específica dentro <xref:System.Windows.FlowDirection> de un contenedor, se puede usar con elementos como, por ejemplo, que <xref:System.Windows.Media.LinearGradientBrush>representa <xref:System.Windows.Media.RadialGradientBrush>la entrada de lápiz en una superficie,,. Siempre que necesite un comportamiento de derecha a izquierda para el contenido que imite un comportamiento de izquierda a derecha, o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona esa funcionalidad.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Sustitución de números  
 Históricamente, Windows ha admitido la sustitución de números al permitir la representación de distintas formas culturales para los mismos dígitos manteniendo el almacenamiento interno de estos dígitos unificado entre diferentes configuraciones regionales, por ejemplo, los números se almacenan en su valores hexadecimales conocidos, 0x40, 0x41, pero mostrados según el idioma seleccionado.  
  
 Esto permite a las aplicaciones procesar valores numéricos sin necesidad de convertirlos de un idioma a otro; por ejemplo, un usuario puede abrir [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] una hoja de cálculo en una ventana en árabe localizada y ver los números con forma de árabe, pero abrirlo en un Versión europea de Windows y ver la representación Europea de los mismos números. Esto también es necesario para otros símbolos, como el símbolo de porcentaje y los separadores de coma, porque suelen acompañar a los números del mismo documento.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] continúa con la tradición y agrega más compatibilidad con esta característica, que aumenta el control del usuario sobre cuándo y cómo usar la sustitución. Aunque esta característica está diseñada para cualquier idioma, es especialmente útil en el contenido bidireccional, donde definir los dígitos de un idioma concreto normalmente constituye un desafío para los desarrolladores de aplicaciones debido a las distintas referencias culturales en las que se puede ejecutar una aplicación.  
  
 La propiedad principal que controla cómo funciona la sustitución [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] de números <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> en es la propiedad de dependencia. La <xref:System.Windows.Media.NumberSubstitution> clase especifica cómo se mostrarán los números en el texto. Tiene tres propiedades públicas que definen su comportamiento. A continuación se muestra un resumen de cada una de las propiedades.  
  
 **CultureSource:**  
  
 Esta propiedad especifica cómo se determina la referencia cultural para los números. Toma uno de los tres <xref:System.Windows.Media.NumberCultureSource> valores de enumeración.  
  
- Estima La referencia cultural de número <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> es la de la propiedad.  
  
- Negrita La referencia cultural de número es la referencia cultural de la ejecución de texto. En el marcado, esto sería `xml:lang`, o su propiedad `Language` alias (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Además, es el valor predeterminado para las clases que derivan de <xref:System.Windows.FrameworkContentElement>. Estas clases incluyen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> etc.  
  
- Usuario: La referencia cultural de número es la referencia cultural del subproceso actual. Esta propiedad es la predeterminada para todas las subclases <xref:System.Windows.FrameworkElement> de <xref:System.Windows.Controls.Page>, como <xref:System.Windows.Window> , <xref:System.Windows.Controls.TextBlock>y.  
  
 **CultureOverride**:  
  
 La <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> propiedad solo se usa si la <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> propiedad está establecida en <xref:System.Windows.Media.NumberCultureSource.Override> y se omite en caso contrario. Especifica la referencia cultural de número. Un valor de `null`, el valor predeterminado, se interpreta como en-US.  
  
 **Substitution**:  
  
 Esta propiedad especifica el tipo de sustitución de números que se va a realizar. Toma uno de los siguientes <xref:System.Windows.Media.NumberSubstitutionMethod> valores de enumeración:  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: El método de sustitución se determina en función de la propiedad <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> de la referencia cultural de número. Este es el valor predeterminado.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Si la referencia cultural de número es una referencia cultural árabe o persa, especifica que los dígitos dependen del contexto.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Los números siempre se representan como dígitos europeos.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Los números se representan mediante los dígitos nacionales de la referencia cultural del número, según lo especificado por <xref:System.Globalization.CultureInfo.NumberFormat%2A>la referencia cultural.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Los números se representan mediante los dígitos tradicionales para la referencia cultural de número. Para la mayoría de las referencias culturales, es <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>igual que. Sin embargo <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> , da como resultado dígitos latinos en algunas referencias culturales árabes, mientras que este valor da como resultado dígitos árabes para todas las referencias culturales árabes.  
  
 ¿Qué significan esos valores para un desarrollador de contenido bidireccional? En la mayoría de los casos, es posible que el <xref:System.Windows.FlowDirection> desarrollador solo necesite definir y el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] idioma de cada elemento `Language="ar-SA"` textual, <xref:System.Windows.Media.NumberSubstitution> por ejemplo, y la lógica se encarga de mostrar los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]números según el correcto. En el siguiente ejemplo se muestra el uso de números árabes [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y ingleses en una aplicación que se ejecuta en una versión árabe de Windows.  
  
 [!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 En el gráfico siguiente se muestra la salida del ejemplo anterior si se ejecuta en una versión árabe de Windows con números árabes y en inglés que se muestran:

 ![Gráfico que muestra números árabes y ingleses.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)  
  
 En este caso, <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection.LeftToRight> era importante porque establecer en en su lugar habría dado como resultado dígitos europeos. <xref:System.Windows.FlowDirection> En las secciones siguientes se explica cómo conseguir una presentación unificada de dígitos en todo el documento. Si este ejemplo no se ejecuta en una versión árabe de Windows, todos los dígitos se mostrarán como dígitos europeos.  
  
 **Definición de reglas de sustitución**  
  
 En una aplicación real, es posible que tenga que establecer el idioma mediante programación. Por ejemplo, si desea establecer el `xml:lang` atributo para que sea el mismo que el utilizado por la del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]sistema, o puede cambiar el idioma en función del estado de la aplicación.  
  
 Si desea realizar cambios en función del estado de la aplicación, haga uso de otras características proporcionadas por [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 En primer lugar, establezca la del `NumberSubstitution.CultureSource="Text"`componente de la aplicación. Al usar esta configuración, se asegura de que la configuración no proviene de los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos de texto que tienen "User" como valor predeterminado, <xref:System.Windows.Controls.TextBlock>como.  
  
Por ejemplo:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

En el código C# correspondiente, establezca la `Language` propiedad, por ejemplo, en `"ar-SA"`.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Si tiene que establecer la `Language` propiedad en el idioma de la interfaz de usuario del usuario actual, use el código siguiente.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>representa la referencia cultural actual utilizada por el subproceso actual en tiempo de ejecución.  
  
 El ejemplo [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] final debería ser similar al ejemplo siguiente.  
  
 [!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 El ejemplo C# final debería ser similar al siguiente.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 En el gráfico siguiente se muestra el aspecto de la ventana para cualquier lenguaje de programación, mostrando números árabes:
     
 ![Gráfico que muestra números árabes.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)  
  
 **Uso de la propiedad Substitution**  
  
 La forma en que funciona la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sustitución de números en depende tanto del idioma del elemento de <xref:System.Windows.FlowDirection>texto como de su. Si es <xref:System.Windows.FlowDirection> de izquierda a derecha, se representan los dígitos europeos. Sin embargo, si va precedido por texto árabe o tiene el idioma establecido en "ar" y <xref:System.Windows.FlowDirection> es <xref:System.Windows.FlowDirection.RightToLeft>, se representan los dígitos árabes en su lugar.  
  
 En algunos casos, sin embargo, es posible que quiera crear una aplicación unificada, como, por ejemplo, dígitos europeos para todos los usuarios. O dígitos árabes en <xref:System.Windows.Documents.Table> las celdas con un <xref:System.Windows.Style>específico. Una manera fácil de hacerlo es usar la <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> propiedad.  
  
 En el ejemplo siguiente, el primero <xref:System.Windows.Controls.TextBlock> no tiene establecida la <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> propiedad, por lo que el algoritmo muestra dígitos árabes según lo esperado. Sin embargo, en <xref:System.Windows.Controls.TextBlock>el segundo, la sustitución se establece en Europea invalidando la sustitución predeterminada de los números árabes y se muestran los dígitos europeos.  
  
 [!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
