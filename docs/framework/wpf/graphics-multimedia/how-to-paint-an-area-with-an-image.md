---
title: "Cómo: Pintar un área con una imagen"
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
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3edbe30347580bb4f9677d7fb98d3b4fd8b92cff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-an-image"></a>Cómo: Pintar un área con una imagen
Este ejemplo muestra cómo utilizar la <xref:System.Windows.Media.ImageBrush> clase para pintar un área con una imagen. Un <xref:System.Windows.Media.ImageBrush> muestra una sola imagen, que se especifica mediante su <xref:System.Windows.Media.ImageBrush.ImageSource%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 Las operaciones de pintura de ejemplo siguiente la <xref:System.Windows.Controls.Control.Background%2A> de un botón mediante el uso de un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 De forma predeterminada, un <xref:System.Windows.Media.ImageBrush> ajusta su imagen para que rellene completamente el área que se está pintando. En el ejemplo anterior, la imagen se ajusta para rellenar el botón, lo que puede distorsionar la imagen. Puede controlar este comportamiento estableciendo el <xref:System.Windows.Media.TileBrush.Stretch%2A> propiedad de <xref:System.Windows.Media.TileBrush> a <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>, lo que hace que el pincel conservar la relación de aspecto de la imagen.  
  
 Si establece la <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedades de un <xref:System.Windows.Media.ImageBrush>, puede crear un patrón de repetición. En el ejemplo siguiente se pinta un botón mediante un patrón creado a partir de una imagen.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Para obtener más información sobre la <xref:System.Windows.Media.ImageBrush> de clases, consulte [pintar con imágenes, gráficos y objetos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Este ejemplo de código forma parte de un ejemplo mayor proporcionado para el <xref:System.Windows.Media.ImageBrush> clase. Para obtener un ejemplo completo, vea [ejemplo ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vea también  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
