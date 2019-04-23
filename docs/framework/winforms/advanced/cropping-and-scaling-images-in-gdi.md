---
title: Recortar y ajustar la escala de las imágenes en GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183734"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="004c3-102">Recortar y ajustar la escala de las imágenes en GDI+</span><span class="sxs-lookup"><span data-stu-id="004c3-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="004c3-103">Puede usar el <xref:System.Drawing.Graphics.DrawImage%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar y colocar imágenes vectoriales e imágenes de trama.</span><span class="sxs-lookup"><span data-stu-id="004c3-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="004c3-104"><xref:System.Drawing.Graphics.DrawImage%2A> es un método sobrecargado, por lo que hay varias maneras de proporcionar argumentos.</span><span class="sxs-lookup"><span data-stu-id="004c3-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="004c3-105">Variaciones de DrawImage</span><span class="sxs-lookup"><span data-stu-id="004c3-105">DrawImage Variations</span></span>  
 <span data-ttu-id="004c3-106">Una variación de la <xref:System.Drawing.Graphics.DrawImage%2A> método recibe una <xref:System.Drawing.Bitmap> y un <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="004c3-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="004c3-107">El rectángulo especifica el destino de la operación de dibujo; es decir, especifica el rectángulo en el que se va a dibujar la imagen.</span><span class="sxs-lookup"><span data-stu-id="004c3-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="004c3-108">Si el tamaño del rectángulo de destino es diferente del tamaño de la imagen original, la imagen se escala para ajustarse el rectángulo de destino.</span><span class="sxs-lookup"><span data-stu-id="004c3-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="004c3-109">En el ejemplo de código siguiente se muestra cómo dibujar la misma imagen tres veces: una vez sin ajuste de escala, una vez con una expansión y otra con una compresión:</span><span class="sxs-lookup"><span data-stu-id="004c3-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="004c3-110">La siguiente ilustración muestra las tres imágenes.</span><span class="sxs-lookup"><span data-stu-id="004c3-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="004c3-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="004c3-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="004c3-112">Algunas variaciones de la <xref:System.Drawing.Graphics.DrawImage%2A> método tiene un parámetro de rectángulo de origen, así como un parámetro de rectángulo de destino.</span><span class="sxs-lookup"><span data-stu-id="004c3-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="004c3-113">El parámetro de rectángulo de origen Especifica la parte de la imagen original se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="004c3-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="004c3-114">El rectángulo de destino Especifica el rectángulo en el que se va a dibujar esa parte de la imagen.</span><span class="sxs-lookup"><span data-stu-id="004c3-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="004c3-115">Si el tamaño del rectángulo de destino es diferente del tamaño del rectángulo de origen, la imagen se escala para ajustarse el rectángulo de destino.</span><span class="sxs-lookup"><span data-stu-id="004c3-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="004c3-116">El ejemplo de código siguiente muestra cómo construir un <xref:System.Drawing.Bitmap> desde el archivo Runner.jpg.</span><span class="sxs-lookup"><span data-stu-id="004c3-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="004c3-117">Toda la imagen se dibuja ningún ajuste de escala en (0, 0).</span><span class="sxs-lookup"><span data-stu-id="004c3-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="004c3-118">A continuación, una pequeña parte de la imagen se dibuja dos veces: una vez con una compresión y otra vez con una expansión.</span><span class="sxs-lookup"><span data-stu-id="004c3-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="004c3-119">La siguiente ilustración muestra la imagen sin escala y las partes de la imagen comprimida y expandida.</span><span class="sxs-lookup"><span data-stu-id="004c3-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="004c3-120">![Recortar y escalar](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="004c3-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004c3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="004c3-121">See also</span></span>

- [<span data-ttu-id="004c3-122">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="004c3-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="004c3-123">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="004c3-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
