---
title: Información general sobre transformaciones
ms.date: 03/30/2017
helpviewer_keywords:
- transformations [WPF], about transformations
- classes [WPF], 2-D transform
- transform classes [WPF], 2-D
- 2-D transform classes
- FrameworkElement objects [WPF], rotating
- FrameworkElement objects [WPF], skewing
- FrameworkElement objects [WPF], translating
- Transforms [WPF], about Transforms
- FrameworkElement objects [WPF], scaling
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
ms.openlocfilehash: ead1d114f773cba88e8b3e20f395019fbde3ee15
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458583"
---
# <a name="transforms-overview"></a>Información general sobre transformaciones
En este tema se describe cómo utilizar las clases de <xref:System.Windows.Media.Transform> 2D para girar, escalar, desplazar (trasladar) y sesgar objetos de <xref:System.Windows.FrameworkElement>.  

<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>¿Qué es una transformación?  
 Un <xref:System.Windows.Media.Transform> define cómo asignar, o transformar, puntos de un espacio de coordenadas a otro espacio de coordenadas. Esta asignación se describe mediante una transformación <xref:System.Windows.Media.Matrix>, que es una colección de tres filas con tres columnas de valores <xref:System.Double>.  
  
> [!NOTE]
> Windows Presentation Foundation (WPF) usa matrices de filas principales. Los vectores se expresan como vectores de fila, no como vectores de columna.  
  
 En la tabla siguiente se muestra la estructura de una matriz de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2-d-transformation-matrix"></a>Matriz de transformación 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valor predeterminado: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valor predeterminado: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valor predeterminado: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valor predeterminado: 0.0|1.0|  
  
 Manipulando los valores de la matriz, puede girar, escalar, sesgar y mover (trasladar) un objeto. Por ejemplo, si cambia el valor de la primera columna de la tercera fila (el valor <xref:System.Windows.Media.Matrix.OffsetX%2A>) a 100, puede utilizarlo para desplace un objeto 100 unidades a lo largo del eje x. Si cambia a 3 el valor de la segunda columna de la segunda fila, puede usarlo para triplicar el alto actual de un objeto. Si cambia ambos valores, mueve el objeto 100 unidades a lo largo del eje X y ajusta su alto a un factor de 3. Dado que Windows Presentation Foundation (WPF) solo admite transformaciones afines, los valores de la columna derecha siempre son 0, 0, 1.  
  
 Aunque Windows Presentation Foundation (WPF) permite manipular directamente los valores de la matriz, también proporciona varias clases <xref:System.Windows.Media.Transform> que permiten transformar un objeto sin saber cómo se configura la estructura de la matriz subyacente. Por ejemplo, la clase <xref:System.Windows.Media.ScaleTransform> permite escalar un objeto estableciendo sus propiedades <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>, en lugar de manipular una matriz de transformación. Del mismo modo, la clase <xref:System.Windows.Media.RotateTransform> permite girar un objeto simplemente estableciendo su propiedad <xref:System.Windows.Media.RotateTransform.Angle%2A>.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Clases Transform  
 Windows Presentation Foundation (WPF) proporciona las siguientes clases de <xref:System.Windows.Media.Transform> 2D para operaciones de transformación comunes:  
  
|Clase|Descripción|Ejemplo|Ilustración|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Gira un elemento por el <xref:System.Windows.Media.RotateTransform.Angle%2A>especificado.|[Girar un objeto](how-to-rotate-an-object.md)|![Girar ilustración](./media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Escala un elemento según las cantidades de <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> especificadas.|[Ajustar la escala de un elemento](how-to-scale-an-element.md)|![Ilustración de escala](./media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Sesga un elemento según las cantidades de <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> especificadas.|[Sesgar un elemento](how-to-skew-an-element.md)|![Ilustración de sesgo](./media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Mueve (traduce) un elemento según las cantidades de <xref:System.Windows.Media.TranslateTransform.X%2A> y <xref:System.Windows.Media.TranslateTransform.Y%2A> especificadas.|[Trasladar un elemento](how-to-translate-an-element.md)|![Traducir ilustración](./media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Para crear transformaciones más complejas, Windows Presentation Foundation (WPF) proporciona las dos clases siguientes:  
  
|Clase|Descripción|Ejemplo|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Agrupa varios objetos de <xref:System.Windows.Media.TransformGroup> en un solo <xref:System.Windows.Media.Transform> que se pueden aplicar a las propiedades de transformación.|[Aplicar varias transformaciones a un objeto](how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea transformaciones personalizadas que no proporcionan otras clases <xref:System.Windows.Media.Transform>. Cuando se usa un <xref:System.Windows.Media.MatrixTransform>, se manipula directamente una matriz.|[Utilizar un objeto MatrixTransform para crear transformaciones personalizadas](how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) también proporciona transformaciones 3D. Para obtener más información, vea la clase <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Propiedades de transformación comunes  
 Una manera de transformar un objeto es declarar el tipo de <xref:System.Windows.Media.Transform> adecuado y aplicarlo a la propiedad de transformación del objeto. Los diferentes tipos de objetos tienen distintos tipos de propiedades de transformación. En la tabla siguiente se enumeran varios tipos de Windows Presentation Foundation (WPF) usados comúnmente y sus propiedades de transformación.  
  
|Type|Propiedades de transformación|  
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
 Al transformar un objeto, no solo transforma el objeto, se transformar el espacio de coordenadas en el que se encuentra. De forma predeterminada, una transformación tiene su centro en el origen del sistema de coordenadas del objeto de destino: (0,0). La única excepción es <xref:System.Windows.Media.TranslateTransform>; un <xref:System.Windows.Media.TranslateTransform> no tiene propiedades de centro para establecer porque el efecto de traslación es el mismo independientemente de dónde se Centre.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RotateTransform> para girar un elemento <xref:System.Windows.Shapes.Rectangle>, un tipo de <xref:System.Windows.FrameworkElement>, de 45 grados sobre su centro predeterminado, (0,0). En la ilustración siguiente se muestra el efecto de la rotación.  
  
 ![FrameworkElement girado 45 grados alrededor de &#40;0,0&#41;](./media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Elemento Rectangle girado 45 grados alrededor del punto (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 De forma predeterminada, el elemento gira sobre su esquina superior izquierda, (0, 0). Las clases <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>y <xref:System.Windows.Media.SkewTransform> proporcionan propiedades CenterX y CenterY que permiten especificar el punto en el que se aplica la transformación.  
  
 En el ejemplo siguiente también se usa un <xref:System.Windows.Media.RotateTransform> para girar un elemento <xref:System.Windows.Shapes.Rectangle> en 45 grados; sin embargo, esta vez se establecen las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> para que el <xref:System.Windows.Media.RotateTransform> tenga un centro de (25, 25). En la ilustración siguiente se muestra el efecto de la rotación.  
  
 ![Elemento Geometry girado 45 grados alrededor de &#40;25, 25&#41;](./media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Elemento Rectangle girado 45 grados alrededor del punto (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Transformación de un elemento FrameworkElement  
 Para aplicar transformaciones a un <xref:System.Windows.FrameworkElement>, cree un <xref:System.Windows.Media.Transform> y aplíquelo a una de las dos propiedades que proporciona la clase <xref:System.Windows.FrameworkElement>:  
  
- <xref:System.Windows.FrameworkElement.LayoutTransform%2A>: una transformación que se aplica antes de la fase de diseño. Después de aplicar la transformación, el sistema de diseño procesa el tamaño y la posición transformados del elemento.  
  
- <xref:System.Windows.UIElement.RenderTransform%2A>: una transformación que modifica la apariencia del elemento, pero se aplica una vez completado el paso de diseño. Mediante el uso de la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> en lugar de la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, puede obtener ventajas de rendimiento.  
  
 ¿Qué propiedad debe usar? Debido a las ventajas de rendimiento que proporciona, utilice la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> siempre que sea posible, especialmente cuando se utilizan objetos de <xref:System.Windows.Media.Transform> animados. Use la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> cuando escale, gire o sesgo y necesite el elemento primario del elemento para ajustarse al tamaño transformado del elemento. Tenga en cuenta que, cuando se usan con la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, los objetos <xref:System.Windows.Media.TranslateTransform> parecen no tener ningún efecto en los elementos. Esto se debe a que el sistema de diseño devuelve el elemento trasladado a su posición original como parte de su procesamiento.  
  
 Para obtener información adicional acerca del diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], consulte la información general sobre [diseño](../advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Ejemplo: Girar un elemento FrameworkElement 45 grados  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RotateTransform> para girar un botón en el sentido de las agujas del reloj por 45 grados. El botón está contenido en un <xref:System.Windows.Controls.StackPanel> que tiene otros dos botones.  
  
 De forma predeterminada, un <xref:System.Windows.Media.RotateTransform> gira sobre el punto (0,0). Puesto que el ejemplo no especifica un centro, el botón gira sobre el punto (0, 0), que está en la esquina superior izquierda. El <xref:System.Windows.Media.RotateTransform> se aplica a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A>. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado mediante RenderTransform](./media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj desde la esquina superior izquierda  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 En el ejemplo siguiente también se usa un <xref:System.Windows.Media.RotateTransform> para girar un botón 45 grados en el sentido de las agujas del reloj, pero también se establece el <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en (0,5, 0,5). El valor de la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> es relativo al tamaño del botón. Como resultado, la rotación se aplica al centro del botón en lugar de a la esquina superior izquierda. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado alrededor de su centro](./media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj alrededor del centro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 En el ejemplo siguiente se usa la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> en lugar de la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> para girar el botón.  Esto hace que la transformación afecte al diseño del botón, lo que desencadena un recorrido completo del sistema de diseño. Como resultado, el botón se gira y se vuelve a cambiar de posición porque su tamaño ha cambiado. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado mediante LayoutTransform](./media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Propiedad LayoutTransform utilizada para girar el botón  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animación de transformaciones  
 Dado que heredan de la clase <xref:System.Windows.Media.Animation.Animatable>, las clases de <xref:System.Windows.Media.Transform> se pueden animar. Para animar un <xref:System.Windows.Media.Transform>, aplique una animación de un tipo compatible a la propiedad que desee animar.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.Storyboard> y un <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.RotateTransform> para hacer que un <xref:System.Windows.Controls.Button> gire en su lugar cuando se hace clic en él.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252). Para más información sobre animaciones, vea [Información general sobre animaciones](animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Características de los objetos Freezable  
 Dado que hereda de la clase <xref:System.Windows.Freezable>, la clase <xref:System.Windows.Media.Transform> proporciona varias características especiales: los objetos <xref:System.Windows.Media.Transform> se pueden declarar como [recursos](../../../desktop-wpf/fundamentals/xaml-resources-define.md), compartirse entre varios objetos, convertirse en de solo lectura para mejorar el rendimiento, clonarse y hacerse seguro para subprocesos. Para obtener más información sobre las distintas características proporcionadas por <xref:System.Windows.Freezable> objetos, vea la [información general sobre objetos Freezable](../advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Matrix>
- [Temas "Cómo..."](transformations-how-to-topics.md)
- [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252)
