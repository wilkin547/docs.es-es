---
title: Filtrar Crear un mapa de bits desde un objeto Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 429aacc99d8ead5a18e9be7602b19a74773b419a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362869"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="b3757-102">Filtrar Crear un mapa de bits desde un objeto Visual</span><span class="sxs-lookup"><span data-stu-id="b3757-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="b3757-103">En este ejemplo se muestra cómo puede crear un mapa de bits desde un <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="b3757-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="b3757-104">Un <xref:System.Windows.Media.DrawingVisual> se presenta con <xref:System.Windows.Media.FormattedText>.</span><span class="sxs-lookup"><span data-stu-id="b3757-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="b3757-105">El <xref:System.Windows.Media.Visual> , a continuación, se representa en el <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creación de un mapa de bits del texto dado.</span><span class="sxs-lookup"><span data-stu-id="b3757-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3757-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3757-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="b3757-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3757-107">See also</span></span>
- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="b3757-108">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="b3757-108">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="b3757-109">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="b3757-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="b3757-110">Usar objetos DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="b3757-110">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
