---
title: "Cómo: Recortar una imagen"
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
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 084e3dc7fad2bcb3b7ab787302f55c824ff3739d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-crop-an-image"></a>Cómo: Recortar una imagen
Este ejemplo muestra cómo recortar una imagen mediante <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>se utiliza principalmente al codificar una versión recortada de una imagen para guardarla en un archivo. Para recortar una imagen para fines de presentación, vea la [crear una región de recorte](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376) tema.  
  
## <a name="example"></a>Ejemplo  
 El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] define los recursos utilizados en los ejemplos siguientes.  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 En el ejemplo siguiente se crea una imagen mediante una <xref:System.Windows.Media.Imaging.CroppedBitmap> como su origen.  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 El <xref:System.Windows.Media.Imaging.CroppedBitmap> también puede utilizarse como origen de otro <xref:System.Windows.Media.Imaging.CroppedBitmap>, el encadenamiento de recorte. Tenga en cuenta que el <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> utiliza valores que están en relación con el origen que se recorta el mapa de bits y no la imagen inicial.  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>Vea también  
 [Crear una región de recorte](http://msdn.microsoft.com/en-us/56e4bed6-78d7-4292-b917-d72d0b3e4376)
