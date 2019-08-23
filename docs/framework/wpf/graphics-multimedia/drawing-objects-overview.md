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
ms.openlocfilehash: d739865a692fa5ef448eba91369015580e5eda97
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916314"
---
# <a name="drawing-objects-overview"></a>Información general sobre objetos Drawing
En este tema <xref:System.Windows.Media.Drawing> se presentan los objetos y se describe cómo usarlos para dibujar eficazmente formas, mapas de bits, texto y elementos multimedia. Utilice <xref:System.Windows.Media.Drawing> los objetos al crear imágenes prediseñadas, pintar <xref:System.Windows.Media.DrawingBrush>con un o <xref:System.Windows.Media.Visual> utilizar objetos.  

<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>¿Qué es un objeto Drawing?  
 Un <xref:System.Windows.Media.Drawing> objeto describe el contenido visible, como una forma, un mapa de bits, un vídeo o una línea de texto. Distintos tipos de dibujo describen tipos de contenido diferentes. La siguiente lista muestra los distintos tipos de objetos de dibujo.  
  
- <xref:System.Windows.Media.GeometryDrawing>: Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>: Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>: Dibuja texto.  
  
- <xref:System.Windows.Media.VideoDrawing>: Reproduce un archivo de audio o de vídeo.  
  
- <xref:System.Windows.Media.DrawingGroup>: Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 <xref:System.Windows.Media.Drawing>los objetos son versátiles; Hay muchas maneras de utilizar un <xref:System.Windows.Media.Drawing> objeto.  
  
- Puede mostrarlo como una imagen <xref:System.Windows.Media.DrawingImage> mediante <xref:System.Windows.Controls.Image> y un control.  
  
- Puede utilizarlo con un <xref:System.Windows.Media.DrawingBrush> para pintar un objeto, como la <xref:System.Windows.Controls.Page.Background%2A> de un <xref:System.Windows.Controls.Page>.  
  
- Puede utilizarlo para describir la apariencia de un <xref:System.Windows.Media.DrawingVisual>.  
  
- Se puede utilizar para enumerar el contenido de un <xref:System.Windows.Media.Visual>.  
  
 WPF ofrece otros tipos de objetos capaces de dibujar formas, mapas de bits, texto y elementos multimedia. Por ejemplo, también puede usar <xref:System.Windows.Shapes.Shape> objetos para dibujar formas y el <xref:System.Windows.Controls.MediaElement> control proporciona otra manera de agregar vídeo a la aplicación. ¿Cuándo debe usar <xref:System.Windows.Media.Drawing> objetos? Cuando se pueden sacrificar características de nivel de marco para obtener ventajas de rendimiento <xref:System.Windows.Freezable> o cuando se necesitan características. Dado <xref:System.Windows.Media.Drawing> que los objetos no admiten el [diseño](../advanced/layout.md), la entrada y el foco, proporcionan ventajas de rendimiento que lo hacen idóneos para describir los terrenos, las imágenes prediseñadas y el <xref:System.Windows.Media.Visual> dibujo de bajo nivel con objetos.  
  
 Dado que son un objeto <xref:System.Windows.Freezable> de tipo <xref:System.Windows.Media.Drawing> , los objetos obtienen varias características especiales, entre las que se incluyen las siguientes: se pueden declarar como [recursos](../advanced/xaml-resources.md), compartirse entre varios objetos, convertirse en de solo lectura para mejorar el rendimiento, clonarse y convertido en seguro para subprocesos. Para obtener más información acerca de las diferentes características <xref:System.Windows.Freezable> proporcionadas por los objetos, consulte la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>Dibujar una forma  
 Para dibujar una forma, se usa un <xref:System.Windows.Media.GeometryDrawing>. La propiedad de un <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> dibujo de geometría describe la forma que se <xref:System.Windows.Media.GeometryDrawing.Brush%2A> va a dibujar, su propiedad describe cómo se debe pintar el interior de <xref:System.Windows.Media.GeometryDrawing.Pen%2A> la forma y su propiedad describe cómo debe dibujarse su contorno.  
  
 <xref:System.Windows.Media.GeometryDrawing> En el ejemplo siguiente se utiliza para dibujar una forma. La forma se describe mediante <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos. El interior de la forma se pinta con <xref:System.Windows.Media.LinearGradientBrush> un y su contorno se dibuja <xref:System.Windows.Media.Brushes.Black%2A> con un <xref:System.Windows.Media.Pen>.  
  
 En este ejemplo se crea <xref:System.Windows.Media.GeometryDrawing>lo siguiente.  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Para obtener el ejemplo completo, vea [Create a GeometryDrawing](how-to-create-a-geometrydrawing.md) (Cómo: Crear un objeto GeometryDrawing).  
  
 Otras <xref:System.Windows.Media.Geometry> clases, <xref:System.Windows.Media.PathGeometry> como permitirle crear formas más complejas creando curvas y arcos. Para obtener más información <xref:System.Windows.Media.Geometry> sobre los objetos, consulte [información general sobre geometría](geometry-overview.md).  
  
 Para obtener más información sobre otras formas de dibujar formas que no <xref:System.Windows.Media.Drawing> usan objetos, vea [información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>Dibujar un objeto Image  
 Para dibujar una imagen, se usa un <xref:System.Windows.Media.ImageDrawing>. La <xref:System.Windows.Media.ImageDrawing> propiedad de <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> un objeto describe la imagen que se va a <xref:System.Windows.Media.ImageDrawing.Rect%2A> dibujar y su propiedad define la región donde se dibuja la imagen.  
  
 En el ejemplo siguiente se dibuja una imagen en un rectángulo situado en (75,75) que ocupa 100 por 100 píxeles. En la ilustración siguiente se <xref:System.Windows.Media.ImageDrawing> muestra el creado por el ejemplo. Se ha agregado un borde gris para mostrar los límites de <xref:System.Windows.Media.ImageDrawing>.  
  
 ![Un ImageDrawing 100 por 100 dibujado en &#40;75, 75&#41; ](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing de 100 por 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Para más información sobre las imágenes, [Información general sobre imágenes](imaging-overview.md).  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>Reproducir elementos multimedia (solo código)  
  
> [!NOTE]
> Aunque puede declarar un <xref:System.Windows.Media.VideoDrawing> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], solo puede cargar y reproducir sus medios mediante el código. Para reproducir vídeo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilice en <xref:System.Windows.Controls.MediaElement> su lugar un.  
  
 Para reproducir un archivo de audio o vídeo, use <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>y. Hay dos maneras de cargar y reproducir elementos multimedia. La <xref:System.Windows.Media.MediaPlayer> primera es usar una y una <xref:System.Windows.Media.VideoDrawing> por sí <xref:System.Windows.Media.MediaPlayer> misma, y la segunda consiste en crear la suya propia <xref:System.Windows.Media.MediaTimeline> para usarla con y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
 Para reproducir contenido multimedia sin crear el <xref:System.Windows.Media.MediaTimeline>suyo propio, realice los pasos siguientes.  
  
1. Crear un objeto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Use el <xref:System.Windows.Media.MediaPlayer.Open%2A> método para cargar el archivo multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creará un control <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Especifique el tamaño y la ubicación para dibujar el medio estableciendo la <xref:System.Windows.Media.VideoDrawing.Rect%2A> propiedad <xref:System.Windows.Media.VideoDrawing>de.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Establezca la <xref:System.Windows.Media.VideoDrawing.Player%2A> propiedad <xref:System.Windows.Media.VideoDrawing> de con el <xref:System.Windows.Media.MediaPlayer> que creó.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Utilice el <xref:System.Windows.Media.MediaPlayer.Play%2A> método <xref:System.Windows.Media.MediaPlayer> de para empezar a reproducir los elementos multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.VideoDrawing> usa un <xref:System.Windows.Media.MediaPlayer> y un para reproducir un archivo de vídeo una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para obtener un <xref:System.Windows.Media.MediaTimeline> control de tiempo adicional sobre los medios, utilice con <xref:System.Windows.Media.MediaPlayer> los <xref:System.Windows.Media.VideoDrawing> objetos y. <xref:System.Windows.Media.MediaTimeline> Permite especificar si el vídeo debe repetirse. Para usar un <xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.VideoDrawing>con, realice los pasos siguientes:  
  
1. Declare <xref:System.Windows.Media.MediaTimeline> y establezca sus comportamientos de control de tiempo.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Cree un <xref:System.Windows.Media.MediaClock> a <xref:System.Windows.Media.MediaTimeline>partir de.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Cree un <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.MediaClock> use para establecer su <xref:System.Windows.Media.MediaPlayer.Clock%2A> propiedad.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Cree un <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing.Player%2A> asigne<xref:System.Windows.Media.VideoDrawing>a la propiedad de.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.MediaTimeline> usa <xref:System.Windows.Media.MediaPlayer> con y para reproducir un vídeo repetidamente. <xref:System.Windows.Media.VideoDrawing>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga <xref:System.Windows.Media.MediaClock> en cuenta que, cuando se <xref:System.Windows.Media.MediaTimeline>usa un, se usa <xref:System.Windows.Media.Animation.ClockController> la interactiva <xref:System.Windows.Media.Animation.Clock.Controller%2A> devuelta desde la propiedad de para controlar la reproducción multimedia en lugar de <xref:System.Windows.Media.MediaPlayer>los métodos interactivos de.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>Dibujar texto  
 Para dibujar texto, use <xref:System.Windows.Media.GlyphRunDrawing> <xref:System.Windows.Media.GlyphRun>y. <xref:System.Windows.Media.GlyphRunDrawing> En el ejemplo siguiente se utiliza para dibujar el texto "Hola mundo".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Un <xref:System.Windows.Media.GlyphRun> es un objeto de bajo nivel diseñado para su uso con escenarios de impresión y presentación de documentos de formato fijo. Una manera más sencilla de dibujar texto en la pantalla es usar <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>o. Para obtener más información <xref:System.Windows.Media.GlyphRun>sobre, vea la [Introducción a la información general sobre el objeto GlyphRun y el elemento glyphs](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) .  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>Dibujos compuestos  
 <xref:System.Windows.Media.DrawingGroup> Permite combinar varios dibujos en un solo dibujo compuesto. Mediante, puede combinar formas, imágenes y texto en un solo <xref:System.Windows.Media.Drawing> objeto. <xref:System.Windows.Media.DrawingGroup>  
  
 <xref:System.Windows.Media.DrawingGroup> En el ejemplo siguiente se usa para combinar <xref:System.Windows.Media.GeometryDrawing> dos objetos y <xref:System.Windows.Media.ImageDrawing> un objeto. Este ejemplo produce el siguiente resultado:  
  
 ![DrawingGroup con varios dibujos](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un dibujo compuesto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <xref:System.Windows.Media.DrawingGroup> También permite aplicar máscaras de opacidad, transformaciones, efectos de imagen y otras operaciones a su contenido. <xref:System.Windows.Media.DrawingGroup>las operaciones se aplican en el orden <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>siguiente <xref:System.Windows.Media.DrawingGroup.Opacity%2A>: <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>,, y <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 En la ilustración siguiente se muestra el orden <xref:System.Windows.Media.DrawingGroup> en que se aplican las operaciones.  
  
 ![Orden de las operaciones de DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Orden de las operaciones de DrawingGroup  
  
 En la tabla siguiente se describen las propiedades que se pueden utilizar para <xref:System.Windows.Media.DrawingGroup> manipular el contenido de un objeto.  
  
|Propiedad|Descripción|Ilustración|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica la opacidad de las <xref:System.Windows.Media.DrawingGroup> partes seleccionadas del contenido. Como ejemplo, vea [Cómo: Controlar la opacidad de un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)).|![DrawingGroup con una máscara de opacidad](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Cambia uniformemente la opacidad del <xref:System.Windows.Media.DrawingGroup> contenido. Utilice esta propiedad para hacer que <xref:System.Windows.Media.Drawing> sea transparente o parcialmente transparente. Como ejemplo, vea [Cómo: Aplicar una máscara de opacidad a un](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90))dibujo.|![DrawingGroups con diferentes valores de opacidad](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Aplica un <xref:System.Windows.Media.Effects.BitmapEffect> al contenido <xref:System.Windows.Media.DrawingGroup> de. Como ejemplo, vea [Cómo: Aplica un BitmapEffect a un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)).|![DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Recorta <xref:System.Windows.Media.DrawingGroup> el contenido a una región que se describe <xref:System.Windows.Media.Geometry>mediante un. Como ejemplo, vea [Cómo: Recortar](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) un dibujo.|![DrawingGroup con una región de recorte definida](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Ajusta los píxeles independientes del dispositivo a los píxeles del dispositivo según las directrices especificadas. Esta propiedad resulta útil para garantizar que los gráficos muy detallados se representan nítidamente en pantallas de baja resolución. Para obtener un ejemplo, vea [Apply a GuidelineSet to a Drawing](how-to-apply-a-guidelineset-to-a-drawing.md) (Aplicar un objeto GuidelineSet a un dibujo).|![DrawingGroup con y sin GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transforma el <xref:System.Windows.Media.DrawingGroup> contenido. Como ejemplo, vea [Cómo: Aplicar una transformación a un dibujo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)).|![DrawingGroup girado](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>Mostrar un dibujo como imagen  
 Para mostrar un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> <xref:System.Windows.Controls.Image.Source%2A> control <xref:System.Windows.Media.DrawingImage> <xref:System.Windows.Media.DrawingImage> , use como del <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> control y establezca la propiedad del objeto en el dibujo que desea mostrar. <xref:System.Windows.Controls.Image>  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.DrawingImage> usa un <xref:System.Windows.Controls.Image> control y para mostrar <xref:System.Windows.Media.GeometryDrawing>un. Este ejemplo produce el siguiente resultado:  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Pintar un objeto con un dibujo  
 Un <xref:System.Windows.Media.DrawingBrush> es un tipo de pincel que pinta un área con un objeto de dibujo. Puede usarlo para pintar casi cualquier objeto gráfico con un dibujo. La <xref:System.Windows.Media.Drawing> propiedad de un <xref:System.Windows.Media.DrawingBrush> describe su <xref:System.Windows.Media.DrawingBrush.Drawing%2A>. Para representar un <xref:System.Windows.Media.Drawing> <xref:System.Windows.Media.DrawingBrush>con, agréguelo al pincel mediante la propiedad del <xref:System.Windows.Media.Drawing> pincel y use el pincel para pintar un objeto gráfico, como un control o un panel.  
  
 <xref:System.Windows.Media.DrawingBrush> En los ejemplos siguientes se usa para pintar <xref:System.Windows.Shapes.Shape.Fill%2A> el de <xref:System.Windows.Shapes.Rectangle> un con un patrón creado a <xref:System.Windows.Media.GeometryDrawing>partir de un. Este ejemplo produce el siguiente resultado:  
  
 ![DrawingBrush en mosaico](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Uso de GeometryDrawing con un objeto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> clase proporciona diversas opciones para ajustar y colocar en mosaico su contenido. Para obtener más información <xref:System.Windows.Media.DrawingBrush>sobre, consulte la información general sobre el [dibujo con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md) .  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>Representar un dibujo con un objeto Visual  
 Un <xref:System.Windows.Media.DrawingVisual> es un tipo de objeto visual diseñado para representar un dibujo. Una posibilidad para los desarrolladores que quieran crear un entorno gráfico muy personalizado es trabajar directamente en la capa visual, que no se describe en esta información general. Para más información, consulte la página de información general [Usar objetos DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>Objetos DrawingContext  
 La <xref:System.Windows.Media.DrawingContext> clase le permite rellenar <xref:System.Windows.Media.Visual> un o <xref:System.Windows.Media.Drawing> un con contenido visual. Muchos de estos objetos gráficos de nivel inferior usan <xref:System.Windows.Media.DrawingContext> un porque describe el contenido gráfico de manera muy eficaz.  
  
 Aunque los <xref:System.Windows.Media.DrawingContext> métodos <xref:System.Drawing.Graphics?displayProperty=nameWithType> de dibujo parecen similares a los métodos de dibujo del tipo, en realidad son muy diferentes. <xref:System.Windows.Media.DrawingContext>se usa con un sistema de gráficos en modo retenido <xref:System.Drawing.Graphics?displayProperty=nameWithType> , mientras que el tipo se usa con un sistema de gráficos de modo inmediato. Cuando se usan comandos <xref:System.Windows.Media.DrawingContext> de dibujo de un objeto, en realidad se almacena un conjunto de instrucciones de representación (aunque el mecanismo de almacenamiento exacto depende del tipo de objeto que proporciona <xref:System.Windows.Media.DrawingContext>el) que el sistema de gráficos usará más adelante. no se dibujan en la pantalla en tiempo real. Para obtener más información sobre cómo funciona el sistema de gráficos de Windows Presentation Foundation (WPF), consulte [información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).  
  
 Nunca se crean instancias directamente de <xref:System.Windows.Media.DrawingContext>un; sin embargo, se puede adquirir un contexto de dibujo de determinados métodos, <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> como <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>y.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerar el contenido de un objeto Visual  
 Además de sus otros usos, <xref:System.Windows.Media.Drawing> los objetos también proporcionan un modelo de objetos para enumerar el contenido <xref:System.Windows.Media.Visual>de.  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> usa el método para <xref:System.Windows.Media.DrawingGroup> recuperar el valor <xref:System.Windows.Media.Visual> de un y enumerarlo.  
  
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
