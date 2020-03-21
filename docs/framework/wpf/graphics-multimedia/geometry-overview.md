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
ms.openlocfilehash: ff42e59edd9d98b0b52dc3bdd3ace0c35df60878
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112380"
---
# <a name="geometry-overview"></a>Información general sobre geometría
Esta información general describe [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> cómo utilizar las clases para describir formas. En este tema también se <xref:System.Windows.Media.Geometry> contrastan las diferencias entre objetos y <xref:System.Windows.Shapes.Shape> elementos.  

<a name="wcpsdk_graphics_geometry_introduction"></a>
## <a name="what-is-a-geometry"></a>¿Qué es una geometría?  
 La <xref:System.Windows.Media.Geometry> clase y las clases que <xref:System.Windows.Media.EllipseGeometry> <xref:System.Windows.Media.PathGeometry>derivan <xref:System.Windows.Media.CombinedGeometry>de ella, como , , y , permiten describir la geometría de una forma 2D. Estas descripciones geométricas tiene muchos usos, como definir una forma para pintarla en la pantalla o definir regiones de recorte y pruebas de posicionamiento. Incluso se puede usar una geometría para definir un trazado de animación.  
  
 <xref:System.Windows.Media.Geometry>los objetos pueden ser simples, como rectángulos y círculos, o compuestos, creados a partir de dos o más objetos de geometría.  Se pueden crear geometrías más <xref:System.Windows.Media.PathGeometry> complejas mediante las clases y, <xref:System.Windows.Media.StreamGeometry> que permiten describir arcos y curvas.  
  
 Dado <xref:System.Windows.Media.Geometry> que a <xref:System.Windows.Freezable>es <xref:System.Windows.Media.Geometry> un tipo de , objetos proporcionan varias características especiales: se pueden declarar como [recursos,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)compartir entre varios objetos, hecho de solo lectura para mejorar el rendimiento, clonado y hecho seguro para subprocesos. Para obtener más información sobre <xref:System.Windows.Freezable> las diferentes características proporcionadas por los objetos, consulte Información general sobre [objetos freezable](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>
## <a name="geometries-vs-shapes"></a>Geometrías frente a formas  
 Las <xref:System.Windows.Media.Geometry> <xref:System.Windows.Shapes.Shape> clases y parecen similares en que <xref:System.Windows.Media.EllipseGeometry> <xref:System.Windows.Shapes.Ellipse> ambas describen formas 2D (comparar y por ejemplo), pero hay diferencias importantes.  
  
 Por un <xref:System.Windows.Media.Geometry> momento, la <xref:System.Windows.Freezable> clase hereda de la clase mientras que la <xref:System.Windows.Shapes.Shape> clase hereda de <xref:System.Windows.FrameworkElement>. Dado que son <xref:System.Windows.Shapes.Shape> elementos, los objetos pueden <xref:System.Windows.Media.Geometry> representarse a sí mismos y participar en el sistema de diseño, mientras que los objetos no.  
  
 Aunque <xref:System.Windows.Shapes.Shape> los objetos son <xref:System.Windows.Media.Geometry> más <xref:System.Windows.Media.Geometry> fácilmente utilizables que los objetos, los objetos son más versátiles. Mientras <xref:System.Windows.Shapes.Shape> que un objeto se utiliza <xref:System.Windows.Media.Geometry> para representar gráficos 2D, un objeto se puede utilizar para definir la región geométrica para gráficos 2D, definir una región para el recorte o definir una región para pruebas de posicionación, por ejemplo.  
  
### <a name="the-path-shape"></a>La forma del trazado  
 Uno <xref:System.Windows.Shapes.Shape>, <xref:System.Windows.Shapes.Path> la clase, <xref:System.Windows.Media.Geometry> en realidad utiliza a para describir su contenido. Al establecer <xref:System.Windows.Shapes.Path.Data%2A> la <xref:System.Windows.Shapes.Path> propiedad <xref:System.Windows.Media.Geometry> de la <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> with y establecer <xref:System.Windows.Media.Geometry>sus propiedades y, puede representar un archivo .  
  
<a name="commonproperties"></a>
## <a name="common-properties-that-take-a-geometry"></a>Propiedades comunes que aceptan un objeto Geometry  
 En las secciones anteriores se menciona que se pueden usar objetos Geometry con otros objetos con diversos fines, como dibujar formas, crear animaciones y efectuar recortes. En la tabla siguiente se enumeran <xref:System.Windows.Media.Geometry> varias clases que tienen propiedades que toman un objeto.  
  
|Tipo|Propiedad|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>
## <a name="simple-geometry-types"></a>Tipos de objeto Geometry simples  
 La clase base para todas las <xref:System.Windows.Media.Geometry>geometrías es la clase abstracta.  Las clases que <xref:System.Windows.Media.Geometry> derivan de la clase se pueden agrupar aproximadamente en tres categorías: geometrías simples, geometrías de ruta y geometrías compuestas.  
  
 Las clases <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>de <xref:System.Windows.Media.EllipseGeometry> geometría simples incluyen , y se utilizan para crear formas geométricas básicas, como líneas, rectángulos y círculos.  
  
- A <xref:System.Windows.Media.LineGeometry> se define especificando el punto inicial de la línea y el punto final.  
  
- A <xref:System.Windows.Media.RectangleGeometry> se define <xref:System.Windows.Rect> con una estructura que especifica su posición relativa y su altura y anchura. Puede crear un rectángulo redondeado <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> estableciendo las propiedades y.  
  
- Un <xref:System.Windows.Media.EllipseGeometry> se define por un punto central, un radio X y un radio Y.  En los ejemplos siguientes se muestra cómo crear geometrías simples de representación y recorte.  
  
 Estas mismas formas, así como formas más complejas, se pueden crear utilizando a o mediante la <xref:System.Windows.Media.PathGeometry> combinación de objetos de geometría juntos, pero estas clases proporcionan un medio más simple para producir estas formas geométricas básicas.  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.LineGeometry>muestra cómo crear y representar un archivo .  Como se indicó anteriormente, un <xref:System.Windows.Media.Geometry> objeto no <xref:System.Windows.Shapes.Path> puede dibujarse a sí mismo, por lo que en el ejemplo se utiliza una forma para representar la línea.  Dado que una línea no <xref:System.Windows.Shapes.Shape.Fill%2A> tiene <xref:System.Windows.Shapes.Path> ningún área, establecer la propiedad de la no tendría ningún efecto; en su <xref:System.Windows.Shapes.Shape.Stroke%2A> lugar, solo se especifican las propiedades y. <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Objeto LineGeometry dibujado desde (10,20) hasta (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.EllipseGeometry>muestra cómo crear y representar un archivo .  Los ejemplos <xref:System.Windows.Media.EllipseGeometry.Center%2A> establecen <xref:System.Windows.Media.EllipseGeometry> el se `50,50` establece en el punto y el radio `50`x y el radio Y se establecen en , lo que crea un círculo con un diámetro de 100.  El interior de la elipse se pinta asignando un valor <xref:System.Windows.Media.Brushes.Gold%2A>a la propiedad Fill del elemento Path, en este caso. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Objeto EllipseGeometry dibujado en (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 En el ejemplo siguiente se <xref:System.Windows.Media.RectangleGeometry>muestra cómo crear y representar un archivo .  La posición y las dimensiones del <xref:System.Windows.Rect> rectángulo se definen mediante una estructura. La posición es `50,50` y el alto y ancho son ambos `25`, lo que crea un cuadrado. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Objeto RectangleGeometry dibujado en 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 En el ejemplo siguiente <xref:System.Windows.Media.EllipseGeometry> se muestra cómo utilizar una región de clip para una imagen.  Un <xref:System.Windows.Controls.Image> objeto se <xref:System.Windows.FrameworkElement.Width%2A> define con un <xref:System.Windows.FrameworkElement.Height%2A> de 200 y uno de 150.  Un <xref:System.Windows.Media.EllipseGeometry> con <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> un valor de <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 100, un <xref:System.Windows.Media.EllipseGeometry.Center%2A> valor de 75 y un valor <xref:System.Windows.UIElement.Clip%2A> de 100,75 se establece en la propiedad de la imagen.  Solo se mostrará la parte de la imagen que queda dentro del área de la elipse. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![Objeto Image con y sin recorte](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Objeto EllipseGeometry usado para recortar un control Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>
## <a name="path-geometries"></a>Geometrías de trazado  
 La <xref:System.Windows.Media.PathGeometry> clase y su <xref:System.Windows.Media.StreamGeometry> equivalente ligero, la clase, proporcionan los medios para describir varias figuras complejas compuestas de arcos, curvas y líneas.  
  
 En el corazón <xref:System.Windows.Media.PathGeometry> de a <xref:System.Windows.Media.PathFigure> hay una colección de objetos, <xref:System.Windows.Media.PathGeometry>así denominada porque cada figura describe una forma discreta en el archivo . Cada <xref:System.Windows.Media.PathFigure> uno se compone de <xref:System.Windows.Media.PathSegment> uno o más objetos, cada uno de los cuales describe un segmento de la figura.  
  
 Hay muchos tipos de segmentos.  
  
|Tipo de segmento|Descripción|Ejemplo|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco elíptico entre dos puntos.|[Cree un arco elíptico](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva Bézier cúbica entre dos puntos.|[Cree una curva de Bézier cúbica](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una línea entre dos puntos.|[Crear un LineSegment en una clase PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie de curvas Bézier cúbicas.|Consulte <xref:System.Windows.Media.PolyBezierSegment> la página de tipos.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie de líneas.|Consulte <xref:System.Windows.Media.PolyLineSegment> la página de tipos.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie de curvas Bézier cuadráticas.|Consulte <xref:System.Windows.Media.PolyQuadraticBezierSegment> la página.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva Bézier cuadrática.|[Cree una curva Bézier cuadrática.](how-to-create-a-quadratic-bezier-curve.md)|  
  
 Los segmentos <xref:System.Windows.Media.PathFigure> dentro de a se combinan en una sola forma geométrica con el punto final de cada segmento como el punto inicial del siguiente segmento. La <xref:System.Windows.Media.PathFigure.StartPoint%2A> propiedad <xref:System.Windows.Media.PathFigure> de a especifica el punto desde el que se dibuja el primer segmento. Cada segmento posterior comienza en el punto final del segmento anterior. Por ejemplo, se `10,50` puede `10,150` definir una línea <xref:System.Windows.Media.PathFigure.StartPoint%2A> vertical `10,50` desde <xref:System.Windows.Media.LineSegment> to <xref:System.Windows.Media.LineSegment.Point%2A> estableciendo `10,150`la propiedad en y creando un valor de propiedad de .  
  
 En el ejemplo <xref:System.Windows.Media.PathGeometry> siguiente se crea <xref:System.Windows.Media.PathFigure> una <xref:System.Windows.Media.LineSegment> simple compuesta <xref:System.Windows.Shapes.Path> de una única con una y se muestra mediante un elemento. El <xref:System.Windows.Media.PathFigure> objeto <xref:System.Windows.Media.PathFigure.StartPoint%2A> se establece `10,20` en <xref:System.Windows.Media.LineSegment> y a se `100,130`define con un punto final de . En la ilustración siguiente se muestra lo <xref:System.Windows.Media.PathGeometry> creado por este ejemplo.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Objeto PathGeometry que contiene un solo LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Vale la pena contrastar este <xref:System.Windows.Media.LineGeometry> ejemplo con el ejemplo anterior.  La sintaxis <xref:System.Windows.Media.PathGeometry> utilizada para a es mucho más <xref:System.Windows.Media.LineGeometry>detallada que la utilizada para <xref:System.Windows.Media.LineGeometry> un simple , y puede tener <xref:System.Windows.Media.PathGeometry> más sentido utilizar la clase en este caso, pero la sintaxis detallada de la permite regiones geométricas extremadamente complejas y complejas.  
  
 Se pueden crear geometrías más complejas <xref:System.Windows.Media.PathSegment> mediante una combinación de objetos.  
  
 En el ejemplo <xref:System.Windows.Media.BezierSegment>siguiente <xref:System.Windows.Media.LineSegment>se <xref:System.Windows.Media.ArcSegment> usa un , a , y un para crear una forma. El ejemplo crea primero una curva Bézier cúbica es definiendo cuatro puntos: un punto inicial, que es el punto final del segmento anterior, un punto final (<xref:System.Windows.Media.BezierSegment.Point3%2A>) y dos puntos de control (<xref:System.Windows.Media.BezierSegment.Point1%2A> y <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Los dos puntos de control de una curva Bézier cúbica se comportan como imanes, atraen hacia ellos partes de lo que de otra manera sería una línea recta y generan una curva. El primer punto <xref:System.Windows.Media.BezierSegment.Point1%2A>de control, , afecta a la parte inicial de la curva; el segundo punto <xref:System.Windows.Media.BezierSegment.Point2%2A>de control, , afecta a la parte final de la curva.  
  
 A continuación, el <xref:System.Windows.Media.LineSegment>ejemplo agrega un , que se <xref:System.Windows.Media.BezierSegment> dibuja entre el punto final <xref:System.Windows.Media.LineSegment> del anterior que le precedió al punto especificado por su propiedad.  
  
 A continuación, el <xref:System.Windows.Media.ArcSegment>ejemplo agrega un , que se <xref:System.Windows.Media.LineSegment> dibuja desde el <xref:System.Windows.Media.ArcSegment.Point%2A> punto final del anterior al punto especificado por su propiedad. El ejemplo también especifica el radio x e<xref:System.Windows.Media.ArcSegment.Size%2A>y del arco<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>( ), un ángulo de rotación (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>), un indicador que indica el tamaño<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>del ángulo del arco resultante ( ) y un valor que indica en qué dirección se dibuja el arco ( ). En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Se pueden crear geometrías aún más <xref:System.Windows.Media.PathFigure> complejas <xref:System.Windows.Media.PathGeometry>mediante el uso de varios objetos dentro de un archivo .  
  
 En el ejemplo <xref:System.Windows.Media.PathGeometry> siguiente <xref:System.Windows.Media.PathFigure> se crea un <xref:System.Windows.Media.PathSegment> con dos objetos, cada uno de los cuales contiene varios objetos.  El <xref:System.Windows.Media.PathFigure> ejemplo anterior y <xref:System.Windows.Media.PathFigure> a <xref:System.Windows.Media.PolyLineSegment> con <xref:System.Windows.Media.QuadraticBezierSegment> a y a se utilizan.  A <xref:System.Windows.Media.PolyLineSegment> se define con una <xref:System.Windows.Media.QuadraticBezierSegment> matriz de puntos y el se define con un punto de control y un punto final. En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Objeto PathGeometry con varias figuras  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Al <xref:System.Windows.Media.PathGeometry> igual que <xref:System.Windows.Media.StreamGeometry> la clase, una define una forma geométrica compleja que puede contener curvas, arcos y líneas. A <xref:System.Windows.Media.PathGeometry>diferencia de un <xref:System.Windows.Media.StreamGeometry> , el contenido de un no admite el enlace de datos, animación o modificación. Utilice <xref:System.Windows.Media.StreamGeometry> a cuando necesite describir una geometría compleja, pero no desee la sobrecarga de admitir el enlace de datos, la animación o la modificación. Debido a su eficiencia, la <xref:System.Windows.Media.StreamGeometry> clase es una buena opción para describir adornos.  
  
 Para obtener un ejemplo, vea [Create a Shape Using a StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md) (Cómo: Crear una forma con un objeto StreamGeometry).  
  
### <a name="path-markup-syntax"></a>Sintaxis de marcado de trazados  
 Los <xref:System.Windows.Media.PathGeometry> <xref:System.Windows.Media.StreamGeometry> tipos y [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] admiten una sintaxis de atributo mediante una serie especial de comandos move y draw. Para más información, consulte [Sintaxis de marcado de trazados](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>
## <a name="composite-geometries"></a>Geometrías compuestas  
 Los objetos de geometría <xref:System.Windows.Media.GeometryGroup>compuesta <xref:System.Windows.Media.CombinedGeometry>se pueden crear <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.Geometry.Combine%2A>mediante un , a , o llamando al método estático .  
  
- El <xref:System.Windows.Media.CombinedGeometry> objeto <xref:System.Windows.Media.Geometry.Combine%2A> y el método realizan una operación booleana para combinar el área definida por dos geometrías. <xref:System.Windows.Media.Geometry>los objetos que no tienen área se descartan. Solo <xref:System.Windows.Media.Geometry> se pueden combinar dos objetos (aunque estas dos geometrías también pueden ser geometrías compuestas).  
  
- La <xref:System.Windows.Media.GeometryGroup> clase crea una amalgama de los <xref:System.Windows.Media.Geometry> objetos que contiene sin combinar su área. Cualquier número <xref:System.Windows.Media.Geometry> de objetos <xref:System.Windows.Media.GeometryGroup>se puede agregar a un archivo . Para obtener un ejemplo, vea [Create a Composite Shape](how-to-create-a-composite-shape.md) (Cómo: Crear una forma compuesta).  
  
 Dado que no realizan una <xref:System.Windows.Media.GeometryGroup> operación de combinación, el uso de objetos proporciona ventajas de rendimiento sobre el uso <xref:System.Windows.Media.CombinedGeometry> de objetos o el <xref:System.Windows.Media.Geometry.Combine%2A> método.  
  
<a name="combindgeometriessection"></a>
## <a name="combined-geometries"></a>Geometrías combinadas  
 En la sección <xref:System.Windows.Media.CombinedGeometry> anterior se <xref:System.Windows.Media.Geometry.Combine%2A> menciona el objeto y el método combinan el área definida por las geometrías que contienen. La <xref:System.Windows.Media.GeometryCombineMode> enumeración especifica cómo se combinan las geometrías. Los valores posibles <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> para <xref:System.Windows.Media.GeometryCombineMode.Union>la <xref:System.Windows.Media.GeometryCombineMode.Intersect> <xref:System.Windows.Media.GeometryCombineMode.Exclude>propiedad <xref:System.Windows.Media.GeometryCombineMode.Xor>son: , , , y .  
  
 En el ejemplo <xref:System.Windows.Media.CombinedGeometry> siguiente, a se define con un modo combinado de Union.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> el <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> como el se definen como círculos del mismo radio, pero con los centros desfasados por 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación Union](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 En el ejemplo <xref:System.Windows.Media.CombinedGeometry> siguiente, a se <xref:System.Windows.Media.GeometryCombineMode.Xor>define con un modo de combinación de .  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> el <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> como el se definen como círculos del mismo radio, pero con los centros desfasados por 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación Xor](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Para obtener otros ejemplos, vea [Create a Composite Shape](how-to-create-a-composite-shape.md) (Cómo: Crear una forma compuesta) y [Create a Combined Geometry](how-to-create-a-combined-geometry.md) (Cómo: Crear una geometría combinada).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Características de objeto Freezable  
 Dado que hereda <xref:System.Windows.Freezable> de <xref:System.Windows.Media.Geometry> la clase, la <xref:System.Windows.Media.Geometry> clase proporciona varias características especiales: los objetos se pueden declarar como [recursos XAML,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)se pueden compartir entre varios objetos, hacer de solo lectura para mejorar el rendimiento, clonado y seguro para subprocesos. Para obtener más información sobre <xref:System.Windows.Freezable> las diferentes características proporcionadas por los objetos, consulte Información general sobre [objetos freezable](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>
## <a name="other-geometry-features"></a>Otras características de objeto Geometry  
 La <xref:System.Windows.Media.Geometry> clase también proporciona métodos de utilidad útiles, como los siguientes:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>- Obtiene el área <xref:System.Windows.Media.Geometry>del archivo .  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>- Determina si la <xref:System.Windows.Media.Geometry>geometría contiene otro archivo .  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>- Determina si el <xref:System.Windows.Media.Geometry> trazo de a contiene un punto especificado.  
  
 Consulte <xref:System.Windows.Media.Geometry> la clase para obtener una lista completa de sus métodos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Sintaxis de marcado de trazados](path-markup-syntax.md)
- [Temas de información](geometries-how-to-topics.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
