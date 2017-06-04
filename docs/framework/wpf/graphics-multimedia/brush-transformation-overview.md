---
title: "Informaci&#243;n general sobre la transformaci&#243;n de pinceles | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "pinceles, propiedades de transformación"
  - "propiedades, transformación"
  - "propiedades de transformación de pinceles"
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre la transformaci&#243;n de pinceles
La clase Brush ofrece dos propiedades de transformación: <xref:System.Windows.Media.Brush.Transform%2A> y <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  Estas propiedades permiten girar, sesgar y convertir el contenido de un pincel, además de ajustar su escala.  En este tema se describen las diferencias entre estas dos propiedades y se proporcionan ejemplos de su uso.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Requisitos previos  
 Para entender este tema, debe entender las características del pincel que vaya a transformar.  Para <xref:System.Windows.Media.LinearGradientBrush> y <xref:System.Windows.Media.RadialGradientBrush>, consulte [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  Para <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush>, consulte [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  También debe estar familiarizado con las transformaciones 2D descritas en [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
<a name="transformversusrelativetransform"></a>   
## Diferencias entre las propiedades Transform y RelativeTransform  
 Cuando se aplica una transformación a la propiedad <xref:System.Windows.Media.Brush.Transform%2A> de un pincel, es preciso conocer el tamaño del área pintada si se desea transformar el contenido del pincel sobre su centro.  Supongamos que el área pintada tiene 200 [píxeles independientes del dispositivo](GTMT) de ancho y 150 de alto.  Si utiliza <xref:System.Windows.Media.RotateTransform> para girar la salida del pincel 45 grados sobre su centro, se establece la propiedad <xref:System.Windows.Media.RotateTransform.CenterX%2A> en 100 y la propiedad <xref:System.Windows.Media.RotateTransform.CenterY%2A> en 75 para <xref:System.Windows.Media.RotateTransform>.  
  
 Cuando se aplica una transformación a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> de un pincel, esa transformación se aplica al pincel antes de asignar su salida al área pintada.  En la lista siguiente se describe el orden en que se procesan y transforman los contenidos de un pincel.  
  
1.  Procese el contenido del pincel.  Para <xref:System.Windows.Media.GradientBrush>, esto significa determinar el área de degradado.  Para <xref:System.Windows.Media.TileBrush>, se asigna <xref:System.Windows.Media.TileBrush.Viewbox%2A> a <xref:System.Windows.Media.TileBrush.Viewport%2A>.  Ésta se convierte en la salida del pincel.  
  
2.  Proyecte la salida del pincel sobre el rectángulo de transformación de 1 x 1.  
  
3.  Aplique la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> del pincel, si la tiene.  
  
4.  Proyecte la salida transformada sobre el área que desea pintar.  
  
5.  Aplique la propiedad <xref:System.Windows.Media.Transform> del pincel, si la tiene.  
  
 Dado que <xref:System.Windows.Media.Brush.RelativeTransform%2A> se aplica mientras la salida del pincel está asignada a un rectángulo de 1 x 1, el centro de la transformación y los valores de desplazamiento parecen ser relativos.  Por ejemplo, si utilizó <xref:System.Windows.Media.RotateTransform> para girar la salida del pincel 45 grados sobre su centro, se establecerá la propiedad <xref:System.Windows.Media.RotateTransform.CenterX%2A> en 0,5 y la propiedad <xref:System.Windows.Media.RotateTransform.CenterY%2A> en 0,5 para <xref:System.Windows.Media.RotateTransform>.  
  
 En la ilustración siguiente se muestra la salida de varios pinceles que se han girado 45 grados mediante las propiedades <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Propiedades RelativeTransform y Transform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm\_brushrelativetransform\_transform\_small")  
  
<a name="relativetransformandtilebrush"></a>   
## Utilizar RelativeTransform con un objeto TileBrush  
 Debido a que los pinceles en mosaico son más complejos que los demás pinceles, aplicar <xref:System.Windows.Media.Brush.RelativeTransform%2A> a uno de ellos puede dar lugar a resultados inesperados.  Por ejemplo, tomemos la imagen siguiente.  
  
 ![Imagen de origen](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.png "graphicsmm\_reltransform\_1\_original\_image")  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.ImageBrush> para pintar una área rectangular con la imagen anterior.  Se aplica <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> del objeto <xref:System.Windows.Media.ImageBrush> y se establece su propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> en <xref:System.Windows.Media.Stretch>, lo que debería conservar la relación de aspecto de la imagen cuando se ajuste para rellenar completamente el rectángulo.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 Este ejemplo produce el siguiente resultado.  
  
 ![Resultado transformado](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm\_reltransform\_6\_output")  
  
 Observe que la imagen se distorsiona, aunque la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> del pincel se estableció en <xref:System.Windows.Media.Stretch>.  Esto se debe a que la transformación relativa se aplica después de asignar la propiedad <xref:System.Windows.Media.TileBrush.Viewbox%2A> del pincel a su propiedad <xref:System.Windows.Media.TileBrush.Viewport%2A>.  En la lista siguiente se describen todos los pasos del proceso:  
  
1.  Proyectar el contenido del pincel \(<xref:System.Windows.Media.TileBrush.Viewbox%2A>\) sobre su mosaico base \(<xref:System.Windows.Media.TileBrush.Viewport%2A>\) utilizando el valor de <xref:System.Windows.Media.TileBrush.Stretch%2A> del pincel.  
  
     ![Expandir Viewbox para que se ajuste a Viewport](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm\_reltransform\_2\_viewbox\_to\_viewport")  
  
2.  Proyectar el mosaico base sobre el rectángulo de transformación de 1 x 1.  
  
     ![Asignar Viewport al rectángulo de transformación](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm\_reltransform\_3\_output\_to\_transform")  
  
3.  Aplicar <xref:System.Windows.Media.RotateTransform>.  
  
     ![Aplicar la transformación relativa](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm\_reltransform\_4\_transform\_rotate")  
  
4.  Proyectar el mosaico base transformado sobre el área que se va a pintar.  
  
     ![Proyectar el pincel transformado en el área de resultado](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm\_reltransform\_5\_transform\_to\_output")  
  
<a name="rotateexample"></a>   
## Ejemplo: Girar un objeto ImageBrush 45 grados  
 En el ejemplo siguiente se aplica <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> de un objeto <xref:System.Windows.Media.ImageBrush>.  Las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> del objeto <xref:System.Windows.Media.RotateTransform> se establecen en 0,5, las coordenadas relativas del punto central del contenido.  Como resultado, el contenido del pincel se gira sobre su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 En el ejemplo siguiente también se aplica <xref:System.Windows.Media.RotateTransform> a un objeto <xref:System.Windows.Media.ImageBrush>, pero se utiliza la propiedad <xref:System.Windows.Media.Brush.Transform%2A> en lugar de la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  Para girar el pincel sobre su centro, las propiedades <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> del objeto <xref:System.Windows.Media.RotateTransform> deben establecerse en coordenadas absolutas.  Dado que el pincel pinta un rectángulo que es de 175 por 90 píxeles, su punto central es \(87,5, 45\).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 En la ilustración siguiente se muestra el pincel sin transformación, con la transformación aplicada a la propiedad <xref:System.Windows.Media.Brush.RelativeTransform%2A> y con la transformación aplicada a la propiedad <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Valores de Brush RelativeTransform y Transform](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
 Este ejemplo forma parte de un ejemplo mayor.  Para obtener el ejemplo completo, vea [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).  Para obtener más información sobre pinceles, consulte [Información general sobre pinceles de WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media.Brush.Transform%2A>   
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>   
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Brush>   
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)