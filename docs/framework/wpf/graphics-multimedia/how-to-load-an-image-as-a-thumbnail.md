---
title: "Cómo: Cargar una imagen como una miniatura"
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
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e91e032162e6e652daf18268d05c2a7db291bfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a>Cómo: Cargar una imagen como una miniatura
Los ejemplos siguientes muestran cómo cargar un <xref:System.Windows.Controls.Image> como una vista en miniatura para ahorrar memoria de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para reducir la memoria necesaria para cargar la imagen.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en el código para reducir la memoria necesaria para cargar la imagen.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
