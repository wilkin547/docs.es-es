---
title: "Recortar y ajustar la escala de las imágenes en GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bbe7ac4b8c541ea76392f94f538e41816cf5c3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="b9b86-102">Recortar y ajustar la escala de las imágenes en GDI+</span><span class="sxs-lookup"><span data-stu-id="b9b86-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="b9b86-103">Puede usar el <xref:System.Drawing.Graphics.DrawImage%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar y colocar imágenes vectoriales e imágenes de trama.</span><span class="sxs-lookup"><span data-stu-id="b9b86-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="b9b86-104"><xref:System.Drawing.Graphics.DrawImage%2A>es un método sobrecargado, por lo que hay varias formas de proporcionar argumentos.</span><span class="sxs-lookup"><span data-stu-id="b9b86-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="b9b86-105">Variaciones de DrawImage</span><span class="sxs-lookup"><span data-stu-id="b9b86-105">DrawImage Variations</span></span>  
 <span data-ttu-id="b9b86-106">Una variación de la <xref:System.Drawing.Graphics.DrawImage%2A> método recibe un <xref:System.Drawing.Bitmap> y <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="b9b86-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="b9b86-107">El rectángulo especifica el destino de la operación de dibujo; es decir, especifica el rectángulo en el que se va a dibujar la imagen.</span><span class="sxs-lookup"><span data-stu-id="b9b86-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="b9b86-108">Si el tamaño del rectángulo de destino es diferente del tamaño de la imagen original, la imagen se escala para ajustarse el rectángulo de destino.</span><span class="sxs-lookup"><span data-stu-id="b9b86-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="b9b86-109">En el ejemplo de código siguiente se muestra cómo dibujar la misma imagen tres veces: una vez sin ajuste de escala, otra con una expansión y otra con una compresión:</span><span class="sxs-lookup"><span data-stu-id="b9b86-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="b9b86-110">La siguiente ilustración muestra las tres imágenes.</span><span class="sxs-lookup"><span data-stu-id="b9b86-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="b9b86-111">![Ajuste de escala](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="b9b86-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="b9b86-112">Algunas variaciones de la <xref:System.Drawing.Graphics.DrawImage%2A> método tiene un parámetro de rectángulo de origen, así como un parámetro de rectángulo de destino.</span><span class="sxs-lookup"><span data-stu-id="b9b86-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="b9b86-113">El parámetro de rectángulo de origen Especifica la parte de la imagen original para dibujar.</span><span class="sxs-lookup"><span data-stu-id="b9b86-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="b9b86-114">El rectángulo de destino Especifica el rectángulo en el que se va a dibujar esa parte de la imagen.</span><span class="sxs-lookup"><span data-stu-id="b9b86-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="b9b86-115">Si el tamaño del rectángulo de destino es diferente del tamaño del rectángulo de origen, la imagen se escala para ajustarse el rectángulo de destino.</span><span class="sxs-lookup"><span data-stu-id="b9b86-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="b9b86-116">En el ejemplo de código siguiente se muestra cómo construir un <xref:System.Drawing.Bitmap> partir del archivo Runner.jpg.</span><span class="sxs-lookup"><span data-stu-id="b9b86-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="b9b86-117">Toda la imagen se dibuja sin ajuste de escala en (0, 0).</span><span class="sxs-lookup"><span data-stu-id="b9b86-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="b9b86-118">A continuación, una pequeña parte de la imagen se dibuja dos veces: una vez con una compresión y otra con una expansión.</span><span class="sxs-lookup"><span data-stu-id="b9b86-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="b9b86-119">En la siguiente ilustración muestra la imagen sin ajuste de escala y las partes de la imagen comprimida y expandida.</span><span class="sxs-lookup"><span data-stu-id="b9b86-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="b9b86-120">![Recortar y ajustar la escala](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="b9b86-120">![Cropping and Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b86-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9b86-121">See Also</span></span>  
 [<span data-ttu-id="b9b86-122">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="b9b86-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="b9b86-123">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="b9b86-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
