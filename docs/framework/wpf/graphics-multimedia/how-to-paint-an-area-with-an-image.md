---
title: 'Cómo: Pintar un área con una imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186049"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Cómo: Pintar un área con una imagen
En este ejemplo se <xref:System.Windows.Media.ImageBrush> muestra cómo utilizar la clase para pintar un área con una imagen. Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que <xref:System.Windows.Media.ImageBrush.ImageSource%2A> se especifica por su propiedad.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Controls.Control.Background%2A> siguiente se pinta <xref:System.Windows.Media.ImageBrush>el de un botón mediante un archivo .  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 De forma <xref:System.Windows.Media.ImageBrush> predeterminada, un estira su imagen para rellenar completamente el área que está pintando. En el ejemplo anterior, la imagen se ajusta para rellenar el botón, lo que puede distorsionar la imagen. Puede controlar este comportamiento <xref:System.Windows.Media.TileBrush.Stretch%2A> estableciendo <xref:System.Windows.Media.TileBrush> <xref:System.Windows.Media.Stretch.Uniform> la <xref:System.Windows.Media.Stretch.UniformToFill>propiedad de to o , lo que hace que el pincel conserve la relación de aspecto de la imagen.  
  
 Si establece <xref:System.Windows.Media.TileBrush.Viewport%2A> las <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedades <xref:System.Windows.Media.ImageBrush>y de un , puede crear un patrón de repetición. En el ejemplo siguiente se pinta un botón mediante un patrón creado a partir de una imagen.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Para obtener más <xref:System.Windows.Media.ImageBrush> información acerca de la clase, vea [Pintar con imágenes, dibujos y objetos visuales](painting-with-images-drawings-and-visuals.md).  
  
 Este ejemplo de código forma parte de <xref:System.Windows.Media.ImageBrush> un ejemplo más amplio que se proporciona para la clase. Para obtener el ejemplo completo, vea [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Consulte también

- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
