---
title: "Informaci&#243;n general sobre geometr&#237;a | Microsoft Docs"
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
  - "clases, geometría"
  - "CombinedGeometry (clase)"
  - "EllipseGeometry (clase)"
  - "clases de geometría"
  - "gráficos, clases de geometría"
  - "LineGeometry (clase)"
  - "PathGeometry (clase)"
  - "RectangleGeometry (clase)"
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Informaci&#243;n general sobre geometr&#237;a
En esta información general se describe cómo utilizar las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<xref:System.Windows.Media.Geometry> para describir formas.  En este tema también se contrastan las diferencias entre los objetos <xref:System.Windows.Media.Geometry> y los elementos <xref:System.Windows.Shapes.Shape>.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## ¿Qué es una geometría?  
 La clase <xref:System.Windows.Media.Geometry> y las clases que derivan de ella, como <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.CombinedGeometry>, permiten describir la geometría de una forma 2D.  Estas descripciones geométricas tienen muchos usos, tales como la definición de una forma para pintarla en la pantalla o la definición de pruebas de posicionamiento y de zonas de recorte.  Incluso puede utilizar una geometría para definir un trazado de animación.  
  
 Los objetos <xref:System.Windows.Media.Geometry> pueden ser simples, tales como rectángulos y círculos, o bien compuestos, creados a partir de dos o más objetos de geometría.  Se pueden crear geometrías más complejas utilizando las clases <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry>, que permiten describir arcos y curvas.  
  
 Dado que <xref:System.Windows.Media.Geometry> es un tipo de <xref:System.Windows.Freezable>, los objetos <xref:System.Windows.Media.Geometry> proporcionan varias características especiales: pueden declararse como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md), compartirse entre varios objetos, convertirse en objetos de sólo lectura para mejorar el rendimiento, clonarse y convertirse en seguros para subprocesos.  Para obtener más información sobre las diferentes características que proporcionan los objetos <xref:System.Windows.Freezable>, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## Comparación entre geometrías yformas  
 Las clases <xref:System.Windows.Media.Geometry> y <xref:System.Windows.Shapes.Shape> parecen similares porque ambas describen formas 2D \(compare <xref:System.Windows.Media.EllipseGeometry> y <xref:System.Windows.Shapes.Ellipse>, por ejemplo\), pero hay diferencias importantes.  
  
 En primer lugar, la clase <xref:System.Windows.Media.Geometry> hereda de la clase <xref:System.Windows.Freezable>, mientras que la clase <xref:System.Windows.Shapes.Shape> hereda de <xref:System.Windows.FrameworkElement>.  Dado que son elementos, los objetos <xref:System.Windows.Shapes.Shape> se pueden representar y participar en el sistema del diseño, mientras que los objetos <xref:System.Windows.Media.Geometry> no pueden.  
  
 Aunque los objetos <xref:System.Windows.Shapes.Shape> se pueden utilizar de un modo más directo que los objetos <xref:System.Windows.Media.Geometry>, los objetos <xref:System.Windows.Media.Geometry> son más versátiles.  Aunque un objeto <xref:System.Windows.Shapes.Shape> se utiliza para representar gráficos 2D, un objeto <xref:System.Windows.Media.Geometry> se puede utilizar para definir el área geométrica para gráficos 2D, definir una zona de recorte o definir un área para pruebas de posicionamiento, por ejemplo.  
  
### Forma del trazado  
 Una forma \(<xref:System.Windows.Shapes.Shape>\), la clase <xref:System.Windows.Shapes.Path>, en realidad utiliza una geometría \(<xref:System.Windows.Media.Geometry>\) para describir su contenido.  Estableciendo la propiedad <xref:System.Windows.Shapes.Path.Data%2A> de <xref:System.Windows.Shapes.Path> con <xref:System.Windows.Media.Geometry> y estableciendo sus propiedades <xref:System.Windows.Shapes.Shape.Fill%2A> y <xref:System.Windows.Shapes.Shape.Stroke%2A>, puede representar <xref:System.Windows.Media.Geometry>.  
  
<a name="commonproperties"></a>   
## Propiedades comunes que aceptan un objeto de geometría  
 En las secciones anteriores se ha mencionado que los objetos de geometría se pueden utilizar con otros objetos para diversos propósitos, tales como dibujar formas, realizar animaciones o recortar.  En la tabla siguiente se muestra una lista con varias clases que tienen propiedades que aceptan un objeto <xref:System.Windows.Media.Geometry>.  
  
|Tipo|Propiedad.|  
|----------|----------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## Tipos de geometría simples  
 La clase base para todas las geometrías es la clase abstracta <xref:System.Windows.Media.Geometry>.  Las clases que se derivan de la clase <xref:System.Windows.Media.Geometry> se pueden agrupar a grandes rasgos en tres categorías: geometrías simples, geometrías de trazado y geometrías compuestas.  
  
 Las clases de geometrías simples incluyen <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> y <xref:System.Windows.Media.EllipseGeometry>, y se utilizan para crear las formas geométricas básicas, como líneas, rectángulos y círculos.  
  
-   Una <xref:System.Windows.Media.LineGeometry> se define especificando los puntos inicial y final de la línea.  
  
-   Una <xref:System.Windows.Media.RectangleGeometry> se define con una estructura <xref:System.Windows.Rect> que especifica su posición relativa, así como su alto y ancho.  Puede crear un rectángulo redondeado estableciendo las propiedades <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> y <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  
  
-   Una <xref:System.Windows.Media.EllipseGeometry> se define mediante un punto central, un radio X y un radio Y.  En los ejemplos siguientes se muestra cómo crear geometrías simples con fines de representación y recorte.  
  
 Estas mismas formas, así como otras más complejas, se pueden crear utilizando una <xref:System.Windows.Media.PathGeometry> o combinando objetos de geometría entre sí, pero estas clases proporcionan un medio más sencillo de generar estas formas geométricas básicas.  
  
 En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.LineGeometry>.  Como se ha indicado previamente, un objeto <xref:System.Windows.Media.Geometry> no puede dibujarse a sí mismo, por lo que en el ejemplo se utiliza una forma <xref:System.Windows.Shapes.Path> para representar la línea.  Dado que una línea no tiene área, establecer la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Path> no tendría ningún efecto; en su lugar, se especifican sólo las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
Objeto LineGeometry dibujado desde \(10,20\) hasta \(100,130\)  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo crear y representar un objeto <xref:System.Windows.Media.EllipseGeometry>.  En los ejemplos se establece el <xref:System.Windows.Media.EllipseGeometry.Center%2A> de <xref:System.Windows.Media.EllipseGeometry> en el punto `50,50` y el radio X y el radio Y se establecen ambos en `50`, lo que da lugar a un círculo con un diámetro de 100.  El interior de la elipse se pinta asignando un valor a la propiedad Fill del elemento Path, en este caso, <xref:System.Windows.Media.Brushes.Gold%2A>.  En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.png "graphicsmm\_ellipse")  
Objeto EllipseGeometry dibujado en \(50,50\)  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo crear y representar una <xref:System.Windows.Media.RectangleGeometry>.  Una estructura <xref:System.Windows.Rect> define la posición y las dimensiones del rectángulo.  La posición es `50,50`; por su parte, el alto y el ancho son ambos `25`, con lo que se crea un cuadrado.  En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
Objeto RectangleGeometry dibujado en 50,50  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 En el ejemplo siguiente se muestra cómo utilizar <xref:System.Windows.Media.EllipseGeometry> como zona de recorte de una imagen.  Un objeto <xref:System.Windows.Controls.Image> se define con un ancho \(<xref:System.Windows.FrameworkElement.Width%2A>\) de 200 y un alto \(<xref:System.Windows.FrameworkElement.Height%2A>\) de 150.  Un objeto <xref:System.Windows.Media.EllipseGeometry>, con un valor de radio X \(<xref:System.Windows.Media.EllipseGeometry.RadiusX%2A>\) de 100, un valor de radio Y \(<xref:System.Windows.Media.EllipseGeometry.RadiusY%2A>\) de 75 y un valor de centro \(<xref:System.Windows.Media.EllipseGeometry.Center%2A>\) de 100,75, se establece en la propiedad <xref:System.Windows.UIElement.Clip%2A> de la imagen.  Únicamente se muestra la parte de la imagen que está dentro del área de la elipse.  En la siguiente ilustración se muestra el resultado del ejemplo.  
  
 ![Image con y sin recorte](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm\_clipexample")  
Objeto EllipseGeometry utilizado para recortar un control de imagen  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## Geometrías de trazado  
 La clase <xref:System.Windows.Media.PathGeometry> y su equivalente ligera, la clase <xref:System.Windows.Media.StreamGeometry>, proporcionan recursos para describir varias figuras complejas compuestas de arcos, curvas y líneas.  
  
 En el núcleo de <xref:System.Windows.Media.PathGeometry> hay una colección de objetos <xref:System.Windows.Media.PathFigure>, que se denominan así porque cada figura describe una forma discreta de <xref:System.Windows.Media.PathGeometry>.  Cada <xref:System.Windows.Media.PathFigure>, a su vez, está compuesta de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales describe un segmento de la figura.  
  
 Existen muchos tipos de segmentos.  
  
|Tipo de segmento|Descripción|Ejemplo|  
|----------------------|-----------------|-------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco elíptico entre dos puntos.|[Crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva Bézier cúbica entre dos puntos.|[Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|Crea una línea entre dos puntos.|[Crear un segmento de línea en una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie de curvas Bézier cúbicas.|Consulte la página del tipo <xref:System.Windows.Media.PolyBezierSegment>.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie de líneas.|Consulte la página del tipo <xref:System.Windows.Media.PolyLineSegment>.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie de curvas Bézier cuadráticas.|Consulte la página de <xref:System.Windows.Media.PolyQuadraticBezierSegment>.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva Bézier cuadrática.|[Crea una curva Bézier cuadrática.](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 Los segmentos de <xref:System.Windows.Media.PathFigure> se combinan en una sola forma geométrica donde el punto final de cada segmento es el punto inicial del segmento siguiente.  La propiedad <xref:System.Windows.Media.PathFigure.StartPoint%2A> de <xref:System.Windows.Media.PathFigure> especifica el punto desde el que se dibuja el primer segmento.  Cada segmento posterior comienza en el punto final del segmento anterior.  Por ejemplo, para definir una línea vertical de `10,50` a `10,150` se establece la propiedad <xref:System.Windows.Media.PathFigure.StartPoint%2A> en `10,50` y se crea un <xref:System.Windows.Media.LineSegment> con un valor de `10,150` para la propiedad <xref:System.Windows.Media.LineSegment.Point%2A>.  
  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Media.PathGeometry> simple compuesto de una sola <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.LineSegment> y se muestra mediante un elemento <xref:System.Windows.Shapes.Path>.  La propiedad <xref:System.Windows.Media.PathFigure.StartPoint%2A> del objeto <xref:System.Windows.Media.PathFigure> se establece en `10,20` y <xref:System.Windows.Media.LineSegment> se define con un punto final de `100,130`.  En la ilustración siguiente se muestra el <xref:System.Windows.Media.PathGeometry> creado por este ejemplo.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
Objeto PathGeometry que contiene un solo elemento LineSegment  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 Es interesante comparar este ejemplo con el anterior, de <xref:System.Windows.Media.LineGeometry>.  La sintaxis utilizada para un objeto <xref:System.Windows.Media.PathGeometry> es mucho más detallada que la utilizada para un objeto <xref:System.Windows.Media.LineGeometry> simple y, en este caso, puede ser más lógico utilizar la clase <xref:System.Windows.Media.LineGeometry>; no obstante la sintaxis detallada de <xref:System.Windows.Media.PathGeometry> permite utilizar áreas geométricas sumamente intrincadas y complejas.  
  
 Puede crear geometrías más complejas utilizando una combinación de objetos <xref:System.Windows.Media.PathSegment>.  
  
 En el ejemplo siguiente se utiliza un <xref:System.Windows.Media.BezierSegment>, un <xref:System.Windows.Media.LineSegment> y un <xref:System.Windows.Media.ArcSegment> para crear una forma.  En el ejemplo, se crea primero una curva Bézier cúbica definiendo cuatro puntos: un punto inicial, que es el punto final del segmento anterior, un punto final \(<xref:System.Windows.Media.BezierSegment.Point3%2A>\) y dos puntos de control \(<xref:System.Windows.Media.BezierSegment.Point1%2A> y <xref:System.Windows.Media.BezierSegment.Point2%2A>\).  Los dos puntos de control de una curva Bézier cúbica se comportan como imanes: atraen hacia sí los segmentos que, de otra forma, serían una línea recta, con lo que se crea una curva.  El primer punto de control, <xref:System.Windows.Media.BezierSegment.Point1%2A>, afecta a la parte inicial de la curva; el segundo punto de control, <xref:System.Windows.Media.BezierSegment.Point2%2A>, afecta a la parte final de la curva.  
  
 A continuación, en el ejemplo se agrega un <xref:System.Windows.Media.LineSegment>, que se dibuja entre el punto final del <xref:System.Windows.Media.BezierSegment> anterior que lo precede y el punto especificado por su propiedad <xref:System.Windows.Media.LineSegment>.  
  
 Luego, en el ejemplo se agrega un <xref:System.Windows.Media.ArcSegment>, que se dibuja desde el punto final del <xref:System.Windows.Media.LineSegment> anterior hasta el punto especificado por su propiedad <xref:System.Windows.Media.ArcSegment.Point%2A>.  En el ejemplo se especifican asimismo los radios X e Y \(<xref:System.Windows.Media.ArcSegment.Size%2A>\), un ángulo de rotación \(<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>\), un marcador que indica la amplitud que deberá tener el ángulo del arco resultante \(<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>\), y un valor que indica la dirección en que se dibuja el arco \(<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>\).  En la ilustración siguiente se muestra la forma creada por este ejemplo.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.png "graphicsmm\_path2")  
Objeto PathGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 Se pueden crear geometrías aún más complejas utilizando varios objetos <xref:System.Windows.Media.PathFigure> dentro de un <xref:System.Windows.Media.PathGeometry>.  
  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Media.PathGeometry> con dos objetos <xref:System.Windows.Media.PathFigure>, cada uno de los cuales contiene varios objetos <xref:System.Windows.Media.PathSegment>.  Se utilizan la <xref:System.Windows.Media.PathFigure> del ejemplo anterior y una <xref:System.Windows.Media.PathFigure> con un <xref:System.Windows.Media.PolyLineSegment> y un <xref:System.Windows.Media.QuadraticBezierSegment>.  <xref:System.Windows.Media.PolyLineSegment> se define con una matriz de puntos y <xref:System.Windows.Media.QuadraticBezierSegment> se define con un punto de control y un punto final.  En la ilustración siguiente se muestra la forma creada por este ejemplo.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.png "graphicsmm\_path")  
Objeto PathGeometry con varias figuras  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### StreamGeometry  
 Al igual que la clase <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.StreamGeometry> define una forma geométrica compleja que puede contener curvas, arcos y líneas.  A diferencia de <xref:System.Windows.Media.PathGeometry>, el contenido de <xref:System.Windows.Media.StreamGeometry> no admite el enlace de datos, la animación ni la modificación.  Utilice un objeto <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desee la sobrecarga que implica la compatibilidad con el enlace de datos, la animación o la modificación.  Debido a su eficacia, la clase <xref:System.Windows.Media.StreamGeometry> es una buena opción para describir adornos.  
  
 Para obtener un ejemplo, vea [Crear una forma utilizando StreamGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
### Sintaxis de marcado de trazados  
 Los tipos <xref:System.Windows.Media.PathGeometry> y <xref:System.Windows.Media.StreamGeometry> admiten una sintaxis de atributo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mediante una serie especial de comandos de movimiento y de dibujo.  Para obtener más información, consulte [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## Geometrías compuestas  
 Los objetos de geometrías compuestas se pueden crear mediante <xref:System.Windows.Media.GeometryGroup>, que es un objeto <xref:System.Windows.Media.CombinedGeometry>, o llamando al método del objeto <xref:System.Windows.Media.Geometry> estático, <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
-   El objeto <xref:System.Windows.Media.CombinedGeometry> y el método <xref:System.Windows.Media.Geometry.Combine%2A> realizan una operación de tipo Boolean para combinar el área definida por dos geometrías.  Se descartan los objetos <xref:System.Windows.Media.Geometry> que no tienen área.  Únicamente es posible combinar dos objetos <xref:System.Windows.Media.Geometry> \(aunque estas dos geometrías también pueden ser geometrías compuestas\).  
  
-   La clase <xref:System.Windows.Media.GeometryGroup> crea una fusión de los objetos <xref:System.Windows.Media.Geometry> que contiene sin combinar su área.  Se puede agregar cualquier número de objetos <xref:System.Windows.Media.Geometry> a un <xref:System.Windows.Media.GeometryGroup>.  Para obtener un ejemplo, vea [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md).  
  
 Dado que no realizan una operación de combinación, el uso de objetos <xref:System.Windows.Media.GeometryGroup> proporciona ventajas de rendimiento con respecto al uso de objetos <xref:System.Windows.Media.CombinedGeometry> o del método <xref:System.Windows.Media.Geometry.Combine%2A>.  
  
<a name="combindgeometriessection"></a>   
## Geometrías combinadas  
 En la sección anterior se menciona que el objeto <xref:System.Windows.Media.CombinedGeometry> y el método <xref:System.Windows.Media.Geometry.Combine%2A> combinan el área definida por las geometrías que contienen.  La enumeración <xref:System.Windows.Media.GeometryCombineMode> especifica cómo se combinan las geometrías.  Los valores posibles para la propiedad <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> son: <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode> y <xref:System.Windows.Media.GeometryCombineMode>.  
  
 En el ejemplo siguiente, se define una <xref:System.Windows.Media.CombinedGeometry> con el modo de combinación Union.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Resultados del modo de combinación Union](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
  
 En el ejemplo siguiente, se define una <xref:System.Windows.Media.CombinedGeometry> con el modo de combinación <xref:System.Windows.Media.GeometryCombineMode>.  Tanto <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> como <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> se definen como círculos del mismo radio, pero con los centros desplazados en 50.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Resultados del modo de combinación Xor](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
  
 Para obtener otros ejemplos, vea [Crear una forma compuesta](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) y [Crear una geometría combinada](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md).  
  
<a name="freezable_features"></a>   
## Características de elementos Freezable  
 Como hereda de la clase <xref:System.Windows.Freezable>, la clase <xref:System.Windows.Media.Geometry> proporciona varias características especiales: los objetos <xref:System.Windows.Media.Geometry> se pueden declarar como [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md), se pueden compartir entre varios objetos, se puede hacer que sean de sólo lectura para mejorar el rendimiento, se pueden clonar y se pueden hacer seguros para subprocesos.  Para obtener más información sobre las diferentes características que proporcionan los objetos <xref:System.Windows.Freezable>, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="othergeometryfeatures"></a>   
## Otras características de las geometrías  
 La clase <xref:System.Windows.Media.Geometry> también proporciona métodos de utilidad prácticos, como los siguientes:  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A>: obtiene el área de <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A>: determina si la geometría contiene otra <xref:System.Windows.Media.Geometry>.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A>: determina si el trazo de una <xref:System.Windows.Media.Geometry> contiene un punto especificado.  
  
 Consulte la clase <xref:System.Windows.Media.Geometry> para obtener una lista completa de sus métodos.  
  
## Vea también  
 <xref:System.Windows.Media.Geometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)