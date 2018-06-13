---
title: Pintar con imágenes, dibujos y elementos visuales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
ms.openlocfilehash: abb5733ed54ea430ba161db5ea2dcb33e99298ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566917"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Pintar con imágenes, dibujos y elementos visuales
Este tema describe cómo usar <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, y <xref:System.Windows.Media.VisualBrush> objetos que se va a pintar un área con una imagen, un <xref:System.Windows.Media.Drawing>, o un <xref:System.Windows.Media.Visual>.  
    
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con los distintos tipos de pinceles que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona y sus características básicas. Para una introducción, consulte [Información general sobre pinceles de WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Pintar un área con una imagen  
 Un <xref:System.Windows.Media.ImageBrush> pinta un área con un <xref:System.Windows.Media.ImageSource>. El tipo más común de <xref:System.Windows.Media.ImageSource> para usar con un <xref:System.Windows.Media.ImageBrush> es un <xref:System.Windows.Media.Imaging.BitmapImage>, que describe un gráfico de mapa de bits. Puede usar un <xref:System.Windows.Media.DrawingImage> para pintar usando un <xref:System.Windows.Media.Drawing> objeto, pero es más fácil de usar un <xref:System.Windows.Media.DrawingBrush> en su lugar. Para obtener más información acerca de <xref:System.Windows.Media.ImageSource> los objetos, vea la [información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
 Para pintar con un <xref:System.Windows.Media.ImageBrush>, cree un <xref:System.Windows.Media.Imaging.BitmapImage> y usarlo para cargar el contenido de mapa de bits. A continuación, utilice la <xref:System.Windows.Media.Imaging.BitmapImage> para establecer el <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad de la <xref:System.Windows.Media.ImageBrush>. Por último, aplique la <xref:System.Windows.Media.ImageBrush> para el objeto que desea pintar.  En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], también puede establecer el <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad de la <xref:System.Windows.Media.ImageBrush> con la ruta de acceso de la imagen para cargar.  
  
 Al igual que todos <xref:System.Windows.Media.Brush> objetos, un <xref:System.Windows.Media.ImageBrush> puede utilizarse para pintar objetos como formas, paneles, controles y texto. En la siguiente ilustración se muestra algunos efectos que se pueden lograr con un <xref:System.Windows.Media.ImageBrush>.  
  
 ![Ejemplos del resultado de ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Objetos pintados mediante ImageBrush  
  
 De forma predeterminada, un <xref:System.Windows.Media.ImageBrush> se expande la imagen para que rellene completamente el área que se va a pintar, lo que puede distorsionar la imagen si el área de pintura tiene una relación de aspecto diferente que la imagen. Puede cambiar este comportamiento cambiando el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad desde su valor predeterminado de <xref:System.Windows.Media.Stretch.Fill> a <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>, o <xref:System.Windows.Media.Stretch.UniformToFill>. Dado que <xref:System.Windows.Media.ImageBrush> es un tipo de <xref:System.Windows.Media.TileBrush>, puede especificar exactamente cómo un pincel de imagen rellena el área de resultados e incluso crear patrones. Para obtener más información sobre opciones avanzadas <xref:System.Windows.Media.TileBrush> características, consulte la [TileBrush Overview](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Ejemplo: Pintar un objeto con una imagen de mapa de bits  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush> para pintar el <xref:System.Windows.Controls.Panel.Background%2A> de un <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Pintar un área con un dibujo  
 Un <xref:System.Windows.Media.DrawingBrush> permite pintar un área con formas, texto, imágenes y vídeo. Formas dentro de un pincel con dibujo pueden pintarse a su vez con un color sólido, degradado, imagen, o incluso otro <xref:System.Windows.Media.DrawingBrush>. En la siguiente ilustración se muestra algunos usos de un <xref:System.Windows.Media.DrawingBrush>.  
  
 ![Ejemplos del resultado de DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Objetos pintados mediante DrawingBrush  
  
 A <xref:System.Windows.Media.DrawingBrush> pinta un área con un <xref:System.Windows.Media.Drawing> objeto. Un <xref:System.Windows.Media.Drawing> objeto describe el contenido visible, como una forma, mapa de bits, vídeo o una línea de texto. Distintos tipos de dibujo describen tipos de contenido diferentes. La siguiente lista muestra los distintos tipos de objetos de dibujo.  
  
-   <xref:System.Windows.Media.GeometryDrawing> – Dibuja una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing> – Dibuja una imagen.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> – Dibuja texto.  
  
-   <xref:System.Windows.Media.VideoDrawing> – Reproduce un archivo de audio o vídeo.  
  
-   <xref:System.Windows.Media.DrawingGroup> – Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 Para obtener más información acerca de <xref:System.Windows.Media.Drawing> los objetos, vea la [información general de objetos de dibujo](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
 Al igual que un <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> ajusta su <xref:System.Windows.Media.DrawingBrush.Drawing%2A> para rellenar su área de salida. Puede invalidar este comportamiento cambiando el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad desde su valor predeterminado de <xref:System.Windows.Media.Stretch.Fill>. Para obtener más información, vea la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Ejemplo: Pintar un objeto con un dibujo  
 En el ejemplo siguiente se muestra cómo pintar un objeto con un dibujo de tres elipses. Un <xref:System.Windows.Media.GeometryDrawing> se usa para describir los puntos suspensivos.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Pintar un área con un objeto visual  
 La más versátil y eficaz de todos los pinceles, los <xref:System.Windows.Media.VisualBrush> pinta un área con un <xref:System.Windows.Media.Visual>. A <xref:System.Windows.Media.Visual> es un tipo gráfico de bajo nivel que actúa como el antecesor de muchos componentes gráficos útiles. Por ejemplo, el <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.Controls.Control> clases son todos los tipos de <xref:System.Windows.Media.Visual> objetos. Con un <xref:System.Windows.Media.VisualBrush>, puede pintar áreas con casi cualquier [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objeto gráfico.  
  
> [!NOTE]
>  Aunque <xref:System.Windows.Media.VisualBrush> es un tipo de <xref:System.Windows.Freezable> objeto, no se pueden inmovilizar (establecer la de solo lectura) cuando su <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad se establece en un valor distinto de `null`.  
  
 Hay dos maneras de especificar el <xref:System.Windows.Media.VisualBrush.Visual%2A> contenido de un <xref:System.Windows.Media.VisualBrush>.  
  
-   Crear un nuevo <xref:System.Windows.Media.Visual> y usarla para definir la <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad de la <xref:System.Windows.Media.VisualBrush>. Si desea ver un ejemplo, consulte la sección [Ejemplo: Pintar un objeto con un objeto visual](#examplevisualbrush1) a continuación.  
  
-   Usar una existente <xref:System.Windows.Media.Visual>, que crea una imagen duplicada del destino <xref:System.Windows.Media.Visual>. A continuación, puede usar el <xref:System.Windows.Media.VisualBrush> para crear efectos interesantes, como la reflexión y ampliación. Si desea ver un ejemplo, consulte la sección [Ejemplo: Crear un reflejo](#examplevisualbrush2).  
  
 Al definir un nuevo <xref:System.Windows.Media.VisualBrush.Visual%2A> para un <xref:System.Windows.Media.VisualBrush> y que <xref:System.Windows.Media.Visual> es un <xref:System.Windows.UIElement> (por ejemplo, un panel o control), el sistema de diseño se ejecuta en el <xref:System.Windows.UIElement> y sus elementos secundarios cuando la <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> propiedad está establecida en `true`. Sin embargo, la raíz <xref:System.Windows.UIElement> se queda aislado del resto del sistema: estilos y el diseño externo no pueden atravesar este límite. Por lo tanto, debe especificar explícitamente el tamaño de la raíz de <xref:System.Windows.UIElement>, porque su único elemento primario es el <xref:System.Windows.Media.VisualBrush> y por lo tanto no se puede cambiar automáticamente de tamaño para el área que se está pintando. Para más información sobre el diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], consulte [Diseño](../../../../docs/framework/wpf/advanced/layout.md).  
  
 Al igual que <xref:System.Windows.Media.ImageBrush> y <xref:System.Windows.Media.DrawingBrush>, un <xref:System.Windows.Media.VisualBrush> ajusta su contenido para rellenar su área de salida. Puede invalidar este comportamiento cambiando el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad desde su valor predeterminado de <xref:System.Windows.Media.Stretch.Fill>. Para obtener más información, vea la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Ejemplo: Pintar un objeto con un objeto visual  
 En el ejemplo siguiente, se usan varios controles y un panel para pintar un rectángulo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Ejemplo: Crear un reflejo  
 En el ejemplo anterior se ha explicado cómo crear un nuevo <xref:System.Windows.Media.Visual> para su uso como fondo. También puede utilizar un <xref:System.Windows.Media.VisualBrush> para mostrar un objeto visual existente; esta función permite producir efectos visuales interesantes, tales como reflexiones y ampliaciones. En el ejemplo siguiente se usa un <xref:System.Windows.Media.VisualBrush> para crear un reflejo de una <xref:System.Windows.Controls.Border> que contiene varios elementos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![Un objeto Visual de reflejan](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Objeto Visual reflejado  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Si quiere ver ejemplos adicionales que muestren cómo aumentar partes de la pantalla y cómo crear reflejos, consulte [Ejemplo de VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Características de TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, y <xref:System.Windows.Media.VisualBrush> son tipos de <xref:System.Windows.Media.TileBrush> objetos. <xref:System.Windows.Media.TileBrush> objetos proporcionan un gran control sobre cómo se pinta un área con una imagen, dibujo o el objeto visual. Por ejemplo, en lugar de limitarse a dibujar un área con una sola imagen ajustada, puede dibujar un área con una serie de mosaicos de imagen que crean un patrón.  
  
 Un <xref:System.Windows.Media.TileBrush> tiene tres componentes principales: contenido, mosaicos y el área de salida.  
  
 ![Componentes de TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componentes de TileBrush con un solo mosaico  
  
 ![Componentes de TileBrush en mosaico](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componentes de TileBrush con varios mosaicos  
  
 Para obtener más información acerca de las características de mosaico de <xref:System.Windows.Media.TileBrush> los objetos, vea la [TileBrush Overview](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [Información general sobre objetos TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [Información general sobre pinceles de WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Información general sobre las máscaras de opacidad](../../../../docs/framework/wpf/graphics-multimedia/opacity-masks-overview.md)  
 [Información general sobre la representación de gráficos en WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Ejemplo de ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [Ejemplo de VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)
