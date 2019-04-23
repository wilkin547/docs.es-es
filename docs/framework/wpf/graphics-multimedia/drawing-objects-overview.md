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
ms.openlocfilehash: c065b06e7542913ae7fb495a0f69ff09dc4238b9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325519"
---
# <a name="drawing-objects-overview"></a>Información general sobre objetos Drawing
Este tema se presentan <xref:System.Windows.Media.Drawing> objetos y se describe cómo se usan para dibujar con eficacia formas, mapas de bits, texto y multimedia. Usar <xref:System.Windows.Media.Drawing> objetos al crear imágenes prediseñadas, pintar con un <xref:System.Windows.Media.DrawingBrush>, o use <xref:System.Windows.Media.Visual> objetos.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>¿Qué es un objeto Drawing?  
 Un <xref:System.Windows.Media.Drawing> objeto describe contenido visible, como una forma, mapa de bits, vídeo o una línea de texto. Distintos tipos de dibujo describen tipos de contenido diferentes. La siguiente lista muestra los distintos tipos de objetos de dibujo.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Dibuja una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Dibuja una imagen.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Dibuja texto.  
  
-   <xref:System.Windows.Media.VideoDrawing> : Reproduce un archivo de audio o vídeo.  
  
-   <xref:System.Windows.Media.DrawingGroup> : Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 <xref:System.Windows.Media.Drawing> los objetos son versátiles; Hay muchas formas en que puede usar un <xref:System.Windows.Media.Drawing> objeto.  
  
-   Puede mostrar como una imagen mediante un <xref:System.Windows.Media.DrawingImage> y un <xref:System.Windows.Controls.Image> control.  
  
-   Puede utilizarlo con un <xref:System.Windows.Media.DrawingBrush> para pintar un objeto, como el <xref:System.Windows.Controls.Page.Background%2A> de un <xref:System.Windows.Controls.Page>.  
  
-   Puede usar para describir la apariencia de un <xref:System.Windows.Media.DrawingVisual>.  
  
-   Puede utilizar para enumerar el contenido de un <xref:System.Windows.Media.Visual>.  
  
 WPF ofrece otros tipos de objetos capaces de dibujar formas, mapas de bits, texto y elementos multimedia. Por ejemplo, también puede usar <xref:System.Windows.Shapes.Shape> objetos que se va a dibujar formas y el <xref:System.Windows.Controls.MediaElement> control proporciona otra manera de agregar vídeo a la aplicación. Así que ¿cuándo debe usar <xref:System.Windows.Media.Drawing> objetos? Cuando se pueden sacrificar características de marco para obtener ventajas de rendimiento o cuando necesite <xref:System.Windows.Freezable> características. Dado que <xref:System.Windows.Media.Drawing> objetos carecen de compatibilidad con [diseño](../advanced/layout.md), entrada ni foco, ofrecen ventajas de rendimiento que los hacen perfectos para describir fondos, imágenes prediseñadas y dibujos de bajo nivel con <xref:System.Windows.Media.Visual> objetos.  
  
 Porque son un tipo <xref:System.Windows.Freezable> objeto, <xref:System.Windows.Media.Drawing> objetos obtienen varias características especiales, como las siguientes: se pueden declarar como [recursos](../advanced/xaml-resources.md)compartida entre varios objetos, de sólo lectura para mejorar rendimiento, clonar y hacerse seguros para subprocesos. Para obtener más información sobre las diferentes características proporcionadas por <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Dibujar una forma  
 Para dibujar una forma, se utiliza un <xref:System.Windows.Media.GeometryDrawing>. Un dibujo de geometría <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> propiedad describe la forma que se va a dibujar, su <xref:System.Windows.Media.GeometryDrawing.Brush%2A> propiedad describe cómo se debe pintar el interior de la forma y su <xref:System.Windows.Media.GeometryDrawing.Pen%2A> propiedad describe cómo se debe dibujar su contorno.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.GeometryDrawing> para dibujar una forma. Se describe la forma mediante una <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos. Se pinta el interior de la forma con un <xref:System.Windows.Media.LinearGradientBrush> y el contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  
  
 Este ejemplo crea la siguiente <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Para obtener el ejemplo completo, vea [Create a GeometryDrawing](how-to-create-a-geometrydrawing.md) (Cómo: Crear un objeto GeometryDrawing).  
  
 Otros <xref:System.Windows.Media.Geometry> clases, como <xref:System.Windows.Media.PathGeometry> le permiten crear formas más complejas mediante curvas y arcos. Para obtener más información acerca de <xref:System.Windows.Media.Geometry> objetos, vea el [información general sobre geometría](geometry-overview.md).  
  
 Para obtener más información sobre otras maneras de dibujar formas que no usan <xref:System.Windows.Media.Drawing> objetos, vea [formas y dibujo básico en WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Dibujar un objeto Image  
 Para dibujar una imagen, use un <xref:System.Windows.Media.ImageDrawing>. Un <xref:System.Windows.Media.ImageDrawing> del objeto <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> propiedad describe la imagen para dibujar y su <xref:System.Windows.Media.ImageDrawing.Rect%2A> propiedad define la región donde se dibuja la imagen.  
  
 En el ejemplo siguiente se dibuja una imagen en un rectángulo situado en (75,75) que ocupa 100 por 100 píxeles. La siguiente ilustración muestra el <xref:System.Windows.Media.ImageDrawing> creado por el ejemplo. Se ha agregado un borde gris para mostrar los límites de la <xref:System.Windows.Media.ImageDrawing>.  
  
 ![Un ImageDrawing 100 por 100 dibujado en &#40;75,75&#41;](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing de 100 por 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Para más información sobre las imágenes, [Información general sobre imágenes](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Reproducir elementos multimedia (solo código)  
  
> [!NOTE]
>  Aunque se puede declarar un <xref:System.Windows.Media.VideoDrawing> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], sólo se puede cargar y reproducir sus elementos multimedia mediante código. Para reproducir vídeo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilice un <xref:System.Windows.Controls.MediaElement> en su lugar.  
  
 Para reproducir un archivo de audio o vídeo, usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer>. Hay dos maneras de cargar y reproducir elementos multimedia. La primera consiste en utilizar un <xref:System.Windows.Media.MediaPlayer> y un <xref:System.Windows.Media.VideoDrawing> por su cuenta y la segunda manera consiste en crear sus propios <xref:System.Windows.Media.MediaTimeline> para usar con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
 Para reproducir archivos multimedia sin necesidad de crear su propio <xref:System.Windows.Media.MediaTimeline>, realice los pasos siguientes.  
  
1. Crear un objeto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Use el <xref:System.Windows.Media.MediaPlayer.Open%2A> método para cargar el archivo multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creará un control <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Especifique el tamaño y ubicación para dibujar el medio estableciendo el <xref:System.Windows.Media.VideoDrawing.Rect%2A> propiedad de la <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Establecer el <xref:System.Windows.Media.VideoDrawing.Player%2A> propiedad de la <xref:System.Windows.Media.VideoDrawing> con el <xref:System.Windows.Media.MediaPlayer> que ha creado.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Use la <xref:System.Windows.Media.MediaPlayer.Play%2A> método de la <xref:System.Windows.Media.MediaPlayer> para empezar a reproducir el medio.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer> para reproducir un archivo de vídeo una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para obtener el control de tiempo sobre los medios, use un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos. El <xref:System.Windows.Media.MediaTimeline> le permite especificar si se debe repetir el vídeo. Para usar un <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.VideoDrawing>, realice los pasos siguientes:  
  
1. Declare el <xref:System.Windows.Media.MediaTimeline> y establezca sus comportamientos de temporización.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Crear un <xref:System.Windows.Media.MediaClock> desde el <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Crear un <xref:System.Windows.Media.MediaPlayer> y usar el <xref:System.Windows.Media.MediaClock> para establecer su <xref:System.Windows.Media.MediaPlayer.Clock%2A> propiedad.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Crear un <xref:System.Windows.Media.VideoDrawing> y asignar la <xref:System.Windows.Media.MediaPlayer> a la <xref:System.Windows.Media.VideoDrawing.Player%2A> propiedad de la <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.MediaTimeline> con un <xref:System.Windows.Media.MediaPlayer> y un <xref:System.Windows.Media.VideoDrawing> para reproducir un vídeo varias veces.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, cuando se usa un <xref:System.Windows.Media.MediaTimeline>, usa el modo interactivo <xref:System.Windows.Media.Animation.ClockController> devuelto desde el <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de la <xref:System.Windows.Media.MediaClock> para controlar la reproducción multimedia en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Dibujar texto  
 Para dibujar texto, use un <xref:System.Windows.Media.GlyphRunDrawing> y un <xref:System.Windows.Media.GlyphRun>. En el ejemplo siguiente se usa un <xref:System.Windows.Media.GlyphRunDrawing> para dibujar el texto "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Un <xref:System.Windows.Media.GlyphRun> es un objeto de bajo nivel pensado para usarse con escenarios de impresión y presentación de documentos de formato fijo. Dibujar texto en la pantalla de manera más sencilla es usar un <xref:System.Windows.Controls.Label> o <xref:System.Windows.Controls.TextBlock>. Para obtener más información acerca de <xref:System.Windows.Media.GlyphRun>, consulte el [Introducción al objeto GlyphRun y al elemento Glyphs](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) información general.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Dibujos compuestos  
 Un <xref:System.Windows.Media.DrawingGroup> le permite combinar varios dibujos en un solo dibujo compuesto. Mediante el uso de un <xref:System.Windows.Media.DrawingGroup>, puede combinar formas, imágenes y texto en una sola <xref:System.Windows.Media.Drawing> objeto.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingGroup> para combinar dos <xref:System.Windows.Media.GeometryDrawing> objetos y una <xref:System.Windows.Media.ImageDrawing> objeto. Este ejemplo produce el siguiente resultado:  
  
 ![DrawingGroup con varios dibujos](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un dibujo compuesto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Un <xref:System.Windows.Media.DrawingGroup> también permite aplicar máscaras de opacidad, transformaciones, efectos de imagen y otras operaciones a su contenido. <xref:System.Windows.Media.DrawingGroup> las operaciones se aplican en el siguiente orden: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>y, a continuación, <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 La siguiente ilustración muestra el orden en que <xref:System.Windows.Media.DrawingGroup> se aplican las operaciones.  
  
 ![Orden de las operaciones de DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Orden de las operaciones de DrawingGroup  
  
 En la tabla siguiente se describe las propiedades que puede usar para manipular un <xref:System.Windows.Media.DrawingGroup> contenido del objeto.  
  
|Propiedad|Descripción|Ilustración|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica la opacidad de partes seleccionadas de la <xref:System.Windows.Media.DrawingGroup> contenido. Como ejemplo, vea [Cómo: Controlar la opacidad de un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![DrawingGroup con una máscara de opacidad](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Cambia de manera uniforme la opacidad de la <xref:System.Windows.Media.DrawingGroup> contenido. Utilice esta propiedad para realizar un <xref:System.Windows.Media.Drawing> total o parcialmente transparentes. Como ejemplo, vea [Cómo: Aplicar una máscara de opacidad a un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)).|![DrawingGroups con diferentes valores de opacidad](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Se aplica un <xref:System.Windows.Media.Effects.BitmapEffect> a la <xref:System.Windows.Media.DrawingGroup> contenido. Como ejemplo, vea [Cómo: Aplicar un objeto BitmapEffect a un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Clips el <xref:System.Windows.Media.DrawingGroup> contenido en una región que se describe mediante un <xref:System.Windows.Media.Geometry>. Como ejemplo, vea [Cómo: Recortar un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) .|![DrawingGroup con una región de recorte definida](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Ajusta los píxeles independientes del dispositivo a los píxeles del dispositivo según las directrices especificadas. Esta propiedad resulta útil para garantizar que los gráficos muy detallados se representan nítidamente en pantallas de baja resolución. Para obtener un ejemplo, vea [Apply a GuidelineSet to a Drawing](how-to-apply-a-guidelineset-to-a-drawing.md) (Aplicar un objeto GuidelineSet a un dibujo).|![DrawingGroup con y sin GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transforma el <xref:System.Windows.Media.DrawingGroup> contenido. Como ejemplo, vea [Cómo: Aplicar una transformación a un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![DrawingGroup girado](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Mostrar un dibujo como imagen  
 Para mostrar un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controlar, use un <xref:System.Windows.Media.DrawingImage> como el <xref:System.Windows.Controls.Image> del control <xref:System.Windows.Controls.Image.Source%2A> y establezca el <xref:System.Windows.Media.DrawingImage> del objeto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> propiedad para el dibujo que desea mostrar.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingImage> y un <xref:System.Windows.Controls.Image> control para mostrar un <xref:System.Windows.Media.GeometryDrawing>. Este ejemplo produce el siguiente resultado:  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Pintar un objeto con un dibujo  
 Un <xref:System.Windows.Media.DrawingBrush> es un tipo de pincel que pinta un área con un objeto de dibujo. Puede usarlo para pintar casi cualquier objeto gráfico con un dibujo. El <xref:System.Windows.Media.Drawing> propiedad de un <xref:System.Windows.Media.DrawingBrush> describe su <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Para representar un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Media.DrawingBrush>, agréguelo al pincel mediante el pincel <xref:System.Windows.Media.Drawing> propiedad y use el pincel para pintar un gráfico de objeto, como un control o panel.  
  
 Los ejemplos siguientes se usa un <xref:System.Windows.Media.DrawingBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> con un patrón creado a partir de un <xref:System.Windows.Media.GeometryDrawing>. Este ejemplo produce el siguiente resultado:  
  
 ![DrawingBrush en mosaico](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Uso de GeometryDrawing con un objeto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> clase proporciona una variedad de opciones para ajustar y disposición en mosaico su contenido. Para obtener más información acerca de <xref:System.Windows.Media.DrawingBrush>, consulte el [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md) información general.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Representar un dibujo con un objeto Visual  
 Un <xref:System.Windows.Media.DrawingVisual> es un tipo de objeto visual diseñado para representar un dibujo. Una posibilidad para los desarrolladores que quieran crear un entorno gráfico muy personalizado es trabajar directamente en la capa visual, que no se describe en esta información general. Para más información, consulte la página de información general [Usar objetos DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Objetos DrawingContext  
 El <xref:System.Windows.Media.DrawingContext> clase le permite rellenar un <xref:System.Windows.Media.Visual> o <xref:System.Windows.Media.Drawing> con contenido visual. Muchos objetos de estos gráficos de nivel inferior usan un <xref:System.Windows.Media.DrawingContext> porque describe contenido gráfico muy eficazmente.  
  
 Aunque el <xref:System.Windows.Media.DrawingContext> un aspecto similares a los métodos de dibujo de los métodos draw el <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo, que son realmente muy diferentes. <xref:System.Windows.Media.DrawingContext> es si se usa con un sistema de gráficos de modo retenido, mientras el <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo se usa con un sistema de gráficos de modo inmediato. Cuando se usa un <xref:System.Windows.Media.DrawingContext> comandos de dibujo del objeto, en realidad se almacena un conjunto de instrucciones de representación (aunque el mecanismo de almacenamiento exacto depende del tipo de objeto que proporciona el <xref:System.Windows.Media.DrawingContext>) que se usará más adelante mediante los gráficos sistema; no se dibuja en la pantalla en tiempo real. Para obtener más información sobre cómo funciona el sistema de gráficos de Windows Presentation Foundation (WPF), consulte el [información general de representación de gráficos de WPF](wpf-graphics-rendering-overview.md).  
  
 Nunca crear instancias directamente un <xref:System.Windows.Media.DrawingContext>; sin embargo, puede adquirir un contexto de dibujo de determinados métodos, como <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> y <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerar el contenido de un objeto Visual  
 Además de sus otros usos, <xref:System.Windows.Media.Drawing> objetos también proporcionan un modelo de objetos para enumerar el contenido de un <xref:System.Windows.Media.Visual>.  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método para recuperar el <xref:System.Windows.Media.DrawingGroup> valor de un <xref:System.Windows.Media.Visual> y enumerarlo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre geometría](geometry-overview.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md)
- [Temas "Cómo..."](drawings-how-to-topics.md)
