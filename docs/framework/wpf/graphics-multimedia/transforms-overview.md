---
title: "Informaci&#243;n general sobre transformaciones | Microsoft Docs"
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
  - "clases de transformación 2D"
  - "clases, transformación 2D"
  - "FrameworkElement (objetos), rotar"
  - "FrameworkElement (objetos), ajustar la escala"
  - "FrameworkElement (objetos), inclinación"
  - "FrameworkElement (objetos), conversión"
  - "clases de transformación, 2D"
  - "transformaciones, acerca de las transformaciones"
  - "Transformaciones, acerca de las transformaciones"
ms.assetid: 8f153d5e-ed61-4aa5-a7cd-286f0c427a13
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Informaci&#243;n general sobre transformaciones
En este tema se describe cómo usar las clases <xref:System.Windows.Media.Transform> [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] para girar, escalar, mover \(trasladar\) y sesgar objetos <xref:System.Windows.FrameworkElement>.  
  
   
  
<a name="whatIsATransformSection"></a>   
## ¿Qué es una transformación?  
 Un elemento <xref:System.Windows.Media.Transform> define cómo asignar, o transformar, puntos de un espacio de coordenadas a otro espacio de coordenadas.  Esta asignación se describe mediante una estructura <xref:System.Windows.Media.Matrix> de transformación, que es una colección de tres filas con tres columnas de valores <xref:System.Double>.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] usa matrices por filas.  Los vectores se expresan como vectores de fila, no como vectores de columna.  
  
 En la tabla siguiente se muestra la estructura de una matriz de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Matriz de transformación 2D  
  
||||  
|-|-|-|  
|<xref:System.Windows.Media.Matrix.M11%2A><br /><br /> Valor predeterminado: 1.0|<xref:System.Windows.Media.Matrix.M12%2A><br /><br /> Valor predeterminado: 0.0|0.0|  
|<xref:System.Windows.Media.Matrix.M21%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.M22%2A><br /><br /> Valor predeterminado: 1.0|0.0|  
|<xref:System.Windows.Media.Matrix.OffsetX%2A><br /><br /> Valor predeterminado: 0.0|<xref:System.Windows.Media.Matrix.OffsetY%2A><br /><br /> Valor predeterminado: 0.0|1.0|  
  
 Manipulando los valores de la matriz, puede girar, escalar, sesgar y mover \(trasladar\) un objeto.  Por ejemplo, si cambia a 100 el valor de la primera columna de la tercera fila \(el valor de <xref:System.Windows.Media.Matrix.OffsetX%2A>\), puede usarlo para mover un objeto 100 unidades a lo largo del eje X.  Si cambia a 3 el valor de la segunda columna de la segunda fila, puede usarlo para triplicar el alto actual de un objeto.  Si cambia ambos valores, mueve el objeto 100 unidades a lo largo del eje X y ajusta su alto a un factor de 3.  Dado que [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] solo admite transformaciones afines, los valores de la columna derecha siempre son 0, 0, 1.  
  
 Aunque [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] permite manipular directamente los valores de matriz, también proporciona varias clases <xref:System.Windows.Media.Transform> que permiten transformar un objeto sin conocer cómo se configura la estructura de matriz subyacente.  Por ejemplo, la clase <xref:System.Windows.Media.ScaleTransform> permite escalar un objeto estableciendo sus propiedades <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A>, en lugar de manipulando una matriz de transformación.  Del mismo modo, la clase <xref:System.Windows.Media.RotateTransform> permite girar un objeto con solo establecer su propiedad <xref:System.Windows.Media.RotateTransform.Angle%2A>.  
  
<a name="transformClassesSection"></a>   
## Clases de transformación  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] proporciona las siguientes clases <xref:System.Windows.Media.Transform> [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] para las operaciones comunes de transformación:  
  
|Clase|Descripción|Ejemplo|Ilustración|  
|-----------|-----------------|-------------|-----------------|  
|<xref:System.Windows.Media.RotateTransform>|Gira un elemento el valor de <xref:System.Windows.Media.RotateTransform.Angle%2A>especificado.|[Girar un objeto](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object.md)||  
|<xref:System.Windows.Media.ScaleTransform>|Escala un elemento usando los valores de <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> especificados.|[Ajustar la escala de un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-scale-an-element.md)||  
|<xref:System.Windows.Media.SkewTransform>|Sesga un elemento los valores de <xref:System.Windows.Media.SkewTransform.AngleX%2A> y <xref:System.Windows.Media.SkewTransform.AngleY%2A> especificados.|[Sesgar un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-skew-an-element.md)||  
|<xref:System.Windows.Media.TranslateTransform>|Mueve \(traslada\) un elemento los valores de <xref:System.Windows.Media.TranslateTransform.X%2A> y <xref:System.Windows.Media.TranslateTransform.Y%2A> especificados.|[Trasladar un elemento](../../../../docs/framework/wpf/graphics-multimedia/how-to-translate-an-element.md)||  
  
 Para crear transformaciones más complejas, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] proporciona las dos clases siguientes:  
  
|Clase|Descripción|Ejemplo|  
|-----------|-----------------|-------------|  
|<xref:System.Windows.Media.TransformGroup>|Agrupa varios objetos <xref:System.Windows.Media.TransformGroup> en un solo objeto <xref:System.Windows.Media.Transform> que después se puede aplicar a propiedades de transformación.|[Aplicar varias transformaciones a un objeto](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-multiple-transforms-to-an-object.md)|  
|<xref:System.Windows.Media.MatrixTransform>|Crea transformaciones personalizadas que las otras clases <xref:System.Windows.Media.Transform> no proporcionan.  Cuando se usa una clase <xref:System.Windows.Media.MatrixTransform>, se manipula una matriz directamente.|[Utilizar un objeto MatrixTransform para crear transformaciones personalizadas](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-matrixtransform-to-create-custom-transforms.md)|  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] también proporciona transformaciones [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)].  Para obtener más información, vea la clase <xref:System.Windows.Media.Media3D.Transform3D>.  
  
<a name="transformationproperties"></a>   
## Propiedades comunes de transformación  
 Una manera de transformar un objeto consiste en declarar el tipo de <xref:System.Windows.Media.Transform> adecuado y aplicarlo a la propiedad de transformación del objeto.  Tipos de objetos diferentes tienen distintos tipos de propiedades de transformación.  En la tabla siguiente se enumeran varios tipos comunes de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] y sus propiedades de transformación.  
  
|Tipo|Propiedades de transformación|  
|----------|-----------------------------------|  
|<xref:System.Windows.Media.Brush>|<xref:System.Windows.Media.Brush.Transform%2A>, <xref:System.Windows.Media.Brush.RelativeTransform%2A>|  
|<xref:System.Windows.Media.ContainerVisual>|<xref:System.Windows.Media.ContainerVisual.Transform%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|  
|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.UIElement.RenderTransform%2A>, <xref:System.Windows.FrameworkElement.LayoutTransform%2A>|  
|<xref:System.Windows.Media.Geometry>|<xref:System.Windows.Media.Geometry.Transform%2A>|  
|<xref:System.Windows.Media.TextEffect>|<xref:System.Windows.Media.TextEffect.Transform%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.RenderTransform%2A>|  
  
<a name="transformcenter"></a>   
## Transformaciones y sistemas de coordenadas  
 Cuando se transforma un objeto, no solo se transforma el objeto, sino también el espacio de coordenadas en que se encuentra.  De forma predeterminada, una transformación se centra en el origen del sistema de coordenadas del objeto de destino: \(0,0\).  La única excepción es <xref:System.Windows.Media.TranslateTransform>; un elemento <xref:System.Windows.Media.TranslateTransform> no tiene propiedades de centrado que se puedan establecer porque el efecto de traslación es el mismo con independencia de dónde se centre.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.RotateTransform> para girar un elemento <xref:System.Windows.Shapes.Rectangle> \(un tipo de <xref:System.Windows.FrameworkElement>\) 45 grados sobre su centro predeterminado \(0,0\).  En la siguiente ilustración se muestra el efecto del giro.  
  
 ![FrameworkElement girado 45 grados alrededor del punto &#40;0,0&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-upperleft-corner.png "graphicsmm\_FE\_rotated\_about\_upperleft\_corner")  
Elemento Rectangle girado 45 grados alrededor del punto \(0,0\)  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedabouttopleft)]  
  
 De manera predeterminada, el elemento gira sobre su esquina superior izquierda, \(0, 0\).  Las clases <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform> y <xref:System.Windows.Media.ScaleTransform> proporcionan propiedades CenterX y CenterY que permiten especificar el punto en el que se aplica la transformación.  
  
 En el ejemplo siguiente se usa también una clase <xref:System.Windows.Media.RotateTransform> para girar un elemento <xref:System.Windows.Shapes.Rectangle> 45 grados; sin embargo, en esta ocasión, las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> se establecen de tal forma que <xref:System.Windows.Media.RotateTransform> tiene un centro de \(25,25\).  En la siguiente ilustración se muestra el efecto del giro.  
  
 ![Geometría girada 45 grados alrededor del punto &#40;25, 25&#41;](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-fe-rotated-about-center.png "graphicsmm\_FE\_rotated\_about\_center")  
Elemento Rectangle girado 45 grados alrededor del punto \(25, 25\)  
  
 [!code-xml[Transforms_snip#TransformsFERotatedAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/CoordinateSystemExample.xaml#transformsferotatedaboutcenter)]  
  
<a name="layoutTransformsAndRenderTransformsSection"></a>   
## Transformar FrameworkElement  
 Para aplicar transformaciones a un objeto <xref:System.Windows.FrameworkElement>, cree un elemento <xref:System.Windows.Media.Transform> y aplíquelo a una de las dos propiedades que proporciona la clase <xref:System.Windows.FrameworkElement>:  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A>: transformación que se aplica antes del paso de diseño.  Una vez aplicada la transformación, el sistema de diseño procesa el tamaño y la posición transformados del elemento.  
  
-   <xref:System.Windows.UIElement.RenderTransform%2A>: transformación que modifica la apariencia del elemento pero se aplica una vez completado el paso de diseño.  El uso de la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> en lugar de la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, permite obtener ventajas de rendimiento.  
  
 ¿Qué propiedad debo utilizar?  Dadas las ventajas de rendimiento que proporciona, utilice la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> siempre que sea posible, especialmente cuando use objetos <xref:System.Windows.Media.Transform> animados.  Utilice la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> al escalar, girar o sesgar si necesita que el elemento primario del elemento se ajuste al tamaño transformado del elemento.  Tenga en cuenta que, cuando se utilizan con la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A>, los objetos <xref:System.Windows.Media.TranslateTransform> parecen no tener ningún efecto en los elementos.  Eso se debe a que el sistema de diseño devuelve el elemento trasladado a su posición original como parte de su procesamiento.  
  
 Para obtener más información sobre el diseño en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], vea la información general de [Diseño](../../../../docs/framework/wpf/advanced/layout.md).  
  
<a name="exampleRotateAnElement45degSection"></a>   
## Ejemplo: Girar FrameworkElement 45 grados  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.RotateTransform> para girar un botón 45 grados en el sentido de las agujas del reloj.  El botón está incluido en un objeto <xref:System.Windows.Controls.StackPanel> que tiene otros dos botones.  
  
 De forma predeterminada, un objeto <xref:System.Windows.Media.RotateTransform>gira alrededor del punto \(0, 0\).  Como en el ejemplo no se especifica un valor central, el botón gira alrededor del punto \(0, 0\), que es su esquina superior izquierda.  El objeto <xref:System.Windows.Media.RotateTransform> se aplica a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A>.  La ilustración siguiente muestra el resultado de la transformación.  
  
 ![Botón transformado mediante RenderTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj desde la esquina superior izquierda  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 En el ejemplo siguiente se usa también un objeto <xref:System.Windows.Media.RotateTransform> para girar un botón 45 grados en el sentido de las agujas del reloj, pero también se establece la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> del botón en \(0,5, 0,5\).  El valor de la propiedad <xref:System.Windows.UIElement.RenderTransformOrigin%2A> es relativo al tamaño del botón.  Como consecuencia, la rotación se aplica al centro del botón, en lugar de a su esquina superior izquierda.  La ilustración siguiente muestra el resultado de la transformación.  
  
 ![Botón transformado alrededor de su centro](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
Rotación de 45 grados en el sentido de las agujas del reloj alrededor del centro  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.FrameworkElement.LayoutTransform%2A> en lugar de la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> para girar el botón.  Esto hace que la transformación afecte al diseño del botón, con lo que el sistema de diseño realiza un paso completo.  Como consecuencia, se gira el botón y, después, cambia de posición porque su tamaño ha cambiado.  La ilustración siguiente muestra el resultado de la transformación.  
  
 ![Botón transformado mediante LayoutTransform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-layouttransform.png "graphicsmm\_LayoutTransform")  
Uso de LayoutTransform para girar el botón  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample3)]  
  
<a name="animate_transforms"></a>   
## Animar transformaciones  
 Dado que heredan de la clase <xref:System.Windows.Media.Animation.Animatable>, las clases <xref:System.Windows.Media.Transform> se pueden animar.  Para animar una clase <xref:System.Windows.Media.Transform>, aplique una animación de un tipo compatible a la propiedad que desea animar.  
  
 En el ejemplo siguiente se usan <xref:System.Windows.Media.Animation.Storyboard> y <xref:System.Windows.Media.Animation.DoubleAnimation> con <xref:System.Windows.Media.RotateTransform> para hacer que un <xref:System.Windows.Controls.Button> vaya girando hasta alcanzar su posición al hacer clic en él.  
  
 [!code-xml[Transforms_snip#GraphicsMMAnimatedRotateButtonExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonAnimatedRotateTransformExample.xaml#graphicsmmanimatedrotatebuttonexamplewholepage)]  
  
 Para obtener el ejemplo completo, vea [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  Para obtener más información sobre animaciones, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
## Características de elementos Freezable  
 Como hereda de la clase <xref:System.Windows.Freezable>, la clase <xref:System.Windows.Media.Transform> proporciona varias características especiales: los objetos <xref:System.Windows.Media.Transform> pueden declararse como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md), compartirse entre varios objetos, convertirse en objetos de sólo lectura para mejorar el rendimiento, clonarse y convertirse en seguros para subprocesos.  Para obtener más información sobre las diferentes características que proporcionan los objetos <xref:System.Windows.Freezable>, vea [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Matrix>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [Ejemplo 2\-D Transforms](http://go.microsoft.com/fwlink/?LinkID=158252)