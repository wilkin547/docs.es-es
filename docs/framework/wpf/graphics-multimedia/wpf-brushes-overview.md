---
title: Información general sobre pinceles de WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 967d0e67ed0ce106de291e1e47b7d72e06560342
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655964"
---
# <a name="wpf-brushes-overview"></a>Información general sobre pinceles de WPF
Todo lo visible en la pantalla está visible porque lo ha pintado por un pincel. Por ejemplo, se usa un pincel para el fondo de un botón, el primer plano del texto y el relleno de una forma de describir. Este tema presentan los conceptos de pintar con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pinceles y proporciona ejemplos. Los pinceles permiten pintar objetos [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con cualquier cosa, desde colores simples y sólidos hasta conjuntos complejos de patrones e imágenes.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Pintar con un pincel  
 Un <xref:System.Windows.Media.Brush> "pinta" un área con su salida. Pinceles diferentes tienen distintos tipos de salida. Algunos pinceles pintan un área con un color sólido, otras personas con un degradado, trama, imagen o dibujo. La siguiente ilustración muestra ejemplos de cada uno de los diferentes <xref:System.Windows.Media.Brush> tipos.  
  
 ![Tipos de pinceles](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Ejemplos de pincel  
  
 La mayoría de los objetos visuales permiten especificar cómo está dibujando. En la tabla siguiente se enumera algunos comunes objetos y propiedades que puede usar un <xref:System.Windows.Media.Brush>.  
  
|Clase|Propiedades de pincel|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Las secciones siguientes describen los diferentes <xref:System.Windows.Media.Brush> tipos y proporcionan un ejemplo de cada uno.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Pintar con un Color sólido  
 Un <xref:System.Windows.Media.SolidColorBrush> pinta un área con un sólido <xref:System.Windows.Media.Color>. Hay una gran variedad de formas de especificar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush>: por ejemplo, puede especificar sus canales alfabéticos, rojos, azules y verdes o use uno de los colores predefinidos proporcionados por el <xref:System.Windows.Media.Colors> clase.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.SolidColorBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>. La siguiente ilustración muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante SolidColorBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Rectángulo pintado mediante SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.SolidColorBrush> de clases, vea [el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Pintar con un degradado lineal  
 Un <xref:System.Windows.Media.LinearGradientBrush> pinta un área con un degradado lineal. Un degradado lineal que combina dos o más colores a través de una línea, el eje de degradado. Usa <xref:System.Windows.Media.GradientStop> objetos para especificar los colores del degradado y sus posiciones.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.LinearGradientBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>. La siguiente ilustración muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante LinearGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Rectángulo pintado mediante LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.LinearGradientBrush> de clases, vea [el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Pintar con un degradado Radial  
 Un <xref:System.Windows.Media.RadialGradientBrush> pinta un área con un degradado radial. Un degradado radial mezcla dos o más colores a lo largo de un círculo. Igual que con el <xref:System.Windows.Media.LinearGradientBrush> (clase), usa <xref:System.Windows.Media.GradientStop> objetos para especificar los colores del degradado y sus posiciones.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.RadialGradientBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>. La siguiente ilustración muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante RadialGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Rectángulo pintado mediante RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.RadialGradientBrush> de clases, vea [el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Pintar con una imagen  
 Un <xref:System.Windows.Media.ImageBrush> pinta un área con un <xref:System.Windows.Media.ImageSource>.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>. La siguiente ilustración muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Rectángulo pintado mediante una imagen  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.ImageBrush> de clases, vea [pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Pintar con un dibujo  
 Un <xref:System.Windows.Media.DrawingBrush> pinta un área con un <xref:System.Windows.Media.Drawing>. Un <xref:System.Windows.Media.Drawing> puede contener formas, imágenes, texto y multimedia.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>. La siguiente ilustración muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Rectángulo pintado mediante DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.DrawingBrush> de clases, vea [pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Pintar con un objeto Visual  
 Un <xref:System.Windows.Media.VisualBrush> pinta un área con un <xref:System.Windows.Media.Visual> objeto. Ejemplos de objetos visuales <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, y <xref:System.Windows.Controls.MediaElement>. Un <xref:System.Windows.Media.VisualBrush> también le permite proyectar el contenido de una parte de la aplicación en otra área; resulta muy útil para crear efectos de reflexión y ampliar partes de la pantalla.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.VisualBrush> para pintar el <xref:System.Windows.Shapes.Shape.Fill%2A> de un <xref:System.Windows.Shapes.Rectangle>. La siguiente ilustración muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante VisualBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Rectángulo pintado mediante VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.VisualBrush> de clases, vea [pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Pintar con pinceles del sistema y predefinida  
 Para mayor comodidad, Windows Presentation Foundation (WPF) proporciona predefinidos de un conjunto de y pinceles de sistema que puede utilizar para pintar objetos.  
  
-   Para obtener una lista de pinceles predefinidos disponibles, consulte el <xref:System.Windows.Media.Brushes> clase. Para obtener un ejemplo que muestra cómo utilizar un pincel predefinido, consulte [pintar un área con un Color sólido](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md).  
  
-   Para obtener una lista de los pinceles del sistema disponibles, consulte el <xref:System.Windows.SystemColors> clase. Para obtener un ejemplo, vea [pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Características comunes de pincel  
 <xref:System.Windows.Media.Brush> los objetos proporcionan una <xref:System.Windows.Media.Brush.Opacity%2A> propiedad que se puede usar para hacer que un pincel transparente o parcialmente transparentes. Un <xref:System.Windows.Media.Brush.Opacity%2A> valor de 0 hace que el pincel completamente transparente, mientras un <xref:System.Windows.Media.Brush.Opacity%2A> valor de 1 hace que un pincel sea completamente opaco. En el ejemplo siguiente se usa el <xref:System.Windows.Media.Brush.Opacity%2A> propiedad para hacer un <xref:System.Windows.Media.SolidColorBrush> opaco en un 25 por ciento.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Si el pincel contiene colores que son parcialmente transparentes, el valor de opacidad del color se combina a través de multiplicación con el valor de opacidad del pincel. Por ejemplo, si un pincel tiene un valor de opacidad de 0,5 y un color utilizado en el pincel también tiene un valor de opacidad de 0,5, el color de salida tiene un valor de opacidad de 0,25.  
  
> [!NOTE]
>  Resulta más eficaz para cambiar el valor de opacidad de un pincel de cambiar la opacidad de un elemento todo mediante su <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> propiedad.  
  
 Puede girar, escalar, sesgar y traducir el contenido de un pincel mediante su <xref:System.Windows.Media.Brush.Transform%2A> o <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedades. Para obtener más información, consulte [información general sobre la transformación de pinceles](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Porque son <xref:System.Windows.Media.Animation.Animatable> objetos, <xref:System.Windows.Media.Brush> objetos se pueden animar. Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Características de los objetos Freezable  
 Porque se hereda de la <xref:System.Windows.Freezable> (clase), el <xref:System.Windows.Media.Brush> clase proporciona varias características especiales: <xref:System.Windows.Media.Brush> objetos se pueden declarar como [recursos](../../../../docs/framework/wpf/advanced/xaml-resources.md), compartirse entre varios objetos y clonar. Además, todas las <xref:System.Windows.Media.Brush> tipos excepto <xref:System.Windows.Media.VisualBrush> puede ser de sólo lectura para mejorar el rendimiento y hacerse seguros para subprocesos.  
  
 Para obtener más información sobre las diferentes características proporcionadas por <xref:System.Windows.Freezable> objetos, vea [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Para obtener más información sobre por qué <xref:System.Windows.Media.VisualBrush> no pueden ser objetos inmovilizados, consulte la <xref:System.Windows.Media.VisualBrush> página tipo.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [Ejemplo de pinceles](https://go.microsoft.com/fwlink/?LinkID=159973)
- [Ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Ejemplo de VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)
- [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
