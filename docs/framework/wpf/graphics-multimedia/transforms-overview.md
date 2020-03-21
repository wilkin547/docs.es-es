---
title: Información general sobre transformaciones
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2D transform
- transform classes [WPF], 2D
- 2D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: c5f29404a301eb023ff24b2890531dede6440ec4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111964"
---
# <a name="transforms-overview"></a>Información general sobre transformaciones
En este tema se describe <xref:System.Windows.Media.Transform> cómo utilizar las clases 2D <xref:System.Windows.FrameworkElement> para rotar, escalar, mover (traducir) y sesgar objetos.  

<a name="whatIsATransformSection"></a>
## <a name="what-is-a-transform"></a>¿Qué es una transformación?  
 A <xref:System.Windows.Media.Transform> define cómo asignar o transformar puntos de un espacio de coordenadas a otro espacio de coordenadas. Esta asignación se <xref:System.Windows.Media.Matrix>describe mediante una transformación, que <xref:System.Double> es una colección de tres filas con tres columnas de valores.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) usa matrices principales de fila. Los vectores se expresan como vectores de fila, no como vectores de columna.  
  
 En la tabla siguiente se muestra la estructura de una matriz de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2d-transformation-matrix"></a>Una matriz de transformación 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valor predeterminado: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valor predeterminado: 0.0|0,0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valor predeterminado: 1.0|0,0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valor predeterminado: 0.0|1.0|  
  
 Manipulando los valores de la matriz, puede girar, escalar, sesgar y mover (trasladar) un objeto. Por ejemplo, si cambia el valor de la primera <xref:System.Windows.Media.Matrix.OffsetX%2A> columna de la tercera fila (el valor) a 100, puede utilizarlo para mover un objeto 100 unidades a lo largo del eje X. Si cambia a 3 el valor de la segunda columna de la segunda fila, puede usarlo para triplicar el alto actual de un objeto. Si cambia ambos valores, mueve el objeto 100 unidades a lo largo del eje X y ajusta su alto a un factor de 3. Dado que Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) solo admite transformaciones afines, los valores de la columna derecha siempre son 0, 0, 1.  
  
 Aunque Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) permite manipular directamente los valores de matriz, también proporciona varias <xref:System.Windows.Media.Transform> clases que le permiten transformar un objeto sin saber cómo se configura la estructura de matriz subyacente. Por ejemplo, <xref:System.Windows.Media.ScaleTransform> la clase permite escalar un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> objeto estableciendo sus propiedades y, en lugar de manipular una matriz de transformación. Del mismo <xref:System.Windows.Media.RotateTransform> modo, la clase permite rotar <xref:System.Windows.Media.RotateTransform.Angle%2A> un objeto simplemente estableciendo su propiedad.  
  
<a name="transformClassesSection"></a>
## <a name="transform-classes"></a>Clases Transform  
 Windows Presentation Foundation (WPF)Windows <xref:System.Windows.Media.Transform> Presentation Foundation (WPF) proporciona las siguientes clases 2D para operaciones de transformación comunes:  
  
|Clase|Descripción|Ejemplo|Ilustración|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Gira un elemento por <xref:System.Windows.Media.RotateTransform.Angle%2A>el archivo .|[Girar un objeto](how-to-rotate-an-object.md)|![Girar ilustración](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Escala un elemento según <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> el especificado y los importes.|[Ajustar la escala de un elemento](how-to-scale-an-element.md)|![Ajustar escala de ilustración](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Sesga un elemento <xref:System.Windows.Media.SkewTransform.AngleX%2A> por <xref:System.Windows.Media.SkewTransform.AngleY%2A> los especificados y los importes.|[Sesgar un elemento](how-to-skew-an-element.md)|![Sesgar ilustración](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Mueve (traduce) un elemento por <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform.Y%2A> los especificados y los importes.|[Trasladar un elemento](how-to-translate-an-element.md)|![Trasladar ilustración](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Para crear transformaciones más complejas, Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona las dos clases siguientes:  
  
|Clase|Descripción|Ejemplo|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Agrupa <xref:System.Windows.Media.TransformGroup> varios objetos <xref:System.Windows.Media.Transform> en un único que, a continuación, puede aplicar para transformar propiedades.|[Aplicar varias transformaciones a un objeto](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea transformaciones personalizadas que no <xref:System.Windows.Media.Transform> son proporcionadas por las otras clases. Cuando se <xref:System.Windows.Media.MatrixTransform>utiliza un , se manipula una matriz directamente.|[Utilizar un objeto MatrixTransform para crear transformaciones personalizadas](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) también proporciona transformaciones 3D. Para obtener más información, vea la clase <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>
## <a name="common-transformation-properties"></a>Propiedades de transformación comunes  
 Una forma de transformar un objeto <xref:System.Windows.Media.Transform> es declarar el tipo adecuado y aplicarlo a la propiedad de transformación del objeto. Los diferentes tipos de objetos tienen distintos tipos de propiedades de transformación. En la tabla siguiente se enumeran varios tipos de Windows Presentation Foundation (WPF) de uso común y sus propiedades de transformación.  
  
|Tipo|Propiedades de transformación|  
|----------|-------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>
## <a name="transformations-and-coordinate-systems"></a>Transformaciones y sistemas de coordenadas  
 Al transformar un objeto, no solo transforma el objeto, se transformar el espacio de coordenadas en el que se encuentra. De forma predeterminada, una transformación tiene su centro en el origen del sistema de coordenadas del objeto de destino: (0,0). La única <xref:System.Windows.Media.TranslateTransform>excepción es ; a <xref:System.Windows.Media.TranslateTransform> no tiene propiedades de centro que establecer porque el efecto de traducción es el mismo independientemente de dónde esté centrado.  
  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente <xref:System.Windows.Shapes.Rectangle> se utiliza a <xref:System.Windows.FrameworkElement>para girar un elemento, un tipo de , por 45 grados sobre su centro predeterminado, (0, 0). En la ilustración siguiente se muestra el efecto de la rotación.  
  
 ![FrameworkElement girado 45 grados alrededor de &#40;0,0&#41;](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Elemento Rectangle girado 45 grados alrededor del punto (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 De forma predeterminada, el elemento gira sobre su esquina superior izquierda, (0, 0). Las <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.ScaleTransform>clases <xref:System.Windows.Media.SkewTransform> , , y CenterY proporcionan propiedades CenterX y CenterY que le permiten especificar el punto en el que se aplica la transformación.  
  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente también <xref:System.Windows.Shapes.Rectangle> se usa a para girar un elemento 45 grados; sin embargo, <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> esta vez las <xref:System.Windows.Media.RotateTransform> propiedades y se establecen de modo que el tiene un centro de (25, 25). En la ilustración siguiente se muestra el efecto de la rotación.  
  
 ![Elemento Geometry girado 45 grados alrededor de &#40;25, 25&#41;](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Elemento Rectangle girado 45 grados alrededor del punto (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>
## <a name="transforming-a-frameworkelement"></a>Transformación de un elemento FrameworkElement  
 Para aplicar transformaciones <xref:System.Windows.FrameworkElement>a <xref:System.Windows.Media.Transform> un , cree a y aplíquelo a una de las dos propiedades que proporciona la <xref:System.Windows.FrameworkElement> clase:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>– Una transformación que se aplica antes de que pase el diseño. Después de aplicar la transformación, el sistema de diseño procesa el tamaño y la posición transformados del elemento.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>– Una transformación que modifica la apariencia del elemento pero se aplica una vez completado el pase de diseño. Mediante el <xref:System.Windows.UIElement.RenderTransform%2A> uso de <xref:System.Windows.FrameworkElement.LayoutTransform%2A> la propiedad en lugar de la propiedad, puede obtener ventajas de rendimiento.  
  
 ¿Qué propiedad debe usar? Debido a las ventajas de <xref:System.Windows.UIElement.RenderTransform%2A> rendimiento que proporciona, utilice <xref:System.Windows.Media.Transform> la propiedad siempre que sea posible, especialmente cuando utilice objetos animados. Utilice <xref:System.Windows.FrameworkElement.LayoutTransform%2A> la propiedad al escalar, rotar o sesgar y necesita el elemento primario del elemento para ajustarse al tamaño transformado del elemento. Tenga en cuenta que, <xref:System.Windows.FrameworkElement.LayoutTransform%2A> cuando <xref:System.Windows.Media.TranslateTransform> se utilizan con la propiedad, los objetos parecen no tener ningún efecto sobre los elementos. Esto se debe a que el sistema de diseño devuelve el elemento trasladado a su posición original como parte de su procesamiento.  
  
 Para obtener información adicional acerca del diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], consulte la información general sobre [diseño](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Ejemplo: Girar un elemento FrameworkElement 45 grados  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente se utiliza a para girar un botón en el sentido de las agujas del reloj 45 grados. El botón está <xref:System.Windows.Controls.StackPanel> contenido en un que tiene otros dos botones.  
  
 De forma <xref:System.Windows.Media.RotateTransform> predeterminada, a gira alrededor del punto (0, 0). Puesto que el ejemplo no especifica un centro, el botón gira sobre el punto (0, 0), que está en la esquina superior izquierda. El <xref:System.Windows.Media.RotateTransform> se aplica <xref:System.Windows.UIElement.RenderTransform%2A> a la propiedad. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado mediante RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj desde la esquina superior izquierda  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 El siguiente ejemplo <xref:System.Windows.Media.RotateTransform> también utiliza a para girar un botón <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 45 grados en el sentido de las agujas del reloj, pero también establece el botón en (0,5, 0,5). El valor <xref:System.Windows.UIElement.RenderTransformOrigin%2A> de la propiedad es relativo al tamaño del botón. Como resultado, la rotación se aplica al centro del botón en lugar de a la esquina superior izquierda. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado alrededor de su centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj alrededor del centro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 En el ejemplo <xref:System.Windows.FrameworkElement.LayoutTransform%2A> siguiente se <xref:System.Windows.UIElement.RenderTransform%2A> utiliza la propiedad en lugar de la propiedad para girar el botón.  Esto hace que la transformación afecte al diseño del botón, lo que desencadena un recorrido completo del sistema de diseño. Como resultado, el botón se gira y se vuelve a cambiar de posición porque su tamaño ha cambiado. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado mediante LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Propiedad LayoutTransform utilizada para girar el botón  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>
## <a name="animating-transformations"></a>Animación de transformaciones  
 Dado que heredan de la <xref:System.Windows.Media.Animation.Animatable> clase, las <xref:System.Windows.Media.Transform> clases se pueden animar. Para animar <xref:System.Windows.Media.Transform>un , aplique una animación de un tipo compatible a la propiedad que desea animar.  
  
 En el ejemplo <xref:System.Windows.Media.Animation.Storyboard> siguiente <xref:System.Windows.Media.Animation.DoubleAnimation> se <xref:System.Windows.Media.RotateTransform> usa <xref:System.Windows.Controls.Button> a y a con a para hacer un giro en su lugar cuando se hace clic en él.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms). Para más información sobre animaciones, vea [Información general sobre animaciones](animation-overview.md).  
  
<a name="freezable_features"></a>
## <a name="freezable-features"></a>Características de objeto Freezable  
 Dado que hereda <xref:System.Windows.Freezable> de <xref:System.Windows.Media.Transform> la clase, la <xref:System.Windows.Media.Transform> clase proporciona varias características especiales: los objetos se pueden declarar como [recursos,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)compartirse entre varios objetos, hacer de solo lectura para mejorar el rendimiento, clonar y proteger los subprocesos. Para obtener más información acerca de <xref:System.Windows.Freezable> las diferentes características proporcionadas por los objetos, vea Información general sobre [objetos freezable](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Temas de información](transformations-how-to-topics.md)
- [Muestra de transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
