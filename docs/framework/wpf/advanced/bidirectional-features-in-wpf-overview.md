---
title: Información general sobre características bidireccionales en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: efe3d06c533d4d2be7364da66ccd3f101c8869d4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188162"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Información general sobre características bidireccionales en WPF
A diferencia de cualquier otra plataforma de desarrollo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene muchas características que admiten el desarrollo rápido de contenido bidireccional, por ejemplo, combinados de izquierda a derecha y de derecha a izquierda datos en el mismo documento. Al mismo tiempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea una excelente experiencia para los usuarios que requieren características bidireccionales, como el árabe y hebreo hablando a los usuarios.  
  
 En las siguientes secciones se explican muchas características bidireccionales, junto con ejemplos que muestran cómo conseguir la mejor visualización de contenido bidireccional. La mayoría de los ejemplos usan [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], aunque se pueden aplicar fácilmente los conceptos de C# o código de Microsoft Visual Basic.  
  

  
<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 La propiedad básica que define la dirección de flujo de contenido en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación es <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Esta propiedad puede establecerse en uno de dos valores de enumeración, <xref:System.Windows.FlowDirection.LeftToRight> o <xref:System.Windows.FlowDirection.RightToLeft>. La propiedad está disponible para todos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos que heredan de <xref:System.Windows.FrameworkElement>.  
  
 El ejemplo siguiente establece la dirección del flujo de un <xref:System.Windows.Controls.TextBox> elemento.  
  
 **Dirección del flujo de izquierda a derecha**  
  
 [!code-xaml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **Dirección del flujo de derecha a izquierda**  
  
 [!code-xaml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 En el gráfico siguiente se muestra cómo se representa el código anterior.  
  
 **Gráfico que ilustra FlowDirection**  
  
 ![Alineación de TextBlock](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.PNG "LefttoRightRighttoLeft")  
  
 Un elemento dentro de un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] árbol heredará el <xref:System.Windows.FrameworkElement.FlowDirection%2A> desde su contenedor. En el ejemplo siguiente, la <xref:System.Windows.Controls.TextBlock> está dentro de un <xref:System.Windows.Controls.Grid>, que reside en un <xref:System.Windows.Window>. Establecer el <xref:System.Windows.FrameworkElement.FlowDirection%2A> para el <xref:System.Windows.Window> implica establecerla también para la <xref:System.Windows.Controls.Grid> y <xref:System.Windows.Controls.TextBlock> así.  
  
 El ejemplo siguiente se muestra cómo establecer <xref:System.Windows.FrameworkElement.FlowDirection%2A>.  
  
 [!code-xaml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 El nivel superior <xref:System.Windows.Window> tiene un <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>, por lo que todos los elementos incluidos en él también heredan la misma <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Para un elemento invalide una especificado <xref:System.Windows.FrameworkElement.FlowDirection%2A> , debe agregar un cambio de dirección explícito como el segundo <xref:System.Windows.Controls.TextBlock> en el ejemplo anterior, que cambia a <xref:System.Windows.FlowDirection.LeftToRight>. Cuando no hay ninguna <xref:System.Windows.FrameworkElement.FlowDirection%2A> está definido, el valor predeterminado <xref:System.Windows.FlowDirection.LeftToRight> se aplica.  
  
 En el gráfico siguiente se muestra la salida del ejemplo anterior.  
  
 **Gráfico que muestra explícitamente la propiedad FlowDirection asignada**  
  
 ![Ilustración de la dirección del flujo](../../../../docs/framework/wpf/advanced/media/flowdir.PNG "FlowDir")  
  
<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 Muchas plataformas de desarrollo como [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] y Java proporcionan una compatibilidad especial para el desarrollo de contenido bidireccional. Lenguajes de marcado como [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] dar a los creadores de contenido el marcado necesario para mostrar texto en cualquier dirección, por ejemplo el [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 etiqueta, "dir" que toma "rtl" o "ltr" como valores. Esta etiqueta es similar a la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad, pero el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad funciona de forma más avanzada para el diseño del contenido textual y se puede usar para el contenido que no sea texto.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un <xref:System.Windows.Documents.FlowDocument> es una versátil [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento que puede hospedar una combinación de texto, tablas, imágenes y otros elementos. Los ejemplos de las secciones siguientes usan este elemento.  
  
 Agregar texto a un <xref:System.Windows.Documents.FlowDocument> se puede realizar de varias maneras. Una manera sencilla de hacerlo es a través de un <xref:System.Windows.Documents.Paragraph> que es un elemento de nivel de bloque usado para agrupar el contenido como texto. Para agregar texto a elementos de nivel alineado los ejemplos utilizan <xref:System.Windows.Documents.Span> y <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span> es un elemento de contenido dinámico insertado utilizado para agrupar otros elementos en línea, mientras que un <xref:System.Windows.Documents.Run> es un flujo de nivel en línea el contenido de elemento está destinado a contener una ejecución de texto sin formato. Un <xref:System.Windows.Documents.Span> puede contener varios <xref:System.Windows.Documents.Run> elementos.  
  
 El primer ejemplo de documento contiene un documento que tiene un número de red comparten nombres; Por ejemplo `\\server1\folder\file.ext`. Tanto si tiene este vínculo de red en un documento en árabe como en inglés, siempre quiere que aparezca de la misma manera. El siguiente gráfico muestra el vínculo en un árabe <xref:System.Windows.FlowDirection.RightToLeft> documento.  
  
 **Gráfico que muestra cómo usar el elemento Span**  
  
 ![Documento con flujo de texto de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/flowdocument.PNG "FlowDocument")  
  
 Dado que el texto es <xref:System.Windows.FlowDirection.RightToLeft>especial todos los caracteres, como el "\\", separar el texto de derecha a izquierda orden. Esto da como resultado el vínculo no se muestra en el orden correcto, por lo tanto, para solucionar el problema, el texto debe estar incrustado para conservar un independiente <xref:System.Windows.Documents.Run> fluir <xref:System.Windows.FlowDirection.LeftToRight>. En lugar de tener otro <xref:System.Windows.Documents.Run> para cada idioma, una mejor manera de resolver el problema es insertar el texto en inglés usado con menos frecuencia en árabe de mayor tamaño <xref:System.Windows.Documents.Span>.  
  
 En el siguiente gráfico se ilustra este proceso.  
  
 **Gráfico que muestra cómo usar el elemento Run insertado en un elemento Span**  
  
 ![Captura de pantalla de XamlPad](../../../../docs/framework/wpf/advanced/media/runspan.PNG "RunSpan")  
  
 El ejemplo siguiente se muestra cómo usar <xref:System.Windows.Documents.Run> y <xref:System.Windows.Documents.Span> elementos de documentos.  
  
 [!code-xaml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Elementos Span  
 El <xref:System.Windows.Documents.Span> elemento funciona como un separador de límite entre textos con diferentes direcciones de flujo.  Incluso <xref:System.Windows.Documents.Span> se consideran elementos con la misma dirección de flujo con ámbitos diferentes bidireccional lo que significa que el <xref:System.Windows.Documents.Span> elementos se ordenan en el contenedor <xref:System.Windows.FlowDirection>, solo el contenido dentro de la <xref:System.Windows.Documents.Span> elemento sigue la <xref:System.Windows.FlowDirection> de la <xref:System.Windows.Documents.Span>.  
  
 El gráfico siguiente muestra la dirección del flujo de varios <xref:System.Windows.Controls.TextBlock> elementos.  
  
 **Gráfico que ilustra la propiedad FlowDirection en varios elementos TextBlock**  
  
 ![Bloques de texto con diferentes direcciones de flujo](../../../../docs/framework/wpf/advanced/media/span.PNG "Span")  
  
 El ejemplo siguiente muestra cómo usar el <xref:System.Windows.Documents.Span> y <xref:System.Windows.Documents.Run> elementos para generar los resultados mostrados en el gráfico anterior.  
  
 [!code-xaml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 En el <xref:System.Windows.Controls.TextBlock> elementos en el ejemplo, el <xref:System.Windows.Documents.Span> elementos se distribuyen según la <xref:System.Windows.FlowDirection> de sus elementos primarios, pero el texto dentro de cada <xref:System.Windows.Documents.Span> elemento flujos según su propio <xref:System.Windows.FlowDirection>. Esto es aplicable a los idiomas latín y árabe, o a cualquier otro idioma.  
  
### <a name="adding-xmllang"></a>Agregar xml:lang  
 El gráfico siguiente muestra otro ejemplo que usa números y expresiones aritméticas, como `"200.0+21.4=221.4"`. Observe que solo el <xref:System.Windows.FlowDirection> está establecido.  
  
 **Gráfico que muestra números usando solo FlowDirection**  
  
 ![Números que fluyen de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/langattribute.PNG "LangAttribute")  
  
 Los usuarios de esta aplicación decepcionará la salida, aunque el <xref:System.Windows.FlowDirection> es correcta, los números no tienen el formato que deben ser en forma de números árabes.  
  
 Los elementos XAML pueden incluir un [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] atributo (`xml:lang`) que define el idioma de cada elemento. XAML también admite un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] principio de idioma mediante el cual `xml:lang` usan los valores que se aplica a los elementos primarios en el árbol de elementos secundarios. En el ejemplo anterior, porque no se definió un idioma para el <xref:System.Windows.Documents.Run> elementos, el valor predeterminado de nivel de elemento o cualquiera de sus principales `xml:lang` se utilizó, que es `en-US` para XAML. El algoritmo para dar forma número interno de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] selecciona los números en el idioma correspondiente, en este caso inglés. Para realizar el árabe números render correctamente `xml:lang` debe establecerse.  
  
 El gráfico siguiente muestra el ejemplo con `xml:lang` agregado.  
  
 **Gráfico que muestra cómo usar el atributo xml:lang**  
  
 ![Números árabes que fluyen de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/langattribute2.PNG "LangAttribute2")  
  
 En el ejemplo siguiente se agrega `xml:lang` a la aplicación.  
  
 [!code-xaml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 Tenga en cuenta que muchos idiomas tienen distintos `xml:lang` valores dependiendo de la región de destino, por ejemplo, `"ar-SA"` y `"ar-EG"` representan dos variaciones de árabe. Los ejemplos anteriores muestran que es necesario definir ambos el `xml:lang` y <xref:System.Windows.FlowDirection> valores.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementos no textuales  
 <xref:System.Windows.FlowDirection> define no solo cómo fluye el texto en un elemento textual, sino también la dirección del flujo de prácticamente cualquier otro [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento. El gráfico siguiente muestra un <xref:System.Windows.Controls.ToolBar> que usa una horizontal <xref:System.Windows.Media.LinearGradientBrush> para dibujar el fondo.  
  
 **Gráfico que muestra una barra de herramientas con un degradado de izquierda a derecha**  
  
 ![Captura de pantalla de degradado](../../../../docs/framework/wpf/advanced/media/gradient.PNG "Gradient")  
  
 Después de establecer el <xref:System.Windows.FlowDirection> a <xref:System.Windows.FlowDirection.RightToLeft>, no solo el <xref:System.Windows.Controls.ToolBar> botones se organizan de derecha a izquierda, pero incluso la <xref:System.Windows.Media.LinearGradientBrush> realinea sus desplazamientos para que fluyan de derecha a izquierda.  
  
 El gráfico siguiente muestra la Realineación de la <xref:System.Windows.Media.LinearGradientBrush>.  
  
 **Gráfico que muestra una barra de herramientas con un degradado de derecha a izquierda**  
  
 ![Degradado que fluye de derecha a izquierda](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.PNG "Gradient2_WPF")  
  
 En el ejemplo siguiente se dibuja un <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>. (Para dibujarlo de izquierda a derecha, quite el <xref:System.Windows.FlowDirection> atributo el <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>Excepciones de FlowDirection  
 Hay algunos casos donde <xref:System.Windows.FlowDirection> no se comporta según lo previsto. En esta sección se describen dos de estas excepciones.  
  
 **Image**  
  
 Un <xref:System.Windows.Controls.Image> representa un control que muestra una imagen. En [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] se puede usar con un <xref:System.Windows.Controls.Image.Source%2A> propiedad que define el [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] de la <xref:System.Windows.Controls.Image> para mostrar.  
  
 A diferencia de otras [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos, un <xref:System.Windows.Controls.Image> no hereda la <xref:System.Windows.FlowDirection> desde el contenedor. Sin embargo, si la <xref:System.Windows.FlowDirection> se establece explícitamente en <xref:System.Windows.FlowDirection.RightToLeft>, un <xref:System.Windows.Controls.Image> se muestra volteado horizontalmente. Se implementa como una práctica característica para los desarrolladores de contenido bidireccional, porque el volteo horizontal de la imagen muestra el efecto deseado en algunos casos.  
  
 El gráfico siguiente muestra un volteado <xref:System.Windows.Controls.Image>.  
  
 **Gráfico que muestra una imagen volteada**  
  
 ![Captura de pantalla de XamlPad](../../../../docs/framework/wpf/advanced/media/image.PNG "Image")  
  
 En el ejemplo siguiente se muestra que el <xref:System.Windows.Controls.Image> no hereda la <xref:System.Windows.FlowDirection> desde el <xref:System.Windows.Controls.StackPanel> que lo contiene. **Tenga en cuenta** debe tener un archivo denominado **ms_logo.jpg** en la unidad C:\ para ejecutar este ejemplo.  
  
 [!code-xaml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **Tenga en cuenta** se incluye en los archivos de descarga es un **ms_logo.jpg** archivo. En el código, se supone que el archivo .jpg no está dentro del proyecto, sino en alguna ubicación de la unidad C:\. Debe copiar el archivo .jpg de los archivos del proyecto en la unidad C:\ o cambiar el código para buscar el archivo dentro del proyecto. Para ello, cambie `Source="file://c:/ms_logo.jpg"` a `Source="ms_logo.jpg"`.  
  
 **Rutas de acceso**  
  
 Además un <xref:System.Windows.Controls.Image>, otro elemento interesante es <xref:System.Windows.Shapes.Path>. Patch es un objeto que puede dibujar una serie de líneas y curvas conectadas. Se comporta de manera similar a un <xref:System.Windows.Controls.Image> relacionada con su <xref:System.Windows.FlowDirection>; por ejemplo su <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> es un reflejo horizontal de su <xref:System.Windows.FlowDirection.LeftToRight> uno. Sin embargo, a diferencia de un <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> hereda su <xref:System.Windows.FlowDirection> desde el contenedor y uno no es necesario especificarla explícitamente.  
  
 En el ejemplo siguiente se dibuja una flecha simple mediante 3 líneas. La primera flecha hereda la <xref:System.Windows.FlowDirection.RightToLeft> flujo dirección desde el <xref:System.Windows.Controls.StackPanel> para que sus puntos inicial y final se midan desde una raíz en el lado derecho. La segunda flecha, que tiene un explícito <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> también se inicia en el lado derecho. Sin embargo, la tercera flecha tiene su raíz de inicio en el lado izquierdo. Para obtener más información sobre el dibujo vea <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.GeometryGroup>.  
  
 [!code-xaml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 En el gráfico siguiente se muestra la salida del ejemplo anterior.  
  
 **Gráfico que muestra las flechas dibujadas mediante el elemento Path**  
  
 ![Rutas de acceso](../../../../docs/framework/wpf/advanced/media/paths.PNG "Paths")  
  
 El <xref:System.Windows.Controls.Image> y <xref:System.Windows.Shapes.Path> son dos ejemplos de cómo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] usa <xref:System.Windows.FlowDirection>. Además de diseñar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos en una dirección específica dentro de un contenedor, <xref:System.Windows.FlowDirection> puede usarse con elementos como <xref:System.Windows.Controls.InkPresenter> que representa la entrada de lápiz en una superficie, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>. Siempre que necesite un derecho al comportamiento de la izquierda para contenido que imite un de izquierda a derecha comportamiento, o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona esa funcionalidad.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>Sustitución de números  
 Históricamente, [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] ha admitido la sustitución de números, ya que permite la representación de formas culturales diferentes para los mismos dígitos al tiempo que mantiene el almacenamiento interno de estos dígitos unificado en diferentes configuraciones regionales, los números de ejemplo están almacenados en sus valores hexadecimales conocidos, 0 x 40, 0 x 41, pero se muestran según el idioma seleccionado.  
  
 Esto permite a las aplicaciones procesar valores numéricos sin necesidad de convertir de un idioma a otro, por ejemplo, un usuario puede abrir un [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] hoja de cálculo en un árabe localizado [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y ver los números en árabe, pero abrir en una versión Europea de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y ver una representación Europea de los mismos números. Esto también es necesario para otros símbolos, como el símbolo de porcentaje y los separadores de coma, porque suelen acompañar a los números del mismo documento.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] continúa con la tradición y agrega más compatibilidad con esta característica, que aumenta el control del usuario sobre cuándo y cómo usar la sustitución. Aunque esta característica está diseñada para cualquier idioma, es especialmente útil en el contenido bidireccional, donde definir los dígitos de un idioma concreto normalmente constituye un desafío para los desarrolladores de aplicaciones debido a las distintas referencias culturales en las que se puede ejecutar una aplicación.  
  
 La propiedad de núcleo que controla la sustitución de números de cómo funciona en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es el <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> propiedad de dependencia. La <xref:System.Windows.Media.NumberSubstitution> clase especifica cómo se mostrarán los números en texto. Tiene tres propiedades públicas que definen su comportamiento. A continuación se muestra un resumen de cada una de las propiedades.  
  
 **CultureSource:**  
  
 Esta propiedad especifica cómo se determina la referencia cultural para los números. Puede tomar uno de tres <xref:System.Windows.Media.NumberCultureSource> valores de enumeración.  
  
-   Reemplazo: Referencia cultural de número es el de <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> propiedad.  
  
-   Text: la referencia cultural de número es la referencia cultural de la ejecución de texto. En el marcado, esto sería `xml:lang`, o su alias `Language` propiedad (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Además, es el valor predeterminado para las clases derivadas de <xref:System.Windows.FrameworkContentElement>. Estas clases incluyen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> y así sucesivamente.  
  
-   User: la referencia cultural de número es la referencia cultural del subproceso actual. Esta propiedad es el valor predeterminado para todas las subclases de <xref:System.Windows.FrameworkElement> como <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> y <xref:System.Windows.Controls.TextBlock>.  
  
 **CultureOverride**:  
  
 El <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> propiedad se usa únicamente si el <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> propiedad está establecida en <xref:System.Windows.Media.NumberCultureSource.Override> y se omite en caso contrario. Especifica la referencia cultural de número. Un valor de `null`, el valor predeterminado, se interpreta como en-US.  
  
 **Substitution**:  
  
 Esta propiedad especifica el tipo de sustitución de números que se va a realizar. Puede tomar uno de los siguientes <xref:System.Windows.Media.NumberSubstitutionMethod> valores de enumeración.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: El método de sustitución se determina según la referencia cultural de número <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> propiedad. Este es el valor predeterminado.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Si la referencia cultural de número es árabe o persa, especifica que los dígitos dependen del contexto.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>: Números siempre se representan como dígitos europeos.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: Los números se representan mediante los dígitos nacionales de la referencia cultural de número, según lo especificado por la referencia cultural <xref:System.Globalization.CultureInfo.NumberFormat%2A>.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: Los números se representan mediante dígitos tradicionales para la referencia cultural de número. La mayoría de las referencias culturales, esto equivale a <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Sin embargo, <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> produce dígitos latinos en algunas referencias culturales árabes, mientras que este valor genera dígitos árabes para todas las referencias culturales árabes.  
  
 ¿Qué significan esos valores para un desarrollador de contenido bidireccional? En la mayoría de los casos, el desarrollador podría sólo necesita definir <xref:System.Windows.FlowDirection> y el idioma de cada uno de ellos textual [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento, por ejemplo `Language="ar-SA"` y <xref:System.Windows.Media.NumberSubstitution> lógica se encarga de mostrar los números de acuerdo con el valor correcto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. En el ejemplo siguiente se muestran números árabes e ingleses en una [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación que se ejecuta en una versión árabe de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 [!code-xaml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 El gráfico siguiente muestra el resultado del ejemplo anterior, si está ejecutando en una versión árabe de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  
  
 **Gráfico que muestra números árabes e ingleses**  
  
 ![Captura de pantalla de XamlPad con números](../../../../docs/framework/wpf/advanced/media/numbers.PNG "Numbers")  
  
 El <xref:System.Windows.FlowDirection> era importante en este caso, dado que establecer el <xref:System.Windows.FlowDirection> a <xref:System.Windows.FlowDirection.LeftToRight> en su lugar habría producido dígitos europeos. En las secciones siguientes se explica cómo conseguir una presentación unificada de dígitos en todo el documento. Si este ejemplo no se ejecuta en una versión árabe de Windows, todos los dígitos se mostrarán como dígitos europeos.  
  
 **Definición de reglas de sustitución**  
  
 En una aplicación real, es posible que tenga que establecer el idioma mediante programación. Por ejemplo, desea establecer el `xml:lang` atributo sea el mismo que el utilizado por el sistema [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], o quizás cambiar el idioma en función del estado de la aplicación.  
  
 Si desea realizar cambios según el estado de la aplicación, asegúrese de utilizar de otras características proporcionadas por [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 En primer lugar, establezca el componente de aplicación `NumberSubstitution.CultureSource="Text"`. Esta configuración garantiza que no provienen de la configuración de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para los elementos de texto que tienen "User" como valor predeterminado, como <xref:System.Windows.Controls.TextBlock>.  
  
Por ejemplo:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

En las correspondientes C# de código, establezca el `Language` propiedad, por ejemplo, para `"ar-SA"`.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Si tiene que establecer el `Language` propiedad para el idioma de interfaz de usuario del usuario actual, use el código siguiente.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> representa la referencia cultural actual utilizada por el subproceso actual en tiempo de ejecución.  
  
 El último [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] ejemplo debería ser similar al ejemplo siguiente.  
  
 [!code-xaml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 El último C# ejemplo debería ser similar al siguiente.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 El gráfico siguiente muestra el aspecto de la ventana para cualquier lenguaje de programación.  
  
 **Gráfico que muestra números árabes**  
  
 ![Números árabes](../../../../docs/framework/wpf/advanced/media/numbers2.PNG "Numbers2")  
  
 **Uso de la propiedad Substitution**  
  
 La sustitución de números forma funciona en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] depende tanto del idioma del elemento de texto y su <xref:System.Windows.FlowDirection>. Si el <xref:System.Windows.FlowDirection> izquierda a derecha y, a continuación, se representan dígitos europeos. Sin embargo si está precedido de texto en árabe, o el idioma establecido en "ar" y el <xref:System.Windows.FlowDirection> es <xref:System.Windows.FlowDirection.RightToLeft>, se representan dígitos árabes en su lugar.  
  
 En algunos casos, sin embargo, es posible que quiera crear una aplicación unificada, como, por ejemplo, dígitos europeos para todos los usuarios. O dígitos árabes en <xref:System.Windows.Documents.Table> celdas con un valor concreto <xref:System.Windows.Style>. Una forma fácil de hacer que está usando el <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> propiedad.  
  
 En el ejemplo siguiente, la primera <xref:System.Windows.Controls.TextBlock> no tiene el <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> establece la propiedad, por lo que el algoritmo muestra dígitos árabes según lo previsto. Sin embargo en el segundo <xref:System.Windows.Controls.TextBlock>, la sustitución está establecida en European invalida la sustitución predeterminada para los números árabes y se muestran dígitos europeos.  
  
 [!code-xaml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
