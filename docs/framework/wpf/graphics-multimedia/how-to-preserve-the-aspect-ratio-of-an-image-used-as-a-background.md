---
title: 'Cómo: Conservar la relación de aspecto de una imagen utilizada como fondo'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: b467fcd353994faef19b5a997e03d6582789eac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186032"
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>Cómo: Conservar la relación de aspecto de una imagen utilizada como fondo
Este ejemplo muestra cómo <xref:System.Windows.Media.TileBrush.Stretch%2A> utilizar <xref:System.Windows.Media.ImageBrush> la propiedad de un para preservar la relación de aspecto de la imagen.  
  
 De forma predeterminada, <xref:System.Windows.Media.ImageBrush> cuando se utiliza un para pintar un área, su contenido se estira para rellenar completamente el área de salida. Cuando el área de salida y la imagen tienen relaciones de aspecto diferentes, la imagen queda distorsionada al ajustarse.  
  
 Para conservar <xref:System.Windows.Media.ImageBrush> la relación de aspecto de <xref:System.Windows.Media.TileBrush.Stretch%2A> su <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>imagen, establezca la propiedad en o .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.ImageBrush> siguiente se utilizan dos objetos para pintar dos rectángulos. Cada rectángulo tiene 300 por 150 píxeles y cada uno contiene una imagen de 300 por 300 píxeles. La <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad del primer pincel <xref:System.Windows.Media.Stretch.Uniform>se <xref:System.Windows.Media.TileBrush.Stretch%2A> establece en , y <xref:System.Windows.Media.Stretch.UniformToFill>la propiedad del segundo pincel se establece en .  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 La siguiente ilustración muestra la salida del <xref:System.Windows.Media.TileBrush.Stretch%2A> primer <xref:System.Windows.Media.Stretch.Uniform>pincel, que tiene un valor de .  
  
 ![ImageBrush con ajuste uniforme](./media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 La siguiente ilustración muestra la salida del <xref:System.Windows.Media.TileBrush.Stretch%2A> segundo <xref:System.Windows.Media.Stretch.UniformToFill>pincel, que tiene un ajuste de .  
  
 ![ImageBrush con ajuste UniformToFill](./media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 Tenga en <xref:System.Windows.Media.TileBrush.Stretch%2A> cuenta que la propiedad <xref:System.Windows.Media.TileBrush> se comporta de <xref:System.Windows.Media.DrawingBrush> forma <xref:System.Windows.Media.VisualBrush>idéntica para los demás objetos, es decir, for y . Para obtener <xref:System.Windows.Media.ImageBrush> más información <xref:System.Windows.Media.TileBrush> sobre y los demás objetos, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
 Tenga en cuenta <xref:System.Windows.Media.TileBrush.Stretch%2A> también que, aunque <xref:System.Windows.Media.TileBrush> la propiedad parece especificar cómo se estira <xref:System.Windows.Media.TileBrush> el contenido para ajustarse a su área de salida, en realidad especifica cómo se estira el contenido para rellenar su icono base. Para más información, consulte <xref:System.Windows.Media.TileBrush>.  
  
 Este ejemplo de código forma parte de <xref:System.Windows.Media.ImageBrush> un ejemplo más amplio que se proporciona para la clase. Para obtener el ejemplo completo, vea [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.TileBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
