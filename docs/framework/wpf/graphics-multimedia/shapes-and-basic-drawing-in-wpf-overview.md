---
title: Información general sobre formas y dibujo básico
description: Mejore su interfaz de usuario con formas listas para usar y varios niveles de servicios de representación en Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: 41d8f2b87232740c8945bd6a6099aa86dbe77bc6
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853690"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a>Información general sobre formas y dibujo básico en WPF
En este tema se proporciona información general sobre cómo dibujar con <xref:System.Windows.Shapes.Shape> objetos. Un <xref:System.Windows.Shapes.Shape> es un tipo de <xref:System.Windows.UIElement> que permite dibujar una forma en la pantalla. Dado que son elementos de interfaz de usuario, <xref:System.Windows.Shapes.Shape> los objetos se pueden usar dentro <xref:System.Windows.Controls.Panel> de los elementos y la mayoría de los controles.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece varias capas de acceso a gráficos y servicios de representación. En la capa superior, los <xref:System.Windows.Shapes.Shape> objetos son fáciles de usar y proporcionan numerosas características útiles, como el diseño y la participación en el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] sistema de eventos.  

<a name="shapes"></a>
## <a name="shape-objects"></a>Objetos Shape  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona una serie de objetos listos para usar <xref:System.Windows.Shapes.Shape> .  Todos los objetos de forma se heredan de la <xref:System.Windows.Shapes.Shape> clase. Los objetos de forma disponibles incluyen <xref:System.Windows.Shapes.Ellipse> , <xref:System.Windows.Shapes.Line> , <xref:System.Windows.Shapes.Path> , <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> y <xref:System.Windows.Shapes.Rectangle> . <xref:System.Windows.Shapes.Shape>los objetos comparten las siguientes propiedades comunes.  
  
- <xref:System.Windows.Shapes.Shape.Stroke%2A>: Describe cómo se pinta el contorno de la forma.  
  
- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describe el grosor del contorno de la forma.  
  
- <xref:System.Windows.Shapes.Shape.Fill%2A>: Describe cómo se pinta el interior de la forma.  
  
- Propiedades de datos para especificar coordenadas y vértices, medidos en píxeles independientes del dispositivo.  
  
 Dado que derivan de <xref:System.Windows.UIElement> , los objetos de forma se pueden usar dentro de los paneles y la mayoría de los controles. El <xref:System.Windows.Controls.Canvas> panel es una opción especialmente adecuada para crear dibujos complejos porque admite el posicionamiento absoluto de sus objetos secundarios.  
  
 La <xref:System.Windows.Shapes.Line> clase le permite dibujar una línea entre dos puntos. En el ejemplo siguiente se muestran varias maneras de especificar coordenadas de línea y propiedades de trazo.  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 En la imagen siguiente se muestra la representación de <xref:System.Windows.Shapes.Line> .  
  
 ![Ilustración de línea](./media/shape-ovw-line2.gif "shape_ovw_line2")  
  
 Aunque la <xref:System.Windows.Shapes.Line> clase proporciona una <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad, establecerla no tiene ningún efecto porque un <xref:System.Windows.Shapes.Line> no tiene área.  
  
 Otra forma común es <xref:System.Windows.Shapes.Ellipse> .  Cree una <xref:System.Windows.Shapes.Ellipse> mediante la definición de las <xref:System.Windows.FrameworkElement.Width%2A> propiedades y de la forma <xref:System.Windows.FrameworkElement.Height%2A> . Para dibujar un círculo, especifique un <xref:System.Windows.Shapes.Ellipse> cuyos <xref:System.Windows.FrameworkElement.Width%2A> valores de y <xref:System.Windows.FrameworkElement.Height%2A> sean iguales.  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 La imagen siguiente muestra un ejemplo de un representado <xref:System.Windows.Shapes.Ellipse> .  
  
 ![Ilustración de elipse](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")  
  
<a name="paths"></a>
## <a name="using-paths-and-geometries"></a>Utilizar trazados y geometrías  
 La <xref:System.Windows.Shapes.Path> clase le permite dibujar curvas y formas complejas. Estas curvas y formas se describen mediante <xref:System.Windows.Media.Geometry> objetos. Para usar <xref:System.Windows.Shapes.Path> , cree un <xref:System.Windows.Media.Geometry> y úselo para establecer la <xref:System.Windows.Shapes.Path> propiedad del objeto <xref:System.Windows.Shapes.Path.Data%2A> .  
  
 Hay una variedad de <xref:System.Windows.Media.Geometry> objetos entre los que elegir. Las <xref:System.Windows.Media.LineGeometry> <xref:System.Windows.Media.RectangleGeometry> clases, y <xref:System.Windows.Media.EllipseGeometry> describen formas relativamente simples. Para crear formas más complejas o crear curvas, use <xref:System.Windows.Media.PathGeometry> .  
  
<a name="pathgeometry"></a>
### <a name="pathgeometry-and-pathsegments"></a>PathGeometry y PathSegments  
 <xref:System.Windows.Media.PathGeometry>los objetos se componen de uno o varios <xref:System.Windows.Media.PathFigure> objetos; cada uno <xref:System.Windows.Media.PathFigure> representa una "figura" o forma diferente. Cada una de ellas <xref:System.Windows.Media.PathFigure> se compone de uno o varios <xref:System.Windows.Media.PathSegment> objetos, cada uno de los cuales representa una parte conectada de la figura o forma. Entre los tipos de segmentos se incluyen los siguientes: <xref:System.Windows.Media.LineSegment> , <xref:System.Windows.Media.BezierSegment> y <xref:System.Windows.Media.ArcSegment> .  
  
 En el ejemplo siguiente, <xref:System.Windows.Shapes.Path> se utiliza una para dibujar una curva Bézier cuadrática.  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 La siguiente imagen muestra la forma representada.  
  
 ![Ilustración de trayecto](./media/shape-ovw-path2.gif "shape_ovw_path2")  
  
 Para obtener más información sobre <xref:System.Windows.Media.PathGeometry> y las demás <xref:System.Windows.Media.Geometry> clases, consulte [información general sobre geometría](geometry-overview.md).  
  
<a name="pathdatastring"></a>
### <a name="xaml-abbreviated-syntax"></a>Sintaxis abreviada de XAML  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , también puede usar una sintaxis abreviada especial para describir un <xref:System.Windows.Shapes.Path> . En el ejemplo siguiente, se utiliza la sintaxis abreviada para dibujar una forma compleja.  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 En la imagen siguiente se muestra una representación de <xref:System.Windows.Shapes.Path> .  
  
 ![Ilustración de trayecto](./media/shape-ovw-path.PNG "shape_ovw_path")  
  
 La <xref:System.Windows.Shapes.Path.Data%2A> cadena de atributo comienza con el comando "moveTo", indicado por M, que establece un punto de inicio para la ruta de acceso en el sistema de coordenadas de <xref:System.Windows.Controls.Canvas> . <xref:System.Windows.Shapes.Path>los parámetros de datos distinguen mayúsculas de minúsculas. La letra M mayúscula indica una ubicación absoluta para el nuevo punto actual. Una m minúscula indica coordenadas relativas. El primer segmento es una curva de Bézier cúbica que comienza en (100,200) y termina en (400,175), trazado con los dos puntos de control (100,25) y (400,350). Este segmento se indica mediante el comando C en la <xref:System.Windows.Shapes.Path.Data%2A> cadena de atributo. De nuevo, la C mayúscula indica una ruta de acceso absoluta; la c minúscula indicaría una ruta de acceso relativa.  
  
 El segundo segmento comienza con un comando H "lineto" horizontal absoluto, que especifica una línea trazada desde el punto de conexión del subtrazado anterior (400,175) hasta un nuevo punto de conexión (280,175). Dado que es un comando "lineTo" horizontal, el valor especificado es una coordenada *x*.  
  
 Para obtener la sintaxis de ruta de acceso completa, vea la <xref:System.Windows.Shapes.Path.Data%2A> referencia y [crear una forma mediante una PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  
  
<a name="fillpaint"></a>
## <a name="painting-shapes"></a>Pintar formas  
 <xref:System.Windows.Media.Brush>los objetos se utilizan para pintar una y una forma <xref:System.Windows.Shapes.Shape.Stroke%2A> <xref:System.Windows.Shapes.Shape.Fill%2A> . En el ejemplo siguiente, se especifican el trazo y el relleno de un <xref:System.Windows.Shapes.Ellipse> . Tenga en cuenta que una entrada válida para las propiedades del pincel puede ser una palabra clave o el valor de color en formato hexadecimal. Para obtener más información sobre las palabras clave de color disponibles, consulte propiedades de la <xref:System.Windows.Media.Colors> clase en el <xref:System.Windows.Media> espacio de nombres.  
  
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
  
 En la imagen siguiente se muestra la representación de <xref:System.Windows.Shapes.Ellipse> .  
  
 ![Elipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")  
  
 Como alternativa, puede usar la sintaxis de elementos de propiedad para crear explícitamente un <xref:System.Windows.Media.SolidColorBrush> objeto para pintar la forma con un color sólido.  
  
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
  
 También puede pintar el trazo o relleno de una forma con degradados, imágenes, patrones y mucho más. Para obtener más información, consulte la información [General sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="stretchableshapessection"></a>
## <a name="stretchable-shapes"></a>Formas extensibles  
 <xref:System.Windows.Shapes.Line>Todas las <xref:System.Windows.Shapes.Path> clases,, <xref:System.Windows.Shapes.Polygon> , <xref:System.Windows.Shapes.Polyline> y <xref:System.Windows.Shapes.Rectangle> tienen una <xref:System.Windows.Shapes.Shape.Stretch%2A> propiedad. Esta propiedad determina cómo <xref:System.Windows.Shapes.Shape> se ajusta el contenido de un objeto (la forma que se va a dibujar) para rellenar el <xref:System.Windows.Shapes.Shape> espacio de diseño del objeto. El <xref:System.Windows.Shapes.Shape> espacio de diseño de un objeto es la cantidad de espacio que el <xref:System.Windows.Shapes.Shape> sistema de diseño asigna a, debido a una <xref:System.Windows.FrameworkElement.Width%2A> configuración explícita y a la <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> configuración de y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> . Para obtener información adicional sobre el diseño en Windows Presentation Foundation, consulte información general de [diseño](../advanced/layout.md) .  
  
 La propiedad Stretch puede tener uno de los siguientes valores:  
  
- <xref:System.Windows.Media.Stretch.None>: El <xref:System.Windows.Shapes.Shape> contenido del objeto no se ajusta.  
  
- <xref:System.Windows.Media.Stretch.Fill>: El <xref:System.Windows.Shapes.Shape> contenido del objeto se ajusta para rellenar el espacio de diseño.  No se mantiene la relación de aspecto.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: El <xref:System.Windows.Shapes.Shape> contenido del objeto se ajusta tanto como sea posible para rellenar el espacio de diseño a la vez que conserva su relación de aspecto original.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: El <xref:System.Windows.Shapes.Shape> contenido del objeto se ajusta para rellenar completamente su espacio de diseño conservando su relación de aspecto original.  
  
 Tenga en cuenta que, cuando <xref:System.Windows.Shapes.Shape> se ajusta el contenido de un objeto, el <xref:System.Windows.Shapes.Shape> contorno del objeto se dibuja después de la ampliación.  
  
 En el ejemplo siguiente, <xref:System.Windows.Shapes.Polygon> se utiliza una para dibujar un triángulo muy pequeño de (0,0) a (0,1) a (1,1). Los <xref:System.Windows.Shapes.Polygon> objetos <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> se establecen en 100 y su propiedad Stretch está establecida en Fill. Como resultado, el <xref:System.Windows.Shapes.Polygon> contenido del objeto (el triángulo) se ajusta para rellenar el espacio mayor.  
  
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
 La <xref:System.Windows.Media.Transform> clase proporciona los medios para transformar las formas en un plano bidimensional.  Entre los distintos tipos de transformación se incluyen la rotación ( <xref:System.Windows.Media.RotateTransform> ), la escala ( <xref:System.Windows.Media.ScaleTransform> ), el sesgado ( <xref:System.Windows.Media.SkewTransform> ) y la traducción ( <xref:System.Windows.Media.TranslateTransform> ).  
  
 Una transformación común para aplicar a una forma es la rotación.  Para girar una forma, cree <xref:System.Windows.Media.RotateTransform> y especifique su <xref:System.Windows.Media.RotateTransform.Angle%2A> . Un <xref:System.Windows.Media.RotateTransform.Angle%2A> de 45 gira el elemento 45 grados en el sentido de las agujas del reloj; un ángulo de 90 gira el elemento 90 grados en el sentido de las agujas del reloj; etc. Establezca las <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades y si desea controlar el punto sobre el que se gira el elemento. Estos valores de propiedad se expresan en el espacio de coordenadas del elemento que se va a transformar. <xref:System.Windows.Media.RotateTransform.CenterX%2A>y <xref:System.Windows.Media.RotateTransform.CenterY%2A> tienen valores predeterminados de cero. Por último, aplique <xref:System.Windows.Media.RotateTransform> al elemento. Si no desea que la transformación afecte al diseño, establezca la propiedad de la forma <xref:System.Windows.UIElement.RenderTransform%2A> .  
  
 En el ejemplo siguiente, <xref:System.Windows.Media.RotateTransform> se usa un para girar una forma 45 grados sobre la esquina superior izquierda de la forma (0,0).  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 En el ejemplo siguiente, otra forma se gira 45 grados, pero esta vez se gira alrededor del punto (25,50).  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 En la ilustración siguiente se muestran los resultados de aplicar las dos transformaciones.  
  
 ![Rotaciones de 45 grados con diferentes centros](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
  
 En los ejemplos anteriores, se aplicó una única transformación a cada objeto de forma. Para aplicar varias transformaciones a una forma (o cualquier otro elemento de la interfaz de usuario), use <xref:System.Windows.Media.TransformGroup> .  
  
## <a name="see-also"></a>Vea también

- [Imágenes y gráficos 2D](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre geometría](geometry-overview.md)
- [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [Información general sobre animaciones](animation-overview.md)
