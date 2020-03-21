---
title: 'Cómo: Transformar un pincel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187335"
---
# <a name="how-to-transform-a-brush"></a>Cómo: Transformar un pincel
En este ejemplo <xref:System.Windows.Media.Brush> se muestra cómo transformar <xref:System.Windows.Media.Brush.RelativeTransform%2A> objetos mediante sus dos propiedades de transformación: y <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 En los ejemplos <xref:System.Windows.Media.RotateTransform> siguientes se usa <xref:System.Windows.Media.ImageBrush> a para rotar el contenido de un 45 grados.  
  
 En la ilustración <xref:System.Windows.Media.RotateTransform>siguiente se <xref:System.Windows.Media.RotateTransform> muestra <xref:System.Windows.Media.Brush.RelativeTransform%2A> el <xref:System.Windows.Media.ImageBrush> sin <xref:System.Windows.Media.RotateTransform> un , <xref:System.Windows.Media.Brush.Transform%2A> con el aplicado a la propiedad y con el aplicado a la propiedad.  
  
 ![Valores de Brush RelativeTransform y Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Ejemplo  
 El primer ejemplo <xref:System.Windows.Media.RotateTransform> aplica <xref:System.Windows.Media.Brush.RelativeTransform%2A> a <xref:System.Windows.Media.ImageBrush>la propiedad de un archivo . Las <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades y <xref:System.Windows.Media.RotateTransform> propiedades de un objeto se establecen en 0,5, que es la coordenada relativa del punto central de este contenido. Como resultado, <xref:System.Windows.Media.ImageBrush> el contenido gira alrededor de su centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 El segundo ejemplo <xref:System.Windows.Media.RotateTransform> también <xref:System.Windows.Media.ImageBrush>aplica a a un ; sin embargo, <xref:System.Windows.Media.Brush.Transform%2A> en este <xref:System.Windows.Media.Brush.RelativeTransform%2A> ejemplo se utiliza la propiedad en lugar de la propiedad.  
  
 Para girar el pincel alrededor de <xref:System.Windows.Media.RotateTransform.CenterX%2A> su <xref:System.Windows.Media.RotateTransform.CenterY%2A> centro, <xref:System.Windows.Media.RotateTransform> el ejemplo establece las propiedades y las propiedades del objeto en coordenadas absolutas. Como el pincel pinta un rectángulo de 175 x 90 píxeles, el punto central del rectángulo es (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Para obtener una <xref:System.Windows.Media.Brush.RelativeTransform%2A> descripción de cómo funcionan las <xref:System.Windows.Media.Brush.Transform%2A> propiedades, vea Información general sobre la transformación de [pinceles](brush-transformation-overview.md).  
  
 Para ver el ejemplo completo, consulte [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Ejemplo de pinceles). Para más información sobre los pinceles, consulte [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre la transformación de pinceles](brush-transformation-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
