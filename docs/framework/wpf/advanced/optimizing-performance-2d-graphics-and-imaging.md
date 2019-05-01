---
title: 'Optimizar el rendimiento: Imágenes y gráficos 2D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2-D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: 4fca9231872a268470c9bcfa73e7a0c0a26d300c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61981947"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimizar el rendimiento: Imágenes y gráficos 2D
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una amplia gama de gráficos 2D y funcionalidad de creación de imágenes que se puede optimizar para los requisitos de la aplicación. Este tema proporciona información acerca de la optimización del rendimiento en esas áreas.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Dibujo y formas  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona ambos <xref:System.Windows.Media.Drawing> y <xref:System.Windows.Shapes.Shape> objetos para representar el contenido de dibujo gráfico. Sin embargo, <xref:System.Windows.Media.Drawing> objetos son construcciones más sencillas que <xref:System.Windows.Shapes.Shape> objetos y proporcionan mejores características de rendimiento.  
  
 Un <xref:System.Windows.Shapes.Shape> permite dibujar una forma gráfica en la pantalla. Dado que se derivan los <xref:System.Windows.FrameworkElement> (clase), <xref:System.Windows.Shapes.Shape> objetos pueden usarse dentro de paneles y la mayoría de los controles.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece varias capas de acceso a gráficos y servicios de representación. En la capa superior, <xref:System.Windows.Shapes.Shape> objetos son fáciles de usar y proporcionan numerosas características útiles, como diseño y control de eventos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un número de objetos de forma listos para usar. Todos los objetos de forma que se heredan de la <xref:System.Windows.Shapes.Shape> clase. Objetos de forma disponibles incluyen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, y <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing> objetos, por otro lado, no se derivan de la <xref:System.Windows.FrameworkElement> clase y proporcionar una implementación más ligera para representar formas, imágenes y texto.  
  
 Hay cuatro tipos de <xref:System.Windows.Media.Drawing> objetos:  
  
- <xref:System.Windows.Media.GeometryDrawing> Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing> Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> Dibuja texto.  
  
- <xref:System.Windows.Media.DrawingGroup> Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 La <xref:System.Windows.Media.GeometryDrawing> objeto se usa para representar contenido geométrico. El <xref:System.Windows.Media.Geometry> clase y las clases concretas que derivan de ella, como <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry>, y <xref:System.Windows.Media.PathGeometry>, proporcionan un medio para representar gráficos 2D, además de proporcionar soporte técnico de recorte y la prueba de posicionamiento. Los objetos geométricos se pueden usar para definir la región de un control, por ejemplo, o para definir la región de recorte que se aplicará a una imagen. Los objetos geométricos pueden ser regiones simples, como rectángulos y círculos, o regiones compuestas creadas a partir de dos o más objetos geométricos. Se pueden crear regiones geométricas más complejas mediante la combinación <xref:System.Windows.Media.PathSegment>-derivadas de los objetos, como <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment>, y <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 En la superficie, el <xref:System.Windows.Media.Geometry> clase y el <xref:System.Windows.Shapes.Shape> clase son bastante parecidas. Ambos se usan en la representación de gráficos 2D y ambos tienen clases concretas parecidas que derivan de ellos, por ejemplo, <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Shapes.Ellipse>. Sin embargo, hay diferencias importantes entre estos dos conjuntos de clases. En primer lugar, el <xref:System.Windows.Media.Geometry> clase carece de algunas de las funcionalidades de la <xref:System.Windows.Shapes.Shape> (clase), como la capacidad para dibujarse a sí mismo. Para dibujar un objeto geométrico, debe usarse otra clase, como la clase DrawingContext, la clase de dibujo o de trazado (merece la pena indicar que un trazado es una forma) para realizar la operación de dibujo. Las propiedades de representación como relleno, trazo y grosor del trazo, se encuentran en la clase que dibuja el objeto geométrico, mientras que un objeto de forma contiene estas propiedades. Una manera de acordarse de esta diferencia es que un objeto geométrico define una región, como un círculo, mientras que un objeto de forma define una región, define cómo es el relleno y el contorno de esa región y participa en el sistema de diseño.  
  
 Puesto que <xref:System.Windows.Shapes.Shape> objetos se derivan de la <xref:System.Windows.FrameworkElement> (clase), su uso puede agregar más considerablemente el consumo de memoria en la aplicación. Si no necesita realmente el <xref:System.Windows.FrameworkElement> características para el contenido gráfico, considere el uso de la ligero <xref:System.Windows.Media.Drawing> objetos.  
  
 Para obtener más información sobre <xref:System.Windows.Media.Drawing> objetos, vea [información general sobre objetos de dibujo](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>Objetos StreamGeometry  
 El <xref:System.Windows.Media.StreamGeometry> objeto es una alternativa ligera a <xref:System.Windows.Media.PathGeometry> para crear formas geométricas. Use un <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja. <xref:System.Windows.Media.StreamGeometry> está optimizado para controlar muchos <xref:System.Windows.Media.PathGeometry> objetos y funciona mejor cuando se usan muchos individuales <xref:System.Windows.Media.PathGeometry> objetos.  
  
 En el ejemplo siguiente se usa la sintaxis de atributo para crear un triangular <xref:System.Windows.Media.StreamGeometry> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener más información sobre <xref:System.Windows.Media.StreamGeometry> objetos, vea [crear una forma utilizando StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>Objetos DrawingVisual  
 La <xref:System.Windows.Media.DrawingVisual> objeto es una ligera dibujo de la clase que se usa para representar formas, imágenes o texto. Esta clase se considera ligera porque no proporciona control de diseño ni control de eventos, lo que mejora su rendimiento. Por esta razón, los dibujos son ideales para fondos e imágenes prediseñadas. Para obtener más información, consulte [Usar objetos DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Imágenes  
 La creación de imágenes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece una mejora considerable sobre las capacidades de creación de imágenes en versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Las funciones de creación de imágenes, como mostrar un mapa de bits o usar una imagen en un control común, se administraban principalmente mediante la Interfaz de dispositivo gráfico de Microsoft Windows (GDI) o la interfaz de programación de aplicaciones (API) de Windows GDI+. Estas API proporcionan funciones de creación de imágenes de línea base, pero carecían de algunas características, como la compatibilidad con la extensibilidad de códec y con imágenes de alta fidelidad. WPF Imaging API se rediseñó para superar las limitaciones de GDI y GDI+ y proporcionar un nuevo conjunto de API para mostrar y usar imágenes en las aplicaciones.  
  
 Al usar imágenes, tenga en cuenta las siguientes recomendaciones para obtener un mejor rendimiento:  
  
- Si su aplicación necesita mostrar imágenes en miniatura, considere la posibilidad de crear una versión en tamaño reducido de la imagen. De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carga la imagen y la descodifica a su tamaño completo. Si solo quiere una versión en miniatura de la imagen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifica innecesariamente la imagen en su tamaño completo y, a continuación, la escala a un tamaño de miniatura. Para evitar esta sobrecarga innecesaria, puede solicitar que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifique la imagen en un tamaño de miniatura o que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cargue una imagen en miniatura.  
  
- Descodifique siempre la imagen en el tamaño deseado y no en el tamaño predeterminado. Como se mencionó anteriormente, solicite que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifique la imagen en el tamaño deseado y no en el tamaño completo predeterminado. No solo reducirá el espacio de trabajo de la aplicación, sino también la velocidad de ejecución.  
  
- Si es posible, combine las imágenes en una sola imagen, como una tira de película compuesta de varias imágenes.  
  
- Para obtener más información, consulte [Información general sobre imágenes](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Al animar la escala de un mapa de bits, el algoritmo para volver a muestrear la imagen de alta calidad predeterminada puede consumir suficientes recursos del sistema para que se produzca una degradación de la velocidad de fotogramas, lo que causa que las animaciones parpadeen. Estableciendo el <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> propiedad de la <xref:System.Windows.Media.RenderOptions> objeto <xref:System.Windows.Media.BitmapScalingMode.LowQuality> puede crear una animación más fluida al escalar un mapa de bits. <xref:System.Windows.Media.BitmapScalingMode.LowQuality> indica el modo el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motor de representación para cambiar de un algoritmo optimizado de calidad a un algoritmo optimizado de velocidad al procesar las imágenes.  
  
 El ejemplo siguiente muestra cómo establecer el <xref:System.Windows.Media.BitmapScalingMode> para un objeto de imagen.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no almacena en caché el contenido representado de <xref:System.Windows.Media.TileBrush> objetos, como <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>. En escenarios estáticos donde ni el contenido ni el uso de la <xref:System.Windows.Media.TileBrush> en la escena está cambiando, esto tiene sentido, ya que ahorra memoria de vídeo. No se realiza como mucho sentido cuando un <xref:System.Windows.Media.TileBrush> con contenido estático se usa en un modo no estático, por ejemplo, cuando una variable static <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> se asigna a la superficie de un objeto 3D giratorio. El comportamiento predeterminado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es volver a representar todo el contenido de la <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> para cada fotograma, aun cuando el contenido es invariable.  
  
 Estableciendo el <xref:System.Windows.Media.RenderOptions.CachingHint%2A> propiedad de la <xref:System.Windows.Media.RenderOptions> objeto <xref:System.Windows.Media.CachingHint.Cache> puede aumentar el rendimiento mediante el uso de versiones en caché de los objetos de pincel en mosaico.  
  
 El <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> y <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> los valores de propiedad son valores de tamaño relativos que determinan cuándo el <xref:System.Windows.Media.TileBrush> objeto debe volver a generarse debido a cambios en la escala. Por ejemplo, estableciendo el <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> propiedad a 2.0, la memoria caché para el <xref:System.Windows.Media.TileBrush> solo necesita regenerarse cuando su tamaño supera el doble del tamaño de la memoria caché actual.  
  
 El ejemplo siguiente muestra cómo usar la opción de sugerencia de almacenamiento en caché para un <xref:System.Windows.Media.DrawingBrush>.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Vea también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de la aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
- [Sugerencias y trucos para animaciones](../graphics-multimedia/animation-tips-and-tricks.md)
