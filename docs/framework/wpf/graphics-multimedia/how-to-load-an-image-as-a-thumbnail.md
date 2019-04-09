---
title: Filtrar Cargar una imagen como una miniatura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: f984293a395e925368b20cef6aa0cd902bd6fc15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134048"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="9d57e-102">Filtrar Cargar una imagen como una miniatura</span><span class="sxs-lookup"><span data-stu-id="9d57e-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="9d57e-103">Los ejemplos siguientes muestran cómo cargar un <xref:System.Windows.Controls.Image> como una miniatura para conservar memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d57e-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d57e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d57e-104">Example</span></span>  
 <span data-ttu-id="9d57e-105">El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para reducir la memoria necesaria para cargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="9d57e-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="9d57e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d57e-106">Example</span></span>  
 <span data-ttu-id="9d57e-107">El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en el código para reducir la memoria necesaria para cargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="9d57e-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="9d57e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d57e-108">See also</span></span>

- [<span data-ttu-id="9d57e-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="9d57e-109">Imaging Overview</span></span>](imaging-overview.md)
