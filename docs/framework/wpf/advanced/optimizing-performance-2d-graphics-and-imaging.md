---
title: "Optimizar el rendimiento: Im&#225;genes y gr&#225;ficos 2D | Microsoft Docs"
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
  - "gráficos 2D"
  - "dibujar, optimizar el rendimiento"
  - "gráficos, rendimiento"
  - "imágenes, optimizar el rendimiento"
  - "imágenes, optimizar el rendimiento"
  - "formas, optimizar el rendimiento"
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Optimizar el rendimiento: Im&#225;genes y gr&#225;ficos 2D
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una gama amplia de gráficos 2D y funcionalidad de creación de imágenes que se pueden optimizar para los requisitos de la aplicación.  En este tema se proporciona información sobre la optimización del rendimiento en esas áreas.  
  
   
  
<a name="Drawing_and_Shapes"></a>   
## Dibujos y formas  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona objetos <xref:System.Windows.Media.Drawing> y <xref:System.Windows.Shapes.Shape> para representar el contenido de los dibujos gráficos.  Sin embargo, los objetos <xref:System.Windows.Media.Drawing> son estructuras más sencillas que los objetos <xref:System.Windows.Shapes.Shape> y proporcionan mejores características de rendimiento.  
  
 Un objeto <xref:System.Windows.Shapes.Shape> permite dibujar una forma gráfica en la pantalla.  Dado que se derivan de la clase <xref:System.Windows.FrameworkElement>, los objetos <xref:System.Windows.Shapes.Shape> se pueden utilizar dentro de los paneles y de la mayoría de los controles.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ofrece varias capas de acceso a los gráficos y a los servicios de representación.  En la capa superior, los objetos <xref:System.Windows.Shapes.Shape> son fáciles de utilizar y proporcionan numerosas características útiles, tales como la administración del diseño y el control de eventos.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varios objetos de forma listos para usar.  Todos los objetos de formas heredan de la clase <xref:System.Windows.Shapes.Shape>.  Los objetos de formas disponibles incluyen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> y <xref:System.Windows.Shapes.Rectangle>.  
  
 Por otro lado, los objetos <xref:System.Windows.Media.Drawing> no se derivan de la clase <xref:System.Windows.FrameworkElement> y proporcionan una implementación más ligera para representar formas, imágenes y texto.  
  
 Hay cuatro tipos de objetos <xref:System.Windows.Media.Drawing>:  
  
-   <xref:System.Windows.Media.GeometryDrawing> dibuja una forma.  
  
-   <xref:System.Windows.Media.ImageDrawing> dibuja una imagen.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> dibuja texto.  
  
-   <xref:System.Windows.Media.DrawingGroup> dibuja otros dibujos.  Utilice un grupo de dibujo para combinar otros dibujos en un único dibujo compuesto.  
  
 El objeto <xref:System.Windows.Media.GeometryDrawing> se utiliza para representar contenido de geometría.  La clase <xref:System.Windows.Media.Geometry> y las clases concretas que se derivan de ella, tales como <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Media.PathGeometry>, proporcionan un medio para representar gráficos 2D, además de compatibilidad con las pruebas de posicionamiento y el recorte.  Los objetos de geometría se pueden utilizar para definir la región de un control, por ejemplo, o definir la región de recorte que se aplicará a una imagen.  Los objetos de geometría pueden ser regiones simples, tales como rectángulos y círculos, o bien regiones compuestas creadas a partir de dos o más objetos de geometría.  Las regiones de geometría más complejas se pueden crear combinando objetos derivados de <xref:System.Windows.Media.PathSegment>, como <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment> y <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 Aparentemente, la clase <xref:System.Windows.Media.Geometry> y la clase <xref:System.Windows.Shapes.Shape> son bastante similares.  Ambas se utilizan para representar gráficos 2D y tienen clases concretas similares que se derivan de ellas, por ejemplo, <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Shapes.Ellipse>.  Sin embargo, existen diferencias importantes entre estos dos conjuntos de clases.  En primer lugar, la clase <xref:System.Windows.Media.Geometry> carece de parte de la funcionalidad de la clase <xref:System.Windows.Shapes.Shape>, como la capacidad de dibujarse a sí misma.  Para dibujar un objeto de geometría, deberá utilizarse otra clase, del tipo de DrawingContext, Drawing o Path \(cabe destacar que Path es una forma\) para realizar la operación de dibujo.  Las propiedades de representación, tales como el relleno, el trazo y el grosor del trazo pertenecen a la clase que dibuja el objeto de geometría, mientras que un objeto de forma contiene estas propiedades.  Podemos pensar en esta diferencia de la siguiente manera: un objeto de geometría define una región, un círculo por ejemplo, mientras que un objeto de forma define una región, define cómo se rellena y perfila esa región, y participa en el sistema de diseño.  
  
 Puesto que los objetos <xref:System.Windows.Shapes.Shape> se derivan de la clase <xref:System.Windows.FrameworkElement>, utilizarlos puede aumentar significativamente el consumo de memoria de la aplicación.  Si realmente no necesita las características de <xref:System.Windows.FrameworkElement> para el contenido gráfico, es conveniente utilizar los objetos <xref:System.Windows.Media.Drawing>, más ligeros.  
  
 Para obtener más información sobre los objetos <xref:System.Windows.Media.Drawing>, consulte [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## Objetos StreamGeometry  
 El objeto <xref:System.Windows.Media.StreamGeometry> constituye una alternativa ligera a <xref:System.Windows.Media.PathGeometry> para crear formas geométricas.  Utilice un objeto <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja.  <xref:System.Windows.Media.StreamGeometry> está optimizada para administrar muchos objetos <xref:System.Windows.Media.PathGeometry> y registra un rendimiento mejor que cuando se utilizan varios objetos <xref:System.Windows.Media.PathGeometry> individuales.  
  
 En el ejemplo siguiente se utiliza la sintaxis de atributo para crear una <xref:System.Windows.Media.StreamGeometry> triangular en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener más información sobre los objetos <xref:System.Windows.Media.StreamGeometry>, consulte [Crear una forma utilizando StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## Objetos DrawingVisual  
 El objeto <xref:System.Windows.Media.DrawingVisual> es una clase de dibujo ligera que se utiliza para representar formas, imágenes o texto.  Esta clase se considera ligera porque no proporciona administración del diseño ni control de eventos, lo que mejora su rendimiento.  Por esta razón, los dibujos son idóneos para fondos e imágenes prediseñadas.  Para obtener más información, consulte [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## Imágenes  
 La creación de imágenes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una mejora significativa con respecto a las funciones de creación de imágenes de las versiones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  Las funciones de creación de imágenes, tales como la presentación de mapas de bits o el uso de imágenes en controles comunes, se administraban principalmente por las interfaces de programación de aplicaciones \(API\) de la interfaz de dispositivo gráfico \(GDI\) o de la GDI\+ de Microsoft Windows.  Estas API proporcionaban la funcionalidad de línea base para la creación de imágenes, pero carecían de características tales como compatibilidad con la extensibilidad de códec y con imágenes de alta fidelidad.  La API de creación de imágenes de WPF se ha rediseñado para superar las limitaciones de GDI y GDI\+ y proporcionar un nuevo conjunto de API para mostrar y utilizar imágenes en las aplicaciones.  
  
 Al utilizar imágenes, tenga en cuenta las recomendaciones siguientes para obtener el mejor rendimiento:  
  
-   Si su aplicación le exige que muestre imágenes en miniatura, puede ser conveniente crear una versión de dimensiones reducidas de la imagen.  De manera predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carga la imagen y la descodifica a su tamaño completo.  Si sólo desea una versión en miniatura de la imagen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] descodifica innecesariamente la imagen a su tamaño completo y, a continuación, la reduce a la escala en miniatura.  Para evitar este consumo de recursos innecesario, puede solicitar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que descodifique la imagen a un tamaño en miniatura o bien solicitar a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que cargue una imagen en miniatura.  
  
-   Siempre descodifique la imagen al tamaño deseado y no al tamaño predeterminado.  Como hemos explicado anteriormente, solicite a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que descodifique la imagen al tamaño deseado y no al tamaño completo predeterminado.  De este modo, no sólo mejorará el espacio de trabajo de la aplicación, sino también la velocidad de ejecución.  
  
-   Si es posible, combine las imágenes en una imagen única, como una tira cinematográfica creada de varias imágenes.  
  
-   Para obtener más información, consulte [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).  
  
### BitmapScalingMode  
 Al animar la escala de un mapa de bits, el algoritmo de remuestreo predeterminado de las imágenes de alta calidad, a veces, puede consumir tantos recursos del sistema que cause la degradación de la velocidad de los fotogramas, lo que provoca el parpadeo de las animaciones.  Si establece el valor de la propiedad <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> del objeto <xref:System.Windows.Media.RenderOptions> en <xref:System.Windows.Media.BitmapScalingMode>, podrá crear una animación más suavizada al escalar un mapa de bits.  El modo <xref:System.Windows.Media.BitmapScalingMode> indica al motor de representación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que cambie de un algoritmo optimizado para la calidad a un algoritmo optimizado para la velocidad al procesar las imágenes.  
  
 En el siguiente ejemplo se muestra cómo establecer el valor de <xref:System.Windows.Media.BitmapScalingMode> para un objeto de imagen.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### CachingHint  
 De manera predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] no almacena en memoria caché el contenido representado de los objetos <xref:System.Windows.Media.TileBrush>, como <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>.  En escenarios estáticos donde no cambia el contenido ni el uso de <xref:System.Windows.Media.TileBrush> en la escena, esto tiene sentido dado que conserva la memoria de vídeo.  No tiene tanto sentido cuando se usa un objeto <xref:System.Windows.Media.TileBrush> con contenido estático de forma no estática; por ejemplo, cuando se asigna un objeto <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> estático a la superficie de un objeto 3D que gira.  El comportamiento predeterminado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es volver a representar el contenido completo de cada fotograma de <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush>, aunque no cambie el contenido.  
  
 Si se establece el valor de la propiedad <xref:System.Windows.Media.RenderOptions.CachingHint%2A> del objeto <xref:System.Windows.Media.RenderOptions> en <xref:System.Windows.Media.CachingHint>, podrá aumentar el rendimiento utilizando versiones almacenadas en memoria caché de los objetos de pincel en mosaico.  
  
 Los valores de propiedad <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> y <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> son valores de tamaño relativo que determinan cuándo se debe regenerar el objeto <xref:System.Windows.Media.TileBrush> debido a cambios en la escala.  Por ejemplo, si establece el valor de la propiedad <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> en 2.0, la memoria caché del objeto <xref:System.Windows.Media.TileBrush> sólo necesita regenerarse cuando su tamaño supere el doble del tamaño de la caché actual.  
  
 En el ejemplo siguiente se muestra cómo utilizar la opción de sugerencia de almacenamiento en caché para <xref:System.Windows.Media.DrawingBrush>.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [Sugerencias y trucos para animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)