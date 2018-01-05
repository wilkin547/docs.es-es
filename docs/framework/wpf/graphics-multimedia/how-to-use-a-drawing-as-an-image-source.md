---
title: "Cómo: Usar un dibujo como el origen de una imagen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e0fe8f7d3633143348693c95d92dd2715bd0442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>Cómo: Usar un dibujo como el origen de una imagen
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.Drawing> como el <xref:System.Windows.Controls.Image.Source%2A> para un <xref:System.Windows.Controls.Image> control. Para mostrar un <xref:System.Windows.Media.Drawing> con una <xref:System.Windows.Controls.Image> controlar, use un <xref:System.Windows.Media.DrawingImage> como el <xref:System.Windows.Controls.Image> del control <xref:System.Windows.Controls.Image.Source%2A> y establezca el <xref:System.Windows.Media.DrawingImage> del objeto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> propiedad al dibujo que desea mostrar.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingImage> y <xref:System.Windows.Controls.Image> control para mostrar un <xref:System.Windows.Media.GeometryDrawing>. Este ejemplo produce el siguiente resultado:  
  
 ![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Dibujar una imagen usando un objeto ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [PresentationOptions:Freeze (Atributo)](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
