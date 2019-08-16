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
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545293"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="f2fd2-102">Procedimiento Codificar un objeto visual en un archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="f2fd2-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="f2fd2-103">En este ejemplo se muestra cómo codificar <xref:System.Windows.Media.Visual> un objeto en un archivo de imagen <xref:System.Windows.Media.Imaging.RenderTargetBitmap> mediante y <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="f2fd2-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2fd2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2fd2-104">Example</span></span>  
 <span data-ttu-id="f2fd2-105">Se crea <xref:System.Windows.Media.Imaging.RenderTargetBitmap>mediante y que<xref:System.Windows.Media.FormattedText> se representa en un. <xref:System.Windows.Media.Imaging.BitmapImage> <xref:System.Windows.Media.DrawingVisual></span><span class="sxs-lookup"><span data-stu-id="f2fd2-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="f2fd2-106">El mapa de bits representado se usa para crear un <xref:System.Windows.Media.Imaging.BitmapFrame> que se agrega <xref:System.Windows.Media.Imaging.PngBitmapEncoder> a para crear un nuevo archivo PNG (Portable Network Graphics).</span><span class="sxs-lookup"><span data-stu-id="f2fd2-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new Portable Network Graphics (PNG) file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="f2fd2-107">Se usó en este ejemplo, pero cualquiera de los objetos <xref:System.Windows.Media.Imaging.BitmapEncoder> derivados podría haberse utilizado para crear el archivo de imagen. <xref:System.Windows.Media.Imaging.PngBitmapEncoder></span><span class="sxs-lookup"><span data-stu-id="f2fd2-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fd2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2fd2-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="f2fd2-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="f2fd2-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="f2fd2-110">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="f2fd2-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="f2fd2-111">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="f2fd2-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
