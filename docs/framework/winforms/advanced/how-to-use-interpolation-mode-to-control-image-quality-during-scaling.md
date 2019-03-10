---
title: Procedimiento Usar el modo de interpolación para controlar la calidad de imagen durante el escalado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 83f1e569f1fb1ae49143f4ed11837759df29fe79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721962"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="bab54-102">Procedimiento Usar el modo de interpolación para controlar la calidad de imagen durante el escalado</span><span class="sxs-lookup"><span data-stu-id="bab54-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="bab54-103">El modo de interpolación de una <xref:System.Drawing.Graphics> objeto influye en la forma [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imágenes escalas (estira y encoge).</span><span class="sxs-lookup"><span data-stu-id="bab54-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="bab54-104">El <xref:System.Drawing.Drawing2D.InterpolationMode> enumeración define varios modos de interpolación, algunos de los cuales se muestran en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="bab54-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="bab54-105">Para ajustar una imagen, cada píxel de la imagen original debe asignarse a un grupo de píxeles de la imagen más grande.</span><span class="sxs-lookup"><span data-stu-id="bab54-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="bab54-106">Para comprimir una imagen, los grupos de píxeles de la imagen original deben asignarse a píxeles únicos de la imagen más pequeña.</span><span class="sxs-lookup"><span data-stu-id="bab54-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="bab54-107">La eficacia de los algoritmos que realizan estas asignaciones determina la calidad de una imagen escalada.</span><span class="sxs-lookup"><span data-stu-id="bab54-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="bab54-108">Los algoritmos que generan imágenes con escala mayor calidad tienden a necesitar más tiempo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="bab54-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="bab54-109">En la lista anterior, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> es el modo de menor calidad y <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> es el modo de mayor calidad.</span><span class="sxs-lookup"><span data-stu-id="bab54-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="bab54-110">Para establecer el modo de interpolación, asigne uno de los miembros de la <xref:System.Drawing.Drawing2D.InterpolationMode> enumeración a la <xref:System.Drawing.Graphics.InterpolationMode%2A> propiedad de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="bab54-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bab54-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bab54-111">Example</span></span>  
 <span data-ttu-id="bab54-112">El ejemplo siguiente dibuja una imagen y, a continuación, reduce la imagen con tres modos de interpolación diferente.</span><span class="sxs-lookup"><span data-stu-id="bab54-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="bab54-113">La siguiente ilustración muestra la imagen original y las tres imágenes más pequeñas.</span><span class="sxs-lookup"><span data-stu-id="bab54-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 <span data-ttu-id="bab54-114">![Imagen con diversos valores de interpolación](./media/csgrapes1.png "csgrapes1")</span><span class="sxs-lookup"><span data-stu-id="bab54-114">![Image with Varied Interpolation Settings](./media/csgrapes1.png "csgrapes1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bab54-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="bab54-115">Compiling the Code</span></span>  
 <span data-ttu-id="bab54-116">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="bab54-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab54-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bab54-117">See also</span></span>
- [<span data-ttu-id="bab54-118">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="bab54-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="bab54-119">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="bab54-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
