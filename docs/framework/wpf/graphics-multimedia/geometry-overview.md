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
ms.openlocfilehash: f45c13e1af9bc2d1f75da11b13a2c03936b136c1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455012"
---
# <a name="geometry-overview"></a>Información general sobre geometría
En esta información general se describe cómo usar las clases de <xref:System.Windows.Media.Geometry> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] para describir las formas. En este tema también se contrastan las diferencias entre <xref:System.Windows.Media.Geometry> objetos y elementos de <xref:System.Windows.Shapes.Shape>.  

<a name="wcpsdk_graphics_geometry_introduction"></a>   
## <a name="what-is-a-geometry"></a>¿Qué es una geometría?  
 La clase <xref:System.Windows.Media.Geometry> y las clases que derivan de ella, como <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>y <xref:System.Windows.Media.CombinedGeometry>, permiten describir la geometría de una forma 2D. Estas descripciones geométricas tiene muchos usos, como definir una forma para pintarla en la pantalla o definir regiones de recorte y pruebas de posicionamiento. Incluso se puede usar una geometría para definir un trazado de animación.  
  
 <xref:System.Windows.Media.Geometry> objetos pueden ser simples, como rectángulos y círculos, o compuesto, creados a partir de dos o más objetos Geometry.  Se pueden crear geometrías más complejas mediante las clases <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry>, que permiten describir arcos y curvas.  
  
 Dado que un <xref:System.Windows.Media.Geometry> es un tipo de <xref:System.Windows.Freezable>, los objetos <xref:System.Windows.Media.Geometry> proporcionan varias características especiales: se pueden declarar como [recursos](../../../desktop-wpf/fundamentals/xaml-resources-define.md), compartirse entre varios objetos, convertirse en de solo lectura para mejorar el rendimiento, clonarse y hacer que sea segura para subprocesos. Para obtener más información sobre las diferentes características proporcionadas por los objetos <xref:System.Windows.Freezable>, consulte la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## <a name="geometries-vs-shapes"></a>Geometrías frente a formas  
 Las clases <xref:System.Windows.Media.Geometry> y <xref:System.Windows.Shapes.Shape> parecen ser similares en que describen las formas 2D (Compare <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Shapes.Ellipse> por ejemplo), pero hay diferencias importantes.  
  
 En el caso de uno, la clase <xref:System.Windows.Media.Geometry> hereda de la clase <xref:System.Windows.Freezable>, mientras que la clase <xref:System.Windows.Shapes.Shape> hereda de <xref:System.Windows.FrameworkElement>. Dado que son elementos, <xref:System.Windows.Shapes.Shape> objetos se pueden representar y participar en el sistema de diseño, mientras que los objetos <xref:System.Windows.Media.Geometry> no.  
  
 Aunque <xref:System.Windows.Shapes.Shape> objetos se pueden usar más fácilmente que los objetos de <xref:System.Windows.Media.Geometry>, los objetos de <xref:System.Windows.Media.Geometry> son más versátiles. Mientras que un objeto de <xref:System.Windows.Shapes.Shape> se usa para representar gráficos 2D, se puede usar un objeto <xref:System.Windows.Media.Geometry> para definir la región geométrica de los gráficos 2D, definir una región para recortar o definir una región para la prueba de posicionamiento, por ejemplo.  
  
### <a name="the-path-shape"></a>La forma del trazado  
 Una <xref:System.Windows.Shapes.Shape>, la clase <xref:System.Windows.Shapes.Path>, utiliza realmente un <xref:System.Windows.Media.Geometry> para describir su contenido. Si establece la propiedad <xref:System.Windows.Shapes.Path.Data%2A> de la <xref:System.Windows.Shapes.Path> con un <xref:System.Windows.Media.Geometry> y establece sus propiedades <xref:System.Windows.Shapes.Shape.Fill%2A> y <xref:System.Windows.Shapes.Shape.Stroke%2A>, puede representar una <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## <a name="common-properties-that-take-a-geometry"></a>Propiedades comunes que aceptan un objeto Geometry  
 En las secciones anteriores se menciona que se pueden usar objetos Geometry con otros objetos con diversos fines, como dibujar formas, crear animaciones y efectuar recortes. En la tabla siguiente se enumeran varias clases que tienen propiedades que toman un objeto <xref:System.Windows.Media.Geometry>.  
  
|Type|Propiedad.|  
|----------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## <a name="simple-geometry-types"></a>Tipos de objeto Geometry simples  
 La clase base para todas las geometrías es la clase abstracta <xref:System.Windows.Media.Geometry>.  Las clases que derivan de la clase <xref:System.Windows.Media.Geometry> se pueden agrupar más o menos en tres categorías: geometrías simples, geometrías de trazado y geometrías compuestas.  
  
 Entre las clases de geometría simples se incluyen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>y <xref:System.Windows.Media.EllipseGeometry> y que se usan para crear formas geométricas básicas, como líneas, rectángulos y círculos.  
  
- Un <xref:System.Windows.Media.LineGeometry> se define especificando el punto inicial de la línea y el punto final.  
  
- Un <xref:System.Windows.Media.RectangleGeometry> se define con una estructura de <xref:System.Windows.Rect> que especifica su posición relativa y su alto y ancho. Puede crear un rectángulo redondeado estableciendo las propiedades <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  
  
- Un <xref:System.Windows.Media.EllipseGeometry> se define mediante un punto central, un radio x y un radio y.  En los ejemplos siguientes se muestra cómo crear geometrías simples de representación y recorte.  
  
 Estas mismas formas, así como las formas más complejas, se pueden crear mediante una <xref:System.Windows.Media.PathGeometry> o combinando objetos Geometry juntos, pero estas clases proporcionan un medio más sencillo para generar estas formas geométricas básicas.  
  
 En el ejemplo siguiente se muestra cómo crear y representar un <xref:System.Windows.Media.LineGeometry>.  Como se indicó anteriormente, un objeto de <xref:System.Windows.Media.Geometry> no puede dibujarse a sí mismo, por lo que en el ejemplo se usa una forma <xref:System.Windows.Shapes.Path> para representar la línea.  Dado que una línea no tiene área, establecer la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Path> no tendría ningún efecto; en su lugar, solo se especifican las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Objeto LineGeometry dibujado desde (10,20) hasta (100,130)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo crear y representar un <xref:System.Windows.Media.EllipseGeometry>.  En los ejemplos se establece el <xref:System.Windows.Media.EllipseGeometry.Center%2A> de la <xref:System.Windows.Media.EllipseGeometry> se establece en el punto `50,50` y el radio x y el radio y se establecen en `50`, lo que crea un círculo con un diámetro de 100.  El interior de la elipse se dibuja asignando un valor a la propiedad Fill del elemento Path, en este caso <xref:System.Windows.Media.Brushes.Gold%2A>. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![EllipseGeometry](./media/graphicsmm-ellipse.gif "graphicsmm_ellipse")  
Objeto EllipseGeometry dibujado en (50,50)  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo crear y representar un <xref:System.Windows.Media.RectangleGeometry>.  La posición y las dimensiones del rectángulo se definen mediante una estructura de <xref:System.Windows.Rect>. La posición es `50,50` y el alto y ancho son ambos `25`, lo que crea un cuadrado. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![RectangleGeometry](./media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
Objeto RectangleGeometry dibujado en 50,50  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo usar un <xref:System.Windows.Media.EllipseGeometry> como la región de recorte de una imagen.  Un objeto de <xref:System.Windows.Controls.Image> se define con un <xref:System.Windows.FrameworkElement.Width%2A> de 200 y un <xref:System.Windows.FrameworkElement.Height%2A> de 150.  Un <xref:System.Windows.Media.EllipseGeometry> con un valor de <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> de 100, un valor de <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> de 75 y un valor de <xref:System.Windows.Media.EllipseGeometry.Center%2A> de 100, 75 se establece en la propiedad <xref:System.Windows.UIElement.Clip%2A> de la imagen.  Solo se mostrará la parte de la imagen que queda dentro del área de la elipse. En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![Objeto Image con y sin recorte](./media/graphicsmm-clipexample.png "graphicsmm_clipexample")  
Objeto EllipseGeometry usado para recortar un control Image  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## <a name="path-geometries"></a>Geometrías de trazado  
 La clase <xref:System.Windows.Media.PathGeometry> y su equivalente ligero, la clase <xref:System.Windows.Media.StreamGeometry>, proporcionan los medios para describir varias figuras complejas que se componen de arcos, curvas y líneas.  
  
 En el corazón de un <xref:System.Windows.Media.PathGeometry> se trata de una colección de objetos <xref:System.Windows.Media.PathFigure>, de modo que cada figura describe una forma discreta en el <xref:System.Windows.Media.PathGeometry>. Cada <xref:System.Windows.Media.PathFigure> se compone de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales describe un segmento de la figura.  
  
 Hay muchos tipos de segmentos.  
  
|Tipo de segmento|Descripción|Ejemplo|  
|------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco elíptico entre dos puntos.|[Crear un arco elíptico](how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva Bézier cúbica entre dos puntos.|[Crear una curva Bézier cúbica](how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una línea entre dos puntos.|[Crear un LineSegment en una clase PathGeometry](how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie de curvas Bézier cúbicas.|Vea la página tipo de <xref:System.Windows.Media.PolyBezierSegment>.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie de líneas.|Vea la página tipo de <xref:System.Windows.Media.PolyLineSegment>.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie de curvas Bézier cuadráticas.|Vea la página <xref:System.Windows.Media.PolyQuadraticBezierSegment>.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva Bézier cuadrática.|[Crear una curva Bézier cuadrática](how-to-create-a-quadratic-bezier-curve.md).|  
  
 Los segmentos de un <xref:System.Windows.Media.PathFigure> se combinan en una sola forma geométrica con el punto final de cada segmento que es el punto inicial del segmento siguiente. La propiedad <xref:System.Windows.Media.PathFigure.StartPoint%2A> de una <xref:System.Windows.Media.PathFigure> especifica el punto desde el que se dibuja el primer segmento. Cada segmento posterior comienza en el punto final del segmento anterior. Por ejemplo, se puede definir una línea vertical de `10,50` a `10,150` estableciendo la propiedad <xref:System.Windows.Media.PathFigure.StartPoint%2A> en `10,50` y creando un <xref:System.Windows.Media.LineSegment> con un valor de propiedad <xref:System.Windows.Media.LineSegment.Point%2A> de `10,150`.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.PathGeometry> simple que consta de un <xref:System.Windows.Media.PathFigure> único con un <xref:System.Windows.Media.LineSegment> y se muestra mediante un elemento de <xref:System.Windows.Shapes.Path>. El <xref:System.Windows.Media.PathFigure.StartPoint%2A> del objeto de <xref:System.Windows.Media.PathFigure> se establece en `10,20` y se define un <xref:System.Windows.Media.LineSegment> con un punto final de `100,130`. En la ilustración siguiente se muestra el <xref:System.Windows.Media.PathGeometry> creado en este ejemplo.  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Objeto PathGeometry que contiene un solo LineSegment  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Merece la pena comparar este ejemplo con el ejemplo anterior <xref:System.Windows.Media.LineGeometry>.  La sintaxis usada para una <xref:System.Windows.Media.PathGeometry> es mucho más detallada que la que se usa para un <xref:System.Windows.Media.LineGeometry>simple y puede tener más sentido usar la clase <xref:System.Windows.Media.LineGeometry> en este caso, pero la sintaxis detallada de la <xref:System.Windows.Media.PathGeometry> permite regiones geométricas muy intrincadas y complejas.  
  
 Se pueden crear geometrías más complejas mediante una combinación de objetos de <xref:System.Windows.Media.PathSegment>.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.BezierSegment>, un <xref:System.Windows.Media.LineSegment>y un <xref:System.Windows.Media.ArcSegment> para crear la forma. En primer lugar, el ejemplo crea una curva Bézier cúbica definiendo cuatro puntos: un punto inicial, que es el punto final del segmento anterior, un punto final (<xref:System.Windows.Media.BezierSegment.Point3%2A>) y dos puntos de control (<xref:System.Windows.Media.BezierSegment.Point1%2A> y <xref:System.Windows.Media.BezierSegment.Point2%2A>).  Los dos puntos de control de una curva Bézier cúbica se comportan como imanes, atraen hacia ellos partes de lo que de otra manera sería una línea recta y generan una curva. El primer punto de control, <xref:System.Windows.Media.BezierSegment.Point1%2A>, afecta a la parte inicial de la curva. el segundo punto de control, <xref:System.Windows.Media.BezierSegment.Point2%2A>, afecta a la parte final de la curva.  
  
 A continuación, en el ejemplo se agrega un <xref:System.Windows.Media.LineSegment>, que se dibuja entre el punto final del <xref:System.Windows.Media.BezierSegment> anterior que lo precede al punto especificado por su propiedad <xref:System.Windows.Media.LineSegment>.  
  
 A continuación, en el ejemplo se agrega un <xref:System.Windows.Media.ArcSegment>, que se dibuja desde el punto final de la <xref:System.Windows.Media.LineSegment> anterior hasta el punto especificado por su propiedad <xref:System.Windows.Media.ArcSegment.Point%2A>. En el ejemplo también se especifica el radio x-e y (<xref:System.Windows.Media.ArcSegment.Size%2A>) del arco, un ángulo de giro (<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>), un marcador que indica el tamaño del ángulo del arco resultante (<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>) y un valor que indica en qué dirección se dibuja el arco (<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>). En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![PathGeometry](./media/graphicsmm-path2.gif "graphicsmm_path2")  
PathGeometry  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Se pueden crear geometrías incluso más complejas mediante el uso de varios objetos <xref:System.Windows.Media.PathFigure> dentro de un <xref:System.Windows.Media.PathGeometry>.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Media.PathGeometry> con dos objetos <xref:System.Windows.Media.PathFigure>, cada uno de los cuales contiene varios objetos <xref:System.Windows.Media.PathSegment>.  Se utiliza el <xref:System.Windows.Media.PathFigure> del ejemplo anterior y un <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.PolyLineSegment> y un <xref:System.Windows.Media.QuadraticBezierSegment>.  Un <xref:System.Windows.Media.PolyLineSegment> se define con una matriz de puntos y el <xref:System.Windows.Media.QuadraticBezierSegment> se define con un punto de control y un punto final. En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![PathGeometry](./media/graphicsmm-path.gif "graphicsmm_path")  
Objeto PathGeometry con varias figuras  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### <a name="streamgeometry"></a>StreamGeometry  
 Al igual que la clase <xref:System.Windows.Media.PathGeometry>, un <xref:System.Windows.Media.StreamGeometry> define una forma geométrica compleja que puede contener curvas, arcos y líneas. A diferencia de un <xref:System.Windows.Media.PathGeometry>, el contenido de un <xref:System.Windows.Media.StreamGeometry> no admite enlaces de datos, animaciones ni modificaciones. Use una <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desee la sobrecarga que supone la compatibilidad con el enlace de datos, la animación o la modificación. Debido a su eficacia, la clase <xref:System.Windows.Media.StreamGeometry> es una buena opción para describir los adornos.  
  
 Para obtener un ejemplo, vea [Create a Shape Using a StreamGeometry](how-to-create-a-shape-using-a-streamgeometry.md) (Cómo: Crear una forma con un objeto StreamGeometry).  
  
### <a name="path-markup-syntax"></a>Sintaxis de marcado de trazados  
 Los tipos <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry> admiten una sintaxis de atributo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mediante una serie especial de comandos de movimiento y dibujo. Para más información, consulte [Sintaxis de marcado de trazados](path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## <a name="composite-geometries"></a>Geometrías compuestas  
 Los objetos de geometría compuestos se pueden crear mediante un <xref:System.Windows.Media.GeometryGroup>, un <xref:System.Windows.Media.CombinedGeometry>o llamando al método estático <xref:System.Windows.Media.Geometry> <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
- El objeto <xref:System.Windows.Media.CombinedGeometry> y el método <xref:System.Windows.Media.Geometry.Combine%2A> realiza una operación booleana para combinar el área definida por dos geometrías. <xref:System.Windows.Media.Geometry> los objetos que no tienen área se descartan. Solo se pueden combinar dos objetos <xref:System.Windows.Media.Geometry> (aunque estas dos geometrías también pueden ser geometrías compuestas).  
  
- La clase <xref:System.Windows.Media.GeometryGroup> crea una fusión de los objetos <xref:System.Windows.Media.Geometry> que contiene sin combinar su área. Se puede agregar cualquier número de objetos <xref:System.Windows.Media.Geometry> a un <xref:System.Windows.Media.GeometryGroup>. Para obtener un ejemplo, vea [Create a Composite Shape](how-to-create-a-composite-shape.md) (Cómo: Crear una forma compuesta).  
  
 Dado que no realizan una operación de combinación, el uso de objetos de <xref:System.Windows.Media.GeometryGroup> proporciona ventajas de rendimiento sobre el uso de objetos de <xref:System.Windows.Media.CombinedGeometry> o el método <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
<a name="combindgeometriessection"></a>   
## <a name="combined-geometries"></a>Geometrías combinadas  
 En la sección anterior se menciona el objeto <xref:System.Windows.Media.CombinedGeometry> y el método <xref:System.Windows.Media.Geometry.Combine%2A> combinan el área definida por las geometrías que contienen. La enumeración <xref:System.Windows.Media.GeometryCombineMode> especifica cómo se combinan las geometrías. Los valores posibles para la propiedad <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> son: <xref:System.Windows.Media.GeometryCombineMode.Union>, <xref:System.Windows.Media.GeometryCombineMode.Intersect>, <xref:System.Windows.Media.GeometryCombineMode.Exclude>y <xref:System.Windows.Media.GeometryCombineMode.Xor>.  
  
 En el ejemplo siguiente, se define un <xref:System.Windows.Media.CombinedGeometry> con un modo de combinación de Union.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como la <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con el desplazamiento de los centros por 50.  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación de uniones](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
  
 En el ejemplo siguiente, se define un <xref:System.Windows.Media.CombinedGeometry> con un modo de combinación de <xref:System.Windows.Media.GeometryCombineMode.Xor>.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como la <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con el desplazamiento de los centros por 50.  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación XOR](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")  
  
 Para obtener otros ejemplos, vea [Create a Composite Shape](how-to-create-a-composite-shape.md) (Cómo: Crear una forma compuesta) y [Create a Combined Geometry](how-to-create-a-combined-geometry.md) (Cómo: Crear una geometría combinada).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Características de los objetos Freezable  
 Dado que hereda de la clase <xref:System.Windows.Freezable>, la clase <xref:System.Windows.Media.Geometry> proporciona varias características especiales: los objetos <xref:System.Windows.Media.Geometry> se pueden declarar como [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md), compartidos entre varios objetos, convertidos en solo lectura para mejorar el rendimiento, clonarse y realizarse seguro para subprocesos. Para obtener más información sobre las diferentes características proporcionadas por los objetos <xref:System.Windows.Freezable>, consulte la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## <a name="other-geometry-features"></a>Otras características de objeto Geometry  
 La clase <xref:System.Windows.Media.Geometry> también proporciona métodos de utilidad útiles, como los siguientes:  
  
- <xref:System.Windows.Media.Geometry.GetArea%2A>: obtiene el área de la <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.FillContains%2A>: determina si la geometría contiene otro <xref:System.Windows.Media.Geometry>.  
  
- <xref:System.Windows.Media.Geometry.StrokeContains%2A>: determina si el trazo de un <xref:System.Windows.Media.Geometry> contiene un punto especificado.  
  
 Vea la clase <xref:System.Windows.Media.Geometry> para obtener una lista completa de sus métodos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Geometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Sintaxis de marcado de trazados](path-markup-syntax.md)
- [Temas "Cómo..."](geometries-how-to-topics.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre formas y dibujo básico en WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
