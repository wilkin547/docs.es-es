---
title: "Informaci&#243;n general sobre caracter&#237;sticas bidireccionales en WPF | Microsoft Docs"
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
  - "características bidireccionales"
  - "FlowDirection (propiedad)"
  - "FlowDocument (propiedad)"
  - "Span (elementos)"
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Informaci&#243;n general sobre caracter&#237;sticas bidireccionales en WPF
A diferencia de cualquier otra plataforma de desarrollo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene muchas características que admiten el desarrollo rápido de contenido bidireccional; por ejemplo, datos de izquierda a derecha y de derecha a izquierda mezclados en el mismo documento.  Al mismo tiempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea una experiencia excelente para aquellos usuarios que requieren características bidireccionales, como son los usuarios de los idiomas árabe y hebreo.  
  
 En las secciones siguientes se explican muchas características bidireccionales, junto con ejemplos que muestran cómo conseguir la mejor presentación de contenido bidireccional.  La mayoría de los ejemplos utiliza [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], aunque puede aplicar con facilidad los mismos conceptos al código [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] o [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)].  
  
   
  
<a name="FlowDirection"></a>   
## FlowDirection  
 La propiedad básica que define la dirección de flujo del contenido en una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  Esta propiedad se puede establecer en uno de dos valores de enumeración, <xref:System.Windows.FlowDirection> o <xref:System.Windows.FlowDirection>.  La propiedad está disponible para todos los elementos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que heredan de <xref:System.Windows.FrameworkElement>.  
  
 Los ejemplos siguientes establecen la dirección de flujo de un elemento <xref:System.Windows.Controls.TextBox>.  
  
 **Dirección de flujo de izquierda a derecha**  
  
 [!code-xml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Dirección de flujo de derecha a izquierda**  
  
 [!code-xml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 El gráfico siguiente muestra cómo se representa el código anterior.  
  
 **Gráfico que ilustra el uso de FlowDirection**  
  
 ![Alineación de TextBlock](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.png "LefttoRightRighttoLeft")  
  
 Un elemento dentro de un árbol [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] heredará la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> de su contenedor.  En el ejemplo siguiente, el objeto <xref:System.Windows.Controls.TextBlock> está dentro de otro objeto <xref:System.Windows.Controls.Grid>, que reside en <xref:System.Windows.Window>.  Si se establece la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> para <xref:System.Windows.Window>, también se establece para <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.TextBlock>.  
  
 En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.FrameworkElement.FlowDirection%2A>:  
  
 [!code-xml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 El objeto de nivel superior <xref:System.Windows.Window> tiene el valor <xref:System.Windows.FlowDirection><xref:System.Windows.FlowDirection>, por lo que todos los elementos incluidos dentro de él también heredan la misma propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  Para que un elemento invalide una propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> especificada, debe agregar un cambio de dirección explícito, como el segundo objeto <xref:System.Windows.Controls.TextBlock> del ejemplo anterior, que cambia a <xref:System.Windows.FlowDirection>.  Cuando no se define ninguna propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>, se aplica el valor <xref:System.Windows.FlowDirection> predeterminado.  
  
 En el gráfico siguiente se muestra el resultado del ejemplo anterior.  
  
 **Gráfico que ilustra el uso de la propiedad FlowDirection asignada explícitamente**  
  
 ![Ilustración de dirección de flujo](../../../../docs/framework/wpf/advanced/media/flowdir.png "FlowDir")  
  
<a name="FlowDocument"></a>   
## FlowDocument  
 Muchas plataformas de desarrollo como [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y Java proporcionan una compatibilidad especial para el desarrollo de contenido bidireccional.  Los lenguajes de marcado como [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] ofrecen a los creadores de contenido el marcado necesario para mostrar texto en cualquier dirección; por ejemplo, la etiqueta "dir" de [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0, que toma "rtl" o "ltr" como valores.  Esta etiqueta es similar a la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>, pero la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> funciona de una manera más avanzada para crear el diseño del contenido textual y se puede utilizar para contenido que no sea texto.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un objeto <xref:System.Windows.Documents.FlowDocument> es un elemento de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] versátil que puede hospedar una combinación de texto, tablas, imágenes y otros elementos.  Los ejemplos de las secciones siguientes utilizan este elemento.  
  
 La adición de texto a <xref:System.Windows.Documents.FlowDocument> se puede realizar de varias maneras.  Una manera sencilla de hacerlo es mediante un objeto <xref:System.Windows.Documents.Paragraph>, que es un elemento de nivel de bloque utilizado para agrupar contenido, por ejemplo texto.  Para agregar texto a elementos insertados, los ejemplos utilizan <xref:System.Windows.Documents.Span> y <xref:System.Windows.Documents.Run>.  <xref:System.Windows.Documents.Span> es un elemento de contenido dinámico insertado utilizado para agrupar otros elementos insertados, mientras que un objeto <xref:System.Windows.Documents.Run> es un elemento de contenido dinámico insertado pensado para contener una ejecución de texto sin formato.  Un objeto <xref:System.Windows.Documents.Span> puede contener varios elementos <xref:System.Windows.Documents.Run>.  
  
 El primer ejemplo de documento contiene un documento con varios nombres de recursos compartidos de red; por ejemplo `\\server1\folder\file.ext`.  Tanto si tiene este vínculo de red en un documento en árabe o en inglés, es conveniente que aparezca siempre de la misma manera.  El gráfico siguiente muestra el vínculo en un documento <xref:System.Windows.FlowDirection> en árabe.  
  
 **Gráfico que ilustra cómo utilizar el elemento Span**  
  
 ![Documento con flujo de texto de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/flowdocument.png "FlowDocument")  
  
 Dado que el texto es <xref:System.Windows.FlowDirection>, todos los caracteres especiales, como la "\\", separan el texto de derecha a izquierda.  Eso hace que el vínculo no se muestre en el orden correcto; por lo tanto, para resolver el problema, el texto se debe incrustar para conservar un objeto <xref:System.Windows.Documents.Run> independiente que fluya <xref:System.Windows.FlowDirection>.  En lugar de tener un objeto <xref:System.Windows.Documents.Run> independiente para cada idioma, una mejor manera de resolver el problema es incrustar el texto en inglés utilizado con menos frecuencia en un objeto <xref:System.Windows.Documents.Span> de mayor tamaño en árabe.  
  
 Esto se ilustra en el siguiente gráfico:  
  
 **Gráfico que muestra cómo utilizar el elemento Run incrustado en un elemento Span**  
  
 ![Captura de pantalla de XamlPad](../../../../docs/framework/wpf/advanced/media/runspan.png "RunSpan")  
  
 En el ejemplo siguiente se muestra cómo utilizar los elementos <xref:System.Windows.Documents.Run> y <xref:System.Windows.Documents.Span> en los documentos.  
  
 [!code-xml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## Elementos Span  
 El elemento <xref:System.Windows.Documents.Span> funciona como un separador de límite entre textos con direcciones de flujo diferentes.  Incluso los elementos <xref:System.Windows.Documents.Span> con la misma dirección de flujo tienen ámbitos bidireccionales diferentes, lo que significa que los elementos <xref:System.Windows.Documents.Span> se ordenan en el objeto <xref:System.Windows.FlowDirection>del contenedor; sólo el contenido dentro de <xref:System.Windows.Documents.Span> sigue la dirección determinada por <xref:System.Windows.FlowDirection> para el elemento <xref:System.Windows.Documents.Span>.  
  
 El gráfico siguiente muestra la dirección de flujo de varios elementos <xref:System.Windows.Controls.TextBlock>.  
  
 **Gráfico que ilustra FlowDirection en varios elementos TextBlock**  
  
 ![Bloques de texto con diferentes direcciones de flujo](../../../../docs/framework/wpf/advanced/media/span.png "Span")  
  
 El ejemplo siguiente muestra cómo utilizar los elementos <xref:System.Windows.Documents.Span> y <xref:System.Windows.Documents.Run> para generar los resultados mostrados en el gráfico anterior.  
  
 [!code-xml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 En los elementos <xref:System.Windows.Controls.TextBlock> del ejemplo, los elementos <xref:System.Windows.Documents.Span> se disponen de acuerdo con la <xref:System.Windows.FlowDirection> de sus elementos primarios, pero el texto dentro de cada elemento <xref:System.Windows.Documents.Span> fluye según su propia <xref:System.Windows.FlowDirection>.  Esto es aplicable al latín y al árabe, o a cualquier otro idioma.  
  
### Agregar xml:lang  
 En el gráfico siguiente se muestra otro ejemplo que utiliza números y expresiones aritméticas, como `"200.0+21.4=221.4"`.  Observe que sólo se establece <xref:System.Windows.FlowDirection>.  
  
 **Gráfico que muestra números usando sólo FlowDirection**  
  
 ![Números que fluyen de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/langattribute.png "LangAttribute")  
  
 El resultado defraudará a los usuarios de esta aplicación; aunque <xref:System.Windows.FlowDirection> es correcto, los números no tienen la forma que deben tener los números árabes.  
  
 Los elementos XAML pueden incluir un atributo [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] \(`xml:lang`\) que define el idioma de cada elemento.  XAML también admite un principio del lenguaje [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] en virtud del cual los valores de `xml:lang` aplicados a los elementos primarios de un árbol se utilizan en los elementos secundarios.  En el ejemplo anterior, dado que no se definió un idioma para el elemento <xref:System.Windows.Documents.Run> ni para ninguno de sus elementos de nivel superior, se utilizó el idioma predeterminado de `xml:lang`, que es `en-US` para XAML.  El algoritmo interno de cambio de forma de números de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] selecciona los números en el idioma correspondiente, en este caso inglés.  Para poder presentar correctamente los números árabes es necesario establecer `xml:lang`.  
  
 En la ilustración siguiente se muestra el ejemplo al que se ha agregado `xml:lang`.  
  
 **Gráfico que ilustra cómo utilizar el atributo xml:lang**  
  
 ![Números árabes que fluyen de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/langattribute2.png "LangAttribute2")  
  
 El ejemplo siguiente agrega `xml:lang` a la aplicación.  
  
 [!code-xml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Tenga en cuenta que muchos idiomas tienen valores de `xml:lang` diferentes que dependen de la región concreta; por ejemplo, `"ar-SA"` y `"ar-EG"` representan dos variaciones del árabe.  Los ejemplos anteriores muestran que es necesario definir los valores de `xml:lang` y de <xref:System.Windows.FlowDirection>.  
  
<a name="FlowDirectionNontext"></a>   
## FlowDirection con elementos que no son de texto  
 <xref:System.Windows.FlowDirection> define no sólo el flujo del texto en un elemento textual, sino también la dirección de flujo de casi todos los demás elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  El gráfico siguiente muestra un elemento <xref:System.Windows.Controls.ToolBar> que utiliza un <xref:System.Windows.Media.LinearGradientBrush> horizontal para dibujar su fondo.  
  
 **Gráfico que muestra una barra de herramientas con un degradado de izquierda a derecha**  
  
 ![Captura de pantalla de degradado](../../../../docs/framework/wpf/advanced/media/gradient.png "Gradient")  
  
 Después de establecer el elemento <xref:System.Windows.FlowDirection> en <xref:System.Windows.FlowDirection>, no sólo los botones de <xref:System.Windows.Controls.ToolBar> están organizados de derecha a izquierda, sino que incluso <xref:System.Windows.Media.LinearGradientBrush> realinea sus desplazamientos para que fluyan de derecha a izquierda.  
  
 El gráfico siguiente muestra la realineación del elemento <xref:System.Windows.Media.LinearGradientBrush>.  
  
 **Gráfico que muestra una barra de herramientas con un degradado de derecha a izquierda**  
  
 ![Degradado que fluye de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.png "Gradient2\_WPF")  
  
 El ejemplo siguiente dibuja un valor <xref:System.Windows.FlowDirection> <xref:System.Windows.Controls.ToolBar>.  \(Para dibujarlo de izquierda a derecha, quite el atributo <xref:System.Windows.FlowDirection> de <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### Excepciones de FlowDirection  
 Hay algunos casos en los que <xref:System.Windows.FlowDirection> no se comporta de la forma esperada.  En esta sección se describen dos de estas excepciones.  
  
 **Image**  
  
 Un elemento <xref:System.Windows.Controls.Image> representa un control que muestra una imagen.  En [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], se puede utilizar con una propiedad <xref:System.Windows.Controls.Image.Source%2A> que define el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] del elemento <xref:System.Windows.Controls.Image> que se va a mostrar.  
  
 A diferencia de otros elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], <xref:System.Windows.Controls.Image> no hereda <xref:System.Windows.FlowDirection> del contenedor.  Sin embargo, si se establece explícitamente <xref:System.Windows.FlowDirection> en <xref:System.Windows.FlowDirection>, <xref:System.Windows.Controls.Image> se muestra volteado horizontalmente.  Esto se implementa como una característica útil para los programadores de contenido bidireccional, ya que, en algunos casos, al voltear horizontalmente la imagen se genera el efecto deseado.  
  
 El gráfico siguiente muestra un elemento <xref:System.Windows.Controls.Image> volteado.  
  
 **Gráfico que ilustra una imagen volteada**  
  
 ![Captura de pantalla de XamlPad](../../../../docs/framework/wpf/advanced/media/image.png "Image")  
  
 En el ejemplo siguiente se muestra que <xref:System.Windows.Controls.Image> no hereda el valor <xref:System.Windows.FlowDirection> del <xref:System.Windows.Controls.StackPanel> que lo contiene.  **Nota**: debe tener un archivo denominado **ms\_logo.jpg** en la unidad C:\\ para poder ejecutar este ejemplo.  
  
 [!code-xml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Nota**: en los archivos de descarga se incluye un archivo **ms\_logo.jpg**.  El código presupone que el archivo .jpg no está en el proyecto sino en alguna parte de la unidad C:\\.  Debe copiar el .jpg de los archivos de proyecto a la unidad C:\\ o cambiar el código para buscar el archivo en el proyecto.  Para ello, cambie `Source="file://c:/ms_logo.jpg"` a `Source="ms_logo.jpg"`.  
  
 **Path**  
  
 Además de un objeto <xref:System.Windows.Controls.Image>, otro elemento interesante es <xref:System.Windows.Shapes.Path>.  Un trazado es un objeto que puede dibujar una serie de líneas y curvas conectadas.  Se comporta de una manera similar a un elemento <xref:System.Windows.Controls.Image> en relación con su <xref:System.Windows.FlowDirection>; por ejemplo su <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection> es una imagen reflejada horizontal de su <xref:System.Windows.FlowDirection>.  Sin embargo, a diferencia de <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> hereda su valor <xref:System.Windows.FlowDirection> del contenedor y no es necesario especificarlo explícitamente.  
  
 El ejemplo siguiente dibuja una flecha simple mediante 3 líneas.  La primera flecha hereda la dirección de flujo <xref:System.Windows.FlowDirection> del elemento <xref:System.Windows.Controls.StackPanel> para que sus puntos inicial y final se midan desde una raíz en el lado derecho.  La segunda flecha, que tiene un valor <xref:System.Windows.FlowDirection> explícito para <xref:System.Windows.FlowDirection>, también se inicia en el lado derecho.  Sin embargo, la tercera flecha tiene su raíz de inicio en el lado izquierdo.  Para obtener más información sobre cómo dibujar, vea <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 En el gráfico siguiente se muestra el resultado del ejemplo anterior.  
  
 **Gráfico que ilustra las flechas dibujadas mediante el elemento Path**  
  
 ![Rutas](../../../../docs/framework/wpf/advanced/media/paths.png "Paths")  
  
 Los elementos <xref:System.Windows.Controls.Image> y <xref:System.Windows.Shapes.Path> son dos ejemplos de cómo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] utiliza <xref:System.Windows.FlowDirection>.  Además de disponer los elementos de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en una dirección concreta dentro de un contenedor, <xref:System.Windows.FlowDirection> se puede utilizar con elementos como <xref:System.Windows.Controls.InkPresenter> que representa la entrada de lápiz en una superficie, <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush>.  Siempre que necesite un comportamiento de derecha a izquierda para el contenido que imite un comportamiento de izquierda a derecha, o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona esa función.  
  
<a name="NumberSubstitution"></a>   
## Sustitución de números  
 Tradicionalmente, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ha admitido la sustitución de números permitiendo la representación de formas culturales diferentes para los mismos dígitos, manteniendo al mismo tiempo unificado el almacenamiento interno de estos dígitos entre las distintas configuraciones regionales; por ejemplo, los números se almacenan en sus valores hexadecimales ya conocidos, 0x40, 0x41, pero se muestran según el idioma seleccionado.  
  
 Esto ha permitido a las aplicaciones procesar los valores numéricos sin necesidad de convertirlos de un idioma a otro; por ejemplo, un usuario puede abrir una hoja de cálculo de [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] en un sistema [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] localizado al árabe y ver los números en forma árabe, pero también puede abrirlo en una versión europea de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y ver la representación europea de los mismos números.  Esto también es necesario para otros símbolos, como los separadores de coma y el símbolo del porcentaje, ya que éstos normalmente acompañan a los números en el mismo documento.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] continúa con la misma tradición y agrega una compatibilidad más extensa para esta característica, permitiendo un mayor control del usuario sobre cuándo y cómo se utiliza la sustitución.  Aunque esta característica está diseñada para cualquier idioma, es particularmente útil en el contenido bidireccional, donde dar forma a los dígitos para un idioma concreto normalmente constituye un desafío para los desarrolladores de aplicaciones debido a las distintas referencias culturales en las que se podría ejecutar una aplicación.  
  
 La propiedad básica que controla cómo funciona la sustitución de números en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es la propiedad de dependencia <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.  La clase <xref:System.Windows.Media.NumberSubstitution> especifica cómo se muestran los números en el texto.  Dicha clase tiene tres propiedades públicas que definen su comportamiento.  A continuación se muestra un resumen de cada una de las propiedades.  
  
 **CultureSource:**  
  
 Esta propiedad especifica cómo se determina la referencia cultural para los números.  Puede tomar uno de los tres valores de enumeración de <xref:System.Windows.Media.NumberCultureSource> siguientes.  
  
-   Override: La referencia cultural de número es la de la propiedad <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A>.  
  
-   Text: La referencia cultural de número es la de la ejecución de texto.  En el marcado, esta sería `xml:lang`, o la propiedad `Language` de alias \(<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>\).  Asimismo, es el valor predeterminado para las clases que derivan de <xref:System.Windows.FrameworkContentElement>.  Entre estas clases se incluyen <xref:System.Windows.Documents.Paragraph?displayProperty=fullName>, <xref:System.Windows.Documents.Table?displayProperty=fullName>, <xref:System.Windows.Documents.TableCell?displayProperty=fullName>, etc.  
  
-   User: La referencia cultural de número es la del subproceso actual.  Esta propiedad es el valor predeterminado para todas las subclases de <xref:System.Windows.FrameworkElement>, como <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> y <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 La propiedad <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> se utiliza sólo si la propiedad <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> se establece en <xref:System.Windows.Media.NumberCultureSource>; de lo contrario, se omite.  Especifica la referencia cultural de número.  El valor `null`, el valor predeterminado, se interpreta como en\-US.  
  
 **Substitution**:  
  
 Esta propiedad especifica el tipo de sustitución de números que se va a realizar.  Puede tomar uno de los valores de enumeración <xref:System.Windows.Media.NumberSubstitutionMethod> siguientes.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: el método de sustitución se determina basándose en la propiedad <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=fullName> de la referencia cultural de número.  Éste es el valor predeterminado.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: si la referencia cultural de número es árabe o persa, especifica que los dígitos dependen del contexto.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: los números siempre se presentan como dígitos europeos.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: los números se presentan utilizando los dígitos nacionales para la referencia cultural de número, tal y como lo especifica la propiedad <xref:System.Globalization.CultureInfo.NumberFormat%2A> de la referencia cultural.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: los números se presentan mediante dígitos tradicionales para la referencia cultural de número.  Para la mayoría de las referencias culturales, esto es lo mismo que <xref:System.Windows.Media.NumberSubstitutionMethod>.  Sin embargo, <xref:System.Windows.Media.NumberSubstitutionMethod> genera dígitos latinos en algunas referencias culturales árabes, mientras que este valor genera dígitos árabes para todas las referencias culturales árabes.  
  
 ¿Qué significan esos valores para un programador de contenido bidireccional?  En la mayoría de los casos, el desarrollador sólo necesitará definir <xref:System.Windows.FlowDirection> y el idioma de cada elemento textual de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], por ejemplo `Language="ar-SA"`; la lógica de <xref:System.Windows.Media.NumberSubstitution> se encargará de mostrar los números según la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] correcta.  El ejemplo siguiente muestra cómo utilizar números árabes e ingleses en una aplicación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que se ejecuta en una versión de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] en árabe.  
  
 [!code-xml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 El gráfico siguiente muestra el resultado del ejemplo anterior si se está ejecutando una versión de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] en árabe.  
  
 **Gráfico que muestra los números árabes e ingleses presentados**  
  
 ![Captura de pantalla de XamlPad con números](../../../../docs/framework/wpf/advanced/media/numbers.png "Numbers")  
  
 El elemento <xref:System.Windows.FlowDirection> era importante en este caso porque si se hubiese establecido <xref:System.Windows.FlowDirection> en <xref:System.Windows.FlowDirection>, se habrían generado dígitos europeos.  Las secciones siguientes describen cómo conseguir una presentación unificada de dígitos en todo el documento.  Si este ejemplo no se ejecuta en un sistema de Windows en árabe, todos los dígitos se mostrarán como dígitos europeos.  
  
 **Definir las reglas de sustitución**  
  
 En una aplicación real es posible que necesite establecer el idioma mediante programación.  Por ejemplo, imagine que desea establecer el atributo `xml:lang` para que sea igual que el utilizado por la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del sistema, o cambiar el idioma dependiendo del estado de la aplicación.  
  
 Si desea realizar modificaciones basándose en el estado de la aplicación, utilice otras características de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 En primer lugar, establezca el valor `NumberSubstitution.CultureSource="Text"` del componente de aplicación.  Utilice dicho valor para asegurarse de que la configuración no procede de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para los elementos de texto que tienen "User" como valor predeterminado, como por ejemplo <xref:System.Windows.Controls.TextBlock>.  
  
 Por ejemplo:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 En el código [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] correspondiente, establezca la propiedad `Language` por ejemplo en `"ar-SA"`.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 Si necesita establecer la propiedad `Language` en el idioma de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del usuario actual, utilice el código siguiente.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> representa la referencia cultural actual utilizada por el subproceso actual en tiempo de ejecución.  
  
 El último ejemplo de [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] debería ser similar al siguiente.  
  
 [!code-xml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 El último ejemplo de [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] debería ser similar al siguiente.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 El gráfico siguiente muestra la apariencia de la ventana para cualquiera de los dos lenguajes de programación.  
  
 **Gráfico que muestra números árabes**  
  
 ![Números árabes](../../../../docs/framework/wpf/advanced/media/numbers2.png "Numbers2")  
  
 **Usar la propiedad de sustitución**  
  
 El funcionamiento de la sustitución de números en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] depende tanto del idioma del elemento de texto como de su <xref:System.Windows.FlowDirection>.  Si el elemento <xref:System.Windows.FlowDirection> es de izquierda a derecha, se representan dígitos europeos.  Sin embargo, si va precedido de texto árabe o se ha establecido el idioma en "ar" y <xref:System.Windows.FlowDirection> es <xref:System.Windows.FlowDirection>, se presentan dígitos árabes.  
  
 En algunos casos, sin embargo, es conveniente crear una aplicación unificada, por ejemplo dígitos europeos para todos los usuarios.  O dígitos árabes en celdas de un elemento <xref:System.Windows.Documents.Table> con un <xref:System.Windows.Style> concreto.  Una forma fácil de hacerlo consiste en utilizar la propiedad <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.  
  
 En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> no tiene establecida la propiedad <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>, por lo que el algoritmo muestra dígitos árabes conforme a lo esperado.  Sin embargo, en el segundo elemento <xref:System.Windows.Controls.TextBlock>, la sustitución se ha establecido en europeo, lo que reemplaza la sustitución predeterminada para los números árabes, y hace que se muestren los dígitos europeos.  
  
 [!code-xml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]