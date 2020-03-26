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
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: eb3686367873276587572addda436471cd1abf27
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291804"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimizar el rendimiento: Imágenes y gráficos 2D
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una amplia gama de gráficos 2D y funcionalidad de creación de imágenes que se puede optimizar para los requisitos de la aplicación. Este tema proporciona información acerca de la optimización del rendimiento en esas áreas.  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>Dibujo y formas  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona <xref:System.Windows.Media.Drawing> tanto <xref:System.Windows.Shapes.Shape> como objetos para representar el contenido del dibujo gráfico. Sin <xref:System.Windows.Media.Drawing> embargo, los objetos son construcciones más simples que <xref:System.Windows.Shapes.Shape> los objetos y proporcionan mejores características de rendimiento.  
  
 A <xref:System.Windows.Shapes.Shape> le permite dibujar una forma gráfica en la pantalla. Dado que se derivan <xref:System.Windows.FrameworkElement> de <xref:System.Windows.Shapes.Shape> la clase, los objetos se pueden utilizar dentro de paneles y la mayoría de los controles.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece varias capas de acceso a gráficos y servicios de representación. En la capa <xref:System.Windows.Shapes.Shape> superior, los objetos son fáciles de usar y proporcionan muchas características útiles, como el diseño y el control de eventos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un número de objetos de forma listos para usar. Todos los objetos <xref:System.Windows.Shapes.Shape> shape heredan de la clase. Los objetos <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Line>de <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Polygon>forma <xref:System.Windows.Shapes.Polyline>disponibles incluyen , , , , , y <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing>los objetos, por otro lado, <xref:System.Windows.FrameworkElement> no derivan de la clase y proporcionan una implementación más ligera para representar formas, imágenes y texto.  
  
 Hay cuatro tipos <xref:System.Windows.Media.Drawing> de objetos:  
  
- <xref:System.Windows.Media.GeometryDrawing>Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Dibuja texto.  
  
- <xref:System.Windows.Media.DrawingGroup>Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 El <xref:System.Windows.Media.GeometryDrawing> objeto se utiliza para representar el contenido de geometría. La <xref:System.Windows.Media.Geometry> clase y las clases concretas <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.EllipseGeometry>que <xref:System.Windows.Media.PathGeometry>derivan de ella, como , , y , proporcionan un medio para representar gráficos 2D y proporcionar compatibilidad con pruebas de posicionamiento y recorte. Los objetos geométricos se pueden usar para definir la región de un control, por ejemplo, o para definir la región de recorte que se aplicará a una imagen. Los objetos geométricos pueden ser regiones simples, como rectángulos y círculos, o regiones compuestas creadas a partir de dos o más objetos geométricos. Se pueden crear regiones <xref:System.Windows.Media.PathSegment>geométricas más complejas <xref:System.Windows.Media.ArcSegment> <xref:System.Windows.Media.BezierSegment>combinando <xref:System.Windows.Media.QuadraticBezierSegment>objetos derivados, como , , y .  
  
 En la superficie, <xref:System.Windows.Media.Geometry> la <xref:System.Windows.Shapes.Shape> clase y la clase son similares. Ambos se utilizan en la representación de gráficos 2D y ambos <xref:System.Windows.Media.EllipseGeometry> <xref:System.Windows.Shapes.Ellipse>tienen clases concretas similares que derivan de ellos, por ejemplo, y . Sin embargo, hay diferencias importantes entre estos dos conjuntos de clases. Por un <xref:System.Windows.Media.Geometry> ejemplo, la clase carece de <xref:System.Windows.Shapes.Shape> algunas de las funciones de la clase, como la capacidad de dibujarse a sí misma. Para dibujar un objeto geométrico, debe usarse otra clase, como la clase DrawingContext, la clase de dibujo o de trazado (merece la pena indicar que un trazado es una forma) para realizar la operación de dibujo. Las propiedades de representación, como el relleno, el trazo y el grosor del trazo, se encuentran en la clase que dibuja el objeto de geometría, mientras que un objeto de forma contiene estas propiedades. Una forma de pensar en esta diferencia es que un objeto de geometría define una región, por ejemplo, un círculo, mientras que un objeto de forma define una región, define cómo se rellena y delinea esa región y participa en el sistema de diseño.  
  
 Dado <xref:System.Windows.Shapes.Shape> que los <xref:System.Windows.FrameworkElement> objetos derivan de la clase, su uso puede agregar significativamente más consumo de memoria en la aplicación. Si realmente no necesita <xref:System.Windows.FrameworkElement> las características para su contenido gráfico, considere la posibilidad de utilizar los objetos más ligeros. <xref:System.Windows.Media.Drawing>  
  
 Para obtener <xref:System.Windows.Media.Drawing> más información sobre los objetos, consulte [Información general sobre objetos](../graphics-multimedia/drawing-objects-overview.md)de dibujo .  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>Objetos StreamGeometry  
 El <xref:System.Windows.Media.StreamGeometry> objeto es una <xref:System.Windows.Media.PathGeometry> alternativa ligera a la creación de formas geométricas. Utilice <xref:System.Windows.Media.StreamGeometry> a cuando necesite describir una geometría compleja. <xref:System.Windows.Media.StreamGeometry>está optimizado para <xref:System.Windows.Media.PathGeometry> manejar muchos objetos y funciona <xref:System.Windows.Media.PathGeometry> mejor en comparación con el uso de muchos objetos individuales.  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.StreamGeometry> utiliza [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]la sintaxis de atributo para crear un triangular en .  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener <xref:System.Windows.Media.StreamGeometry> más información sobre los objetos, vea [Crear una forma mediante una StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>Objetos DrawingVisual  
 El <xref:System.Windows.Media.DrawingVisual> objeto es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto. Esta clase se considera ligera porque no proporciona control de diseño ni evento, lo que mejora su rendimiento. Por esta razón, los dibujos son ideales para fondos e imágenes prediseñadas. Para más información, consulte [Usar objetos DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>
## <a name="images"></a>Imágenes  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]imágenes proporciona una mejora significativa con respecto a las capacidades de creación de imágenes en versiones anteriores de Windows. Las capacidades de creación de imágenes, como mostrar un mapa de bits o usar una imagen en un control común, se controlaban principalmente mediante la interfaz de dispositivo de gráficos de Microsoft Windows (GDI) o la interfaz de programación de aplicaciones (API) de Microsoft Windows GDI+. Estas API proporcionaban funcionalidad de creación de imágenes de línea base, pero carecía de características como la compatibilidad con la extensibilidad de códecs y la compatibilidad con imágenes de alta fidelidad. Las API de IMÁGENes de WPFWPF se han rediseñado para superar las deficiencias de GDI y GDI+GDI+C. y proporcionar un nuevo conjunto de API para mostrar y usar imágenes dentro de las aplicaciones.  
  
 Al usar imágenes, tenga en cuenta las siguientes recomendaciones para obtener un mejor rendimiento:  
  
- Si su aplicación necesita mostrar imágenes en miniatura, considere la posibilidad de crear una versión en tamaño reducido de la imagen. De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carga la imagen y la descodifica a su tamaño completo. Si solo quiere una versión en miniatura de la imagen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifica innecesariamente la imagen en su tamaño completo y, a continuación, la escala a un tamaño de miniatura. Para evitar esta sobrecarga innecesaria, puede solicitar que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifique la imagen en un tamaño de miniatura o que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cargue una imagen en miniatura.  
  
- Descodifique siempre la imagen en el tamaño deseado y no en el tamaño predeterminado. Como se mencionó anteriormente, solicite que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifique la imagen en el tamaño deseado y no en el tamaño completo predeterminado. No solo reducirá el espacio de trabajo de la aplicación, sino también la velocidad de ejecución.  
  
- Si es posible, combine las imágenes en una sola imagen, como una tira de película compuesta de varias imágenes.  
  
- Para obtener más información, consulte [Información general sobre imágenes](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Al animar la escala de cualquier mapa de bits, el algoritmo de remuestreo de imagen de alta calidad predeterminado a veces puede consumir suficientes recursos del sistema para provocar la degradación de la velocidad de fotogramas, lo que provoca que las animaciones se tartamudeen. Al establecer <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> la <xref:System.Windows.Media.RenderOptions> propiedad <xref:System.Windows.Media.BitmapScalingMode.LowQuality>del objeto en , puede crear una animación más suave al escalar un mapa de bits. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>el modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] indica al motor de renderizado que cambie de un algoritmo optimizado para la calidad a un algoritmo optimizado para la velocidad al procesar imágenes.  
  
 En el ejemplo siguiente <xref:System.Windows.Media.BitmapScalingMode> se muestra cómo establecer el para un objeto de imagen.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 De forma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminada, no almacena <xref:System.Windows.Media.TileBrush> en caché <xref:System.Windows.Media.DrawingBrush> el <xref:System.Windows.Media.VisualBrush>contenido representado de los objetos, como y . En escenarios estáticos donde el <xref:System.Windows.Media.TileBrush> contenido o el uso de la en la escena no están cambiando, esto tiene sentido, ya que conserva la memoria de vídeo. No tiene tanto sentido cuando <xref:System.Windows.Media.TileBrush> se utiliza un contenido estático de forma no estática, por ejemplo, cuando una estática <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> se asigna a la superficie de un objeto 3D giratorio. El comportamiento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminado de es volver a <xref:System.Windows.Media.DrawingBrush> representar <xref:System.Windows.Media.VisualBrush> todo el contenido del fotograma o para cada fotograma, aunque el contenido no cambie.  
  
 Al establecer <xref:System.Windows.Media.RenderOptions.CachingHint%2A> la <xref:System.Windows.Media.RenderOptions> propiedad <xref:System.Windows.Media.CachingHint.Cache>del objeto en , puede aumentar el rendimiento mediante el uso de versiones almacenadas en caché de los objetos de pincel en mosaico.  
  
 Los <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> valores y los valores de <xref:System.Windows.Media.TileBrush> propiedad son valores de tamaño relativo que determinan cuándo se debe regenerar el objeto debido a cambios en la escala. Por ejemplo, al <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> establecer la propiedad en 2.0, la memoria caché de la <xref:System.Windows.Media.TileBrush> única debe regenerarse cuando su tamaño supera el doble del tamaño de la memoria caché actual.  
  
 En el ejemplo siguiente se muestra cómo <xref:System.Windows.Media.DrawingBrush>utilizar la opción de sugerencia de almacenamiento en caché para un archivo .  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Vea también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
- [Sugerencias y trucos para animaciones](../graphics-multimedia/animation-tips-and-tricks.md)
