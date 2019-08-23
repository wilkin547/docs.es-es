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
ms.openlocfilehash: 764e7e802ccaff50b76229b9441380bfe77fefb5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933345"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Optimizar el rendimiento: Imágenes y gráficos 2D
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una amplia gama de gráficos 2D y funcionalidad de creación de imágenes que se puede optimizar para los requisitos de la aplicación. Este tema proporciona información acerca de la optimización del rendimiento en esas áreas.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Dibujo y formas  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona los <xref:System.Windows.Media.Drawing> objetos <xref:System.Windows.Shapes.Shape> y para representar el contenido de dibujo gráfico. Sin embargo <xref:System.Windows.Media.Drawing> , los objetos son construcciones más sencillas <xref:System.Windows.Shapes.Shape> que los objetos y proporcionan mejores características de rendimiento.  
  
 <xref:System.Windows.Shapes.Shape> Permite dibujar una forma gráfica en la pantalla. Dado que se derivan de <xref:System.Windows.FrameworkElement> la clase <xref:System.Windows.Shapes.Shape> , los objetos se pueden usar dentro de los paneles y la mayoría de los controles.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece varias capas de acceso a gráficos y servicios de representación. En la capa superior, <xref:System.Windows.Shapes.Shape> los objetos son fáciles de usar y proporcionan muchas características útiles, como el diseño y el control de eventos. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un número de objetos de forma listos para usar. Todos los objetos de forma se <xref:System.Windows.Shapes.Shape> heredan de la clase. Los objetos de forma <xref:System.Windows.Shapes.Ellipse>disponibles <xref:System.Windows.Shapes.Line>incluyen <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>,, <xref:System.Windows.Shapes.Rectangle>y.  
  
 <xref:System.Windows.Media.Drawing>por otro lado, los objetos no se derivan de la <xref:System.Windows.FrameworkElement> clase y proporcionan una implementación más ligera para representar formas, imágenes y texto.  
  
 Hay cuatro tipos de <xref:System.Windows.Media.Drawing> objetos:  
  
- <xref:System.Windows.Media.GeometryDrawing>Dibuja una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>Dibuja una imagen.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Dibuja texto.  
  
- <xref:System.Windows.Media.DrawingGroup>Dibuja otros dibujos. Use un grupo de dibujo para combinar otros dibujos en un solo dibujo compuesto.  
  
 El <xref:System.Windows.Media.GeometryDrawing> objeto se utiliza para representar el contenido de la geometría. La <xref:System.Windows.Media.Geometry> clase y las clases concretas que derivan de ella, <xref:System.Windows.Media.CombinedGeometry>como, <xref:System.Windows.Media.EllipseGeometry>y <xref:System.Windows.Media.PathGeometry>, proporcionan un medio para representar gráficos 2D, así como para proporcionar compatibilidad con la prueba de posicionamiento y el recorte. Los objetos geométricos se pueden usar para definir la región de un control, por ejemplo, o para definir la región de recorte que se aplicará a una imagen. Los objetos geométricos pueden ser regiones simples, como rectángulos y círculos, o regiones compuestas creadas a partir de dos o más objetos geométricos. Las regiones geométricas más complejas se pueden <xref:System.Windows.Media.PathSegment>crear mediante la combinación de objetos <xref:System.Windows.Media.ArcSegment>derivados <xref:System.Windows.Media.BezierSegment>de, <xref:System.Windows.Media.QuadraticBezierSegment>como, y.  
  
 En la superficie, la <xref:System.Windows.Media.Geometry> clase y la <xref:System.Windows.Shapes.Shape> clase son bastante similares. Ambos se usan en la representación de gráficos 2D y ambos tienen clases concretas similares que derivan de ellos, por ejemplo, <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Shapes.Ellipse>. Sin embargo, hay diferencias importantes entre estos dos conjuntos de clases. En el caso de <xref:System.Windows.Media.Geometry> una, la clase carece de algunas de las <xref:System.Windows.Shapes.Shape> funciones de la clase, como la capacidad de dibujarse a sí misma. Para dibujar un objeto geométrico, debe usarse otra clase, como la clase DrawingContext, la clase de dibujo o de trazado (merece la pena indicar que un trazado es una forma) para realizar la operación de dibujo. Las propiedades de representación como relleno, trazo y grosor del trazo, se encuentran en la clase que dibuja el objeto geométrico, mientras que un objeto de forma contiene estas propiedades. Una manera de acordarse de esta diferencia es que un objeto geométrico define una región, como un círculo, mientras que un objeto de forma define una región, define cómo es el relleno y el contorno de esa región y participa en el sistema de diseño.  
  
 Puesto <xref:System.Windows.Shapes.Shape> que los objetos se <xref:System.Windows.FrameworkElement> derivan de la clase, utilizarlos puede Agregar significativamente más consumo de memoria en la aplicación. Si realmente no necesita las <xref:System.Windows.FrameworkElement> características para el contenido gráfico, considere la posibilidad de usar los objetos de peso <xref:System.Windows.Media.Drawing> más ligero.  
  
 Para obtener más información <xref:System.Windows.Media.Drawing> sobre los objetos, vea [información general sobre objetos Drawing](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>Objetos StreamGeometry  
 El <xref:System.Windows.Media.StreamGeometry> objeto es una alternativa ligera a <xref:System.Windows.Media.PathGeometry> para crear formas geométricas. <xref:System.Windows.Media.StreamGeometry> Use cuando necesite describir una geometría compleja. <xref:System.Windows.Media.StreamGeometry>está optimizado para controlar <xref:System.Windows.Media.PathGeometry> muchos objetos y funciona mejor cuando se compara con el <xref:System.Windows.Media.PathGeometry> uso de muchos objetos individuales.  
  
 En el ejemplo siguiente se usa la sintaxis de atributo para <xref:System.Windows.Media.StreamGeometry> crear [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]un triangular en.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener más información <xref:System.Windows.Media.StreamGeometry> sobre los objetos, vea [crear una forma mediante StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>Objetos DrawingVisual  
 El <xref:System.Windows.Media.DrawingVisual> objeto es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto. Esta clase se considera ligera porque no proporciona control de diseño ni control de eventos, lo que mejora su rendimiento. Por esta razón, los dibujos son ideales para fondos e imágenes prediseñadas. Para obtener más información, consulte [Usar objetos DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Imágenes  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]la creación de imágenes proporciona una mejora significativa con respecto a las capacidades de creación de imágenes en versiones anteriores de Windows. Las funciones de creación de imágenes, como mostrar un mapa de bits o usar una imagen en un control común, se administraban principalmente mediante la Interfaz de dispositivo gráfico de Microsoft Windows (GDI) o la interfaz de programación de aplicaciones (API) de Windows GDI+. Estas API proporcionan funciones de creación de imágenes de línea base, pero carecían de algunas características, como la compatibilidad con la extensibilidad de códec y con imágenes de alta fidelidad. WPF Imaging API se rediseñó para superar las limitaciones de GDI y GDI+ y proporcionar un nuevo conjunto de API para mostrar y usar imágenes en las aplicaciones.  
  
 Al usar imágenes, tenga en cuenta las siguientes recomendaciones para obtener un mejor rendimiento:  
  
- Si su aplicación necesita mostrar imágenes en miniatura, considere la posibilidad de crear una versión en tamaño reducido de la imagen. De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carga la imagen y la descodifica a su tamaño completo. Si solo quiere una versión en miniatura de la imagen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifica innecesariamente la imagen en su tamaño completo y, a continuación, la escala a un tamaño de miniatura. Para evitar esta sobrecarga innecesaria, puede solicitar que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifique la imagen en un tamaño de miniatura o que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cargue una imagen en miniatura.  
  
- Descodifique siempre la imagen en el tamaño deseado y no en el tamaño predeterminado. Como se mencionó anteriormente, solicite que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifique la imagen en el tamaño deseado y no en el tamaño completo predeterminado. No solo reducirá el espacio de trabajo de la aplicación, sino también la velocidad de ejecución.  
  
- Si es posible, combine las imágenes en una sola imagen, como una tira de película compuesta de varias imágenes.  
  
- Para obtener más información, consulte [Información general sobre imágenes](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Al animar la escala de un mapa de bits, el algoritmo para volver a muestrear la imagen de alta calidad predeterminada puede consumir suficientes recursos del sistema para que se produzca una degradación de la velocidad de fotogramas, lo que causa que las animaciones parpadeen. Al establecer la <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> propiedad <xref:System.Windows.Media.RenderOptions> del objeto en <xref:System.Windows.Media.BitmapScalingMode.LowQuality> , puede crear una animación más suave al escalar un mapa de bits. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modo indica al motor de representación que cambie de un algoritmo optimizado de calidad a un algoritmo optimizado para velocidad al procesar imágenes.  
  
 En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.Media.BitmapScalingMode> para un objeto de imagen.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 De forma predeterminada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , no almacena en caché el contenido representado <xref:System.Windows.Media.TileBrush> de objetos, <xref:System.Windows.Media.DrawingBrush> como y <xref:System.Windows.Media.VisualBrush>. En escenarios estáticos en los que no está cambiando el <xref:System.Windows.Media.TileBrush> contenido ni el uso de en la escena, esto tiene sentido, ya que conserva la memoria de vídeo. No tiene tantas sentido cuando <xref:System.Windows.Media.TileBrush> se usa un objeto con contenido estático de forma no estática, por ejemplo, cuando se asigna un estático <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> a la superficie de un objeto 3D de rotación. El comportamiento predeterminado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es volver a representar todo el contenido <xref:System.Windows.Media.DrawingBrush> de o <xref:System.Windows.Media.VisualBrush> para cada fotograma, aunque el contenido no cambie.  
  
 Al establecer la <xref:System.Windows.Media.RenderOptions.CachingHint%2A> propiedad <xref:System.Windows.Media.RenderOptions> del objeto en <xref:System.Windows.Media.CachingHint.Cache> , puede aumentar el rendimiento mediante el uso de versiones almacenadas en caché de los objetos de pincel en mosaico.  
  
 Los <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> valores <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> de las propiedades y son valores de tamaño relativo que <xref:System.Windows.Media.TileBrush> determinan cuándo se debe volver a generar el objeto debido a los cambios en la escala. Por ejemplo, al establecer la <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> propiedad en 2,0, la memoria caché <xref:System.Windows.Media.TileBrush> de solo debe volver a generarse cuando su tamaño supera el doble del tamaño de la memoria caché actual.  
  
 En el ejemplo siguiente se muestra cómo utilizar la opción de sugerencia de <xref:System.Windows.Media.DrawingBrush>almacenamiento en caché para un.  
  
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
