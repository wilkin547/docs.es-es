---
title: Información general sobre características bidireccionales
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 17167b1afa5037998d9ea8ed679a66c89babe242
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741633"
---
# <a name="bidirectional-features-in-wpf-overview"></a>Información general sobre características bidireccionales en WPF

A diferencia de cualquier otra plataforma de desarrollo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene muchas características que admiten el desarrollo rápido de contenido bidireccional, por ejemplo, mixto de izquierda a derecha y de derecha a izquierda en el mismo documento. Al mismo tiempo, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea una excelente experiencia para los usuarios que requieren características bidireccionales como los usuarios de habla árabe y hebreo.

En las siguientes secciones se explican muchas características bidireccionales, junto con ejemplos que muestran cómo conseguir la mejor visualización de contenido bidireccional. La mayoría de los ejemplos usan XAML, aunque puede aplicar fácilmente los conceptos a C# o a Microsoft Visual Basic código.

<a name="FlowDirection"></a>

## <a name="flowdirection"></a>FlowDirection

La propiedad básica que define la dirección del flujo de contenido en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Esta propiedad se puede establecer en uno de los dos valores de enumeración <xref:System.Windows.FlowDirection.LeftToRight> o <xref:System.Windows.FlowDirection.RightToLeft>. La propiedad está disponible para todos los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que heredan de <xref:System.Windows.FrameworkElement>.

En los ejemplos siguientes se establece la dirección de flujo de un elemento <xref:System.Windows.Controls.TextBox>.

**Dirección del flujo de izquierda a derecha**

[!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]

**Dirección del flujo de derecha a izquierda**

[!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]

En el gráfico siguiente se muestra cómo se representa el código anterior.

![Gráfico que muestra las distintas direcciones de flujo.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)

Un elemento dentro de un árbol de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] heredará el <xref:System.Windows.FrameworkElement.FlowDirection%2A> de su contenedor. En el ejemplo siguiente, el <xref:System.Windows.Controls.TextBlock> está dentro de un <xref:System.Windows.Controls.Grid>, que se encuentra en un <xref:System.Windows.Window>. Establecer la <xref:System.Windows.FrameworkElement.FlowDirection%2A> para el <xref:System.Windows.Window> implica establecerla también para el <xref:System.Windows.Controls.Grid> y el <xref:System.Windows.Controls.TextBlock>.

En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.FrameworkElement.FlowDirection%2A>.

[!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]

El <xref:System.Windows.Window> de nivel superior tiene un <xref:System.Windows.FlowDirection><xref:System.Windows.FlowDirection.RightToLeft>, por lo que todos los elementos contenidos en él también heredan la misma <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Para que un elemento invalide una <xref:System.Windows.FrameworkElement.FlowDirection%2A> especificada, debe agregar un cambio de dirección explícito como el segundo <xref:System.Windows.Controls.TextBlock> en el ejemplo anterior que cambia a <xref:System.Windows.FlowDirection.LeftToRight>. Cuando no se define ningún <xref:System.Windows.FrameworkElement.FlowDirection%2A>, se aplica la <xref:System.Windows.FlowDirection.LeftToRight> predeterminada.

En el gráfico siguiente se muestra la salida del ejemplo anterior:

![Gráfico que muestra el cambio de dirección de flujo explícito.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)

<a name="FlowDocument"></a>

## <a name="flowdocument"></a>FlowDocument

Muchas plataformas de desarrollo como HTML, Win32 y Java proporcionan compatibilidad especial para el desarrollo de contenido bidireccional. Los lenguajes de marcado, como HTML, proporcionan a los escritores de contenido el marcado necesario para mostrar texto en cualquier dirección requerida, por ejemplo, la etiqueta HTML 4,0, "dir" que toma "RTL" o "LTR" como valores. Esta etiqueta es similar a la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>, pero la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> funciona de forma más avanzada para el diseño del contenido textual y se puede usar para contenido que no sea texto.

En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], un <xref:System.Windows.Documents.FlowDocument> es un elemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] versátil que puede hospedar una combinación de texto, tablas, imágenes y otros elementos. Los ejemplos de las secciones siguientes usan este elemento.

Agregar texto a un <xref:System.Windows.Documents.FlowDocument> se puede hacer de una sola manera. Una manera sencilla de hacerlo es a través de una <xref:System.Windows.Documents.Paragraph> que es un elemento de nivel de bloque usado para agrupar contenido como texto. Para agregar texto a los elementos en el nivel insertado, los ejemplos usan <xref:System.Windows.Documents.Span> y <xref:System.Windows.Documents.Run>. <xref:System.Windows.Documents.Span> es un elemento de contenido dinámico de nivel insertado que se utiliza para agrupar otros elementos insertados, mientras que un <xref:System.Windows.Documents.Run> es un elemento de contenido dinámico de nivel insertado diseñado para contener una ejecución de texto sin formato. Un <xref:System.Windows.Documents.Span> puede contener varios elementos <xref:System.Windows.Documents.Run>.

El primer ejemplo de documento contiene un documento que tiene un número de nombres de recurso compartido de red; por ejemplo `\\server1\folder\file.ext`. Tanto si tiene este vínculo de red en un documento en árabe como en inglés, siempre quiere que aparezca de la misma manera. En el gráfico siguiente se ilustra el uso del elemento span y se muestra el vínculo en un documento <xref:System.Windows.FlowDirection.RightToLeft> árabe:

![Gráfico que ilustra el uso del elemento span.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")

Dado que el texto se <xref:System.Windows.FlowDirection.RightToLeft>, todos los caracteres especiales, como "\\", separan el texto de derecha a izquierda. Esto hace que el vínculo no se muestre en el orden correcto, por lo que para resolver el problema, el texto debe estar incrustado para conservar un <xref:System.Windows.FlowDirection.LeftToRight>de flujo de <xref:System.Windows.Documents.Run> independiente. En lugar de tener un <xref:System.Windows.Documents.Run> independiente para cada idioma, una mejor manera de resolver el problema es insertar el texto en inglés que se usa con menos frecuencia en un <xref:System.Windows.Documents.Span>árabe más grande.

En el gráfico siguiente se ilustra esto mediante el elemento Run insertado en un elemento span:

![Gráfico que muestra el elemento de ejecución incrustado en un elemento span.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)

En el ejemplo siguiente se muestra cómo usar los elementos <xref:System.Windows.Documents.Run> y <xref:System.Windows.Documents.Span> en los documentos.

[!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]

<a name="SpanElements"></a>

## <a name="span-elements"></a>Elementos Span

El elemento <xref:System.Windows.Documents.Span> funciona como un separador de límites entre textos con diferentes direcciones de flujo.  Incluso <xref:System.Windows.Documents.Span> elementos con la misma dirección de flujo se consideran diferentes ámbitos bidireccionales, lo que significa que los elementos <xref:System.Windows.Documents.Span> se ordenan en el <xref:System.Windows.FlowDirection>del contenedor, solo el contenido dentro del elemento <xref:System.Windows.Documents.Span> sigue el <xref:System.Windows.FlowDirection> de la <xref:System.Windows.Documents.Span>.

En el gráfico siguiente se muestra la dirección del flujo de varios elementos <xref:System.Windows.Controls.TextBlock>.

![Gráfico que ilustra los bloques de texto con diferentes direcciones de flujo.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)

En el ejemplo siguiente se muestra cómo usar los elementos <xref:System.Windows.Documents.Span> y <xref:System.Windows.Documents.Run> para generar los resultados que se muestran en el gráfico anterior.

[!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]

En los elementos <xref:System.Windows.Controls.TextBlock> del ejemplo, los elementos de la <xref:System.Windows.Documents.Span> se disponen de acuerdo con la <xref:System.Windows.FlowDirection> de sus elementos primarios, pero el texto de cada elemento de <xref:System.Windows.Documents.Span> fluye según su propio <xref:System.Windows.FlowDirection>. Esto es aplicable a los idiomas latín y árabe, o a cualquier otro idioma.

### <a name="adding-xmllang"></a>Agregar xml:lang

En el gráfico siguiente se muestra otro ejemplo que usa números y expresiones aritméticas, como `"200.0+21.4=221.4"`. Observe que solo se establece el <xref:System.Windows.FlowDirection>.

![Gráfico que muestra números usando solo FlowDirection.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)

Los usuarios de esta aplicación estarán decepcionados por la salida, aunque la <xref:System.Windows.FlowDirection> sea correcta, los números no se conforman como números arábigos.

Los elementos XAML pueden incluir un atributo XML (`xml:lang`) que define el idioma de cada elemento. XAML también admite un principio de lenguaje XML en el que los elementos secundarios usan `xml:lang` valores que se aplican a los elementos primarios del árbol. En el ejemplo anterior, dado que no se definió un idioma para el elemento <xref:System.Windows.Documents.Run> o ninguno de sus elementos de nivel superior, se usó el `xml:lang` predeterminado, que es `en-US` para XAML. El algoritmo de forma de número interno de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] selecciona números en el idioma correspondiente (en este caso, Inglés). Para que los números árabes se representen correctamente `xml:lang` es necesario establecerlo.

En el gráfico siguiente se muestra el ejemplo con `xml:lang` agregado.

![Gráfico que muestra números árabes que fluyen de derecha a izquierda.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)

En el ejemplo siguiente se agrega `xml:lang` a la aplicación.

[!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]

Tenga en cuenta que muchos idiomas tienen diferentes valores de `xml:lang` en función de la región de destino; por ejemplo, `"ar-SA"` y `"ar-EG"` representan dos variaciones de árabe. En los ejemplos anteriores se muestra que debe definir los valores `xml:lang` y <xref:System.Windows.FlowDirection>.

<a name="FlowDirectionNontext"></a>

## <a name="flowdirection-with-non-text-elements"></a>FlowDirection con elementos no textuales

<xref:System.Windows.FlowDirection> define no solo cómo fluye el texto en un elemento de texto sino también la dirección de flujo de casi todos los demás [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento. En el gráfico siguiente se muestra un <xref:System.Windows.Controls.ToolBar> que usa un <xref:System.Windows.Media.LinearGradientBrush> horizontal para dibujar su fondo con un degradado de izquierda a derecha.

![Gráfico que muestra una barra de herramientas con un degradado de izquierda a derecha.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)

Después de establecer el <xref:System.Windows.FlowDirection> en <xref:System.Windows.FlowDirection.RightToLeft>, no solo los botones de <xref:System.Windows.Controls.ToolBar> se organizan de derecha a izquierda, pero incluso el <xref:System.Windows.Media.LinearGradientBrush> realinea sus desplazamientos para fluir de derecha a izquierda.

En el gráfico siguiente se muestra la realineación del <xref:System.Windows.Media.LinearGradientBrush>.

![Gráfico que muestra una barra de herramientas con un degradado de derecha a izquierda.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)

En el ejemplo siguiente se dibuja un <xref:System.Windows.Controls.ToolBar>de <xref:System.Windows.FlowDirection.RightToLeft>. (Para dibujarlo de izquierda a derecha, quite el atributo de <xref:System.Windows.FlowDirection> en el <xref:System.Windows.Controls.ToolBar>.

[!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]

<a name="FlowDirectionExceptions"></a>

### <a name="flowdirection-exceptions"></a>Excepciones de FlowDirection

Hay algunos casos en los que <xref:System.Windows.FlowDirection> no se comporta de la manera esperada. En esta sección se describen dos de estas excepciones.

**Image**

Un <xref:System.Windows.Controls.Image> representa un control que muestra una imagen. En XAML, se puede usar con una propiedad <xref:System.Windows.Controls.Image.Source%2A> que define el identificador uniforme de recursos (URI) del <xref:System.Windows.Controls.Image> que se va a mostrar.

A diferencia de otros elementos de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], un <xref:System.Windows.Controls.Image> no hereda la <xref:System.Windows.FlowDirection> del contenedor. Sin embargo, si el <xref:System.Windows.FlowDirection> se establece explícitamente en <xref:System.Windows.FlowDirection.RightToLeft>, se muestra una <xref:System.Windows.Controls.Image> volteada horizontalmente. Se implementa como una práctica característica para los desarrolladores de contenido bidireccional, porque el volteo horizontal de la imagen muestra el efecto deseado en algunos casos.

En el gráfico siguiente se muestra un <xref:System.Windows.Controls.Image>volteado.

![Gráfico que muestra una imagen volteada.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)

En el ejemplo siguiente se muestra que el <xref:System.Windows.Controls.Image> no puede heredar el <xref:System.Windows.FlowDirection> de la <xref:System.Windows.Controls.StackPanel> que lo contiene.

> [!NOTE]
> Debe tener un archivo denominado **ms_logo. jpg** en C:\ para ejecutar este ejemplo.

[!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]

> [!NOTE]
> En los archivos de descarga se incluye un archivo **ms_logo. jpg** . En el código, se supone que el archivo .jpg no está dentro del proyecto, sino en alguna ubicación de la unidad C:\. Debe copiar el archivo .jpg de los archivos del proyecto en la unidad C:\ o cambiar el código para buscar el archivo dentro del proyecto. Para realizar este cambio `Source="file://c:/ms_logo.jpg"` a `Source="ms_logo.jpg"`.

**Rutas de acceso**

Además de un <xref:System.Windows.Controls.Image>, se <xref:System.Windows.Shapes.Path>otro elemento interesante. Patch es un objeto que puede dibujar una serie de líneas y curvas conectadas. Se comporta de forma similar a un <xref:System.Windows.Controls.Image> con respecto a su <xref:System.Windows.FlowDirection>; por ejemplo, su <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection.RightToLeft>es un reflejo horizontal de su <xref:System.Windows.FlowDirection.LeftToRight> uno. Sin embargo, a diferencia de un <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> hereda su <xref:System.Windows.FlowDirection> del contenedor y no es necesario especificarlo explícitamente.

En el ejemplo siguiente se dibuja una flecha simple mediante 3 líneas. La primera flecha hereda la dirección del flujo de <xref:System.Windows.FlowDirection.RightToLeft> de la <xref:System.Windows.Controls.StackPanel> para que sus puntos inicial y final se midan desde una raíz en el lado derecho. La segunda flecha que tiene una <xref:System.Windows.FlowDirection.RightToLeft>explícita <xref:System.Windows.FlowDirection> se inicia también en el lado derecho. Sin embargo, la tercera flecha tiene su raíz de inicio en el lado izquierdo. Para obtener más información acerca del dibujo, vea <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.GeometryGroup>.

[!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]

En el gráfico siguiente se muestra la salida del ejemplo anterior con las flechas dibujadas mediante el elemento `Path`:

![Gráfico que muestra las flechas dibujadas mediante el elemento path.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)

Los <xref:System.Windows.Controls.Image> y <xref:System.Windows.Shapes.Path> son dos ejemplos de cómo usa [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.FlowDirection>. Además de diseñar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos en una dirección específica dentro de un contenedor, <xref:System.Windows.FlowDirection> se puede usar con elementos como <xref:System.Windows.Controls.InkPresenter> que representa la entrada de lápiz en una superficie, <xref:System.Windows.Media.LinearGradientBrush><xref:System.Windows.Media.RadialGradientBrush>. Siempre que necesite un comportamiento de derecha a izquierda para el contenido que imite un comportamiento de izquierda a derecha, o viceversa, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona esa funcionalidad.

<a name="NumberSubstitution"></a>

## <a name="number-substitution"></a>Sustitución de números

Históricamente, Windows ha admitido la sustitución de números al permitir la representación de distintas formas culturales para los mismos dígitos manteniendo el almacenamiento interno de estos dígitos unificado entre diferentes configuraciones regionales, por ejemplo, los números se almacenan en su valores hexadecimales conocidos, 0x40, 0x41, pero mostrados según el idioma seleccionado.

Esto permite que las aplicaciones procesen valores numéricos sin necesidad de convertirlos de un idioma a otro; por ejemplo, un usuario puede abrir una hoja de cálculo de Microsoft Excel en una ventana en árabe traducida y ver los números con forma de árabe, pero abrirlo en un Versión europea de Windows y ver la representación Europea de los mismos números. Esto también es necesario para otros símbolos, como el símbolo de porcentaje y los separadores de coma, porque suelen acompañar a los números del mismo documento.

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] continúa con la tradición y agrega más compatibilidad con esta característica, que aumenta el control del usuario sobre cuándo y cómo usar la sustitución. Aunque esta característica está diseñada para cualquier idioma, es especialmente útil en el contenido bidireccional, donde definir los dígitos de un idioma concreto normalmente constituye un desafío para los desarrolladores de aplicaciones debido a las distintas referencias culturales en las que se puede ejecutar una aplicación.

La propiedad principal que controla cómo funciona la sustitución de números en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] es la propiedad de dependencia <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>. La clase <xref:System.Windows.Media.NumberSubstitution> especifica cómo se mostrarán los números en el texto. Tiene tres propiedades públicas que definen su comportamiento. El siguiente es un resumen de cada una de las propiedades:

**CultureSource:**

Esta propiedad especifica cómo se determina la referencia cultural para los números. Toma uno de tres valores de enumeración de <xref:System.Windows.Media.NumberCultureSource>.

- Override: la referencia cultural de número es la de <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> propiedad.

- Text: la referencia cultural de número es la referencia cultural de la ejecución de texto. En el marcado, esto sería `xml:lang`, o su `Language` propiedad de alias (<xref:System.Windows.FrameworkElement.Language%2A> o <xref:System.Windows.FrameworkContentElement.Language%2A>). Además, es el valor predeterminado para las clases que derivan de <xref:System.Windows.FrameworkContentElement>. Estas clases incluyen <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> y así sucesivamente.

- User: la referencia cultural de número es la referencia cultural del subproceso actual. Esta propiedad es la predeterminada para todas las subclases de <xref:System.Windows.FrameworkElement> como <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> y <xref:System.Windows.Controls.TextBlock>.

**CultureOverride**:

La propiedad <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> solo se utiliza si la propiedad <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> está establecida en <xref:System.Windows.Media.NumberCultureSource.Override> y se omite en caso contrario. Especifica la referencia cultural de número. Un valor de `null`, el valor predeterminado, se interpreta como en-US.

**Substitution**:

Esta propiedad especifica el tipo de sustitución de números que se va a realizar. Toma uno de los siguientes valores de enumeración de <xref:System.Windows.Media.NumberSubstitutionMethod>:

- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: el método de sustitución se determina en función de la propiedad <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> de la referencia cultural del número. Esta es la opción predeterminada.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: Si la referencia cultural de número es una referencia cultural árabe o persa, especifica que los dígitos dependen del contexto.

- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: los números siempre se representan como dígitos europeos.

- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: los números se representan mediante los dígitos nacionales de la referencia cultural de número, tal y como se especifica en el <xref:System.Globalization.CultureInfo.NumberFormat%2A>de la referencia cultural.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: los números se representan mediante los dígitos tradicionales para la referencia cultural de número. Para la mayoría de las referencias culturales, es lo mismo que <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>. Sin embargo, <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> da como resultado dígitos latinos en algunas referencias culturales árabes, mientras que este valor da como resultado dígitos árabes para todas las referencias culturales árabes.

¿Qué significan esos valores para un desarrollador de contenido bidireccional? En la mayoría de los casos, es posible que el desarrollador solo necesite definir <xref:System.Windows.FlowDirection> y el idioma de cada elemento de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] textual, por ejemplo `Language="ar-SA"` y la lógica de <xref:System.Windows.Media.NumberSubstitution> se encarga de mostrar los números según el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]correcto. En el ejemplo siguiente se muestra el uso de números árabes y ingleses en una aplicación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que se ejecuta en una versión árabe de Windows.

[!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]

En el gráfico siguiente se muestra la salida del ejemplo anterior si se ejecuta en una versión árabe de Windows con números árabes y en inglés que se muestran:

![Gráfico que muestra números árabes y ingleses.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)

El <xref:System.Windows.FlowDirection> era importante en este caso porque al establecer el <xref:System.Windows.FlowDirection> en <xref:System.Windows.FlowDirection.LeftToRight> en su lugar habría dado como resultado dígitos europeos. En las secciones siguientes se explica cómo conseguir una presentación unificada de dígitos en todo el documento. Si este ejemplo no se ejecuta en una versión árabe de Windows, todos los dígitos se mostrarán como dígitos europeos.

**Definición de reglas de sustitución**

En una aplicación real, es posible que tenga que establecer el idioma mediante programación. Por ejemplo, si desea establecer el atributo de `xml:lang` para que sea el mismo que el utilizado por el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]del sistema, o puede cambiar el idioma en función del estado de la aplicación.

Si desea realizar cambios en función del estado de la aplicación, haga uso de otras características proporcionadas por [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

En primer lugar, establezca el `NumberSubstitution.CultureSource="Text"`del componente de la aplicación. Con esta configuración, se asegura de que la configuración no proviene de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para los elementos de texto que tienen "User" como valor predeterminado, como <xref:System.Windows.Controls.TextBlock>.

Por ejemplo:

```xaml
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

En el código C# correspondiente, establezca la propiedad `Language`, por ejemplo, en `"ar-SA"`.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

Si tiene que establecer la propiedad `Language` en el idioma de la interfaz de usuario del usuario actual, use el código siguiente.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> representa la referencia cultural actual utilizada por el subproceso actual en tiempo de ejecución.

El ejemplo de XAML final debería ser similar al ejemplo siguiente.

[!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]

El ejemplo C# final debería ser similar al siguiente.

[!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]

En el gráfico siguiente se muestra el aspecto de la ventana para cualquier lenguaje de programación, mostrando números árabes:

![Gráfico que muestra números árabes.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)

**Uso de la propiedad Substitution**

La forma en que se usa la sustitución de números en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] depende tanto del lenguaje del elemento de texto como de su <xref:System.Windows.FlowDirection>. Si el <xref:System.Windows.FlowDirection> es de izquierda a derecha, se representan los dígitos europeos. Sin embargo, si va precedido por texto árabe o tiene el idioma establecido en "ar" y el <xref:System.Windows.FlowDirection> es <xref:System.Windows.FlowDirection.RightToLeft>, en su lugar se representan los dígitos árabes.

En algunos casos, sin embargo, es posible que quiera crear una aplicación unificada, como, por ejemplo, dígitos europeos para todos los usuarios. O dígitos árabes en <xref:System.Windows.Documents.Table> celdas con un <xref:System.Windows.Style>específico. Una manera fácil de hacerlo es usar la propiedad <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>.

En el ejemplo siguiente, el primer <xref:System.Windows.Controls.TextBlock> no tiene establecida la propiedad <xref:System.Windows.Media.NumberSubstitution.Substitution%2A>, por lo que el algoritmo muestra dígitos árabes según lo esperado. Sin embargo, en el segundo <xref:System.Windows.Controls.TextBlock>, la sustitución se establece en Europea invalidando la sustitución predeterminada de los números árabes y se muestran los dígitos europeos.

[!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
