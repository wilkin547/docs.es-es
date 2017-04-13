---
title: "Informaci&#243;n general sobre objetos Drawing | Microsoft Docs"
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
  - "Drawing (objetos)"
  - "DrawingGroup (objetos)"
  - "dibujos, acerca de los dibujos"
  - "GeometryDrawing (objetos)"
  - "GlyphRunDrawing (objetos)"
  - "ImageDrawing (objetos)"
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre objetos Drawing
En este tema se presentan los objetos <xref:System.Windows.Media.Drawing> y se describe cómo utilizarlos para dibujar con eficacia formas, mapas de bits, texto y multimedia.  Utilice objetos <xref:System.Windows.Media.Drawing> cuando cree imágenes prediseñadas, pinte con <xref:System.Windows.Media.DrawingBrush> o use objetos <xref:System.Windows.Media.Visual>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whatisadrawingsection"></a>   
## ¿Qué es un objeto Drawing?  
 Un objeto de dibujo, o <xref:System.Windows.Media.Drawing>, describe el contenido visible, como una forma, un mapa de bits, vídeo o una línea de texto.  Los diferentes tipos de dibujos describen tipos diferentes de contenido.  A continuación, se muestra una lista de tipos diferentes de objetos de dibujo.  
  
-   <xref:System.Windows.Media.GeometryDrawing>: dibuja una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing>: dibuja una imagen.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing>: dibuja texto.  
  
-   <xref:System.Windows.Media.VideoDrawing>: reproduce un archivo de audio o vídeo.  
  
-   <xref:System.Windows.Media.DrawingGroup>: dibuja otros dibujos.  Utilice un grupo de dibujo para combinar otros dibujos en un único dibujo compuesto.  
  
 Los objetos <xref:System.Windows.Media.Drawing> son versátiles; existen numerosas maneras de utilizar un objeto <xref:System.Windows.Media.Drawing>.  
  
-   Puede mostrarlo como una imagen utilizando un objeto <xref:System.Windows.Media.DrawingImage> y un control <xref:System.Windows.Controls.Image>.  
  
-   Puede utilizarlo con un objeto <xref:System.Windows.Media.DrawingBrush> para pintar un objeto, como la propiedad <xref:System.Windows.Controls.Page.Background%2A> de <xref:System.Windows.Controls.Page>.  
  
-   Puede utilizarlo para describir el aspecto de un objeto <xref:System.Windows.Media.DrawingVisual>.  
  
-   Puede utilizarlo para enumerar el contenido de un objeto <xref:System.Windows.Media.Visual>.  
  
 WPF proporciona otros tipos de objetos que son capaces de dibujar formas, mapas de bits, texto y multimedia.  Por ejemplo, también puede utilizar objetos <xref:System.Windows.Shapes.Shape> para dibujar formas, mientras que el control <xref:System.Windows.Controls.MediaElement> proporciona otra manera de agregar vídeo a la aplicación.  Así pues, ¿cuándo se deben utilizar los objetos <xref:System.Windows.Media.Drawing>?  Cuando se pueden sacrificar las características de nivel de marco de trabajo para obtener ventajas de rendimiento, o cuando se necesitan las características de <xref:System.Windows.Freezable>.  Debido a que los objetos <xref:System.Windows.Media.Drawing> carecen de compatibilidad con [Diseño](../../../../docs/framework/wpf/advanced/layout.md), la información de entrada y el foco, proporcionan ventajas de rendimiento que los hace idóneos para describir fondos o imágenes prediseñadas, así como para dibujos de bajo nivel con objetos <xref:System.Windows.Media.Visual>.  
  
 Al ser un objeto de tipo <xref:System.Windows.Freezable>, los objetos <xref:System.Windows.Media.Drawing> obtienen varias características especiales, entre las que se incluyen las siguientes: pueden declararse como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md), compartirse entre varios objetos, convertirse en objetos de sólo lectura para mejorar el rendimiento, clonarse y convertirse en seguros para subprocesos.  Para obtener más información sobre las diferentes características que proporcionan los objetos <xref:System.Windows.Freezable>, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="drawinggeometriessection"></a>   
## Dibujar una forma  
 Para dibujar una forma, se utiliza un objeto <xref:System.Windows.Media.GeometryDrawing>.  La propiedad <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> de un dibujo de geometría describe la forma que se va a dibujar, su propiedad <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describe cómo se debe pintar el interior de la forma, y su propiedad <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describe cómo se debe dibujar su contorno.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.GeometryDrawing> para dibujar una forma.  La forma se describe mediante un objeto <xref:System.Windows.Media.GeometryGroup> y dos objetos <xref:System.Windows.Media.EllipseGeometry>.  El interior de la forma se pinta con <xref:System.Windows.Media.LinearGradientBrush> y su contorno se dibuja con un objeto <xref:System.Windows.Media.Pen> con la propiedad <xref:System.Windows.Media.Brushes.Black%2A>.  
  
 En este ejemplo se crea el objeto <xref:System.Windows.Media.GeometryDrawing> siguiente.  
  
 ![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
Objeto GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 Para obtener el ejemplo completo, consulte [Crear un objeto GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md).  
  
 Otras clases <xref:System.Windows.Media.Geometry>, como <xref:System.Windows.Media.PathGeometry>, permiten crear formas más complejas con curvas y arcos.  Para obtener más información acerca de los objetos <xref:System.Windows.Media.Geometry>, consulte [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Para obtener más información sobre otras maneras de dibujar formas en las que no se utilizan objetos <xref:System.Windows.Media.Drawing>, consulte [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).  
  
<a name="drawingimagessection"></a>   
## Dibujar una imagen  
 Para dibujar una imagen, se utiliza <xref:System.Windows.Media.ImageDrawing>.  La propiedad <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> de un objeto <xref:System.Windows.Media.ImageDrawing> describe la imagen que se va a dibujar, mientras que su propiedad <xref:System.Windows.Media.ImageDrawing.Rect%2A> define el área donde se dibuja la imagen.  
  
 En el ejemplo siguiente se dibuja una imagen en un rectángulo situado en \(75,75\), es decir, de 100 por 100 [píxeles](GTMT).  En la ilustración siguiente se muestra el objeto <xref:System.Windows.Media.ImageDrawing> creado por el ejemplo.  Se agregó un borde gris para mostrar los límites de <xref:System.Windows.Media.ImageDrawing>.  
  
 ![ImageDrawing de 100 por 100 dibujada en &#40;75,75&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm\_simple\_imagedrawing\_offset")  
Objeto ImageDrawing de 100 por 100 píxeles  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 Para obtener más información acerca de las imágenes, consulte [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
<a name="playmedia"></a>   
## Reproducir multimedia \(sólo mediante código\)  
  
> [!NOTE]
>  Aunque puede declarar un objeto <xref:System.Windows.Media.VideoDrawing> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], únicamente se pueden cargar y reproducir sus elementos multimedia mediante código.  Para reproducir vídeo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], utilice un elemento <xref:System.Windows.Controls.MediaElement> en su lugar.  
  
 Para reproducir un archivo de audio o vídeo, se utiliza un objeto <xref:System.Windows.Media.VideoDrawing> y un objeto <xref:System.Windows.Media.MediaPlayer>.  Hay dos maneras de cargar y reproducir elementos multimedia.  La primera es utilizar <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> por sí solos; la segunda consiste en crear su propio objeto <xref:System.Windows.Media.MediaTimeline> para utilizarlo con <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Al distribuir los objetos multimedia con la aplicación, no se puede usar ningún archivo multimedia como recurso del proyecto, como se haría con una imagen.  En lugar de ello, en el archivo del proyecto debe establecer en `Content` el tipo de medios y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
 Para reproducir los elementos multimedia sin crear su propio objeto <xref:System.Windows.Media.MediaTimeline>, siga estos pasos.  
  
1.  Crear un objeto <xref:System.Windows.Media.MediaPlayer>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  Utilice el método <xref:System.Windows.Media.MediaPlayer.Open%2A> para cargar el archivo multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  Cree un control <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  Especifique el tamaño y la ubicación donde dibujar el elemento multimedia estableciendo la propiedad <xref:System.Windows.Media.VideoDrawing.Rect%2A> de <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  Establezca la propiedad <xref:System.Windows.Media.VideoDrawing.Player%2A> de <xref:System.Windows.Media.VideoDrawing> con el objeto <xref:System.Windows.Media.MediaPlayer> que ha creado.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  Utilice el método <xref:System.Windows.Media.MediaPlayer.Play%2A> de <xref:System.Windows.Media.MediaPlayer> para iniciar la reproducción del elemento multimedia.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 En el ejemplo siguiente se utilizan los objetos <xref:System.Windows.Media.VideoDrawing> y <xref:System.Windows.Media.MediaPlayer> para reproducir una vez un archivo de vídeo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para controlar mejor el tiempo en los elementos multimedia, utilice un objeto <xref:System.Windows.Media.MediaTimeline> con los objetos <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  <xref:System.Windows.Media.MediaTimeline> permite especificar si el vídeo se debe repetir.  Para utilizar <xref:System.Windows.Media.MediaTimeline> con <xref:System.Windows.Media.VideoDrawing>, siga estos pasos:  
  
1.  Declare <xref:System.Windows.Media.MediaTimeline> y establezca sus comportamientos del control de tiempo.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  Cree un <xref:System.Windows.Media.MediaClock> a partir de <xref:System.Windows.Media.MediaTimeline>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  Cree un <xref:System.Windows.Media.MediaPlayer> y utilice <xref:System.Windows.Media.MediaClock> para establecer su propiedad <xref:System.Windows.Media.MediaPlayer.Clock%2A>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  Cree un <xref:System.Windows.Media.VideoDrawing> y asigne <xref:System.Windows.Media.MediaPlayer> a la propiedad <xref:System.Windows.Media.VideoDrawing.Player%2A> de <xref:System.Windows.Media.VideoDrawing>.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.MediaTimeline> con <xref:System.Windows.Media.MediaPlayer> y con <xref:System.Windows.Media.VideoDrawing> para reproducir repetidamente un vídeo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, al utilizar <xref:System.Windows.Media.MediaTimeline>, se utiliza el objeto <xref:System.Windows.Media.Animation.ClockController> interactivo devuelto de la propiedad <xref:System.Windows.Media.Animation.Clock.Controller%2A> de <xref:System.Windows.Media.MediaClock> para controlar la reproducción multimedia, en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer>.  
  
<a name="drawtext"></a>   
## Dibujar texto  
 Para dibujar texto, se utiliza un objeto <xref:System.Windows.Media.GlyphRunDrawing> y un objeto <xref:System.Windows.Media.GlyphRun>.  En el ejemplo siguiente, se utiliza <xref:System.Windows.Media.GlyphRunDrawing> para dibujar el texto "Hello World".  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun> es un objeto de nivel bajo cuya finalidad es su uso en escenarios de presentación de documento de formato fijo y de impresión.  Una manera más fácil de mostrar texto en la pantalla es utilizar <xref:System.Windows.Controls.Label> o <xref:System.Windows.Controls.TextBlock>.  Para obtener más información sobre <xref:System.Windows.Media.GlyphRun>, consulte la información general de [Introducción al objeto GlyphRun y al elemento Glyphs](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md).  
  
<a name="compositedrawingssection"></a>   
## Dibujos compuestos  
 Un objeto <xref:System.Windows.Media.DrawingGroup> permite combinar varios dibujos en un único dibujo compuesto.  Mediante un objeto <xref:System.Windows.Media.DrawingGroup>, puede combinar formas, imágenes y texto en un mismo objeto <xref:System.Windows.Media.Drawing>.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.DrawingGroup> para combinar dos objetos <xref:System.Windows.Media.GeometryDrawing> y un objeto <xref:System.Windows.Media.ImageDrawing>.  Este ejemplo produce el siguiente resultado.  
  
 ![DrawingGroup con varios dibujos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
Dibujo compuesto  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Un objeto <xref:System.Windows.Media.DrawingGroup> también permite aplicar las máscaras de opacidad, las transformaciones, los efectos de imagen y otras operaciones a su contenido.  Las operaciones de <xref:System.Windows.Media.DrawingGroup> se aplican en el orden siguiente: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> y, a continuación, <xref:System.Windows.Media.DrawingGroup.Transform%2A>.  
  
 En la ilustración siguiente se muestra el orden en el que se aplican las operaciones de <xref:System.Windows.Media.DrawingGroup>.  
  
 ![Orden de operaciones de DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
Orden de las operaciones de DrawingGroup  
  
 En la tabla siguiente se describen las propiedades que puede utilizar para manipular el contenido de un objeto <xref:System.Windows.Media.DrawingGroup>.  
  
|Propiedad.|Descripción|Ilustración|  
|----------------|-----------------|-----------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|Modifica la opacidad de partes seleccionadas del contenido de <xref:System.Windows.Media.DrawingGroup>.  Para obtener un ejemplo, consulte [How to: Control the Opacity of a Drawing](http://msdn.microsoft.com/es-es/68580652-7d32-4d27-93cc-a5148cf4d5ee).||  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|Cambia de manera uniforme la opacidad del contenido de <xref:System.Windows.Media.DrawingGroup>.  Utilice esta propiedad para hacer un <xref:System.Windows.Media.Drawing> transparente total o parcialmente.  Para obtener un ejemplo, vea [How to: Apply an Opacity Mask to a Drawing](http://msdn.microsoft.com/es-es/d77b420b-9be2-479c-a45e-82f4da30eb9f).||  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|Aplica <xref:System.Windows.Media.Effects.BitmapEffect> al contenido de <xref:System.Windows.Media.DrawingGroup>.  Para obtener un ejemplo, consulte [How to: Apply a BitmapEffect to a Drawing](http://msdn.microsoft.com/es-es/c5b1de83-8d09-47fb-96db-5f174471f4b5).||  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|Recorta el contenido de <xref:System.Windows.Media.DrawingGroup> a un área descrita mediante <xref:System.Windows.Media.Geometry>.  Para obtener un ejemplo, consulte [How to: Clip a Drawing](http://msdn.microsoft.com/es-es/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058).||  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|Ajusta los [píxeles independientes del dispositivo](GTMT) a los píxeles del dispositivo a lo largo de las líneas de guía especificadas.  Esta propiedad es útil para asegurarse de que los gráficos finamente detallados se representen con nitidez en las pantallas con un valor bajo de PPP.  Para obtener un ejemplo, vea [Aplicar un objeto GuidelineSet a un dibujo](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md).||  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|Transforma el contenido de <xref:System.Windows.Media.DrawingGroup>.  Para obtener un ejemplo, consulte [How to: Apply a Transform to a Drawing](http://msdn.microsoft.com/es-es/0d525f2b-682d-4d67-9660-cf46929fbabd).||  
  
<a name="usingimagedrawing"></a>   
## Mostrar un dibujo como una imagen  
 Para mostrar <xref:System.Windows.Media.Drawing> con un control <xref:System.Windows.Controls.Image>, utilice <xref:System.Windows.Media.DrawingImage> como propiedad <xref:System.Windows.Controls.Image.Source%2A> del control <xref:System.Windows.Controls.Image> y establezca la propiedad <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName> del objeto <xref:System.Windows.Media.DrawingImage> en el dibujo que desea mostrar.  
  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.DrawingImage> y un control <xref:System.Windows.Controls.Image> para mostrar <xref:System.Windows.Media.GeometryDrawing>.  Este ejemplo produce el siguiente resultado.  
  
 ![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
Objeto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## Pintar un objeto con un dibujo  
 Un objeto <xref:System.Windows.Media.DrawingBrush> es un tipo de pincel que pinta una área con un objeto de dibujo.  Puede utilizarlo para pintar casi cualquier objeto gráfico con un dibujo.  La propiedad <xref:System.Windows.Media.Drawing> de un objeto <xref:System.Windows.Media.DrawingBrush> describe su propiedad <xref:System.Windows.Media.DrawingBrush.Drawing%2A>.  Para representar un <xref:System.Windows.Media.Drawing> con <xref:System.Windows.Media.DrawingBrush>, agréguelo al pincel utilizando la propiedad <xref:System.Windows.Media.Drawing> del pincel y utilice el pincel para pintar un objeto gráfico, como un control o panel.  
  
 En los ejemplos siguientes se utiliza un <xref:System.Windows.Media.DrawingBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle> con una trama creada a partir de un objeto <xref:System.Windows.Media.GeometryDrawing>.  Este ejemplo produce el siguiente resultado.  
  
 ![DrawingBrush en mosaico](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm\_drawingbrush\_geometrydrawing")  
  
        Objeto GeometryDrawing utilizado con un objeto DrawingBrush  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 La clase <xref:System.Windows.Media.DrawingBrush> proporciona gran variedad de opciones para ajustar y colocar en mosaico su contenido.  Para obtener más información sobre <xref:System.Windows.Media.DrawingBrush>, consulte la información general de [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="renderingwithvisualsection"></a>   
## Representar un dibujo con un objeto visual  
 Un objeto <xref:System.Windows.Media.DrawingVisual> es un tipo de objeto visual diseñado para representar un dibujo.  El trabajo directo con la capa visual es una opción para aquellos programadores que desean compilar un entorno gráfico muy personalizado y no se describe en esta información general.  Para obtener más información, consulte la información general de [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="drawingcontextobjects"></a>   
## Objetos DrawingContext  
 La clase <xref:System.Windows.Media.DrawingContext> permite rellenar un objeto <xref:System.Windows.Media.Visual> o <xref:System.Windows.Media.Drawing> con contenido visual.  Muchos de estos objetos gráficos de bajo nivel utilizan <xref:System.Windows.Media.DrawingContext> porque describe con gran eficacia el contenido gráfico.  
  
 Aunque los métodos de dibujo de <xref:System.Windows.Media.DrawingContext> parecen similares a los métodos de dibujo de tipo <xref:System.Drawing.Graphics?displayProperty=fullName>, funcionan de manera muy distinta:  <xref:System.Windows.Media.DrawingContext> se utiliza con un sistema de gráficos de modo retenido, mientras que <xref:System.Drawing.Graphics?displayProperty=fullName> se utiliza con un sistema de gráficos de modo inmediato.  Cuando utiliza los comandos de dibujo de un objeto <xref:System.Windows.Media.DrawingContext>, en realidad está almacenando un conjunto de instrucciones de representación \(si bien el mecanismo de almacenamiento exacto depende del tipo de objeto que proporcione <xref:System.Windows.Media.DrawingContext>\) que el sistema de gráficos utilizará más adelante; no dibuja en la pantalla en tiempo real.  Para obtener más información sobre cómo funciona el sistema de gráficos de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], consulte [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 Nunca se crea directamente una instancia de <xref:System.Windows.Media.DrawingContext>; sin embargo, se puede adquirir un contexto de dibujo a partir de determinados métodos, como <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> y <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>.  
  
<a name="enumeratevisualcontents"></a>   
## Enumerar el contenido de un objeto visual  
 Además de sus otros usos, los objetos <xref:System.Windows.Media.Drawing> también proporcionan un modelo de objetos para enumerar el contenido de <xref:System.Windows.Media.Visual>.  
  
 En el ejemplo siguiente se utiliza el método <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> para recuperar el valor de <xref:System.Windows.Media.DrawingGroup> de un objeto <xref:System.Windows.Media.Visual> y enumerarlo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## Vea también  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)