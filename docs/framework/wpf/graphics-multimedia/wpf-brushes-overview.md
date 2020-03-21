---
title: Visión general de los pinceles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 7a9474b392052900952f5b677ad94b16025de8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186578"
---
# <a name="wpf-brushes-overview"></a>Información general sobre pinceles de WPF
Todo lo visible en la pantalla es visible porque fue pintado por un pincel. Por ejemplo, un pincel se utiliza para describir el fondo de un botón, el primer plano del texto y el relleno de una forma. En este tema se presentan [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] los conceptos de pintura con pinceles y se proporcionan ejemplos. Los pinceles permiten pintar objetos [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con cualquier cosa, desde colores simples y sólidos hasta conjuntos complejos de patrones e imágenes.  
  
<a name="paintingwithbrush"></a>
## <a name="painting-with-a-brush"></a>Pintar con un pincel  
 Un <xref:System.Windows.Media.Brush> "pinta" un área con su salida. Distintos pinceles tienen tipos de salida diferentes. Algunos pinceles pintan un área con un color sólido, otros con un degradado, patrón, imagen o dibujo. En la ilustración siguiente se <xref:System.Windows.Media.Brush> muestran ejemplos de cada uno de los diferentes tipos.  
  
 ![Tipos de pincel](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Ejemplos de pinceles  
  
 La mayoría de los objetos visuales permiten especificar cómo se pintan. En la tabla siguiente se enumeran algunos objetos y propiedades comunes con los que puede utilizar un <xref:System.Windows.Media.Brush>archivo .  
  
|Clase|Propiedades de pincel|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 En las secciones <xref:System.Windows.Media.Brush> siguientes se describen los diferentes tipos y se proporciona un ejemplo de cada uno.  
  
<a name="paintwithsolidcolorbrush"></a>
## <a name="paint-with-a-solid-color"></a>Pintar con un color sólido  
 Un <xref:System.Windows.Media.SolidColorBrush> pinta un área <xref:System.Windows.Media.Color>con un sólido . Hay una variedad de maneras de especificar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> de un <xref:System.Windows.Media.SolidColorBrush>: por ejemplo, puede especificar sus canales alfa, <xref:System.Windows.Media.Colors> rojo, azul y verde o utilizar uno de los colores predefinidos proporcionados por la clase.  
  
 En el ejemplo <xref:System.Windows.Media.SolidColorBrush> siguiente <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle>utiliza a para pintar el archivo . En la ilustración siguiente se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Un Rectangle pintado con un SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Para obtener más <xref:System.Windows.Media.SolidColorBrush> información acerca de la clase, consulte [Pintura con colores sólidos y detalles de degradados .](painting-with-solid-colors-and-gradients-overview.md)  
  
<a name="paintwithlineargradientbrush"></a>
## <a name="paint-with-a-linear-gradient"></a>Pintar con un degradado lineal  
 Un <xref:System.Windows.Media.LinearGradientBrush> pinta un área con un degradado lineal. Un degradado lineal combina dos o más colores en una línea, el eje de degradado. Los <xref:System.Windows.Media.GradientStop> objetos se utilizan para especificar los colores del degradado y sus posiciones.  
  
 En el ejemplo <xref:System.Windows.Media.LinearGradientBrush> siguiente <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle>utiliza a para pintar el archivo . En la ilustración siguiente se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Un Rectangle pintado con un LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Para obtener más <xref:System.Windows.Media.LinearGradientBrush> información acerca de la clase, consulte [Pintura con colores sólidos y detalles de degradados .](painting-with-solid-colors-and-gradients-overview.md)  
  
<a name="paintwithradialgradientbrush"></a>
## <a name="paint-with-a-radial-gradient"></a>Pintar con un degradado radial  
 Un <xref:System.Windows.Media.RadialGradientBrush> pinta un área con un degradado radial. Un degradado radial combina dos o más colores en un círculo. Al igual <xref:System.Windows.Media.LinearGradientBrush> que con <xref:System.Windows.Media.GradientStop> la clase, se utilizan objetos para especificar los colores en el degradado y sus posiciones.  
  
 En el ejemplo <xref:System.Windows.Media.RadialGradientBrush> siguiente <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle>utiliza a para pintar el archivo . En la ilustración siguiente se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Un Rectangle pintado con un RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Para obtener más <xref:System.Windows.Media.RadialGradientBrush> información acerca de la clase, consulte [Pintura con colores sólidos y detalles de degradados .](painting-with-solid-colors-and-gradients-overview.md)  
  
<a name="paintwithimage"></a>
## <a name="paint-with-an-image"></a>Pintar con una imagen  
 Un <xref:System.Windows.Media.ImageBrush> pinta un área <xref:System.Windows.Media.ImageSource>con un archivo .  
  
 En el ejemplo <xref:System.Windows.Media.ImageBrush> siguiente <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle>utiliza un para pintar el de un archivo . En la ilustración siguiente se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Un rectángulo pintado con una imagen  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Para obtener más <xref:System.Windows.Media.ImageBrush> información acerca de la clase, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>
## <a name="paint-with-a-drawing"></a>Pintar con un dibujo  
 Un <xref:System.Windows.Media.DrawingBrush> pinta un área <xref:System.Windows.Media.Drawing>con un . A <xref:System.Windows.Media.Drawing> puede contener formas, imágenes, texto y medios.  
  
 En el ejemplo <xref:System.Windows.Media.DrawingBrush> siguiente <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle>utiliza a para pintar el archivo . En la ilustración siguiente se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Un Rectangle pintado con un DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Para obtener más <xref:System.Windows.Media.DrawingBrush> información acerca de la clase, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>
## <a name="paint-with-a-visual"></a>Pintar con un visual  
 Un <xref:System.Windows.Media.VisualBrush> pinta un área <xref:System.Windows.Media.Visual> con un objeto. Entre los ejemplos <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Page>de <xref:System.Windows.Controls.MediaElement>objetos Visual se incluyen , , y . A <xref:System.Windows.Media.VisualBrush> también le permite proyectar contenido de una parte de la aplicación en otra área; es muy útil para crear efectos de reflexión y magnificar partes de la pantalla.  
  
 En el ejemplo <xref:System.Windows.Media.VisualBrush> siguiente <xref:System.Windows.Shapes.Shape.Fill%2A> se <xref:System.Windows.Shapes.Rectangle>utiliza a para pintar el archivo . En la ilustración siguiente se muestra el rectángulo pintado.  
  
 ![Rectángulo pintado mediante VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Un Rectangle pintado con un VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Para obtener más <xref:System.Windows.Media.VisualBrush> información acerca de la clase, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>
## <a name="paint-using-predefined-and-system-brushes"></a>Pintar con pinceles predefinidos y del sistema  
 Para mayor comodidad, Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona un conjunto de pinceles predefinidos y del sistema que puede usar para pintar objetos.  
  
- Para obtener una lista de los <xref:System.Windows.Media.Brushes> pinceles predefinidos disponibles, consulte la clase. Para obtener un ejemplo que muestra cómo utilizar un pincel predefinido, consulte [Pintar un área con un color sólido](how-to-paint-an-area-with-a-solid-color.md).  
  
- Para obtener una lista de los <xref:System.Windows.SystemColors> pinceles del sistema disponibles, consulte la clase. Para obtener un ejemplo, vea [Pintar un área con un pincel del sistema](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>
## <a name="common-brush-features"></a>Características comunes del pincel  
 <xref:System.Windows.Media.Brush>los objetos proporcionan una <xref:System.Windows.Media.Brush.Opacity%2A> propiedad que se puede utilizar para hacer que un pincel sea transparente o parcialmente transparente. Un <xref:System.Windows.Media.Brush.Opacity%2A> valor de 0 hace que <xref:System.Windows.Media.Brush.Opacity%2A> un pincel sea completamente transparente, mientras que un valor de 1 hace que un pincel sea completamente opaco. En el ejemplo <xref:System.Windows.Media.Brush.Opacity%2A> siguiente se <xref:System.Windows.Media.SolidColorBrush> utiliza la propiedad para hacer un 25 por ciento opaco.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Si el pincel contiene colores parcialmente transparentes, el valor de opacidad del color se combina mediante la multiplicación con el valor de opacidad del pincel. Por ejemplo, si un pincel tiene un valor de opacidad de 0,5 y un color utilizado en el pincel también tiene un valor de opacidad de 0,5, el color de salida tiene un valor de opacidad de 0,25.  
  
> [!NOTE]
> Es más eficaz cambiar el valor de opacidad de un pincel que cambiar la <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> opacidad de un elemento completo mediante su propiedad.  
  
 Puede rotar, escalar, sesgar y traducir el <xref:System.Windows.Media.Brush.Transform%2A> contenido <xref:System.Windows.Media.Brush.RelativeTransform%2A> de un pincel mediante sus propiedades o. Para obtener más información, consulte [Información general sobre la transformación de pinceles](brush-transformation-overview.md).  
  
 Debido a <xref:System.Windows.Media.Animation.Animatable> que <xref:System.Windows.Media.Brush> son objetos, los objetos se pueden animar. Para obtener más información, consulte [Información general sobre animaciones](animation-overview.md).  
  
<a name="freezable_features"></a>
### <a name="freezable-features"></a>Características de objeto Freezable  
 Dado que hereda <xref:System.Windows.Freezable> de <xref:System.Windows.Media.Brush> la clase, la <xref:System.Windows.Media.Brush> clase proporciona varias características especiales: los objetos se pueden declarar como [recursos,](../../../desktop-wpf/fundamentals/xaml-resources-define.md)compartir entre varios objetos y clonar. Además, <xref:System.Windows.Media.Brush> todos <xref:System.Windows.Media.VisualBrush> los tipos excepto se pueden hacer de solo lectura para mejorar el rendimiento y proteger los subprocesos.  
  
 Para obtener más información sobre <xref:System.Windows.Freezable> las diferentes características proporcionadas por los objetos, vea Información general sobre [objetos freezable](../advanced/freezable-objects-overview.md).  
  
 Para obtener más <xref:System.Windows.Media.VisualBrush> información sobre por <xref:System.Windows.Media.VisualBrush> qué los objetos no se pueden inmovilizar, consulte la página de tipos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable)
- [Ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
- [Ejemplo de ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Ejemplo de VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
- [Temas de información](brushes-how-to-topics.md)
- [Otras recomendaciones de rendimiento](../advanced/optimizing-performance-other-recommendations.md)
