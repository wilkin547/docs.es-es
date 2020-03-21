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
ms.openlocfilehash: deac1be2fd19703055b76af8173111b4453f0d6b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186527"
---
# <a name="brush-transformation-overview"></a>Información general sobre la transformación de pinceles
La clase Brush proporciona <xref:System.Windows.Media.Brush.Transform%2A> dos <xref:System.Windows.Media.Brush.RelativeTransform%2A>propiedades de transformación: y . Las propiedades permiten girar, escalar, sesgar y trasladar el contenido de un pincel. En este tema se describen las diferencias entre estas dos propiedades y proporciona ejemplos de su uso.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe entender las características del pincel que se va a transformar. Para <xref:System.Windows.Media.LinearGradientBrush> <xref:System.Windows.Media.RadialGradientBrush>y , consulte la [Descripción general de la pintura con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md). Para <xref:System.Windows.Media.ImageBrush> <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush>, o , consulte [Pintura con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md). También debe estar familiarizado con las transformaciones 2D descritas en [Información general sobre transformaciones](transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Diferencias entre las propiedades Transform y RelativeTransform  
 Al aplicar una transformación a <xref:System.Windows.Media.Brush.Transform%2A> la propiedad de un pincel, debe conocer el tamaño del área pintada si desea transformar el contenido del pincel sobre su centro. Supongamos que el área pintada tiene 200 píxeles independientes del dispositivo de ancho y 150 de alto.  Si usaras <xref:System.Windows.Media.RotateTransform> a para girar la salida del pincel 45 grados <xref:System.Windows.Media.RotateTransform.CenterX%2A> alrededor de su <xref:System.Windows.Media.RotateTransform.CenterY%2A> centro, darías el <xref:System.Windows.Media.RotateTransform> a de 100 y un de 75.  
  
 Cuando se aplica una transformación <xref:System.Windows.Media.Brush.RelativeTransform%2A> a la propiedad de un pincel, esa transformación se aplica al pincel antes de que su salida se asigne al área pintada. En la lista siguiente se describe el orden en el que se procesan y transforman los contenidos de un pincel.  
  
1. Procese el contenido del pincel. Para <xref:System.Windows.Media.GradientBrush>un , esto significa determinar el área de degradado. Para <xref:System.Windows.Media.TileBrush>un <xref:System.Windows.Media.TileBrush.Viewbox%2A> , se <xref:System.Windows.Media.TileBrush.Viewport%2A>asigna al archivo . Esto se convierte en la salida del pincel.  
  
2. Proyecte la salida del pincel en el rectángulo de transformación de 1 x 1.  
  
3. Aplicar el <xref:System.Windows.Media.Brush.RelativeTransform%2A>pincel, si tiene uno.  
  
4. Proyecte la salida transformada en el área que se va a pintar.  
  
5. Aplicar el <xref:System.Windows.Media.Transform>pincel, si tiene uno.  
  
 Dado <xref:System.Windows.Media.Brush.RelativeTransform%2A> que se aplica mientras la salida del pincel se asigna a un rectángulo de 1 x 1, los valores de centro de transformación y desplazamiento parecen ser relativos. Por ejemplo, si <xref:System.Windows.Media.RotateTransform> utiliza a para girar la salida del pincel 45 <xref:System.Windows.Media.RotateTransform> grados alrededor de su centro, daría la a <xref:System.Windows.Media.RotateTransform.CenterX%2A> de 0,5 y una <xref:System.Windows.Media.RotateTransform.CenterY%2A> de 0,5.  
  
 La siguiente ilustración muestra la salida de varios pinceles que <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> se han girado 45 grados utilizando las propiedades y.  
  
 ![Propiedades RelativeTransform y Transform](./media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>
## <a name="using-relativetransform-with-a-tilebrush"></a>Utilizar RelativeTransform con un objeto TileBrush  
 Dado que los pinceles de mosaico son <xref:System.Windows.Media.Brush.RelativeTransform%2A> más complejos que otros pinceles, aplicar una a una puede producir resultados inesperados. Por ejemplo, veamos la imagen siguiente.  
  
 ![Imagen de origen](./media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 En el ejemplo <xref:System.Windows.Media.ImageBrush> siguiente se utiliza un para pintar un área rectangular con la imagen anterior. <xref:System.Windows.Media.RotateTransform> Aplica a la <xref:System.Windows.Media.ImageBrush> propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> del objeto y <xref:System.Windows.Media.TileBrush.Stretch%2A> establece <xref:System.Windows.Media.Stretch.UniformToFill>su propiedad en , que debe conservar la relación de aspecto de la imagen cuando se estira para rellenar completamente el rectángulo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 En este ejemplo se produce la siguiente salida:  
  
 ![Resultado transformado](./media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Observe que la imagen está distorsionada, <xref:System.Windows.Media.TileBrush.Stretch%2A> aunque <xref:System.Windows.Media.Stretch.UniformToFill>el pincel se haya establecido en . Esto se debe a que la transformación <xref:System.Windows.Media.TileBrush.Viewbox%2A> relativa se <xref:System.Windows.Media.TileBrush.Viewport%2A>aplica después de asignar el pincel a su archivo . La lista siguiente describe cada paso del proceso:  
  
1. Proyecte el contenido<xref:System.Windows.Media.TileBrush.Viewbox%2A>del pincel ( )<xref:System.Windows.Media.TileBrush.Viewport%2A>en su mosaico <xref:System.Windows.Media.TileBrush.Stretch%2A> base ( ) usando el ajuste del pincel.  
  
     ![Expandir Viewbox para que se ajuste a Viewport](./media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2. Proyecte el icono base del rectángulo de transformación de 1 x 1.  
  
     ![Asignar Viewport al rectángulo de transformación](./media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3. Aplique <xref:System.Windows.Media.RotateTransform>el archivo .  
  
     ![Aplicar la transformación relativa](./media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4. Proyecte el icono base transformado en el área que se va a pintar.  
  
     ![Proyectar el pincel transformado en el área de resultado](./media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Ejemplo: Girar un objeto ImageBrush 45 grados  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente <xref:System.Windows.Media.Brush.RelativeTransform%2A> se <xref:System.Windows.Media.ImageBrush>aplica a la propiedad de un archivo . Las <xref:System.Windows.Media.RotateTransform> propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> del objeto se establecen en 0,5, las coordenadas relativas del punto central del contenido. Como resultado, el contenido del pincel se gira sobre su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 En el ejemplo <xref:System.Windows.Media.RotateTransform> siguiente <xref:System.Windows.Media.ImageBrush>también se <xref:System.Windows.Media.Brush.Transform%2A> aplica un <xref:System.Windows.Media.Brush.RelativeTransform%2A> a un , pero utiliza la propiedad en lugar de la propiedad. Para girar el pincel alrededor <xref:System.Windows.Media.RotateTransform> de <xref:System.Windows.Media.RotateTransform.CenterX%2A> su <xref:System.Windows.Media.RotateTransform.CenterY%2A> centro, el objeto y debe establecerse en coordenadas absolutas. Como el rectángulo pintado por el pincel es 175 por 90 píxeles, su punto central es (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 En la ilustración siguiente se muestra el pincel <xref:System.Windows.Media.Brush.RelativeTransform%2A> sin transformación, con <xref:System.Windows.Media.Brush.Transform%2A> la transformación aplicada a la propiedad y con la transformación aplicada a la propiedad.  
  
 ![Valores de Brush RelativeTransform y Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Este ejemplo forma parte de un ejemplo mayor. Para ver el ejemplo completo, consulte la [muestra Pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Para más información, consulte [Información general sobre pinceles de WPF](wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Brush.Transform%2A>
- <xref:System.Windows.Media.Brush.RelativeTransform%2A>
- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.Brush>
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
- [Información general sobre transformaciones](transforms-overview.md)
