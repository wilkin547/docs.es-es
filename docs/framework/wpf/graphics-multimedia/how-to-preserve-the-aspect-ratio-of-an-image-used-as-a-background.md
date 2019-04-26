---
title: Procedimiento Conservar la relación de aspecto de una imagen usada como fondo
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 4ae6f1242548038bcd54b7218783e5063fa67872
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921776"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Procedimiento Conservar la relación de aspecto de una imagen usada como fondo
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de un <xref:System.Windows.Media.ImageBrush> con el fin de conservar la relación de aspecto de la imagen.  
  
 De forma predeterminada, cuando se usa un <xref:System.Windows.Media.ImageBrush> para pintar un área, el contenido se expande para rellenar completamente el área de salida. Cuando el área de salida y la imagen tienen relaciones de aspecto diferentes, la imagen queda distorsionada al ajustarse.  
  
 Para realizar una <xref:System.Windows.Media.ImageBrush> conservar la relación de aspecto de su imagen, establezca la <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza dos <xref:System.Windows.Media.ImageBrush> objetos para pintar dos rectángulos. Cada rectángulo tiene 300 por 150 píxeles y cada uno contiene una imagen de 300 por 300 píxeles. El <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad del primer pincel se establece en <xref:System.Windows.Media.Stretch.Uniform>y el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad del segundo pincel se establece en <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 La siguiente ilustración muestra la salida del primer pincel, que tiene un <xref:System.Windows.Media.TileBrush.Stretch%2A> de <xref:System.Windows.Media.Stretch.Uniform>.  
  
 ![ImageBrush con Uniform stretching](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 La siguiente ilustración muestra el resultado del segundo pincel, que tiene un <xref:System.Windows.Media.TileBrush.Stretch%2A> de <xref:System.Windows.Media.Stretch.UniformToFill>.  
  
 ![ImageBrush con UniformToFill stretching](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Tenga en cuenta que el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad se comporta exactamente igual para los demás <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>. Para obtener más información acerca de <xref:System.Windows.Media.ImageBrush> y el otro <xref:System.Windows.Media.TileBrush> objetos, vea [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).  
  
 Tenga en cuenta también que, aunque el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad aparece para especificar cómo el <xref:System.Windows.Media.TileBrush> contenido se estira para ajustarse a su área de salida, en realidad especifica cómo el <xref:System.Windows.Media.TileBrush> contenido se expande para rellenar su mosaico base. Para obtener más información, consulta <xref:System.Windows.Media.TileBrush>.  
  
 Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para el <xref:System.Windows.Media.ImageBrush> clase. Para obtener un ejemplo completo, vea [ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.TileBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
