---
title: Procedimiento Recortar una imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: e672c7e24ec4db2d6424fa0b611cb1c135cf8eec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195558"
---
# <a name="how-to-crop-an-image"></a>Procedimiento Recortar una imagen
En este ejemplo se muestra cómo recortar una imagen mediante <xref:System.Windows.Media.Imaging.CroppedBitmap>.  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> se utiliza principalmente al codificar una versión recortada de una imagen para guardarla en un archivo. Para recortar una imagen para fines de presentación, vea el [Cómo: Creación de una región de recorte](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) tema.  
  
## <a name="example"></a>Ejemplo  
 La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] define los recursos usados en los ejemplos siguientes.  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 El ejemplo siguiente crea una imagen mediante un <xref:System.Windows.Media.Imaging.CroppedBitmap> como su origen.  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 El <xref:System.Windows.Media.Imaging.CroppedBitmap> también puede usarse como origen de otro <xref:System.Windows.Media.Imaging.CroppedBitmap>, encadena el recorte. Tenga en cuenta que el <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> utiliza los valores que están en relación con el origen que se recorta el mapa de bits y no la imagen inicial.  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Creación de una región de recorte](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))
