---
title: Procedimiento Cargar una imagen como una miniatura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: d92a489f19f8c7160bed5ec83535bdc33cfe561b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735995"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="03f06-102">Procedimiento Cargar una imagen como una miniatura</span><span class="sxs-lookup"><span data-stu-id="03f06-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="03f06-103">Los ejemplos siguientes muestran cómo cargar un <xref:System.Windows.Controls.Image> como una miniatura para conservar memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="03f06-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03f06-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03f06-104">Example</span></span>  
 <span data-ttu-id="03f06-105">El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para reducir la memoria necesaria para cargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="03f06-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="03f06-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03f06-106">Example</span></span>  
 <span data-ttu-id="03f06-107">El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en el código para reducir la memoria necesaria para cargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="03f06-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="03f06-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="03f06-108">See also</span></span>
- [<span data-ttu-id="03f06-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="03f06-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
