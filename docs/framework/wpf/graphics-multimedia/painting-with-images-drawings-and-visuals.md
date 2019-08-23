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
ms.openlocfilehash: e80132a5467f932e5569787f43427044ba2be256
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929608"
---
# <a name="painting-with-images-drawings-and-visuals"></a>Pintar con imágenes, dibujos y elementos visuales
En este tema se describe cómo <xref:System.Windows.Media.ImageBrush>utilizar <xref:System.Windows.Media.DrawingBrush>los objetos <xref:System.Windows.Media.VisualBrush> , y para pintar un área con una imagen, <xref:System.Windows.Media.Drawing>un o un <xref:System.Windows.Media.Visual>.  

<a name="prereqs"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con los distintos tipos de pinceles que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona y sus características básicas. Para una introducción, consulte [Información general sobre pinceles de WPF](wpf-brushes-overview.md).  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>Pintar un área con una imagen  
 Dibuja un área con un <xref:System.Windows.Media.ImageSource>. <xref:System.Windows.Media.ImageBrush> El tipo más común de <xref:System.Windows.Media.ImageSource> que <xref:System.Windows.Media.ImageBrush> se utiliza con es un <xref:System.Windows.Media.Imaging.BitmapImage>, que describe un gráfico de mapa de bits. Puede usar <xref:System.Windows.Media.DrawingImage> para pintar con un <xref:System.Windows.Media.Drawing> objeto, pero es <xref:System.Windows.Media.DrawingBrush> más sencillo utilizar en su lugar. Para obtener más información <xref:System.Windows.Media.ImageSource> acerca de los objetos, consulte la [información general sobre imágenes](imaging-overview.md).  
  
 Para pintar con <xref:System.Windows.Media.ImageBrush>, cree un <xref:System.Windows.Media.Imaging.BitmapImage> y úselo para cargar el contenido del mapa de bits. A continuación, utilice <xref:System.Windows.Media.Imaging.BitmapImage> para establecer la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad de <xref:System.Windows.Media.ImageBrush>. Por último, aplique <xref:System.Windows.Media.ImageBrush> al objeto que desea pintar.  En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], también puede establecer la <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad de <xref:System.Windows.Media.ImageBrush> con la ruta de acceso de la imagen que se va a cargar.  
  
 Al igual <xref:System.Windows.Media.Brush> que todos los <xref:System.Windows.Media.ImageBrush> objetos, se puede usar para pintar objetos como formas, paneles, controles y texto. En la ilustración siguiente se muestran algunos efectos que se pueden lograr <xref:System.Windows.Media.ImageBrush>con un.  
  
 ![Ejemplos de salida de ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Objetos pintados mediante ImageBrush  
  
 De forma predeterminada, <xref:System.Windows.Media.ImageBrush> un ajusta su imagen para rellenar completamente el área que se está pintando, lo que posiblemente distorsiona la imagen si el área pintada tiene una relación de aspecto diferente a la imagen. Puede cambiar este comportamiento <xref:System.Windows.Media.TileBrush.Stretch%2A> cambiando la propiedad de su valor predeterminado de <xref:System.Windows.Media.Stretch.Fill> a <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>o <xref:System.Windows.Media.Stretch.UniformToFill>. Dado <xref:System.Windows.Media.ImageBrush> que es un tipo <xref:System.Windows.Media.TileBrush>de, puede especificar exactamente cómo un pincel de imagen rellena el área de salida e incluso crear patrones. Para obtener más información acerca <xref:System.Windows.Media.TileBrush> de las características avanzadas, consulte [información general de TileBrush](tilebrush-overview.md).  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>Ejemplo: Pintar un objeto con una imagen de mapa de bits  
 <xref:System.Windows.Media.ImageBrush> En el ejemplo siguiente se utiliza para pintar <xref:System.Windows.Controls.Panel.Background%2A> el de <xref:System.Windows.Controls.Canvas>un.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Pintar un área con un dibujo  
 <xref:System.Windows.Media.DrawingBrush> Permite pintar un área con formas, texto, imágenes y vídeo. Las formas que se encuentran dentro de un pincel de dibujo pueden dibujarse a sí mismas con un color sólido <xref:System.Windows.Media.DrawingBrush>, un degradado, una imagen o incluso otro. En la ilustración siguiente se muestran algunos usos <xref:System.Windows.Media.DrawingBrush>de un.  
  
 ![Ejemplos de resultados de DrawingBrush](./media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
Objetos pintados mediante DrawingBrush  
  
 Dibuja un área con un <xref:System.Windows.Media.Drawing> objeto. <xref:System.Windows.Media.DrawingBrush> Un <xref:System.Windows.Media.Drawing> objeto describe el contenido visible, como una forma, un mapa de bits, un vídeo o una línea de texto. Distintos tipos de dibujo describen tipos de contenido diferentes. La siguiente lista muestra los distintos tipos de objetos de dibujo.  
  
- <xref:System.Windows.Media.GeometryDrawing>: Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>: Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>: Dibuja texto.  
  
- <xref:System.Windows.Media.VideoDrawing>: Reproduce un archivo de audio o de vídeo.  
  
- <xref:System.Windows.Media.DrawingGroup>: Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 Para obtener más información <xref:System.Windows.Media.Drawing> sobre los objetos, vea [información general sobre objetos Drawing](drawing-objects-overview.md).  
  
 Al igual que <xref:System.Windows.Media.DrawingBrush.Drawing%2A> <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.ImageBrush>, un amplía su para rellenar su área de salida. Puede invalidar este comportamiento cambiando la <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de su configuración predeterminada de. <xref:System.Windows.Media.Stretch.Fill> Para obtener más información, vea la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>Ejemplo: Pintar un objeto con un dibujo  
 En el ejemplo siguiente se muestra cómo pintar un objeto con un dibujo de tres elipses. <xref:System.Windows.Media.GeometryDrawing> Se usa para describir los puntos suspensivos.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>Pintar un área con un objeto visual  
 La más versátil y eficaz de todos los pinceles, <xref:System.Windows.Media.VisualBrush> pinta un área con un <xref:System.Windows.Media.Visual>. Un <xref:System.Windows.Media.Visual> es un tipo gráfico de bajo nivel que actúa como antecesor de muchos componentes gráficos útiles. Por ejemplo, las <xref:System.Windows.Window>clases <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.Controls.Control> son todos los tipos de <xref:System.Windows.Media.Visual> objetos. Con, puede pintar áreas con casi cualquier [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objeto gráfico. <xref:System.Windows.Media.VisualBrush>  
  
> [!NOTE]
> Aunque <xref:System.Windows.Media.VisualBrush> es un tipo de <xref:System.Windows.Freezable> objeto, no se puede inmovilizar (hacer de solo lectura) <xref:System.Windows.Media.VisualBrush.Visual%2A> cuando su propiedad se establece en un valor `null`distinto de.  
  
 Hay dos maneras de especificar el <xref:System.Windows.Media.VisualBrush.Visual%2A> contenido de un. <xref:System.Windows.Media.VisualBrush>  
  
- Cree un nuevo <xref:System.Windows.Media.Visual> y úselo para establecer la <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad de <xref:System.Windows.Media.VisualBrush>. Para obtener un ejemplo, vea [el ejemplo: Pinte un objeto con una sección](#examplevisualbrush1) visual que se muestra a continuación.  
  
- Use un existente <xref:System.Windows.Media.Visual>, que crea una imagen duplicada del destino <xref:System.Windows.Media.Visual>. Después, puede usar <xref:System.Windows.Media.VisualBrush> para crear efectos interesantes, como la reflexión y la ampliación. Para obtener un ejemplo, vea [el ejemplo: Cree una sección](#examplevisualbrush2) de reflexión.  
  
 Al definir un nuevo <xref:System.Windows.Media.VisualBrush.Visual%2A> para un <xref:System.Windows.Media.VisualBrush> y que <xref:System.Windows.Media.Visual> es un <xref:System.Windows.UIElement> (como un <xref:System.Windows.UIElement> panel o control), el sistema de diseño se ejecuta en y sus elementos secundarios cuando la <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> propiedad está establecida en `true`. Sin embargo, la <xref:System.Windows.UIElement> raíz está esencialmente aislada del resto del sistema: los estilos y el diseño externo no pueden contratar este límite. Por lo tanto, debe especificar explícitamente el tamaño de <xref:System.Windows.UIElement>la raíz, porque su único elemento <xref:System.Windows.Media.VisualBrush> primario es y, por lo tanto, no puede ajustarse automáticamente al área que se está pintando. Para más información sobre el diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], consulte [Diseño](../advanced/layout.md).  
  
 Al <xref:System.Windows.Media.ImageBrush> igual <xref:System.Windows.Media.DrawingBrush>que y <xref:System.Windows.Media.VisualBrush> , un ajusta su contenido para rellenar su área de salida. Puede invalidar este comportamiento cambiando la <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de su configuración predeterminada de. <xref:System.Windows.Media.Stretch.Fill> Para obtener más información, vea la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A>.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>Ejemplo: Pintar un objeto con un objeto visual  
 En el ejemplo siguiente, se usan varios controles y un panel para pintar un rectángulo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>Ejemplo: Crear una reflexión  
 En el ejemplo anterior se mostró cómo crear un <xref:System.Windows.Media.Visual> nuevo para usarlo como fondo. También puede usar un <xref:System.Windows.Media.VisualBrush> para mostrar un visual existente; esta funcionalidad le permite generar efectos visuales interesantes, como reflejos y aumento. <xref:System.Windows.Media.VisualBrush> En el ejemplo siguiente se usa para crear un reflejo de <xref:System.Windows.Controls.Border> un que contiene varios elementos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![Objeto visual reflejado](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Objeto Visual reflejado  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Si quiere ver ejemplos adicionales que muestren cómo aumentar partes de la pantalla y cómo crear reflejos, consulte [Ejemplo de VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>Características de TileBrush  
 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.TileBrush> y <xref:System.Windows.Media.VisualBrush> son tipos de objetos. <xref:System.Windows.Media.TileBrush>los objetos proporcionan un gran control sobre cómo se pinta un área con una imagen, un dibujo o un objeto visual. Por ejemplo, en lugar de limitarse a dibujar un área con una sola imagen ajustada, puede dibujar un área con una serie de mosaicos de imagen que crean un patrón.  
  
 Un <xref:System.Windows.Media.TileBrush> tiene tres componentes principales: contenido, mosaicos y el área de salida.  
  
 ![Componentes de TileBrush](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
Componentes de TileBrush con un solo mosaico  
  
 ![Componentes de TileBrush en mosaico](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
Componentes de TileBrush con varios mosaicos  
  
 Para obtener más información sobre las características de <xref:System.Windows.Media.TileBrush> mosaico de los objetos, vea [información general sobre TileBrush](tilebrush-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [Información general sobre objetos TileBrush](tilebrush-overview.md)
- [Información general sobre pinceles de WPF](wpf-brushes-overview.md)
- [Información general sobre imágenes](imaging-overview.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre las máscaras de opacidad](opacity-masks-overview.md)
- [Información general sobre la representación de gráficos en WPF](wpf-graphics-rendering-overview.md)
- [Ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Ejemplo de VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
