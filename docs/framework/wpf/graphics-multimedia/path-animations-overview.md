---
title: "Informaci&#243;n general sobre animaciones en trazados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, las rutas de acceso"
  - "animaciones de trayectoria"
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general sobre animaciones en trazados
<a name="introduction"></a>Este tema presenta las animaciones de trazado, que le permiten usar un trazado geométrico para generar valores de salida. Las animaciones de trazado son útiles para mover y girar objetos a lo largo de las rutas de acceso complejas.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características de animaciones. Para obtener una introducción a las características de animación, consulte el [Introducción a la animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Debido a que usa un <xref:System.Windows.Media.PathGeometry> objeto para definir una animación de trazado, también debe estar familiarizado con <xref:System.Windows.Media.PathGeometry> y los diferentes tipos de <xref:System.Windows.Media.PathSegment> objetos. Para obtener más información, consulte el [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>¿Qué es una animación de trazado?  
 Una animación de trazado es un tipo de <xref:System.Windows.Media.Animation.AnimationTimeline> que usa un <xref:System.Windows.Media.PathGeometry> como entrada. En lugar de establecer un desde a, o por propiedad (como lo haría para un From/To/By animación) o mediante fotogramas clave (tal como se utiliza para una animación de fotogramas clave), define un trazado geométrico y usarlo para definir la `PathGeometry` propiedad de la animación de trazado. Progreso de la animación de ruta de acceso, lee el x, y y la información de ángulo de la ruta de acceso y utiliza esa información para generar sus resultados.  
  
 Las animaciones de trazado son muy útiles para animar un objeto a lo largo de una trayectoria compleja. Una manera de mover un objeto a lo largo de una ruta de acceso es usar un <xref:System.Windows.Media.MatrixTransform> y un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> para transformar un objeto a lo largo de una trayectoria compleja. En el ejemplo siguiente se muestra esta técnica mediante el uso de la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que desea animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform>. El <xref:System.Windows.Media.MatrixTransform> se aplica a un botón y hace que se mueva a lo largo de un trazado curvo. Dado que la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad se establece en `true`, el rectángulo se gira en la tangente de la ruta de acceso.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Para obtener más información acerca de la sintaxis de ruta de acceso que se utiliza en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ejemplo, consulte el [sintaxis de marcado de la ruta de acceso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) información general. Para obtener un ejemplo completo, vea [ejemplo Path Animation](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Puede aplicar una animación de trazado a una propiedad mediante un <xref:System.Windows.Media.Animation.Storyboard> en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y el código o mediante el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en código. También puede usar una animación de trazado para crear un <xref:System.Windows.Media.Animation.AnimationClock> y aplicarlo a una o más propiedades. Para obtener más información sobre los distintos métodos para aplicar animaciones, consulte [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Tipos de animación de trazado  
 Dado que animaciones generan valores de propiedad, existen distintos tipos de animaciones para distintos tipos de propiedades. Para animar una propiedad que acepta un <xref:System.Double> (como el <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de un <xref:System.Windows.Media.TranslateTransform>), se usa una animación que genera <xref:System.Double> valores. Para animar una propiedad que acepta un <xref:System.Windows.Point>, se usa una animación que genera <xref:System.Windows.Point> valores y así sucesivamente.  
  
 Clases de animación de trazado pertenecen a la <xref:System.Windows.Media.Animation> espacio de nombres y utilizan la convención de nomenclatura siguiente:  
  
 *<>\>*`AnimationUsingPath`  
  
 Donde * <> \> * es el tipo de valor que anima la clase.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Proporciona clases de animación de la siguiente ruta de acceso.  
  
|Tipo de propiedad|Clase de animación de trazado correspondiente|Ejemplo|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Animar un objeto a lo largo de un trazado (animación doble)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animar un objeto a lo largo de un trazado (animación en matriz)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animar un objeto a lo largo de un trazado (animación en punto)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> genera <xref:System.Windows.Media.Matrix> los valores de sus <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. Cuando se usa con un <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> puede mover un objeto a lo largo de una ruta de acceso. Si establece la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> propiedad de la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> a `true`, también gira el objeto a lo largo de las curvas de la ruta de acceso.  
  
 Un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> genera <xref:System.Windows.Point> valores de las coordenadas x e y-de su <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Mediante el uso de un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar una propiedad que acepta <xref:System.Windows.Point> valores, puede mover un objeto a lo largo de una ruta de acceso. Un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> no se puede girar objetos.  
  
 Un <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> genera <xref:System.Double> los valores de sus <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Estableciendo la <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> propiedad, puede especificar si el <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> usa la coordenada x, la coordenada y o el ángulo de la ruta de acceso como salida. Puede usar un <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> para girar un objeto o moverlo a lo largo del eje x o el eje y.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Entrada de animación de trazado  
 Cada clase de animación de trazado proporciona una <xref:System.Windows.Media.PathGeometry> propiedad para especificar su entrada. La animación de trazado usa el <xref:System.Windows.Media.PathGeometry> para generar sus valores de salida. El <xref:System.Windows.Media.PathGeometry> clase le permite describir varias figuras complejas que se componen de líneas, arcos y curvas.  
  
 En el corazón de un <xref:System.Windows.Media.PathGeometry> es una colección de <xref:System.Windows.Media.PathFigure> objetos; estos objetos se denominan así porque cada figura describe una forma discreta en el <xref:System.Windows.Media.PathGeometry>. Cada <xref:System.Windows.Media.PathFigure> consta de uno o más <xref:System.Windows.Media.PathSegment> objetos, cada uno de los cuales describe un segmento de la figura.  
  
 Hay muchos tipos de segmentos.  
  
|Tipo de segmento|Descripción|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco elíptico entre dos puntos.|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva Bézier cúbica entre dos puntos.|  
|<xref:System.Windows.Media.LineSegment>|Crea una línea entre dos puntos.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie de curvas Bézier cúbicas.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie de líneas.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie de curvas Bézier cuadráticas.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva Bézier cuadrática.|  
  
 Los segmentos en una <xref:System.Windows.Media.PathFigure> se combinan en una sola forma geométrica que usa el punto final de un segmento como el punto inicial del segmento siguiente. El <xref:System.Windows.Media.PathFigure.StartPoint%2A> propiedad de un <xref:System.Windows.Media.PathFigure> especifica el punto desde el que se dibuja el primer segmento. Cada segmento posterior comienza en el punto final del segmento anterior. Por ejemplo, una línea vertical de `10,50` a `10,150` puede definirse estableciendo el <xref:System.Windows.Media.PathFigure.StartPoint%2A> propiedad `10,50` y la creación de un <xref:System.Windows.Media.LineSegment> con una <xref:System.Windows.Media.LineSegment.Point%2A> valor de propiedad `10,150`.  
  
 Para obtener más información acerca de <xref:System.Windows.Media.PathGeometry> los objetos, vea la [información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede usar una sintaxis abreviada especial para establecer el <xref:System.Windows.Media.PathGeometry.Figures%2A> propiedad de un <xref:System.Windows.Media.PathGeometry>. Para obtener más información, consulte [sintaxis de marcado de la ruta de acceso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) información general.  
  
 Para obtener más información acerca de la sintaxis de ruta de acceso que se utiliza en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ejemplo, consulte el [sintaxis de marcado de la ruta de acceso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) información general.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de animación de trazado](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Sintaxis de marcado de la ruta de acceso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)   
 [Información general de animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general de las técnicas de animación de propiedad](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)