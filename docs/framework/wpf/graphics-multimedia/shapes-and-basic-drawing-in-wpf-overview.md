---
title: Formas y resumen básico del dibujo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 44104bec478f1fbb10acc0e591af43ea95fecdc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141333"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Información general sobre formas y dibujo básico en WPF
En este tema se proporciona <xref:System.Windows.Shapes.Shape> información general sobre cómo dibujar con objetos. A <xref:System.Windows.Shapes.Shape> es un <xref:System.Windows.UIElement> tipo de que le permite dibujar una forma en la pantalla. Dado que son <xref:System.Windows.Shapes.Shape> elementos de <xref:System.Windows.Controls.Panel> interfaz de usuario, los objetos se pueden usar dentro de los elementos y la mayoría de los controles.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece varias capas de acceso a gráficos y servicios de representación. En la capa <xref:System.Windows.Shapes.Shape> superior, los objetos son fáciles de usar [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y proporcionan muchas características útiles, como el diseño y la participación en el sistema de eventos.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Objetos Shape  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona una serie de objetos listos para usar. <xref:System.Windows.Shapes.Shape>  Todos los objetos <xref:System.Windows.Shapes.Shape> shape heredan de la clase. Los objetos <xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Line>de <xref:System.Windows.Shapes.Path> <xref:System.Windows.Shapes.Polygon>forma <xref:System.Windows.Shapes.Polyline>disponibles incluyen , , , , , y <xref:System.Windows.Shapes.Rectangle>. <xref:System.Windows.Shapes.Shape>objetos comparten las siguientes propiedades comunes.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: describe cómo se pinta el contorno de la forma.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: describe el grosor del contorno de la forma.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: Describe cómo se pinta el interior de la forma.  
  
- Propiedades de datos para especificar coordenadas y vértices, medidos en píxeles independientes del dispositivo.  
  
 Debido a <xref:System.Windows.UIElement>que derivan de , los objetos de forma se pueden utilizar dentro de paneles y la mayoría de los controles. El <xref:System.Windows.Controls.Canvas> panel es una opción particularmente buena para crear dibujos complejos porque admite el posicionamiento absoluto de sus objetos secundarios.  
  
 La <xref:System.Windows.Shapes.Line> clase le permite dibujar una línea entre dos puntos. En el ejemplo siguiente se muestran varias maneras de especificar coordenadas de línea y propiedades de trazo.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 La siguiente imagen muestra <xref:System.Windows.Shapes.Line>el archivo .  
  
 ![Ilustración de línea](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Aunque <xref:System.Windows.Shapes.Line> la clase <xref:System.Windows.Shapes.Shape.Fill%2A> proporciona una propiedad, establecerla <xref:System.Windows.Shapes.Line> no tiene ningún efecto porque a no tiene ningún área.  
  
 Otra forma común <xref:System.Windows.Shapes.Ellipse>es el archivo .  Cree <xref:System.Windows.Shapes.Ellipse> un definiendo las <xref:System.Windows.FrameworkElement.Width%2A> propiedades <xref:System.Windows.FrameworkElement.Height%2A> y la forma. Para dibujar un círculo, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> especifique un <xref:System.Windows.Shapes.Ellipse> cuyo y los valores son iguales.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 La siguiente imagen muestra un <xref:System.Windows.Shapes.Ellipse>ejemplo de un archivo .  
  
 ![Ilustración de elipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Utilizar trazados y geometrías  
 La <xref:System.Windows.Shapes.Path> clase le permite dibujar curvas y formas complejas. Estas curvas y formas <xref:System.Windows.Media.Geometry> se describen mediante objetos. Para utilizar <xref:System.Windows.Shapes.Path>un , <xref:System.Windows.Media.Geometry> se crea un <xref:System.Windows.Shapes.Path> y <xref:System.Windows.Shapes.Path.Data%2A> se usa para establecer la propiedad del objeto.  
  
 Hay una variedad <xref:System.Windows.Media.Geometry> de objetos para elegir. Las <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry>clases <xref:System.Windows.Media.EllipseGeometry> , , y describen formas relativamente simples. Para crear formas más complejas o <xref:System.Windows.Media.PathGeometry>crear curvas, utilice un archivo .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry y PathSegments  
 <xref:System.Windows.Media.PathGeometry>los objetos se componen <xref:System.Windows.Media.PathFigure> de uno o más objetos; cada <xref:System.Windows.Media.PathFigure> uno representa una "figura" o forma diferente. Cada <xref:System.Windows.Media.PathFigure> uno se compone de <xref:System.Windows.Media.PathSegment> uno o más objetos, cada uno de los cuales representa una parte conectada de la figura o forma. Los tipos de <xref:System.Windows.Media.LineSegment>segmento <xref:System.Windows.Media.BezierSegment>incluyen <xref:System.Windows.Media.ArcSegment>lo siguiente: , , y .  
  
 En el ejemplo <xref:System.Windows.Shapes.Path> siguiente, a se utiliza para dibujar una curva Bézier cuadrática.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 La siguiente imagen muestra la forma representada.  
  
 ![Ilustración de trayecto](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Para obtener <xref:System.Windows.Media.PathGeometry> más información <xref:System.Windows.Media.Geometry> sobre y las otras clases, vea [Información general sobre geometría](geometry-overview.md).  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Sintaxis abreviada de XAML  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], también puede utilizar una sintaxis abreviada especial para describir un <xref:System.Windows.Shapes.Path>archivo . En el ejemplo siguiente, se utiliza la sintaxis abreviada para dibujar una forma compleja.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 La siguiente imagen muestra <xref:System.Windows.Shapes.Path>un archivo .  
  
 ![Ilustración de trayecto](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 La <xref:System.Windows.Shapes.Path.Data%2A> cadena de atributo comienza con el comando "moveto", indicado por M, que establece <xref:System.Windows.Controls.Canvas>un punto de inicio para la ruta de acceso en el sistema de coordenadas del archivo . <xref:System.Windows.Shapes.Path>los parámetros de datos distinguen mayúsculas de minúsculas. La mayúscula M indica una ubicación absoluta para el nuevo punto actual. Una m minúscula indica coordenadas relativas. El primer segmento es una curva de Bézier cúbica que comienza en (100,200) y termina en (400,175), trazado con los dos puntos de control (100,25) y (400,350). Este segmento se indica mediante el <xref:System.Windows.Shapes.Path.Data%2A> comando C en la cadena de atributo. De nuevo, la C mayúscula indica una ruta de acceso absoluta; la c minúscula indicaría una ruta de acceso relativa.  
  
 El segundo segmento comienza con un comando H "lineto" horizontal absoluto, que especifica una línea trazada desde el punto de conexión del subtrazado anterior (400,175) hasta un nuevo punto de conexión (280,175). Dado que es un comando horizontal "lineto", el valor especificado es una coordenada *x.*  
  
 Para obtener la sintaxis <xref:System.Windows.Shapes.Path.Data%2A> completa de la ruta de acceso, vea la referencia y [Crear una forma mediante un PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Pintar formas  
 <xref:System.Windows.Media.Brush>objetos se utilizan para <xref:System.Windows.Shapes.Shape.Stroke%2A> pintar <xref:System.Windows.Shapes.Shape.Fill%2A>una forma y . En el ejemplo siguiente, se <xref:System.Windows.Shapes.Ellipse> especifican el trazo y el relleno de un. Tenga en cuenta que una entrada válida para las propiedades del pincel puede ser una palabra clave o el valor de color en formato hexadecimal. Para obtener más información acerca de las <xref:System.Windows.Media.Colors> palabras <xref:System.Windows.Media> clave de color disponibles, vea las propiedades de la clase en el espacio de nombres.  
  
```xaml
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
  
 La siguiente imagen muestra <xref:System.Windows.Shapes.Ellipse>el archivo .  
  
 ![Elipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 Como alternativa, puede utilizar la sintaxis <xref:System.Windows.Media.SolidColorBrush> de elemento de propiedad para crear explícitamente un objeto para pintar la forma con un color sólido.  
  
```xaml
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
  
 En la ilustración siguiente se muestra la forma representada.  
  
 ![Ilustración de SolidColorBrush](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")  
  
 También puede pintar el trazo o relleno de una forma con degradados, imágenes, patrones y mucho más. Para obtener más información, consulte Información general sobre [la pintura con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>Formas extensibles  
 Las <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>clases <xref:System.Windows.Shapes.Polyline>, <xref:System.Windows.Shapes.Rectangle> , <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Shape.Stretch%2A> , y todas tienen una propiedad. Esta propiedad determina <xref:System.Windows.Shapes.Shape> cómo se estira el contenido de un objeto <xref:System.Windows.Shapes.Shape> (la forma que se va a dibujar) para rellenar el espacio de diseño del objeto. El <xref:System.Windows.Shapes.Shape> espacio de diseño de un <xref:System.Windows.Shapes.Shape> objeto es la cantidad de espacio <xref:System.Windows.FrameworkElement.Width%2A> que <xref:System.Windows.FrameworkElement.Height%2A> el sistema <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> de <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> diseño asigna, debido a una configuración explícita y de unobjeto o a su configuración. Para obtener información adicional sobre el diseño en Windows Presentation Foundation, vea Introducción al [diseño.](../advanced/layout.md)  
  
 La propiedad Stretch puede tener uno de los siguientes valores:  
  
- <xref:System.Windows.Media.Stretch.None>: <xref:System.Windows.Shapes.Shape> el contenido del objeto no se estira.  
  
- <xref:System.Windows.Media.Stretch.Fill>: <xref:System.Windows.Shapes.Shape> el contenido del objeto se estira para rellenar su espacio de diseño.  No se mantiene la relación de aspecto.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: <xref:System.Windows.Shapes.Shape> El contenido del objeto se estira tanto como sea posible para rellenar su espacio de diseño conservando su relación de aspecto original.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: <xref:System.Windows.Shapes.Shape> El contenido del objeto se estira para llenar completamente su espacio de diseño conservando su relación de aspecto original.  
  
 Tenga en cuenta <xref:System.Windows.Shapes.Shape> que, cuando se <xref:System.Windows.Shapes.Shape> estira el contenido de un objeto, el contorno del objeto se pinta después del estiramiento.  
  
 En el ejemplo <xref:System.Windows.Shapes.Polygon> siguiente, a se utiliza para dibujar un triángulo muy pequeño de (0,0) a (0,1) a (1,1). El <xref:System.Windows.Shapes.Polygon> objeto <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> se establecen en 100, y su propiedad stretch se establece en Fill. Como resultado, <xref:System.Windows.Shapes.Polygon> el contenido del objeto (el triángulo) se estira para llenar el espacio más grande.  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
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
```

<a name="transforms"></a>
## <a name="transforming-shapes"></a>Transformar formas  
 La <xref:System.Windows.Media.Transform> clase proporciona los medios para transformar formas en un plano bidimensional.  Los diferentes tipos de<xref:System.Windows.Media.RotateTransform>transformación<xref:System.Windows.Media.ScaleTransform>incluyen rotación ( ), escala ( ), sesgo (<xref:System.Windows.Media.SkewTransform>) y traslación (<xref:System.Windows.Media.TranslateTransform>).  
  
 Una transformación común para aplicar a una forma es la rotación.  Para rotar una forma, <xref:System.Windows.Media.RotateTransform> cree <xref:System.Windows.Media.RotateTransform.Angle%2A>a y especifique su archivo . Un <xref:System.Windows.Media.RotateTransform.Angle%2A> de 45 gira el elemento 45 grados en el sentido de las agujas del reloj; un ángulo de 90 gira el elemento 90 grados en el sentido de las agujas del reloj; y así sucesivamente. Establezca <xref:System.Windows.Media.RotateTransform.CenterX%2A> las <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades y si desea controlar el punto sobre el que se gira el elemento. Estos valores de propiedad se expresan en el espacio de coordenadas del elemento que se va a transformar. <xref:System.Windows.Media.RotateTransform.CenterX%2A>y <xref:System.Windows.Media.RotateTransform.CenterY%2A> tienen valores predeterminados de cero. Por último, <xref:System.Windows.Media.RotateTransform> aplique el elemento. Si no desea que la transformación afecte al <xref:System.Windows.UIElement.RenderTransform%2A> diseño, establezca la propiedad de la forma.  
  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente, a se utiliza para girar una forma 45 grados alrededor de la esquina superior izquierda de la forma (0,0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 En el ejemplo siguiente, otra forma se gira 45 grados, pero esta vez se gira alrededor del punto (25,50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 En la ilustración siguiente se muestran los resultados de aplicar las dos transformaciones.  
  
 ![Rotaciones de 45 grados con diferentes centros](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 En los ejemplos anteriores, se aplicó una única transformación a cada objeto de forma. Para aplicar varias transformaciones a una forma (o <xref:System.Windows.Media.TransformGroup>a cualquier otro elemento de interfaz de usuario), utilice un archivo .  
  
## <a name="see-also"></a>Consulte también

- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre geometría](geometry-overview.md)
- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Información general sobre animaciones](animation-overview.md)
