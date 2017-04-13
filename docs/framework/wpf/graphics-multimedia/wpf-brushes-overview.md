---
title: "Informaci&#243;n general sobre pinceles de WPF | Microsoft Docs"
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
  - "pinceles, acerca de los pinceles"
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre pinceles de WPF
Todo lo que aparece visible en la pantalla lo está porque lo ha pintado un pincel.  Por ejemplo, se utiliza un pincel para describir el fondo de un botón, el primer plano del texto y el relleno de una forma.  En este tema se introducen los conceptos relativos a pintar con los pinceles de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y se proporcionan ejemplos.  Los pinceles permiten pintar los objetos de una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con cualquier cosa desde simples colores sólidos hasta conjuntos complejos de tramas e imágenes.  
  
<a name="paintingwithbrush"></a>   
## Pintar con un pincel  
 Un objeto <xref:System.Windows.Media.Brush> \(pincel\), "pinta" un área con su salida.  Los distintos pinceles tienen tipos de salidas diferentes.  Algunos pinceles pintan una área con un color sólido, otros con un degradado, una trama, una imagen o un dibujo.  En la ilustración siguiente se muestran ejemplos de cada uno de los tipos de <xref:System.Windows.Media.Brush> diferentes.  
  
 ![Tipos de pincel](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.png "graphicsmm\_brushtypes")  
Ejemplos de pinceles  
  
 La mayoría de los objetos visuales permiten especificar cómo pintarlos.  En la tabla siguiente se muestra una lista de algunos objetos y propiedades comunes con los que puede utilizar un objeto <xref:System.Windows.Media.Brush>.  
  
|Clase|Propiedades de pincel|  
|-----------|---------------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 En las secciones siguientes se describen los distintos tipos de <xref:System.Windows.Media.Brush> y se proporciona un ejemplo de cada uno.  
  
<a name="paintwithsolidcolorbrush"></a>   
## Pintar con un color sólido  
 Un objeto <xref:System.Windows.Media.SolidColorBrush> pinta un área con un color \(<xref:System.Windows.Media.Color>\) sólido.  Existen varias maneras de especificar la propiedad <xref:System.Windows.Media.SolidColorBrush.Color%2A> de <xref:System.Windows.Media.SolidColorBrush>: por ejemplo, puede especificar sus canales alfa, rojo, azul y verde, o utilizar uno de los colores predefinidos proporcionados por la clase <xref:System.Windows.Media.Colors>.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.SolidColorBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle>.  En la siguiente ilustración se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm\_brush\_ovw\_solidcolorbrush")  
Rectángulo pintado mediante SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.SolidColorBrush>, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## Pintar con un degradado lineal  
 <xref:System.Windows.Media.LinearGradientBrush> pinta un área con un degradado lineal.  Un degradado lineal mezcla dos o más colores a lo largo de una línea, el eje de degradado.  Se utilizan objetos <xref:System.Windows.Media.GradientStop> para especificar los colores del degradado y sus posiciones.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.LinearGradientBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle>.  En la siguiente ilustración se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.png "graphicsmm\_brush\_ovw\_lineargradientbrush")  
Rectángulo pintado mediante LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.LinearGradientBrush>, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## Pintar con un degradado radial  
 <xref:System.Windows.Media.RadialGradientBrush> pinta un área con un degradado radial.  Un degradado radial mezcla dos o más colores a lo largo de un círculo.  Al igual que con la clase <xref:System.Windows.Media.LinearGradientBrush>, se utilizan objetos <xref:System.Windows.Media.GradientStop> para especificar los colores del degradado y sus posiciones.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.RadialGradientBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle>.  En la siguiente ilustración se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante RadialGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.png "graphicsmm\_brush\_ovw\_radialgradientbrush")  
Rectángulo pintado mediante RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.RadialGradientBrush>, vea [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## Pintar con una imagen  
 Un objeto <xref:System.Windows.Media.ImageBrush> pinta una área con un objeto <xref:System.Windows.Media.ImageSource>.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.ImageBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle>.  En la siguiente ilustración se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.png "graphicsmm\_brush\_ovw\_imagebrush")  
Rectángulo pintado mediante una imagen  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.ImageBrush>, vea [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## Pintar con un dibujo  
 Un objeto <xref:System.Windows.Media.DrawingBrush> pinta una área con un objeto <xref:System.Windows.Media.Drawing>.  Un objeto <xref:System.Windows.Media.Drawing> puede contener formas, imágenes, texto y multimedia.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.DrawingBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle>.  En la siguiente ilustración se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.png "graphicsmm\_brush\_ovw\_drawingbrush")  
Rectángulo pintado mediante DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.DrawingBrush>, vea [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## Pintar con un objeto visual  
 Un objeto <xref:System.Windows.Media.VisualBrush> pinta un área con un objeto <xref:System.Windows.Media.Visual>.  Algunos ejemplos de objetos visuales son <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page> y <xref:System.Windows.Controls.MediaElement>.  <xref:System.Windows.Media.VisualBrush> también permite proyectar el contenido de una parte de la aplicación en otra área; resulta muy útil para crear efectos de reflexión y para ampliar partes de la pantalla.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Windows.Media.VisualBrush> para pintar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un objeto <xref:System.Windows.Shapes.Rectangle>.  En la siguiente ilustración se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante VisualBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.png "graphicsmm\_brush\_ovw\_visualbrush")  
Rectángulo pintado mediante VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Para obtener más información sobre la clase <xref:System.Windows.Media.VisualBrush>, vea [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## Pintar mediante pinceles predefinidos y del sistema  
 Para mayor comodidad, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] proporciona un conjunto de pinceles predefinidos y del sistema que puede utilizar para pintar objetos.  
  
-   Para obtener una lista de pinceles predefinidos disponibles, consulte la clase <xref:System.Windows.Media.Brushes>.  Para obtener un ejemplo en que se muestra cómo utilizar un pincel predefinido, consulte [Pintar un área con un color sólido](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md).  
  
-   Para obtener una lista de pinceles del sistema disponibles, consulte la clase <xref:System.Windows.SystemColors>.  Para obtener un ejemplo, vea [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## Características comunes de los pinceles  
 Los objetos <xref:System.Windows.Media.Brush> proporcionan una propiedad <xref:System.Windows.Media.Brush.Opacity%2A> que se puede utilizar para que un pincel sea transparente total o parcialmente.  Un valor de <xref:System.Windows.Media.Brush.Opacity%2A> de 0 hace que el pincel sea completamente transparente, mientras que un valor de <xref:System.Windows.Media.Brush.Opacity%2A> de 1 lo hace totalmente opaco.  En el ejemplo siguiente se utiliza la propiedad <xref:System.Windows.Media.Brush.Opacity%2A> para hacer que un objeto <xref:System.Windows.Media.SolidColorBrush> tenga una opacidad del 25 por ciento.  
  
 [!code-xml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Si el pincel contiene colores que son parcialmente transparentes, el valor de opacidad del color se combina por multiplicación con el valor de opacidad del pincel.  Por ejemplo, si un pincel tiene un valor de opacidad de 0,5 y un color utilizado en el pincel también tiene un valor de opacidad de 0,5, el color de salida tiene un valor de opacidad de 0,25.  
  
> [!NOTE]
>  Es más eficaz cambiar el valor de opacidad de un pincel que modificar la opacidad de un elemento completo mediante su propiedad <xref:System.Windows.UIElement.Opacity%2A?displayProperty=fullName>.  
  
 El contenido de los pinceles se puede girar, sesgar y convertir, y se puede ajustar su escala, mediante las propiedades <xref:System.Windows.Media.Brush.Transform%2A> o <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  Para obtener más información, consulte [Información general sobre la transformación de pinceles](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Al tratarse de objetos <xref:System.Windows.Media.Animation.Animatable>, los objetos <xref:System.Windows.Media.Brush> se pueden animar.  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
### Características de elementos Freezable  
 Al heredar de la clase <xref:System.Windows.Freezable>, la clase <xref:System.Windows.Media.Brush> proporciona varias características especiales: los objetos <xref:System.Windows.Media.Brush> pueden declararse como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md), compartirse entre varios objetos y clonarse.  Además, todos los tipos de <xref:System.Windows.Media.Brush>, con excepción de <xref:System.Windows.Media.VisualBrush>, pueden hacerse de sólo lectura para mejorar el rendimiento y que sean seguros para subprocesos.  
  
 Para obtener más información acerca de las diferentes características que proporcionan los objetos <xref:System.Windows.Freezable>, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Para obtener más información sobre los motivos que impiden inmovilizar los objetos <xref:System.Windows.Media.VisualBrush>, consulte la página del tipo <xref:System.Windows.Media.VisualBrush>.  
  
## Vea también  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.Brushes>   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Ejemplo Brushes](http://go.microsoft.com/fwlink/?LinkID=159973)   
 [Ejemplo ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [Ejemplo VisualBrush](http://go.microsoft.com/fwlink/?LinkID=160049)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)