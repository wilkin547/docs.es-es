---
title: Información general sobre la transformación de pinceles
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 1d3a56014e0975f3616b7f90021b4290ced5daab
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453135"
---
# <a name="brush-transformation-overview"></a>Información general sobre la transformación de pinceles
La clase Brush proporciona dos propiedades de transformación: <xref:System.Windows.Media.Brush.Transform%2A> y <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Las propiedades permiten girar, escalar, sesgar y trasladar el contenido de un pincel. En este tema se describen las diferencias entre estas dos propiedades y proporciona ejemplos de su uso.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Para entender este tema, debe entender las características del pincel que se va a transformar. Para obtener <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush>, consulte la [información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md). Por <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>o <xref:System.Windows.Media.VisualBrush>, vea [pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md). También debe estar familiarizado con las transformaciones 2D descritas en [Información general sobre transformaciones](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Diferencias entre las propiedades Transform y RelativeTransform  
 Al aplicar una transformación a la propiedad <xref:System.Windows.Media.Brush.Transform%2A> de un pincel, debe conocer el tamaño del área pintada si desea transformar el contenido del pincel sobre su centro. Supongamos que el área pintada tiene 200 píxeles independientes del dispositivo de ancho y 150 de alto.  Si ha usado una <xref:System.Windows.Media.RotateTransform> para rotar la salida del pincel 45 grados sobre su centro, deberá asignar a la <xref:System.Windows.Media.RotateTransform> un <xref:System.Windows.Media.RotateTransform.CenterX%2A> de 100 y un <xref:System.Windows.Media.RotateTransform.CenterY%2A> de 75.  
  
 Al aplicar una transformación a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> de un pincel, esa transformación se aplica al pincel antes de que su salida se asigne al área pintada. En la lista siguiente se describe el orden en el que se procesan y transforman los contenidos de un pincel.  
  
1. Procese el contenido del pincel. Para un <xref:System.Windows.Media.GradientBrush>, esto significa determinar el área de degradado. Para un <xref:System.Windows.Media.TileBrush>, el <xref:System.Windows.Media.TileBrush.Viewbox%2A> se asigna a la <xref:System.Windows.Media.TileBrush.Viewport%2A>. Esto se convierte en la salida del pincel.  
  
2. Proyecte la salida del pincel en el rectángulo de transformación de 1 x 1.  
  
3. Aplique el <xref:System.Windows.Media.Brush.RelativeTransform%2A>del pincel, si lo tiene.  
  
4. Proyecte la salida transformada en el área que se va a pintar.  
  
5. Aplique el <xref:System.Windows.Media.Transform>del pincel, si lo tiene.  
  
 Dado que el <xref:System.Windows.Media.Brush.RelativeTransform%2A> se aplica mientras la salida del pincel está asignada a un rectángulo de 1 x 1, los valores del centro de transformación y del desplazamiento parecen ser relativos. Por ejemplo, si ha usado una <xref:System.Windows.Media.RotateTransform> para girar la salida del pincel 45 grados sobre su centro, deberá asignar a la <xref:System.Windows.Media.RotateTransform> un <xref:System.Windows.Media.RotateTransform.CenterX%2A> de 0,5 y un <xref:System.Windows.Media.RotateTransform.CenterY%2A> de 0,5.  
  
 En la ilustración siguiente se muestra la salida de varios pinceles que se han girado en 45 grados mediante las propiedades <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Propiedades de RelativeTransform y Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Utilizar RelativeTransform con un objeto TileBrush  
 Dado que los pinceles de mosaico son más complejos que otros pinceles, aplicar un <xref:System.Windows.Media.Brush.RelativeTransform%2A> a uno podría producir resultados inesperados. Por ejemplo, veamos la imagen siguiente.  
  
 ![La imagen de origen](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush> para pintar un área rectangular con la imagen anterior. Aplica un <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> del objeto <xref:System.Windows.Media.ImageBrush> y establece su propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> en <xref:System.Windows.Media.Stretch.UniformToFill>, que debe conservar la relación de aspecto de la imagen cuando se ajusta para rellenar completamente el rectángulo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 En este ejemplo se produce la siguiente salida:  
  
 ![La salida transformada](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Observe que la imagen está distorsionada, aunque el <xref:System.Windows.Media.TileBrush.Stretch%2A> del pincel se haya establecido en <xref:System.Windows.Media.Stretch.UniformToFill>. Esto se debe a que la transformación relativa se aplica después de que la <xref:System.Windows.Media.TileBrush.Viewbox%2A> del pincel se asigna a su <xref:System.Windows.Media.TileBrush.Viewport%2A>. La lista siguiente describe cada paso del proceso:  
  
1. Proyectar el contenido del pincel (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) en su mosaico base (<xref:System.Windows.Media.TileBrush.Viewport%2A>) mediante el valor <xref:System.Windows.Media.TileBrush.Stretch%2A> del pincel.  
  
     ![Expandir Viewbox para que se ajuste a la ventanilla](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Proyecte el icono base del rectángulo de transformación de 1 x 1.  
  
     ![Asignar la ventanilla al rectángulo de transformación](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Aplique el <xref:System.Windows.Media.RotateTransform>.  
  
     ![Aplicar la transformación relativa](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Proyecte el icono base transformado en el área que se va a pintar.  
  
     ![Proyectar el pincel transformado en el área de salida](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Ejemplo: Girar un objeto ImageBrush 45 grados  
 En el ejemplo siguiente se aplica un <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> de una <xref:System.Windows.Media.ImageBrush>. Las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> del objeto <xref:System.Windows.Media.RotateTransform> se establecen en 0,5, las coordenadas relativas del punto central del contenido. Como resultado, el contenido del pincel se gira sobre su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 En el ejemplo siguiente también se aplica un <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Media.ImageBrush>, pero se usa la propiedad <xref:System.Windows.Media.Brush.Transform%2A> en lugar de la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Para girar el pincel sobre su centro, los <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> del objeto de la <xref:System.Windows.Media.RotateTransform> deben establecerse en coordenadas absolutas. Como el rectángulo pintado por el pincel es 175 por 90 píxeles, su punto central es (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 En la ilustración siguiente se muestra el pincel sin una transformación, con la transformación aplicada a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> y con la transformación aplicada a la propiedad <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Configuración de RelativeTransform y transformación de pincel](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Este ejemplo forma parte de un ejemplo mayor. Para ver el ejemplo completo, consulte el [ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Para más información, consulte [Información general sobre pinceles de WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre transformaciones](transforms-overview.md)
