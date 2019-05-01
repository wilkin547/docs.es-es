---
title: Procedimiento Codificar un objeto visual en un archivo de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 872c19af0cfcf4fc980643c37e9a6028457c03b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947581"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="803a6-102">Procedimiento Codificar un objeto visual en un archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="803a6-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="803a6-103">En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Visual> objeto en un archivo de imagen con un <xref:System.Windows.Media.Imaging.RenderTargetBitmap> y un <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="803a6-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="803a6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="803a6-104">Example</span></span>  
 <span data-ttu-id="803a6-105">El <xref:System.Windows.Media.DrawingVisual> se crea mediante un <xref:System.Windows.Media.Imaging.BitmapImage> y <xref:System.Windows.Media.FormattedText> que se representa en un <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="803a6-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="803a6-106">El mapa de bits representado, a continuación, se usa para crear un <xref:System.Windows.Media.Imaging.BitmapFrame> que se agrega a la <xref:System.Windows.Media.Imaging.PngBitmapEncoder> para crear un nuevo [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] archivo.</span><span class="sxs-lookup"><span data-stu-id="803a6-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="803a6-107">Un <xref:System.Windows.Media.Imaging.PngBitmapEncoder> se usó en este ejemplo, pero los de la clase derivada <xref:System.Windows.Media.Imaging.BitmapEncoder> objetos se podrían haber utilizado para crear el archivo de imagen.</span><span class="sxs-lookup"><span data-stu-id="803a6-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803a6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="803a6-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="803a6-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="803a6-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="803a6-110">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="803a6-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="803a6-111">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="803a6-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
