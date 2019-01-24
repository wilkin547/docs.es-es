---
title: Información general sobre geometría
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometry classes [WPF]
- graphics [WPF], geometry classes
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
ms.openlocfilehash: 0c30bc99939b7e60e7e36b698776951cc6181497
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532362"
---
# <a name="geometry-overview"></a>Información general sobre geometría
Esta introducción describe cómo usar el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> clases para describir las formas. En este tema también se contrasta las diferencias entre <xref:System.Windows.Media.Geometry> objetos y <xref:System.Windows.Shapes.Shape> elementos.  
  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>¿Qué es una geometría?  
 El <xref:System.Windows.Media.Geometry> clase y las clases que derivan de ella, como <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>, y <xref:System.Windows.Media.CombinedGeometry>, le permiten describir la geometría de una forma 2D. Estas descripciones geométricas tiene muchos usos, como definir una forma para pintarla en la pantalla o definir regiones de recorte y pruebas de posicionamiento. Incluso se puede usar una geometría para definir un trazado de animación.  
  
 <xref:System.Windows.Media.Geometry> objetos pueden ser simples, tales como rectángulos y círculos o compuestos, crean a partir de dos o más objetos geométricos.  Se pueden crear geometrías más complejas mediante el uso de la <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry> clases, que le permiten describir arcos y curvas.  
  
 Dado que un <xref:System.Windows.Media.Geometry> es un tipo de <xref:System.Windows.Freezable>, <xref:System.Windows.Media.Geometry> objetos proporcionan varias características especiales: se pueden declarar como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md)compartida entre varios objetos, de sólo lectura para mejorar el rendimiento, clonar, y hacerse seguros para subprocesos. Para obtener más información sobre las diferentes características proporcionadas por <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Geometrías frente a Formas  
 El <xref:System.Windows.Media.Geometry> y <xref:System.Windows.Shapes.Shape> parecen clases en que las dos describen formas 2D (comparar <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Shapes.Ellipse> por ejemplo), pero hay diferencias importantes.  
  
 En primer lugar, el <xref:System.Windows.Media.Geometry> clase hereda de la <xref:System.Windows.Freezable> clase mientras el <xref:System.Windows.Shapes.Shape> clase hereda de <xref:System.Windows.FrameworkElement>. Dado que son elementos, <xref:System.Windows.Shapes.Shape> objetos pueden representarse a sí mismos y participar en el sistema de diseño, mientras <xref:System.Windows.Media.Geometry> no objetos.  
  
 Aunque <xref:System.Windows.Shapes.Shape> objetos son más fácil de usar que <xref:System.Windows.Media.Geometry> objetos, <xref:System.Windows.Media.Geometry> son más versátiles. Mientras un <xref:System.Windows.Shapes.Shape> objeto se usa para representar gráficos 2D, un <xref:System.Windows.Media.Geometry> objeto puede utilizarse para definir la región geométrica de gráficos 2D, definir una región de recorte o definir una región de la prueba de posicionamiento, por ejemplo.  
  
### <a name="the-path-shape"></a>La forma del trazado  
 Una <xref:System.Windows.Shapes.Shape>, <xref:System.Windows.Shapes.Path> clase utiliza realmente un <xref:System.Windows.Media.Geometry> para describir su contenido. Estableciendo el <xref:System.Windows.Shapes.Path.Data%2A> propiedad de la <xref:System.Windows.Shapes.Path> con un <xref:System.Windows.Media.Geometry> y estableciendo su <xref:System.Windows.Shapes.Shape.Fill%2A> y <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedades, puede representar un <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Propiedades comunes que aceptan un objeto Geometry  
 En las secciones anteriores se menciona que se pueden usar objetos Geometry con otros objetos con diversos fines, como dibujar formas, crear animaciones y efectuar recortes. La tabla siguiente enumeran varias clases que tienen propiedades que toman un <xref:System.Windows.Media.Geometry> objeto.  
  
|Tipo|Property|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Tipos de objeto Geometry simples  
 La clase base para todas las geometrías es la clase abstracta <xref:System.Windows.Media.Geometry>.  Las clases que derivan de la <xref:System.Windows.Media.Geometry> clase puede agruparse aproximadamente en tres categorías: geometrías simples, geometrías de trazado y geometrías compuestas.  
  
 Las clases de geometría simple se incluyen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, y <xref:System.Windows.Media.EllipseGeometry> y se usan para crear formas geométricas básicas, como líneas, rectángulos y círculos.  
  
-   Un <xref:System.Windows.Media.LineGeometry> se define especificando el punto inicial de la línea y el punto final.  
  
-   Un <xref:System.Windows.Media.RectangleGeometry> se define con un <xref:System.Windows.Rect> estructura que especifica su posición relativa y su alto y ancho. Puede crear un rectángulo redondeado estableciendo el <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> propiedades.  
  
-   Un <xref:System.Windows.Media.EllipseGeometry> se define mediante un punto central, un radio x y un radio "y".  En los ejemplos siguientes se muestra cómo crear geometrías simples de representación y recorte.  
  
 Estas mismas formas, así como las formas más complejas, se pueden crear mediante un <xref:System.Windows.Media.PathGeometry> o combinando varios objetos geométricos, pero estas clases proporcionan una manera más sencilla para producir estas formas geométricas básicas.  
  
 El ejemplo siguiente muestra cómo crear y representar un <xref:System.Windows.Media.LineGeometry>.  Como se indicó anteriormente, un <xref:System.Windows.Media.Geometry> objeto no puede dibujarse a sí mismo, por lo que en el ejemplo se usa un <xref:System.Windows.Shapes.Path> forma para representar la línea.  Dado que una línea no tiene área, establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad del <xref:System.Windows.Shapes.Path> tendría ningún efecto; en su lugar, solo el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> se especifican las propiedades. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Objeto LineGeometry dibujado desde (10,20) hasta (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo crear y representar un <xref:System.Windows.Media.EllipseGeometry>.  Los conjuntos de ejemplos del <xref:System.Windows.Media.EllipseGeometry.Center%2A> de la <xref:System.Windows.Media.EllipseGeometry> está establecido en el punto `50,50` y el radio x y el radio y se establecen en `50`, que crea un círculo con un diámetro de 100.  El interior de la elipse se pinta asignando un valor para la propiedad de relleno del elemento de la ruta de acceso, en este caso <xref:System.Windows.Media.Brushes.Gold%2A>. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![Objeto EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Objeto EllipseGeometry dibujado en (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 El ejemplo siguiente muestra cómo crear y representar un <xref:System.Windows.Media.RectangleGeometry>.  La posición y las dimensiones del rectángulo se definen mediante un <xref:System.Windows.Rect> estructura. La posición es `50,50` y el alto y ancho son ambos `25`, lo que crea un cuadrado. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![Una clase RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Objeto RectangleGeometry dibujado en 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 El ejemplo siguiente muestra cómo usar un <xref:System.Windows.Media.EllipseGeometry> como región de recorte de una imagen.  Un <xref:System.Windows.Controls.Image> objeto se define con un <xref:System.Windows.FrameworkElement.Width%2A> de 200 y un <xref:System.Windows.FrameworkElement.Height%2A> de 150.  Un <xref:System.Windows.Media.EllipseGeometry> con un <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> valor de 100, un <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> valor 75 y un <xref:System.Windows.Media.EllipseGeometry.Center%2A> valor de 100,75 se establece en el <xref:System.Windows.UIElement.Clip%2A> propiedad de la imagen.  Solo se mostrará la parte de la imagen que queda dentro del área de la elipse. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![Una imagen con y sin recorte](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Objeto EllipseGeometry usado para recortar un control Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Geometrías de trazado  
 El <xref:System.Windows.Media.PathGeometry> clase y su equivalente ligera, la <xref:System.Windows.Media.StreamGeometry> clase, proporcione los medios para describir varias figuras complejas se componen de arcos, curvas y líneas.  
  
 En el corazón de un <xref:System.Windows.Media.PathGeometry> es una colección de <xref:System.Windows.Media.PathFigure> objetos, denominados así porque cada figura describe una forma discreta del <xref:System.Windows.Media.PathGeometry>. Cada <xref:System.Windows.Media.PathFigure> propio consta de uno o varios <xref:System.Windows.Media.PathSegment> objetos, cada uno de los cuales describe un segmento de la figura.  
  
 Hay muchos tipos de segmentos.  
  
|Tipo de segmento|Descripción|Ejemplo|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco elíptico entre dos puntos.|[Crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva Bézier cúbica entre dos puntos.|[Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una línea entre dos puntos.|[Crear un LineSegment en una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie de curvas Bézier cúbicas.|Consulte la <xref:System.Windows.Media.PolyBezierSegment> página de tipo.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie de líneas.|Consulte la <xref:System.Windows.Media.PolyLineSegment> página de tipo.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie de curvas Bézier cuadráticas.|Consulte la <xref:System.Windows.Media.PolyQuadraticBezierSegment> página.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva Bézier cuadrática.|[Crear una curva Bézier cuadrática](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 Los segmentos de un <xref:System.Windows.Media.PathFigure> se combinan en una sola forma geométrica donde el punto final de cada segmento es el punto inicial del segmento siguiente. El <xref:System.Windows.Media.PathFigure.StartPoint%2A> propiedad de un <xref:System.Windows.Media.PathFigure> especifica el punto desde el que se dibuja el primer segmento. Cada segmento posterior comienza en el punto final del segmento anterior. Por ejemplo, una línea vertical desde `10,50` a `10,150` pueden definirse mediante el establecimiento la <xref:System.Windows.Media.PathFigure.StartPoint%2A> propiedad `10,50` y la creación de un <xref:System.Windows.Media.LineSegment> con un <xref:System.Windows.Media.LineSegment.Point%2A> configuración de la propiedad de `10,150`.  
  
 En el ejemplo siguiente se crea una sencilla <xref:System.Windows.Media.PathGeometry> consta de una sola <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.LineSegment> y lo muestra mediante un <xref:System.Windows.Shapes.Path> elemento. El <xref:System.Windows.Media.PathFigure> del objeto <xref:System.Windows.Media.PathFigure.StartPoint%2A> está establecido en `10,20` y un <xref:System.Windows.Media.LineSegment> se define con un punto final de `100,130`. La siguiente ilustración muestra el <xref:System.Windows.Media.PathGeometry> creado por este ejemplo.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
Objeto PathGeometry que contiene un solo LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Merece la pena comparar este ejemplo con la anterior <xref:System.Windows.Media.LineGeometry> ejemplo.  La sintaxis usada para un <xref:System.Windows.Media.PathGeometry> es mucho más detallado que se usa para una sencilla <xref:System.Windows.Media.LineGeometry>, y es posible que más sentido usar el <xref:System.Windows.Media.LineGeometry> clase en este caso, pero la sintaxis detallada de la <xref:System.Windows.Media.PathGeometry> permite extremadamente complicada y compleja regiones geométricas.  
  
 Se pueden crear geometrías más complejas mediante una combinación de <xref:System.Windows.Media.PathSegment> objetos.  
  
 El ejemplo siguiente se usa un <xref:System.Windows.Media.BezierSegment>, un <xref:System.Windows.Media.LineSegment>y una <xref:System.Windows.Media.ArcSegment> para crear la forma. El ejemplo crea primero una curva Bézier cúbica definiendo cuatro puntos: un punto inicial, que es el punto final del segmento anterior, un punto de conexión (<xref:System.Windows.Media.BezierSegment.Point3%2A>), y dos puntos de control (<xref:System.Windows.Media.BezierSegment.Point1%2A> y <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Los dos puntos de control de una curva Bézier cúbica se comportan como imanes, atraen hacia ellos partes de lo que de otra manera sería una línea recta y generan una curva. El primer punto de control, <xref:System.Windows.Media.BezierSegment.Point1%2A>, afecta al principio de la curva; el segundo punto de control, <xref:System.Windows.Media.BezierSegment.Point2%2A>, afecta a la parte final de la curva.  
  
 El ejemplo, a continuación, se agrega un <xref:System.Windows.Media.LineSegment>, que se dibuja entre el punto final de los anteriores <xref:System.Windows.Media.BezierSegment> que lo precede hasta el punto especificado por su <xref:System.Windows.Media.LineSegment> propiedad.  
  
 El ejemplo, a continuación, se agrega un <xref:System.Windows.Media.ArcSegment>, que se dibuja desde el punto final de los anteriores <xref:System.Windows.Media.LineSegment> para el punto especificado por su <xref:System.Windows.Media.ArcSegment.Point%2A> propiedad. El ejemplo también se especifica radios del arco x e y-(<xref:System.Windows.Media.ArcSegment.Size%2A>), un ángulo de giro (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), una marca que indica cómo de grande que debería ser el ángulo del arco resultante (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>) y un valor que indica en qué dirección se dibuja el arco (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Se pueden crear geometrías más complejas utilizando varias <xref:System.Windows.Media.PathFigure> objetos dentro de un <xref:System.Windows.Media.PathGeometry>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.PathGeometry> con dos <xref:System.Windows.Media.PathFigure> objetos, cada uno de los cuales contiene varias <xref:System.Windows.Media.PathSegment> objetos.  El <xref:System.Windows.Media.PathFigure> del ejemplo anterior y un <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.PolyLineSegment> y un <xref:System.Windows.Media.QuadraticBezierSegment> se usan.  Un <xref:System.Windows.Media.PolyLineSegment> se define con una matriz de puntos y el <xref:System.Windows.Media.QuadraticBezierSegment> se define con un punto de control y un punto de conexión. En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![Una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.gif "graphicsmm_path")  
Objeto PathGeometry con varias figuras  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Al igual que el <xref:System.Windows.Media.PathGeometry> (clase), un <xref:System.Windows.Media.StreamGeometry> define una forma geométrica compleja que puede contener curvas, arcos y líneas. A diferencia de un <xref:System.Windows.Media.PathGeometry>, el contenido de un <xref:System.Windows.Media.StreamGeometry> no admiten el enlace de datos, animaciones ni modificaciones. Use un <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desea la sobrecarga de admitir el enlace de datos, animaciones ni modificaciones. Debido a su eficacia, la <xref:System.Windows.Media.StreamGeometry> clase es una buena elección para describir adornos.  
  
 Para obtener un ejemplo, vea [Create a Shape Using a StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md) (Cómo: Crear una forma con un objeto StreamGeometry).  
  
### <a name="path-markup-syntax"></a>Sintaxis de marcado de trazados  
 El <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry> admiten un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mediante una serie especial de movimiento de sintaxis de atributo y comandos de dibujo. Para más información, consulte [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Geometrías compuestas  
 Se pueden crear objetos de geometría compuesta mediante una <xref:System.Windows.Media.GeometryGroup>, un <xref:System.Windows.Media.CombinedGeometry>, o mediante una llamada a estático <xref:System.Windows.Media.Geometry> método <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
-   El <xref:System.Windows.Media.CombinedGeometry> objeto y el <xref:System.Windows.Media.Geometry.Combine%2A> método realiza una operación booleana para combinar el área definida por dos geometrías. <xref:System.Windows.Media.Geometry> los objetos que no tienen ninguna área se descartan. Solo dos <xref:System.Windows.Media.Geometry> se pueden combinar objetos (aunque estas dos geometrías pueden ser también geometrías compuestas).  
  
-   El <xref:System.Windows.Media.GeometryGroup> clase crea una amalgama de la <xref:System.Windows.Media.Geometry> objetos que contiene sin combinar sus áreas. Cualquier número de <xref:System.Windows.Media.Geometry> se pueden agregar objetos a un <xref:System.Windows.Media.GeometryGroup>. Para obtener un ejemplo, vea [Create a Composite Shape](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) (Cómo: Crear una forma compuesta).  
  
 Dado que no lleva a cabo una operación de combinación, el uso <xref:System.Windows.Media.GeometryGroup> objetos ofrece ventajas de rendimiento con respecto a <xref:System.Windows.Media.CombinedGeometry> objetos o <xref:System.Windows.Media.Geometry.Combine%2A> método.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Geometrías combinadas  
 La sección anterior se ha mencionado la <xref:System.Windows.Media.CombinedGeometry> objeto y el <xref:System.Windows.Media.Geometry.Combine%2A> método combinar el área definida por las geometrías que contienen. El <xref:System.Windows.Media.GeometryCombineMode> enumeración especifica cómo se combinan las geometrías. Los valores posibles de la <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> propiedad son: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>, y <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 En el ejemplo siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con un modo de combinación de unión.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 En el ejemplo siguiente, un <xref:System.Windows.Media.CombinedGeometry> se define con el modo de combinación <xref:System.Windows.Media.GeometryCombineMode.Xor>.  Ambos <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> y <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Para obtener otros ejemplos, vea [Create a Composite Shape](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) (Cómo: Crear una forma compuesta) y [Create a Combined Geometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md) (Cómo: Crear una geometría combinada).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Características de los objetos Freezable  
 Porque se hereda de la <xref:System.Windows.Freezable> (clase), el <xref:System.Windows.Media.Geometry> clase proporcionan varias características especiales: <xref:System.Windows.Media.Geometry> objetos se pueden declarar como [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)compartida entre varios objetos, de sólo lectura para mejorar rendimiento, clonar y hacerse seguros para subprocesos. Para obtener más información sobre las diferentes características proporcionadas por <xref:System.Windows.Freezable> objetos, vea el [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Otras características de objeto Geometry  
 La <xref:System.Windows.Media.Geometry> clase también proporciona métodos de utilidad, como la siguiente:  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A> : Obtiene el área de la <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A> -Determina si la geometría contiene otro <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A> -Determina si el trazo de un <xref:System.Windows.Media.Geometry> contiene un punto especificado.  
  
 Consulte la <xref:System.Windows.Media.Geometry> clase para obtener una lista completa de sus métodos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)
- [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
