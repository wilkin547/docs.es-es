---
title: Procedimiento Pintar un área con una imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 2b88982e7a8d196c31869dc74aac636d78f68386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921659"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Procedimiento Pintar un área con una imagen
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.ImageBrush> clase para pintar un área con una imagen. Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que se especifica mediante su <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 Las operaciones de pintura de ejemplo siguiente la <xref:System.Windows.Controls.Control.Background%2A> de un botón mediante el uso de un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 De forma predeterminada, un <xref:System.Windows.Media.ImageBrush> ajusta su imagen hasta rellenar completamente el área que se está pintando. En el ejemplo anterior, la imagen se ajusta para rellenar el botón, lo que puede distorsionar la imagen. Puede controlar este comportamiento estableciendo el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de <xref:System.Windows.Media.TileBrush> a <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>, lo que hace que el pincel conserve la relación de aspecto de la imagen.  
  
 Si establece la <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.TileMode%2A> las propiedades de un <xref:System.Windows.Media.ImageBrush>, puede crear un patrón de repetición. En el ejemplo siguiente se pinta un botón mediante un patrón creado a partir de una imagen.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.ImageBrush> de clases, vea [pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md).  
  
 Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para el <xref:System.Windows.Media.ImageBrush> clase. Para obtener un ejemplo completo, vea [ejemplo de ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vea también

- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
