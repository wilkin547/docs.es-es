---
title: "Información general sobre la transformación de pinceles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa4a533594c1e89942406e7df0a49215e3885418
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="brush-transformation-overview"></a>Información general sobre la transformación de pinceles
La clase Brush proporciona dos propiedades de transformación: <xref:System.Windows.Media.Brush.Transform%2A> y <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Las propiedades permiten girar, escalar, sesgar y trasladar el contenido de un pincel. En este tema se describen las diferencias entre estas dos propiedades y proporciona ejemplos de su uso.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe entender las características del pincel que se va a transformar. Para <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush>, consulte el [pintar con colores sólidos y degradados información general sobre](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md). Para <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, o <xref:System.Windows.Media.VisualBrush>, consulte [pintar con imágenes, gráficos y objetos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md). También debe estar familiarizado con las transformaciones 2D descritas en [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Diferencias entre las propiedades Transform y RelativeTransform  
 Al aplicar una transformación a un pincel <xref:System.Windows.Media.Brush.Transform%2A> propiedad, debe conocer el tamaño del área de pintura si desea transformar el contenido del pincel sobre su centro. Supongamos que el área pintada tiene 200 píxeles independientes del dispositivo de ancho y 150 de alto.  Si ha usado un <xref:System.Windows.Media.RotateTransform> para girar el pincel el resultado de 45 grados alrededor de su centro, debe dar el <xref:System.Windows.Media.RotateTransform> una <xref:System.Windows.Media.RotateTransform.CenterX%2A> de 100 y un <xref:System.Windows.Media.RotateTransform.CenterY%2A> de 75.  
  
 Al aplicar una transformación a un pincel <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad, esa transformación se aplica al pincel antes de que su resultado se asigna al área de pintura. En la lista siguiente se describe el orden en el que se procesan y transforman los contenidos de un pincel.  
  
1.  Procese el contenido del pincel. Para una <xref:System.Windows.Media.GradientBrush>, esto significa determinar el área de degradado. Para una <xref:System.Windows.Media.TileBrush>, <xref:System.Windows.Media.TileBrush.Viewbox%2A> se asigna a la <xref:System.Windows.Media.TileBrush.Viewport%2A>. Esto se convierte en la salida del pincel.  
  
2.  Proyecte la salida del pincel en el rectángulo de transformación de 1 x 1.  
  
3.  Aplicar el pincel <xref:System.Windows.Media.Brush.RelativeTransform%2A>, si lo tiene.  
  
4.  Proyecte la salida transformada en el área que se va a pintar.  
  
5.  Aplicar el pincel <xref:System.Windows.Media.Transform>, si lo tiene.  
  
 Dado que el <xref:System.Windows.Media.Brush.RelativeTransform%2A> se aplica mientras la salida del pincel está asignada a un rectángulo de 1 x 1, el centro de transformación y los valores de desplazamiento parecen ser relativos. Por ejemplo, si ha usado un <xref:System.Windows.Media.RotateTransform> para girar el pincel el resultado de 45 grados alrededor de su centro, debe dar el <xref:System.Windows.Media.RotateTransform> una <xref:System.Windows.Media.RotateTransform.CenterX%2A> de 0,5 y un <xref:System.Windows.Media.RotateTransform.CenterY%2A> de 0,5.  
  
 En la siguiente ilustración muestra la salida de varios pinceles que se han girado 45 grados mediante la <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A> propiedades.  
  
 ![Propiedades RelativeTransform y Transform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>Utilizar RelativeTransform con un objeto TileBrush  
 Dado que son más complejos que los otros pinceles pinceles de mosaico, aplicar un <xref:System.Windows.Media.Brush.RelativeTransform%2A> a uno podría producir resultados inesperados. Por ejemplo, veamos la imagen siguiente.  
  
 ![La imagen de origen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.ImageBrush> para pintar un área rectangular a la imagen anterior. Se aplica un <xref:System.Windows.Media.RotateTransform> para el <xref:System.Windows.Media.ImageBrush> del objeto <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad y establece su <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad a <xref:System.Windows.Media.Stretch.UniformToFill>, que debe mantener la relación de aspecto de la imagen cuando se expande para llenar completamente el rectángulo.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Este ejemplo produce el siguiente resultado:  
  
 ![La salida transformada](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 Tenga en cuenta que la imagen se distorsiona, aunque el pincel <xref:System.Windows.Media.TileBrush.Stretch%2A> se estableció en <xref:System.Windows.Media.Stretch.UniformToFill>. La razón es que la transformación relativa se aplica después del pincel <xref:System.Windows.Media.TileBrush.Viewbox%2A> se asigna a su <xref:System.Windows.Media.TileBrush.Viewport%2A>. La lista siguiente describe cada paso del proceso:  
  
1.  El contenido del pincel de proyecto (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) en su mosaico base (<xref:System.Windows.Media.TileBrush.Viewport%2A>) con el pincel <xref:System.Windows.Media.TileBrush.Stretch%2A> configuración.  
  
     ![Expandir Viewbox para que se ajuste a Viewport](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2.  Proyecte el icono base del rectángulo de transformación de 1 x 1.  
  
     ![Asignar Viewport al rectángulo de transformación](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3.  Aplicar el <xref:System.Windows.Media.RotateTransform>.  
  
     ![Aplicar la transformación relativa](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4.  Proyecte el icono base transformado en el área que se va a pintar.  
  
     ![Proyectar el pincel transformado en el área de resultados](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>Ejemplo: Girar un objeto ImageBrush 45 grados  
 El ejemplo siguiente aplica un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad de un <xref:System.Windows.Media.ImageBrush>. El <xref:System.Windows.Media.RotateTransform> del objeto <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades están establecidas en 0,5, las coordenadas relativas del centro del contenido de punto. Como resultado, el contenido del pincel se gira sobre su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 En el ejemplo siguiente también se aplica un <xref:System.Windows.Media.RotateTransform> a una <xref:System.Windows.Media.ImageBrush>, pero usa el <xref:System.Windows.Media.Brush.Transform%2A> propiedad en lugar de la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad. Para girar el pincel sobre su centro, el <xref:System.Windows.Media.RotateTransform> del objeto <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> debe establecerse en coordenadas absolutas. Como el rectángulo pintado por el pincel es 175 por 90 píxeles, su punto central es (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 La siguiente ilustración muestra el pincel sin una transformación, con la transformación aplicada a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad y con la transformación aplicada a la <xref:System.Windows.Media.Brush.Transform%2A> propiedad.  
  
 ![Valores de Brush RelativeTransform y Transform](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 Este ejemplo forma parte de un ejemplo mayor. Para ver el ejemplo completo, consulte el [ejemplo de pinceles](http://go.microsoft.com/fwlink/?LinkID=159973). Para más información, consulte [Información general sobre pinceles de WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Brush.Transform%2A>  
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Brush>  
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
