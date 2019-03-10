---
title: Filtrar Girar, reflejar y sesgar imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 3e539f41667edb505269fe420396c79b68f34e8f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711504"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="33f8c-102">Filtrar Girar, reflejar y sesgar imágenes</span><span class="sxs-lookup"><span data-stu-id="33f8c-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="33f8c-103">Puede girar, reflejar y sesgar una imagen mediante la especificación de puntos de destino para las esquinas superior izquierda, superior derecha e inferior izquierda de la imagen original.</span><span class="sxs-lookup"><span data-stu-id="33f8c-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="33f8c-104">Los tres puntos de destino determinan una transformación afín que asigna la imagen rectangular original a un paralelogramo.</span><span class="sxs-lookup"><span data-stu-id="33f8c-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33f8c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33f8c-105">Example</span></span>  
 <span data-ttu-id="33f8c-106">Por ejemplo, suponga que la imagen original es un rectángulo con la esquina superior izquierda en (0, 0), la esquina superior derecha en (100, 0) y en la esquina inferior izquierda en (0, 50).</span><span class="sxs-lookup"><span data-stu-id="33f8c-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="33f8c-107">Ahora supongamos que asignan esos tres puntos a puntos de destino como sigue:</span><span class="sxs-lookup"><span data-stu-id="33f8c-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="33f8c-108">Punto original</span><span class="sxs-lookup"><span data-stu-id="33f8c-108">Original point</span></span>|<span data-ttu-id="33f8c-109">Punto de destino</span><span class="sxs-lookup"><span data-stu-id="33f8c-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="33f8c-110">Superior izquierda (0, 0)</span><span class="sxs-lookup"><span data-stu-id="33f8c-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="33f8c-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="33f8c-111">(200, 20)</span></span>|  
|<span data-ttu-id="33f8c-112">Superior derecha (100, 0)</span><span class="sxs-lookup"><span data-stu-id="33f8c-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="33f8c-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="33f8c-113">(110, 100)</span></span>|  
|<span data-ttu-id="33f8c-114">Inferior izquierda (0, 50)</span><span class="sxs-lookup"><span data-stu-id="33f8c-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="33f8c-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="33f8c-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="33f8c-116">La siguiente ilustración muestra la imagen original y la imagen asignada en el paralelogramo.</span><span class="sxs-lookup"><span data-stu-id="33f8c-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="33f8c-117">La imagen original ha tiene sesgada, reflejan, girar y traducir.</span><span class="sxs-lookup"><span data-stu-id="33f8c-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="33f8c-118">El eje x en el borde superior de la imagen original se asigna a la línea que se ejecuta a través (200, 20) y (110, 100).</span><span class="sxs-lookup"><span data-stu-id="33f8c-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="33f8c-119">El eje y en el borde izquierdo de la imagen original se asigna a la línea que se ejecuta a través (200, 20) y (250, 30).</span><span class="sxs-lookup"><span data-stu-id="33f8c-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="33f8c-120">![Franjas](./media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="33f8c-120">![Stripes](./media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="33f8c-121">La siguiente ilustración muestra una transformación similar aplicada a una imagen de papel fotográfica.</span><span class="sxs-lookup"><span data-stu-id="33f8c-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="33f8c-122">![Transforma el Escalador](./media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="33f8c-122">![Transformed Climber](./media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="33f8c-123">La siguiente ilustración muestra una transformación similar aplicada a un metarchivo.</span><span class="sxs-lookup"><span data-stu-id="33f8c-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="33f8c-124">![Transforma el metarchivo](./media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="33f8c-124">![Transformed Metafile](./media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="33f8c-125">El ejemplo siguiente genera las imágenes que se muestra en la primera ilustración.</span><span class="sxs-lookup"><span data-stu-id="33f8c-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33f8c-126">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="33f8c-126">Compiling the Code</span></span>  
 <span data-ttu-id="33f8c-127">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="33f8c-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="33f8c-128">No olvide reemplazar `Stripes.bmp` con la ruta de acceso a una imagen que sea válida en el sistema.</span><span class="sxs-lookup"><span data-stu-id="33f8c-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f8c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="33f8c-129">See also</span></span>
- [<span data-ttu-id="33f8c-130">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="33f8c-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
