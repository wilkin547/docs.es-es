---
title: Información general sobre objetos Drawing
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: 7a5d00eb2fb7c66e5e42d40893806e13717e1d2e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186534"
---
# <a name="drawing-objects-overview"></a>Información general sobre objetos Drawing
En este <xref:System.Windows.Media.Drawing> tema se presentan objetos y se describe cómo usarlos para dibujar formas, mapas de bits, texto y medios de forma eficaz. Utilice <xref:System.Windows.Media.Drawing> objetos al crear imágenes prediseñadas, pintar con un <xref:System.Windows.Media.DrawingBrush>objeto o utilizarobjetos. <xref:System.Windows.Media.Visual>  

<a name="whatisadrawingsection"></a>
## <a name="what-is-a-drawing-object"></a>¿Qué es un objeto Drawing?  
 Un <xref:System.Windows.Media.Drawing> objeto describe contenido visible, como una forma, un mapa de bits, un vídeo o una línea de texto. Distintos tipos de dibujo describen tipos de contenido diferentes. La siguiente lista muestra los distintos tipos de objetos de dibujo.  
  
- <xref:System.Windows.Media.GeometryDrawing>– Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>– Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>– Dibuja texto.  
  
- <xref:System.Windows.Media.VideoDrawing>– Reproduce un archivo de audio o vídeo.  
  
- <xref:System.Windows.Media.DrawingGroup>– Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 <xref:System.Windows.Media.Drawing>los objetos son versátiles; hay muchas maneras de <xref:System.Windows.Media.Drawing> usar un objeto.  
  
- Puede mostrarla como una imagen <xref:System.Windows.Media.DrawingImage> mediante <xref:System.Windows.Controls.Image> un control y un control.  
  
- Puede usarlo con <xref:System.Windows.Media.DrawingBrush> a para pintar un <xref:System.Windows.Controls.Page.Background%2A> objeto, <xref:System.Windows.Controls.Page>como el de un archivo .  
  
- Puede usarlo para describir la <xref:System.Windows.Media.DrawingVisual>apariencia de un archivo .  
  
- Puede usarlo para enumerar el contenido <xref:System.Windows.Media.Visual>de un archivo .  
  
 WPF ofrece otros tipos de objetos capaces de dibujar formas, mapas de bits, texto y elementos multimedia. Por ejemplo, también <xref:System.Windows.Shapes.Shape> puede usar objetos <xref:System.Windows.Controls.MediaElement> para dibujar formas y el control proporciona otra forma de agregar vídeo a la aplicación. Entonces, ¿cuándo debe usar <xref:System.Windows.Media.Drawing> objetos? Cuando puede sacrificar características de nivel de marco <xref:System.Windows.Freezable> de trabajo para obtener beneficios de rendimiento o cuando necesite características. Dado <xref:System.Windows.Media.Drawing> que los objetos carecen de compatibilidad con [Layout](../advanced/layout.md), input y focus, proporcionan ventajas de <xref:System.Windows.Media.Visual> rendimiento que los hacen ideales para describir fondos, imágenes prediseñadas y para dibujos de bajo nivel con objetos.  
  
 Dado que son <xref:System.Windows.Freezable> un <xref:System.Windows.Media.Drawing> objeto de tipo, los objetos obtienen varias características especiales, que incluyen lo siguiente: se pueden declarar como [recursos,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)compartirse entre varios objetos, hacer que sea de solo lectura para mejorar el rendimiento, clonar y proteger los subprocesos. Para obtener más información sobre <xref:System.Windows.Freezable> las diferentes características proporcionadas por los objetos, consulte Información general sobre [objetos freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>
## <a name="draw-a-shape"></a>Dibujar una forma  
 Para dibujar una forma, <xref:System.Windows.Media.GeometryDrawing>utilice un archivo . La propiedad de <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> un dibujo de geometría <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe la forma que se va a dibujar, su propiedad describe cómo se debe pintar el interior de la forma y su <xref:System.Windows.Media.GeometryDrawing.Pen%2A> propiedad describe cómo se debe dibujar su contorno.  
  
 En el ejemplo <xref:System.Windows.Media.GeometryDrawing> siguiente se usa a para dibujar una forma. La forma se <xref:System.Windows.Media.GeometryGroup> describe <xref:System.Windows.Media.EllipseGeometry> mediante un y dos objetos. El interior de la forma <xref:System.Windows.Media.LinearGradientBrush> está pintado con <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>un y su contorno se dibuja con un .  
  
 En este ejemplo <xref:System.Windows.Media.GeometryDrawing>se crea el siguiente archivo .  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Para obtener el ejemplo completo, vea [Create a GeometryDrawing](how-to-create-a-geometrydrawing.md) (Cómo: Crear un objeto GeometryDrawing).  
  
 Otras <xref:System.Windows.Media.Geometry> clases, <xref:System.Windows.Media.PathGeometry> como permitirle crear formas más complejas mediante la creación de curvas y arcos. Para obtener <xref:System.Windows.Media.Geometry> más información acerca de los objetos, consulte [Información general sobre geometría](geometry-overview.md).  
  
 Para obtener más información acerca de otras <xref:System.Windows.Media.Drawing> formas de dibujar formas que no usan objetos, vea [Formas y dibujo básico en Información general de WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>
## <a name="draw-an-image"></a>Dibujar un objeto Image  
 Para dibujar una imagen, <xref:System.Windows.Media.ImageDrawing>utilice un archivo . La <xref:System.Windows.Media.ImageDrawing> propiedad <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> de un objeto describe la <xref:System.Windows.Media.ImageDrawing.Rect%2A> imagen que se va a dibujar y su propiedad define la región donde se dibuja la imagen.  
  
 En el ejemplo siguiente se dibuja una imagen en un rectángulo situado en (75,75) que ocupa 100 por 100 píxeles. En la ilustración siguiente se muestra el <xref:System.Windows.Media.ImageDrawing> creado por el ejemplo. Se ha añadido un borde gris <xref:System.Windows.Media.ImageDrawing>para mostrar los límites del archivo .  
  
 ![Objeto ImageDrawing de 100 por 100 dibujado en (75,75)](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing de 100 por 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Para más información sobre las imágenes, [Información general sobre imágenes](imaging-overview.md).  
  
<a name="playmedia"></a>
## <a name="play-media-code-only"></a>Reproducir elementos multimedia (solo código)  
  
> [!NOTE]
> Aunque puede declarar <xref:System.Windows.Media.VideoDrawing> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]un in , solo puede cargar y reproducir sus medios mediante código. Para reproducir [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]vídeo en <xref:System.Windows.Controls.MediaElement> , utilice a en su lugar.  
  
 Para reproducir un archivo de audio <xref:System.Windows.Media.VideoDrawing> o <xref:System.Windows.Media.MediaPlayer>vídeo, utilice a y a . Hay dos maneras de cargar y reproducir elementos multimedia. La primera es <xref:System.Windows.Media.MediaPlayer> usar <xref:System.Windows.Media.VideoDrawing> a y a por sí mismos, y la segunda manera es crear el suyo propio <xref:System.Windows.Media.MediaTimeline> para usar con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
 Para reproducir contenido multimedia <xref:System.Windows.Media.MediaTimeline>sin crear los suyos propios, realice los pasos siguientes.  
  
1. Crear un objeto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Utilice <xref:System.Windows.Media.MediaPlayer.Open%2A> el método para cargar el archivo multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creará un control <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Especifique el tamaño y la ubicación <xref:System.Windows.Media.VideoDrawing.Rect%2A> para dibujar <xref:System.Windows.Media.VideoDrawing>el medio estableciendo la propiedad del archivo .  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Establezca <xref:System.Windows.Media.VideoDrawing.Player%2A> la propiedad <xref:System.Windows.Media.VideoDrawing> de <xref:System.Windows.Media.MediaPlayer> la con la que creó.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Utilice <xref:System.Windows.Media.MediaPlayer.Play%2A> el método <xref:System.Windows.Media.MediaPlayer> de la para empezar a reproducir el medio.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 En el ejemplo <xref:System.Windows.Media.VideoDrawing> siguiente <xref:System.Windows.Media.MediaPlayer> se utiliza a y a para reproducir un archivo de vídeo una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para obtener un control de temporización <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing> adicional sobre el medio, utilice a <xref:System.Windows.Media.MediaTimeline> con los objetos y. Le <xref:System.Windows.Media.MediaTimeline> permite especificar si el vídeo debe repetirse. Para utilizar <xref:System.Windows.Media.MediaTimeline> a <xref:System.Windows.Media.VideoDrawing>con un , realice los pasos siguientes:  
  
1. Declare <xref:System.Windows.Media.MediaTimeline> el y establezca sus comportamientos de sincronización.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Cree <xref:System.Windows.Media.MediaClock> un <xref:System.Windows.Media.MediaTimeline>desde el archivo .  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Cree <xref:System.Windows.Media.MediaPlayer> un y <xref:System.Windows.Media.MediaClock> use <xref:System.Windows.Media.MediaPlayer.Clock%2A> el para establecer su propiedad.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Cree <xref:System.Windows.Media.VideoDrawing> a y <xref:System.Windows.Media.MediaPlayer> asigne <xref:System.Windows.Media.VideoDrawing.Player%2A> el <xref:System.Windows.Media.VideoDrawing>a la propiedad del archivo .  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 En el ejemplo <xref:System.Windows.Media.MediaTimeline> siguiente <xref:System.Windows.Media.MediaPlayer> se <xref:System.Windows.Media.VideoDrawing> utiliza a con a y a para reproducir un vídeo repetidamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, cuando <xref:System.Windows.Media.MediaTimeline>se <xref:System.Windows.Media.Animation.ClockController> utiliza <xref:System.Windows.Media.Animation.Clock.Controller%2A> un , <xref:System.Windows.Media.MediaClock> se utiliza el interactivo devuelto <xref:System.Windows.Media.MediaPlayer>desde la propiedad de la para controlar la reproducción multimedia en lugar de los métodos interactivos de .  
  
<a name="drawtext"></a>
## <a name="draw-text"></a>Dibujar texto  
 Para dibujar texto, <xref:System.Windows.Media.GlyphRunDrawing> utilice <xref:System.Windows.Media.GlyphRun>a y a . En el ejemplo <xref:System.Windows.Media.GlyphRunDrawing> siguiente se usa a para dibujar el texto "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 A <xref:System.Windows.Media.GlyphRun> es un objeto de bajo nivel destinado a su uso con escenarios de impresión y presentación de documentos de formato fijo. Una forma más sencilla de dibujar texto <xref:System.Windows.Controls.Label> en <xref:System.Windows.Controls.TextBlock>la pantalla es usar un archivo . Para obtener <xref:System.Windows.Media.GlyphRun>más información acerca de , vea la [Introducción a la GlyphRun objeto y pictogramas elemento](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) información general.  
  
<a name="compositedrawingssection"></a>
## <a name="composite-drawings"></a>Dibujos compuestos  
 A <xref:System.Windows.Media.DrawingGroup> permite combinar varios dibujos en un único dibujo compuesto. Mediante un <xref:System.Windows.Media.DrawingGroup>, puede combinar formas, imágenes <xref:System.Windows.Media.Drawing> y texto en un solo objeto.  
  
 En el ejemplo <xref:System.Windows.Media.DrawingGroup> siguiente <xref:System.Windows.Media.GeometryDrawing> se utiliza <xref:System.Windows.Media.ImageDrawing> a para combinar dos objetos y un objeto. Este ejemplo produce el siguiente resultado:  
  
 ![DrawingGroup con varios dibujos](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un dibujo compuesto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 A <xref:System.Windows.Media.DrawingGroup> también le permite aplicar máscaras de opacidad, transformaciones, efectos de mapa de bits y otras operaciones a su contenido. <xref:System.Windows.Media.DrawingGroup>las operaciones se aplican <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> <xref:System.Windows.Media.DrawingGroup.Opacity%2A>en <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>el <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>siguiente <xref:System.Windows.Media.DrawingGroup.Transform%2A>orden: , , , , , , y, a continuación, .  
  
 En la ilustración siguiente <xref:System.Windows.Media.DrawingGroup> se muestra el orden en el que se aplican las operaciones.  
  
 ![Orden de las operaciones de DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Orden de las operaciones de DrawingGroup  
  
 En la tabla siguiente se describen <xref:System.Windows.Media.DrawingGroup> las propiedades que puede utilizar para manipular el contenido de un objeto.  
  
|Propiedad|Descripción|Ilustración|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Altera la opacidad de las partes <xref:System.Windows.Media.DrawingGroup> seleccionadas del contenido. Para obtener un ejemplo, vea [How to: Control the Opacity of a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)) (Cómo: Controlar la opacidad de un dibujo).|![DrawingGroup con una máscara de opacidad](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Cambia uniformemente la opacidad <xref:System.Windows.Media.DrawingGroup> del contenido. Utilice esta propiedad <xref:System.Windows.Media.Drawing> para hacer un transparente o parcialmente transparente. Para obtener un ejemplo, vea [How to: Apply an Opacity Mask to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)) (Cómo: Aplicar una máscara de opacidad a un dibujo).|![DrawingGroups con diferentes valores de opacidad](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Aplica <xref:System.Windows.Media.Effects.BitmapEffect> a <xref:System.Windows.Media.DrawingGroup> al contenido. Para obtener un ejemplo, vea [How to: Apply a BitmapEffect to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)) (Cómo: Aplicar un objeto BitmapEffect a un dibujo).|![DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Recorta <xref:System.Windows.Media.DrawingGroup> el contenido a una <xref:System.Windows.Media.Geometry>región que se describe mediante un archivo . Para obtener un ejemplo, vea [How to: Clip a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) (Cómo: Recortar un dibujo).|![DrawingGroup con una región de recorte definida](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Ajusta los píxeles independientes del dispositivo a los píxeles del dispositivo según las directrices especificadas. Esta propiedad resulta útil para garantizar que los gráficos muy detallados se representan nítidamente en pantallas de baja resolución. Para obtener un ejemplo, vea [Apply a GuidelineSet to a Drawing](how-to-apply-a-guidelineset-to-a-drawing.md) (Aplicar un objeto GuidelineSet a un dibujo).|![DrawingGroup con y sin GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transforma el <xref:System.Windows.Media.DrawingGroup> contenido. Para obtener un ejemplo, vea [How to: Apply a Transform to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)) (Cómo: Aplicar una transformación a un dibujo).|![DrawingGroup girado](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>
## <a name="display-a-drawing-as-an-image"></a>Mostrar un dibujo como imagen  
 Para mostrar <xref:System.Windows.Media.Drawing> un <xref:System.Windows.Controls.Image> control con <xref:System.Windows.Media.DrawingImage> un <xref:System.Windows.Controls.Image> control, <xref:System.Windows.Controls.Image.Source%2A> utilice <xref:System.Windows.Media.DrawingImage> a como <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> el control y establezca la propiedad del objeto en el dibujo que desea mostrar.  
  
 En el ejemplo <xref:System.Windows.Media.DrawingImage> siguiente <xref:System.Windows.Controls.Image> se utiliza <xref:System.Windows.Media.GeometryDrawing>un control a y un control para mostrar un archivo . Este ejemplo produce el siguiente resultado:  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>
## <a name="paint-an-object-with-a-drawing"></a>Pintar un objeto con un dibujo  
 A <xref:System.Windows.Media.DrawingBrush> es un tipo de pincel que pinta un área con un objeto de dibujo. Puede usarlo para pintar casi cualquier objeto gráfico con un dibujo. La <xref:System.Windows.Media.Drawing> propiedad <xref:System.Windows.Media.DrawingBrush> de un <xref:System.Windows.Media.DrawingBrush.Drawing%2A>describe su . Para renderizar <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush>un con un , agréguelo al pincel usando la propiedad del <xref:System.Windows.Media.Drawing> pincel y utilice el pincel para pintar un objeto gráfico, como un control o un panel.  
  
 En los ejemplos <xref:System.Windows.Media.DrawingBrush> siguientes <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle> utiliza a para <xref:System.Windows.Media.GeometryDrawing>pintar la de a con un patrón creado a partir de un archivo . Este ejemplo produce el siguiente resultado:  
  
 ![DrawingBrush en mosaico](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Uso de GeometryDrawing con un objeto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> clase proporciona una variedad de opciones para estirar y enmosaicor su contenido. Para obtener <xref:System.Windows.Media.DrawingBrush>más información acerca de , vea la información general [de pintura con imágenes, dibujos y objetos visuales.](painting-with-images-drawings-and-visuals.md)  
  
<a name="renderingwithvisualsection"></a>
## <a name="render-a-drawing-with-a-visual"></a>Representar un dibujo con un objeto Visual  
 A <xref:System.Windows.Media.DrawingVisual> es un tipo de objeto visual diseñado para representar un dibujo. Una posibilidad para los desarrolladores que quieran crear un entorno gráfico muy personalizado es trabajar directamente en la capa visual, que no se describe en esta información general. Para más información, consulte la página de información general [Usar objetos DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>
## <a name="drawingcontext-objects"></a>Objetos DrawingContext  
 La <xref:System.Windows.Media.DrawingContext> clase le permite <xref:System.Windows.Media.Visual> rellenar <xref:System.Windows.Media.Drawing> a o a con contenido visual. Muchos de estos objetos <xref:System.Windows.Media.DrawingContext> gráficos de nivel inferior utilizan a porque describe el contenido gráfico de forma muy eficiente.  
  
 Aunque <xref:System.Windows.Media.DrawingContext> los métodos de dibujo parecen <xref:System.Drawing.Graphics?displayProperty=nameWithType> similares a los métodos de dibujo del tipo, en realidad son muy diferentes. <xref:System.Windows.Media.DrawingContext>se utiliza con un sistema de <xref:System.Drawing.Graphics?displayProperty=nameWithType> gráficos en modo retenido, mientras que el tipo se utiliza con un sistema de gráficos en modo inmediato. Cuando se <xref:System.Windows.Media.DrawingContext> utilizan los comandos de dibujo de un objeto, en realidad se almacena un conjunto de <xref:System.Windows.Media.DrawingContext>instrucciones de representación (aunque el mecanismo de almacenamiento exacto depende del tipo de objeto que proporciona el ) que utilizará más adelante el sistema de gráficos; no está dibujando a la pantalla en tiempo real. Para obtener más información sobre cómo funciona el sistema de gráficos de Windows Presentation Foundation (WPF), vea [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).  
  
 Nunca se <xref:System.Windows.Media.DrawingContext>crea una instancia directa de un ; sin embargo, puede adquirir un contexto de <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>dibujo a partir de ciertos métodos, como y .  
  
<a name="enumeratevisualcontents"></a>
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerar el contenido de un objeto Visual  
 Además de sus <xref:System.Windows.Media.Drawing> otros usos, los objetos también <xref:System.Windows.Media.Visual>proporcionan un modelo de objetos para enumerar el contenido de un archivo .  
  
 En el ejemplo <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> siguiente se <xref:System.Windows.Media.DrawingGroup> utiliza <xref:System.Windows.Media.Visual> el método para recuperar el valor de a y enumerarlo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre geometría](geometry-overview.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable)
- [Temas de información](drawings-how-to-topics.md)
