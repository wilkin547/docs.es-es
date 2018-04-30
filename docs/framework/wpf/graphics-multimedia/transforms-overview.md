---
title: Información general sobre transformaciones
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e63b83ea455a342d5d3fedaee0ad7d1714e90998
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="transforms-overview"></a>Información general sobre transformaciones
Este tema describe cómo utilizar el [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> clases para girar, escalar, mover (trasladar) y sesgar <xref:System.Windows.FrameworkElement> objetos.  
  
  
<a name="whatIsATransformSection"></a>   
## <a name="what-is-a-transform"></a>¿Qué es una transformación?  
 Un <xref:System.Windows.Media.Transform> define cómo asignar o transformar, puntos de un espacio de coordenadas a otro espacio de coordenadas. Esta asignación se describe mediante una transformación <xref:System.Windows.Media.Matrix>, que es una colección de tres filas con tres columnas de <xref:System.Double> valores.  
  
> [!NOTE]
>  Windows Presentation Foundation (WPF) usa matrices de fila principal. Los vectores se expresan como vectores de fila, no como vectores de columna.  
  
 En la tabla siguiente se muestra la estructura de una matriz de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="a-2-d-transformation-matrix"></a>Matriz de transformación 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valor predeterminado: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valor predeterminado: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valor predeterminado: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valor predeterminado: 0.0|1.0|  
  
 Manipulando los valores de la matriz, puede girar, escalar, sesgar y mover (trasladar) un objeto. Por ejemplo, si cambia el valor de la primera columna de la tercera fila (la <xref:System.Windows.Media.Matrix.OffsetX%2A> valor) a 100, se puede usar para mover un objeto 100 unidades a lo largo del eje x. Si cambia a 3 el valor de la segunda columna de la segunda fila, puede usarlo para triplicar el alto actual de un objeto. Si cambia ambos valores, mueve el objeto 100 unidades a lo largo del eje X y ajusta su alto a un factor de 3. Dado que Windows Presentation Foundation (WPF) solo admite transformaciones afines, los valores de la columna derecha siempre son 0, 0, 1.  
  
 Aunque Windows Presentation Foundation (WPF) le permite manipular directamente los valores de matriz, también proporciona varias <xref:System.Windows.Media.Transform> clases que permiten transformar un objeto sin conocer cómo se configura la estructura subyacente de la matriz. Por ejemplo, el <xref:System.Windows.Media.ScaleTransform> clase le permite escalar un objeto estableciendo su <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades, en lugar de manipular una matriz de transformación. Del mismo modo, el <xref:System.Windows.Media.RotateTransform> clase le permite girar un objeto con solo establecer su <xref:System.Windows.Media.RotateTransform.Angle%2A> propiedad.  
  
<a name="transformClassesSection"></a>   
## <a name="transform-classes"></a>Clases Transform  
 Windows Presentation Foundation (WPF) proporciona la siguiente [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] <xref:System.Windows.Media.Transform> clases para las operaciones de transformación comunes:  
  
|Clase|Descripción|Ejemplo|Ilustración|  
|-----------|-----------------|-------------|------------------|  
|<xref:System.Windows.Media.RotateTransform>|Gira un elemento especificado <xref:System.Windows.Media.RotateTransform.Angle%2A>.|[Girar un objeto](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)|![Ilustración de un giro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-rotate.png "graphicsmm_thumbnails_rotate")|  
|<xref:System.Windows.Media.ScaleTransform>|Amplía la escala de un elemento especificado <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> cantidades.|[Ajustar la escala de un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)|![Ilustración del ajuste de la escala](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-scale.png "graphicsmm_thumbnails_scale")|  
|<xref:System.Windows.Media.SkewTransform>|Sesga un elemento especificado <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> cantidades.|[Sesgar un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)|![Ilustración del sesgo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-skew.png "graphicsmm_thumbnails_skew")|  
|<xref:System.Windows.Media.TranslateTransform>|Mueve (traslada) un elemento según los valores especificados <xref:System.Windows.Media.TranslateTransform.X%2A> y <xref:System.Windows.Media.TranslateTransform.Y%2A> cantidades.|[Trasladar un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)|![Ilustración de un traslado](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-thumbnails-translate.png "graphicsmm_thumbnails_translate")|  
  
 Para crear transformaciones más complejas, Windows Presentation Foundation (WPF) proporciona las dos clases siguientes:  
  
|Clase|Descripción|Ejemplo|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Agrupa varias <xref:System.Windows.Media.TransformGroup> objetos en una sola <xref:System.Windows.Media.Transform> que, a continuación, se puede aplicar a propiedades de transformación.|[Aplicar varias transformaciones a un objeto](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea transformaciones personalizadas que no proceden de otro <xref:System.Windows.Media.Transform> clases. Cuando se usa un <xref:System.Windows.Media.MatrixTransform>, se manipula una matriz directamente.|[Utilizar un objeto MatrixTransform para crear transformaciones personalizadas](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 Windows Presentation Foundation (WPF) también proporciona [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] transformaciones. Para obtener más información, vea la clase <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## <a name="common-transformation-properties"></a>Propiedades de transformación comunes  
 Una manera de transformar un objeto consiste en declarar adecuado <xref:System.Windows.Media.Transform> escriba y aplicarlo a la propiedad de transformación del objeto. Los diferentes tipos de objetos tienen distintos tipos de propiedades de transformación. En la tabla siguiente se enumera varios tipos de Windows Presentation Foundation (WPF) utilizadas y sus propiedades de la transformación.  
  
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
 Al transformar un objeto, no solo transforma el objeto, se transformar el espacio de coordenadas en el que se encuentra. De forma predeterminada, una transformación tiene su centro en el origen del sistema de coordenadas del objeto de destino: (0,0). La única excepción es <xref:System.Windows.Media.TranslateTransform>; <xref:System.Windows.Media.TranslateTransform> no tiene ninguna propiedad center establecer porque el efecto de traslación es el mismo independientemente de dónde se centre.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RotateTransform> para girar una <xref:System.Windows.Shapes.Rectangle> elemento, un tipo de <xref:System.Windows.FrameworkElement>, 45 grados alrededor de su centro de manera predeterminada, (0, 0). En la ilustración siguiente se muestra el efecto de la rotación.  
  
 ![FrameworkElement girado 45 grados sobre &#40;0,0&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm_FE_rotated_about_upperleft_corner")  
Elemento Rectangle girado 45 grados alrededor del punto (0,0)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 De forma predeterminada, el elemento gira sobre su esquina superior izquierda, (0, 0). El <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.ScaleTransform>, y <xref:System.Windows.Media.SkewTransform> clases proporcionan propiedades CenterX y CenterY que permiten especificar el punto en el que se aplica la transformación.  
  
 El siguiente ejemplo se usa también un <xref:System.Windows.Media.RotateTransform> para girar una <xref:System.Windows.Shapes.Rectangle> elemento 45 grados; sin embargo, este momento la <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades se establecen para que el <xref:System.Windows.Media.RotateTransform> tiene un centro de (25, 25). En la ilustración siguiente se muestra el efecto de la rotación.  
  
 ![Geometría girada 45 grados alrededor del punto &#40;25, 25&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm_FE_rotated_about_center")  
Elemento Rectangle girado 45 grados alrededor del punto (25, 25)  
  
 [!code-xaml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## <a name="transforming-a-frameworkelement"></a>Transformación de un elemento FrameworkElement  
 Aplicar transformaciones a una <xref:System.Windows.FrameworkElement>, cree un <xref:System.Windows.Media.Transform> y aplicarla a una de las dos propiedades que la <xref:System.Windows.FrameworkElement> clase proporciona:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A> : Una transformación que se aplica antes de la fase de diseño. Después de aplicar la transformación, el sistema de diseño procesa el tamaño y la posición transformados del elemento.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A> : Una transformación que modifica la apariencia del elemento pero se aplica una vez completada la fase de diseño. Mediante el uso de la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad en lugar de la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> propiedad, puede obtener ventajas de rendimiento.  
  
 ¿Qué propiedad debe usar? Debido a las ventajas de rendimiento que proporciona, utilice la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad siempre que sea posible, especialmente cuando se usa anime <xref:System.Windows.Media.Transform> objetos. Use la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> propiedad al ajuste de escala, rotación o sesgar y necesita el elemento primario del elemento para ajustar al tamaño del elemento transformado. Tenga en cuenta que, cuando se usan con la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> propiedad <xref:System.Windows.Media.TranslateTransform> parece que no tienen ningún efecto en elementos de los objetos. Esto se debe a que el sistema de diseño devuelve el elemento trasladado a su posición original como parte de su procesamiento.  
  
 Para obtener información adicional acerca del diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], consulte la información general sobre [diseño](../../../../docs/framework/wpf/advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## <a name="example-rotate-a-frameworkelement-45-degrees"></a>Ejemplo: Girar un elemento FrameworkElement 45 grados  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RotateTransform> para girar un botón a la derecha 45 grados. El botón se encuentra en un <xref:System.Windows.Controls.StackPanel> que tiene otros dos botones.  
  
 De forma predeterminada, un <xref:System.Windows.Media.RotateTransform> rota alrededor del punto (0, 0). Puesto que el ejemplo no especifica un centro, el botón gira sobre el punto (0, 0), que está en la esquina superior izquierda. El <xref:System.Windows.Media.RotateTransform> se aplica a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado mediante RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm_RenderTransformWithDefaultCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj desde la esquina superior izquierda  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 El ejemplo siguiente también se usa un <xref:System.Windows.Media.RotateTransform> girar un botón 45 grados a la derecha, pero también establece la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en (0,5, 0,5). El valor de la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad es relativo al tamaño del botón. Como resultado, la rotación se aplica al centro del botón en lugar de a la esquina superior izquierda. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado alrededor de su centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm_RenderTransformRelativeCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj alrededor del centro  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.FrameworkElement.LayoutTransform%2A> propiedad en lugar de la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad que se va a girar el botón.  Esto hace que la transformación afecte al diseño del botón, lo que desencadena un recorrido completo del sistema de diseño. Como resultado, el botón se gira y se vuelve a cambiar de posición porque su tamaño ha cambiado. En la ilustración siguiente se muestra el resultado de la transformación.  
  
 ![Botón transformado mediante LayoutTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm_LayoutTransform")  
Propiedad LayoutTransform utilizada para girar el botón  
  
 [!code-xaml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## <a name="animating-transformations"></a>Animación de transformaciones  
 Dado que heredan de la <xref:System.Windows.Media.Animation.Animatable> (clase), el <xref:System.Windows.Media.Transform> clases se pueden animar. Animar un <xref:System.Windows.Media.Transform>, aplique una animación de un tipo compatible a la propiedad que desea animar.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.Storyboard> y un <xref:System.Windows.Media.Animation.DoubleAnimation> con un <xref:System.Windows.Media.RotateTransform> para realizar un <xref:System.Windows.Controls.Button> número en su lugar cuando se hace clic en.  
  
 [!code-xaml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](http://go.microsoft.com/fwlink/?LinkID=158252). Para más información sobre animaciones, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
## <a name="freezable-features"></a>Características de los objetos Freezable  
 Puesto que hereda de la <xref:System.Windows.Freezable> (clase), el <xref:System.Windows.Media.Transform> clase proporcionan varias características especiales: <xref:System.Windows.Media.Transform> objetos se pueden declarar como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md), compartir entre varios objetos, solo lectura para mejorar rendimiento, clonar y estará seguro para subprocesos. Para obtener más información sobre las diferentes características que se proporcionan con <xref:System.Windows.Freezable> los objetos, vea la [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Matrix>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [Ejemplo de transformaciones 2D](http://go.microsoft.com/fwlink/?LinkID=158252)
