---
title: Información general sobre objetos Drawing
description: Familiarícese con los objetos y cómo usarlos para dibujar eficazmente formas, mapas de bits, texto y elementos multimedia en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
ms.openlocfilehash: f00a59cd6e799e57f238c5f9b72ecc48e8445475
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853832"
---
# <a name="drawing-objects-overview"></a>Información general sobre objetos Drawing
En este tema <xref:System.Windows.Media.Drawing> se presentan los objetos y se describe cómo usarlos para dibujar eficazmente formas, mapas de bits, texto y elementos multimedia. Utilice los <xref:System.Windows.Media.Drawing> objetos al crear imágenes prediseñadas, pintar con un <xref:System.Windows.Media.DrawingBrush> o utilizar <xref:System.Windows.Media.Visual> objetos.  

<a name="whatisadrawingsection"></a>
## <a name="what-is-a-drawing-object"></a>¿Qué es un objeto Drawing?  
 Un <xref:System.Windows.Media.Drawing> objeto describe el contenido visible, como una forma, un mapa de bits, un vídeo o una línea de texto. Distintos tipos de dibujo describen tipos de contenido diferentes. La siguiente lista muestra los distintos tipos de objetos de dibujo.  
  
- <xref:System.Windows.Media.GeometryDrawing>: Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>: Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>: Dibuja texto.  
  
- <xref:System.Windows.Media.VideoDrawing>: Reproduce un archivo de audio o de vídeo.  
  
- <xref:System.Windows.Media.DrawingGroup>: Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 <xref:System.Windows.Media.Drawing>los objetos son versátiles; Hay muchas maneras de utilizar un <xref:System.Windows.Media.Drawing> objeto.  
  
- Puede mostrarlo como una imagen mediante <xref:System.Windows.Media.DrawingImage> y un <xref:System.Windows.Controls.Image> control.  
  
- Puede utilizarlo con un <xref:System.Windows.Media.DrawingBrush> para pintar un objeto, como la <xref:System.Windows.Controls.Page.Background%2A> de un <xref:System.Windows.Controls.Page> .  
  
- Puede utilizarlo para describir la apariencia de un <xref:System.Windows.Media.DrawingVisual> .  
  
- Se puede utilizar para enumerar el contenido de un <xref:System.Windows.Media.Visual> .  
  
 WPF ofrece otros tipos de objetos capaces de dibujar formas, mapas de bits, texto y elementos multimedia. Por ejemplo, también puede usar <xref:System.Windows.Shapes.Shape> objetos para dibujar formas y el <xref:System.Windows.Controls.MediaElement> control proporciona otra manera de agregar vídeo a la aplicación. ¿Cuándo debe usar <xref:System.Windows.Media.Drawing> objetos? Cuando se pueden sacrificar características de nivel de marco para obtener ventajas de rendimiento o cuando se necesitan <xref:System.Windows.Freezable> características. Dado <xref:System.Windows.Media.Drawing> que los objetos no admiten el [diseño](../advanced/layout.md), la entrada y el foco, proporcionan ventajas de rendimiento que lo hacen idóneos para describir los terrenos, las imágenes prediseñadas y el dibujo de bajo nivel con <xref:System.Windows.Media.Visual> objetos.  
  
 Dado que se trata de un objeto de tipo <xref:System.Windows.Freezable> , <xref:System.Windows.Media.Drawing> los objetos obtienen varias características especiales, entre las que se incluyen las siguientes: se pueden declarar como [recursos](../../../desktop-wpf/fundamentals/xaml-resources-define.md), compartirse entre varios objetos, convertirse en de solo lectura para mejorar el rendimiento, clonarse y hacerse seguro para subprocesos. Para obtener más información acerca de las diferentes características proporcionadas por los <xref:System.Windows.Freezable> objetos, consulte la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>
## <a name="draw-a-shape"></a>Dibujar una forma  
 Para dibujar una forma, se usa un <xref:System.Windows.Media.GeometryDrawing> . La propiedad de un dibujo de geometría <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describe la forma que se va a dibujar, su <xref:System.Windows.Media.GeometryDrawing.Brush%2A> propiedad describe cómo se debe pintar el interior de la forma y su <xref:System.Windows.Media.GeometryDrawing.Pen%2A> propiedad describe cómo debe dibujarse su contorno.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.GeometryDrawing> se utiliza para dibujar una forma. La forma se describe mediante <xref:System.Windows.Media.GeometryGroup> y dos <xref:System.Windows.Media.EllipseGeometry> objetos. El interior de la forma se pinta con un <xref:System.Windows.Media.LinearGradientBrush> y su contorno se dibuja con un <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen> .  
  
 En este ejemplo se crea lo siguiente <xref:System.Windows.Media.GeometryDrawing> .  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Para obtener el ejemplo completo, vea [Create a GeometryDrawing](how-to-create-a-geometrydrawing.md) (Cómo: Crear un objeto GeometryDrawing).  
  
 Otras <xref:System.Windows.Media.Geometry> clases, como <xref:System.Windows.Media.PathGeometry> permitirle crear formas más complejas creando curvas y arcos. Para obtener más información sobre <xref:System.Windows.Media.Geometry> los objetos, consulte [información general sobre geometría](geometry-overview.md).  
  
 Para obtener más información sobre otras formas de dibujar formas que no usan <xref:System.Windows.Media.Drawing> objetos, vea [información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>
## <a name="draw-an-image"></a>Dibujar un objeto Image  
 Para dibujar una imagen, se usa un <xref:System.Windows.Media.ImageDrawing> . <xref:System.Windows.Media.ImageDrawing>La propiedad de un objeto <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> describe la imagen que se va a dibujar y su <xref:System.Windows.Media.ImageDrawing.Rect%2A> propiedad define la región donde se dibuja la imagen.  
  
 En el ejemplo siguiente se dibuja una imagen en un rectángulo situado en (75,75) que ocupa 100 por 100 píxeles. En la ilustración siguiente se muestra el <xref:System.Windows.Media.ImageDrawing> creado por el ejemplo. Se ha agregado un borde gris para mostrar los límites de <xref:System.Windows.Media.ImageDrawing> .  
  
 ![Objeto ImageDrawing de 100 por 100 dibujado en (75,75)](./media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
ImageDrawing de 100 por 100  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Para más información sobre las imágenes, [Información general sobre imágenes](imaging-overview.md).  
  
<a name="playmedia"></a>
## <a name="play-media-code-only"></a>Reproducir elementos multimedia (solo código)  
  
> [!NOTE]
> Aunque puede declarar un <xref:System.Windows.Media.VideoDrawing> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , solo puede cargar y reproducir sus medios mediante el código. Para reproducir vídeo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , utilice en <xref:System.Windows.Controls.MediaElement> su lugar un.  
  
 Para reproducir un archivo de audio o vídeo, use <xref:System.Windows.Media.VideoDrawing> y <xref:System.Windows.Media.MediaPlayer> . Hay dos maneras de cargar y reproducir elementos multimedia. La primera es usar una <xref:System.Windows.Media.MediaPlayer> y una <xref:System.Windows.Media.VideoDrawing> por sí misma, y la segunda consiste en crear la suya propia <xref:System.Windows.Media.MediaTimeline> para usarla con <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> .  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
 Para reproducir contenido multimedia sin crear el suyo propio <xref:System.Windows.Media.MediaTimeline> , realice los pasos siguientes.  
  
1. Crear un objeto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2. Use el <xref:System.Windows.Media.MediaPlayer.Open%2A> método para cargar el archivo multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3. Creará un control <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4. Especifique el tamaño y la ubicación para dibujar el medio estableciendo la <xref:System.Windows.Media.VideoDrawing.Rect%2A> propiedad de <xref:System.Windows.Media.VideoDrawing> .  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5. Establezca la <xref:System.Windows.Media.VideoDrawing.Player%2A> propiedad de <xref:System.Windows.Media.VideoDrawing> con el <xref:System.Windows.Media.MediaPlayer> que creó.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6. Utilice el <xref:System.Windows.Media.MediaPlayer.Play%2A> método de <xref:System.Windows.Media.MediaPlayer> para empezar a reproducir los elementos multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer> para reproducir un archivo de vídeo una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para obtener un control de tiempo adicional sobre los medios, utilice <xref:System.Windows.Media.MediaTimeline> con <xref:System.Windows.Media.MediaPlayer> los <xref:System.Windows.Media.VideoDrawing> objetos y. <xref:System.Windows.Media.MediaTimeline>Permite especificar si el vídeo debe repetirse. Para usar un <xref:System.Windows.Media.MediaTimeline> con <xref:System.Windows.Media.VideoDrawing> , realice los pasos siguientes:  
  
1. Declare <xref:System.Windows.Media.MediaTimeline> y establezca sus comportamientos de control de tiempo.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2. Cree un a <xref:System.Windows.Media.MediaClock> partir de <xref:System.Windows.Media.MediaTimeline> .  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3. Cree un <xref:System.Windows.Media.MediaPlayer> y use <xref:System.Windows.Media.MediaClock> para establecer su <xref:System.Windows.Media.MediaPlayer.Clock%2A> propiedad.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4. Cree un <xref:System.Windows.Media.VideoDrawing> y asigne <xref:System.Windows.Media.MediaPlayer> a la <xref:System.Windows.Media.VideoDrawing.Player%2A> propiedad de <xref:System.Windows.Media.VideoDrawing> .  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 En el ejemplo siguiente <xref:System.Windows.Media.MediaTimeline> se usa con <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> para reproducir un vídeo repetidamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, cuando se usa un <xref:System.Windows.Media.MediaTimeline> , se usa la interactiva <xref:System.Windows.Media.Animation.ClockController> devuelta desde la <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de <xref:System.Windows.Media.MediaClock> para controlar la reproducción multimedia en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer> .  
  
<a name="drawtext"></a>
## <a name="draw-text"></a>Dibujar texto  
 Para dibujar texto, use <xref:System.Windows.Media.GlyphRunDrawing> y <xref:System.Windows.Media.GlyphRun> . En el ejemplo siguiente <xref:System.Windows.Media.GlyphRunDrawing> se utiliza para dibujar el texto "Hola mundo".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 Un <xref:System.Windows.Media.GlyphRun> es un objeto de bajo nivel diseñado para su uso con escenarios de impresión y presentación de documentos de formato fijo. Una manera más sencilla de dibujar texto en la pantalla es usar <xref:System.Windows.Controls.Label> o <xref:System.Windows.Controls.TextBlock> . Para obtener más información sobre <xref:System.Windows.Media.GlyphRun> , vea la [Introducción a la información general sobre el objeto GlyphRun y el elemento glyphs](../advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) .  
  
<a name="compositedrawingssection"></a>
## <a name="composite-drawings"></a>Dibujos compuestos  
 <xref:System.Windows.Media.DrawingGroup>Permite combinar varios dibujos en un solo dibujo compuesto. Mediante <xref:System.Windows.Media.DrawingGroup> , puede combinar formas, imágenes y texto en un solo <xref:System.Windows.Media.Drawing> objeto.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.DrawingGroup> se usa para combinar dos <xref:System.Windows.Media.GeometryDrawing> objetos y un <xref:System.Windows.Media.ImageDrawing> objeto. Este ejemplo produce el siguiente resultado:  
  
 ![DrawingGroup con varios dibujos](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un dibujo compuesto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <xref:System.Windows.Media.DrawingGroup>También permite aplicar máscaras de opacidad, transformaciones, efectos de imagen y otras operaciones a su contenido. <xref:System.Windows.Media.DrawingGroup>las operaciones se aplican en el orden siguiente: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A> , <xref:System.Windows.Media.DrawingGroup.Opacity%2A> , <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A> , <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> , <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> y <xref:System.Windows.Media.DrawingGroup.Transform%2A> .  
  
 En la ilustración siguiente se muestra el orden en que <xref:System.Windows.Media.DrawingGroup> se aplican las operaciones.  
  
 ![Orden de las operaciones de DrawingGroup](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Orden de las operaciones de DrawingGroup  
  
 En la tabla siguiente se describen las propiedades que se pueden utilizar para manipular el <xref:System.Windows.Media.DrawingGroup> contenido de un objeto.  
  
|Propiedad.|Descripción|Ilustración|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica la opacidad de las partes seleccionadas del <xref:System.Windows.Media.DrawingGroup> contenido. Para obtener un ejemplo, vea [How to: Control the Opacity of a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms748242(v=vs.90)) (Cómo: Controlar la opacidad de un dibujo).|![DrawingGroup con una máscara de opacidad](./media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Cambia uniformemente la opacidad del <xref:System.Windows.Media.DrawingGroup> contenido. Utilice esta propiedad para hacer que sea <xref:System.Windows.Media.Drawing> transparente o parcialmente transparente. Para obtener un ejemplo, vea [How to: Apply an Opacity Mask to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms753195(v=vs.90)) (Cómo: Aplicar una máscara de opacidad a un dibujo).|![DrawingGroups con diferentes valores de opacidad](./media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Aplica un <xref:System.Windows.Media.Effects.BitmapEffect> al <xref:System.Windows.Media.DrawingGroup> contenido de. Para obtener un ejemplo, vea [How to: Apply a BitmapEffect to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752341(v=vs.90)) (Cómo: Aplicar un objeto BitmapEffect a un dibujo).|![DrawingGroup con BlurBitmapEffect](./media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Recorta el <xref:System.Windows.Media.DrawingGroup> contenido a una región que se describe mediante un <xref:System.Windows.Media.Geometry> . Para obtener un ejemplo, vea [How to: Clip a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms743068(v=vs.90)) (Cómo: Recortar un dibujo).|![DrawingGroup con una región de recorte definida](./media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Ajusta los píxeles independientes del dispositivo a los píxeles del dispositivo según las directrices especificadas. Esta propiedad resulta útil para garantizar que los gráficos muy detallados se representan nítidamente en pantallas de baja resolución. Para obtener un ejemplo, vea [Apply a GuidelineSet to a Drawing](how-to-apply-a-guidelineset-to-a-drawing.md) (Aplicar un objeto GuidelineSet a un dibujo).|![DrawingGroup con y sin GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transforma el <xref:System.Windows.Media.DrawingGroup> contenido. Para obtener un ejemplo, vea [How to: Apply a Transform to a Drawing](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms742304(v=vs.90)) (Cómo: Aplicar una transformación a un dibujo).|![DrawingGroup girado](./media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>
## <a name="display-a-drawing-as-an-image"></a>Mostrar un dibujo como imagen  
 Para mostrar un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> control, use <xref:System.Windows.Media.DrawingImage> como <xref:System.Windows.Controls.Image> del control <xref:System.Windows.Controls.Image.Source%2A> y establezca la <xref:System.Windows.Media.DrawingImage> propiedad del objeto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> en el dibujo que desea mostrar.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.DrawingImage> se usa un <xref:System.Windows.Controls.Image> control y para mostrar un <xref:System.Windows.Media.GeometryDrawing> . Este ejemplo produce el siguiente resultado:  
  
 ![GeometryDrawing de dos elipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>
## <a name="paint-an-object-with-a-drawing"></a>Pintar un objeto con un dibujo  
 Un <xref:System.Windows.Media.DrawingBrush> es un tipo de pincel que pinta un área con un objeto de dibujo. Puede usarlo para pintar casi cualquier objeto gráfico con un dibujo. La <xref:System.Windows.Media.Drawing> propiedad de un <xref:System.Windows.Media.DrawingBrush> describe su <xref:System.Windows.Media.DrawingBrush.Drawing%2A> . Para representar un <xref:System.Windows.Media.Drawing> con <xref:System.Windows.Media.DrawingBrush> , agréguelo al pincel mediante la propiedad del pincel <xref:System.Windows.Media.Drawing> y use el pincel para pintar un objeto gráfico, como un control o un panel.  
  
 En los ejemplos siguientes <xref:System.Windows.Media.DrawingBrush> se usa para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle> con un patrón creado a partir de un <xref:System.Windows.Media.GeometryDrawing> . Este ejemplo produce el siguiente resultado:  
  
 ![DrawingBrush en mosaico](./media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
Uso de GeometryDrawing con un objeto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La <xref:System.Windows.Media.DrawingBrush> clase proporciona diversas opciones para ajustar y colocar en mosaico su contenido. Para obtener más información sobre <xref:System.Windows.Media.DrawingBrush> , consulte la información general sobre el [dibujo con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md) .  
  
<a name="renderingwithvisualsection"></a>
## <a name="render-a-drawing-with-a-visual"></a>Representar un dibujo con un objeto Visual  
 Un <xref:System.Windows.Media.DrawingVisual> es un tipo de objeto visual diseñado para representar un dibujo. Una posibilidad para los desarrolladores que quieran crear un entorno gráfico muy personalizado es trabajar directamente en la capa visual, que no se describe en esta información general. Para más información, consulte la página de información general [Usar objetos DrawingVisual](using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>
## <a name="drawingcontext-objects"></a>Objetos DrawingContext  
 La <xref:System.Windows.Media.DrawingContext> clase le permite rellenar un <xref:System.Windows.Media.Visual> o un <xref:System.Windows.Media.Drawing> con contenido visual. Muchos de estos objetos gráficos de nivel inferior usan un <xref:System.Windows.Media.DrawingContext> porque describe el contenido gráfico de manera muy eficaz.  
  
 Aunque los <xref:System.Windows.Media.DrawingContext> métodos de dibujo parecen similares a los métodos de dibujo del <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo, en realidad son muy diferentes. <xref:System.Windows.Media.DrawingContext>se usa con un sistema de gráficos en modo retenido, mientras que el <xref:System.Drawing.Graphics?displayProperty=nameWithType> tipo se usa con un sistema de gráficos de modo inmediato. Cuando se usan <xref:System.Windows.Media.DrawingContext> comandos de dibujo de un objeto, en realidad se almacena un conjunto de instrucciones de representación (aunque el mecanismo de almacenamiento exacto depende del tipo de objeto que proporciona el <xref:System.Windows.Media.DrawingContext> ) que el sistema de gráficos usará más adelante; no se dibuja en la pantalla en tiempo real. Para obtener más información sobre cómo funciona el sistema de gráficos de Windows Presentation Foundation (WPF), consulte [información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md).  
  
 Nunca se crean instancias directamente de un <xref:System.Windows.Media.DrawingContext> ; sin embargo, se puede adquirir un contexto de dibujo de determinados métodos, como <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> y <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType> .  
  
<a name="enumeratevisualcontents"></a>
## <a name="enumerate-the-contents-of-a-visual"></a>Enumerar el contenido de un objeto Visual  
 Además de sus otros usos, los <xref:System.Windows.Media.Drawing> objetos también proporcionan un modelo de objetos para enumerar el contenido de <xref:System.Windows.Media.Visual> .  
  
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
