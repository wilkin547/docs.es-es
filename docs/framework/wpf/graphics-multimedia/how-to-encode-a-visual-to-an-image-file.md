---
title: "Cómo: Codificar un objeto Visual en un archivo de imagen"
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
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88a5d93c9c4726d1f6493df28d0a2a559394ef74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="727a0-102">Cómo: Codificar un objeto Visual en un archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="727a0-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="727a0-103">Este ejemplo muestra cómo codificar un <xref:System.Windows.Media.Visual> objeto en un archivo de imagen mediante una <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="727a0-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="727a0-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="727a0-104">Example</span></span>  
 <span data-ttu-id="727a0-105">El <xref:System.Windows.Media.DrawingVisual> se crea con un <xref:System.Windows.Media.Imaging.BitmapImage> y <xref:System.Windows.Media.FormattedText> que se representa en un <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="727a0-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="727a0-106">El mapa de bits representado, a continuación, se utiliza para crear un <xref:System.Windows.Media.Imaging.BitmapFrame> que se agrega a la <xref:System.Windows.Media.Imaging.PngBitmapEncoder> para crear un nuevo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] archivo.</span><span class="sxs-lookup"><span data-stu-id="727a0-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="727a0-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> se usó en este ejemplo, pero los de la clase derivada <xref:System.Windows.Media.Imaging.BitmapEncoder> objetos podrían haberse utilizados para crear el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="727a0-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727a0-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="727a0-108">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="727a0-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="727a0-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="727a0-110">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="727a0-110">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="727a0-111">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="727a0-111">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
