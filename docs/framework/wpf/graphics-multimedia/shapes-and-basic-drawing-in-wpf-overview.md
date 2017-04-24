---
title: "Informaci&#243;n general sobre formas y dibujo b&#225;sico en WPF | Microsoft Docs"
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
  - "dibujo básico"
  - "Shape (objetos)"
  - "formas, acerca de las formas"
  - "dibujo vectorial, información general"
  - "vectores, dibujar"
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Informaci&#243;n general sobre formas y dibujo b&#225;sico en WPF
En este tema se proporciona información general sobre cómo dibujar con objetos <xref:System.Windows.Shapes.Shape>.  <xref:System.Windows.Shapes.Shape> es un tipo de <xref:System.Windows.UIElement> que permite dibujar una forma en la pantalla.  Dado que son elementos de interfaz de usuario, los objetos <xref:System.Windows.Shapes.Shape> se pueden utilizar dentro de elementos <xref:System.Windows.Controls.Panel> y de la mayoría de los controles.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece varias capas de acceso a los gráficos y a los servicios de representación.  En la capa superior, los objetos <xref:System.Windows.Shapes.Shape> son fáciles de utilizar y proporcionan numerosas características útiles, como diseño y participación en el sistema de eventos de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="shapes"></a>   
## Objetos de formas  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varios objetos <xref:System.Windows.Shapes.Shape> listos para usar.  Todos los objetos de formas heredan de la clase <xref:System.Windows.Shapes.Shape>.  Los objetos de formas disponibles incluyen <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> y <xref:System.Windows.Shapes.Rectangle>. Los objetos <xref:System.Windows.Shapes.Shape> comparten las siguientes propiedades comunes.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: describe cómo se pinta el contorno de la forma.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: describe el grosor del contorno de la forma.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: describe cómo se pinta el interior de la forma.  
  
-   Propiedades de datos para especificar coordenadas y vértices, medidos en [píxeles independientes del dispositivo](GTMT).  
  
 Dado que se derivan de <xref:System.Windows.UIElement>, los objetos de formas se pueden utilizar dentro de los paneles y en la mayoría de los controles.  El panel <xref:System.Windows.Controls.Canvas> es una opción particularmente apropiada para crear dibujos complejos, porque admite la posición absoluta de sus objetos secundarios.  
  
 La clase <xref:System.Windows.Shapes.Line> permite dibujar una línea entre dos puntos.  En el ejemplo siguiente se muestran varias maneras de especificar coordenadas de línea y propiedades de trazo.  
  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 En la siguiente ilustración se muestra la línea \(<xref:System.Windows.Shapes.Line>\) representada.  
  
 ![Ilustración de línea](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.png "shape\_ovw\_line2")  
  
 Aunque la clase <xref:System.Windows.Shapes.Line> proporciona una propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>, establecerla no surte ningún efecto porque <xref:System.Windows.Shapes.Line> no tiene área.  
  
 Otra forma común es <xref:System.Windows.Shapes.Ellipse>.  Cree una forma <xref:System.Windows.Shapes.Ellipse> definiendo las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de la forma.  Para dibujar un círculo, especifique una forma <xref:System.Windows.Shapes.Ellipse> cuyos valores de <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> sean iguales.  
  
 [!code-xml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 En la siguiente ilustración se muestra un ejemplo de <xref:System.Windows.Shapes.Ellipse> representada.  
  
 ![Ilustración de elipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape\_ovw\_ellipse2")  
  
<a name="paths"></a>   
## Utilizar trazados y geometrías  
 La clase <xref:System.Windows.Shapes.Path> permite dibujar curvas y formas complejas.  Estas curvas y formas se describen mediante objetos <xref:System.Windows.Media.Geometry>.  Para utilizar un <xref:System.Windows.Shapes.Path>, se crea una <xref:System.Windows.Media.Geometry> y se utiliza para establecer la propiedad <xref:System.Windows.Shapes.Path.Data%2A> del objeto <xref:System.Windows.Shapes.Path>.  
  
 Hay gran variedad de objetos <xref:System.Windows.Media.Geometry> entre los que elegir.  Las clases <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> y <xref:System.Windows.Media.EllipseGeometry> describen formas relativamente simples.  Para crear formas más complejas o crear curvas, utilice <xref:System.Windows.Media.PathGeometry>.  
  
<a name="pathgeometry"></a>   
### PathGeometry y PathSegments  
 Los objetos <xref:System.Windows.Media.PathGeometry> se componen de uno o más objetos <xref:System.Windows.Media.PathFigure>; cada <xref:System.Windows.Media.PathFigure> representa una "figura" o forma diferente.  Cada <xref:System.Windows.Media.PathFigure>, a su vez, está compuesta de uno o varios objetos <xref:System.Windows.Media.PathSegment>, cada uno de los cuales representa una parte conectada de la figura o forma.  Los tipos de segmentos incluyen los siguientes: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment> y <xref:System.Windows.Media.ArcSegment>.  
  
 En el ejemplo siguiente, se utiliza <xref:System.Windows.Shapes.Path> para dibujar una curva Bézier cuadrática.  
  
 [!code-xml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 En la siguiente ilustración se muestra la forma representada.  
  
 ![Ilustración de trayecto](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.png "shape\_ovw\_path2")  
  
 Para obtener más información sobre <xref:System.Windows.Media.PathGeometry> y las demás clases <xref:System.Windows.Media.Geometry>, consulte [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="pathdatastring"></a>   
### Sintaxis XAML abreviada  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar también una sintaxis abreviada especial para describir <xref:System.Windows.Shapes.Path>.  En el ejemplo siguiente, se utiliza la sintaxis abreviada para dibujar una forma compleja.  
  
```xaml  
<Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 En la ilustración siguiente, se muestra el trazado \(<xref:System.Windows.Shapes.Path>\) representado.  
  
 ![Ilustración de trayecto](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.png "shape\_ovw\_path")  
  
 La cadena de atributos de <xref:System.Windows.Shapes.Path.Data%2A> comienza con el comando "moveto", indicado por M, que establece un punto de inicio para el trazado en el sistema de coordenadas de <xref:System.Windows.Controls.Canvas>.  Los parámetros de datos de <xref:System.Windows.Shapes.Path> distinguen mayúsculas de minúsculas.  La M mayúscula indica una ubicación absoluta para el nuevo punto activo.  Una m minúscula indicaría coordenadas relativas.  El primer segmento es una [curva Bézier](GTMT) cúbica que empieza en \(100,200\) y termina en \(400,175\), y se dibuja mediante los dos puntos de control \(100,25\) y \(400,350\).  Este segmento se indica mediante el comando C en la cadena de atributos de <xref:System.Windows.Shapes.Path.Data%2A>.  De nuevo, la C mayúscula indica un trazado absoluto; la c minúscula indicaría un trazado relativo.  
  
 El segundo segmento comienza con un comando "lineto" horizontal absoluto, indicado por H, que especifica una línea trazada desde el extremo del subtrazado anterior \(400,175\) hasta un nuevo extremo \(280,175\).  Puesto que se trata de un comando "lineto" horizontal, el valor especificado es una coordenada *x*.  
  
 Para obtener la sintaxis del trazado completo, consulte la referencia de <xref:System.Windows.Shapes.Path.Data%2A> y [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>   
## Pintar formas  
 Los objetos <xref:System.Windows.Media.Brush> se utilizan para pintar las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.Fill%2A> de una forma.  En el ejemplo siguiente, se especifican el trazo y el relleno de <xref:System.Windows.Shapes.Ellipse>.  Observe que para las propiedades de pincel es válido especificar una palabra clave o un valor de color hexadecimal.  Para obtener más información sobre las palabras clave de colores disponibles, consulte las propiedades de la clase <xref:System.Windows.Media.Colors> en el espacio de nombres <xref:System.Windows.Media>.  
  
```  
  
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
  
```  
  
 En la siguiente ilustración se muestra la forma <xref:System.Windows.Shapes.Ellipse> representada.  
  
 ![Elipse](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.png "shape\_ovw\_ellipsefill")  
  
 Como alternativa, puede utilizar la sintaxis de elementos de propiedades para crear explícitamente un objeto <xref:System.Windows.Media.SolidColorBrush> a fin de pintar la forma con un color sólido.  
  
```  
  
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 En la siguiente ilustración se muestra la forma representada.  
  
 ![Ilustración de SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.png "shape\_ovw\_solidcolorbrush")  
  
 También puede pintar el trazo o el relleno de una forma con degradados, imágenes, patrones, etc.  Para obtener más información, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>   
## Formas extensibles  
 Todas las clases <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> y <xref:System.Windows.Shapes.Rectangle> tienen una propiedad <xref:System.Windows.Shapes.Shape.Stretch%2A>.  Esta propiedad determina cómo se ajusta el contenido de un objeto <xref:System.Windows.Shapes.Shape> \(la forma que se va a dibujar\) hasta rellenar el espacio de diseño del objeto <xref:System.Windows.Shapes.Shape>.  El objeto de diseño de un objeto <xref:System.Windows.Shapes.Shape> es la cantidad de espacio que el sistema de diseño asigna a <xref:System.Windows.Shapes.Shape>, bien basándose en un valor explícito de <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>, o bien en sus valores de <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  Para obtener información adicional sobre el diseño en Windows Presentation Foundation, consulte la información general de [Diseño](../../../../docs/framework/wpf/advanced/layout.md).  
  
 La propiedad Stretch acepta uno de los valores siguientes:  
  
-   <xref:System.Windows.Media.Stretch>: no se ajusta el contenido del objeto <xref:System.Windows.Shapes.Shape>.  
  
-   <xref:System.Windows.Media.Stretch>: el contenido del objeto <xref:System.Windows.Shapes.Shape> se ajusta hasta rellenar su espacio de diseño.  No se conserva la relación de aspecto.  
  
-   <xref:System.Windows.Media.Stretch>: el contenido del objeto <xref:System.Windows.Shapes.Shape> se ajusta tanto como sea posible hasta rellenar su espacio de diseño conservando su relación de aspecto original.  
  
-   <xref:System.Windows.Media.Stretch>: el contenido del objeto <xref:System.Windows.Shapes.Shape> se ajusta hasta rellenar completamente su espacio de diseño conservando su relación de aspecto original.  
  
 Tenga en cuenta que, cuando se ajusta el contenido de un objeto <xref:System.Windows.Shapes.Shape>, el contorno del objeto <xref:System.Windows.Shapes.Shape> se pinta después de efectuar la expansión.  
  
 En el ejemplo siguiente, se usa <xref:System.Windows.Shapes.Polygon> para dibujar un triángulo muy pequeño de \(0,0\) a \(0,1\) y a \(1,1\).  Las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> del objeto <xref:System.Windows.Shapes.Polygon> se establecen en 100 y su propiedad Stretch se establece en Fill.  Como resultado, el contenido del objeto <xref:System.Windows.Shapes.Polygon> \(el triángulo\), se ajusta hasta rellenar el espacio mayor.  
  
```  
...  
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
...  
```  
  
```  
...  
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
...  
```  
  
<a name="transforms"></a>   
## Transformar formas  
 La clase <xref:System.Windows.Media.Transform> proporciona el medio para transformar las formas en un plano bidimensional.  Los distintos tipos de transformación incluyen rotación \(<xref:System.Windows.Media.RotateTransform>\), escala \(<xref:System.Windows.Media.ScaleTransform>\), sesgo \(<xref:System.Windows.Media.SkewTransform>\) y traslación \(<xref:System.Windows.Media.TranslateTransform>\).  
  
 Una transformación común que se aplica a las formas es el giro.  Para girar una forma, cree una <xref:System.Windows.Media.RotateTransform> y especifique su <xref:System.Windows.Media.RotateTransform.Angle%2A>.  Un valor de <xref:System.Windows.Media.RotateTransform.Angle%2A> de 45 gira el elemento 45 grados en el sentido de las agujas del reloj; un ángulo de 90 gira el elemento 90 grados en el sentido de las agujas del reloj; y así sucesivamente.  Establezca las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> si desea controlar el punto sobre el que se gira el elemento.  Estos valores de propiedad se expresan en el espacio de coordenadas del elemento que se transforma.  <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> tienen un valor predeterminado de cero.  Por último, aplique <xref:System.Windows.Media.RotateTransform> al elemento.  Si desea que la transformación no afecte al diseño, establezca la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de la forma.  
  
 En el ejemplo siguiente, se utiliza <xref:System.Windows.Media.RotateTransform> para girar una forma 45 grados sobre la esquina superior izquierda de la misma \(0,0\).  
  
 [!code-xml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 En el ejemplo siguiente, se gira otra forma 45 grados, pero esta vez sobre el punto \(25,50\).  
  
 [!code-xml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 En la ilustración siguiente se muestran los resultados de aplicar las dos transformaciones.  
  
 ![rotaciones de 45 grados con diferentes centros](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
  
 En los ejemplos anteriores, se aplicó una sola transformación a cada objeto de forma.  Para aplicar varias transformaciones a una forma \(o a cualquier otro elemento de la interfaz de usuario\), utilice <xref:System.Windows.Media.TransformGroup>.  
  
## Vea también  
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Tutorial: Introducción a WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)