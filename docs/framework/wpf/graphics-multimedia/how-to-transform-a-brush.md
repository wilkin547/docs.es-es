---
title: "Cómo: Transformar un pincel"
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
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ee517eb76877bb4e02c021061055b328597c517
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-transform-a-brush"></a>Cómo: Transformar un pincel
Este ejemplo muestra cómo transformar <xref:System.Windows.Media.Brush> objetos mediante el uso de sus dos propiedades de transformación: <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Los ejemplos siguientes usan una <xref:System.Windows.Media.RotateTransform> para girar el contenido de un <xref:System.Windows.Media.ImageBrush> 45 grados.  
  
 La siguiente ilustración muestra la <xref:System.Windows.Media.ImageBrush> sin un <xref:System.Windows.Media.RotateTransform>, con el <xref:System.Windows.Media.RotateTransform> aplicado a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad y con el <xref:System.Windows.Media.RotateTransform> aplicado a la <xref:System.Windows.Media.Brush.Transform%2A> propiedad.  
  
 ![Valores de Brush RelativeTransform y Transform](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Ejemplo  
 El primer ejemplo se aplica un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad de un <xref:System.Windows.Media.ImageBrush>. El <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades de un <xref:System.Windows.Media.RotateTransform> objeto están establecidos en 0,5, que es la coordenada relativa del punto central de este contenido. Como resultado, la <xref:System.Windows.Media.ImageBrush> contenido gira alrededor de su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 El segundo ejemplo también se aplica un <xref:System.Windows.Media.RotateTransform> a una <xref:System.Windows.Media.ImageBrush>; sin embargo, este ejemplo se utiliza la <xref:System.Windows.Media.Brush.Transform%2A> propiedad en lugar de la <xref:System.Windows.Media.Brush.RelativeTransform%2A> propiedad.  
  
 Para girar el pincel sobre su centro, el ejemplo establece la <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades de la <xref:System.Windows.Media.RotateTransform> objeto en coordenadas absolutas. Como el pincel pinta un rectángulo de 175 x 90 píxeles, el punto central del rectángulo es (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Para obtener una descripción de cómo el <xref:System.Windows.Media.Brush.RelativeTransform%2A> y <xref:System.Windows.Media.Brush.Transform%2A> propiedades de trabajo, consulte la [Brush Transformation Overview](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Para ver el ejemplo completo, consulte [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) (Ejemplo de pinceles). Para más información sobre los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la transformación de pinceles](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
