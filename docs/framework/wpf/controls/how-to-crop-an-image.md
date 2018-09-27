---
title: 'Cómo: Recortar una imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 189cb92d581ccc9209ebdb4de18487951d17818a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47234934"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="3cc19-102">Cómo: Recortar una imagen</span><span class="sxs-lookup"><span data-stu-id="3cc19-102">How to: Crop an Image</span></span>
<span data-ttu-id="3cc19-103">En este ejemplo se muestra cómo recortar una imagen mediante <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span><span class="sxs-lookup"><span data-stu-id="3cc19-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="3cc19-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> se utiliza principalmente al codificar una versión recortada de una imagen para guardarla en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3cc19-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="3cc19-105">Para recortar una imagen para fines de presentación, vea el [crear una región de recorte](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) tema.</span><span class="sxs-lookup"><span data-stu-id="3cc19-105">To crop an image for display purposes see the [Create a Clip Region](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cc19-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cc19-106">Example</span></span>  
 <span data-ttu-id="3cc19-107">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] define los recursos usados en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="3cc19-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="3cc19-108">El ejemplo siguiente crea una imagen mediante un <xref:System.Windows.Media.Imaging.CroppedBitmap> como su origen.</span><span class="sxs-lookup"><span data-stu-id="3cc19-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="3cc19-109">El <xref:System.Windows.Media.Imaging.CroppedBitmap> también puede usarse como origen de otro <xref:System.Windows.Media.Imaging.CroppedBitmap>, encadena el recorte.</span><span class="sxs-lookup"><span data-stu-id="3cc19-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="3cc19-110">Tenga en cuenta que el <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> utiliza los valores que están en relación con el origen que se recorta el mapa de bits y no la imagen inicial.</span><span class="sxs-lookup"><span data-stu-id="3cc19-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="3cc19-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cc19-111">See Also</span></span>  
 [<span data-ttu-id="3cc19-112">Creación de una región de recorte</span><span class="sxs-lookup"><span data-stu-id="3cc19-112">Create a Clip Region</span></span>](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
