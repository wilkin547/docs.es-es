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
ms.openlocfilehash: adcbd5fb82ce9ae89ac59db5aeb7f384f8cc1fc7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="e3eac-102">Cómo: Cargar una imagen como una miniatura</span><span class="sxs-lookup"><span data-stu-id="e3eac-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="e3eac-103">Los ejemplos siguientes muestran cómo cargar un <xref:System.Windows.Controls.Image> como una vista en miniatura para ahorrar memoria de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3eac-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3eac-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3eac-104">Example</span></span>  
 <span data-ttu-id="e3eac-105">El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para reducir la memoria necesaria para cargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="e3eac-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="e3eac-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3eac-106">Example</span></span>  
 <span data-ttu-id="e3eac-107">El ejemplo siguiente se establece la <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> propiedad de un <xref:System.Windows.Media.Imaging.BitmapImage> en el código para reducir la memoria necesaria para cargar la imagen.</span><span class="sxs-lookup"><span data-stu-id="e3eac-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="e3eac-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3eac-108">See Also</span></span>  
 [<span data-ttu-id="e3eac-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="e3eac-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
