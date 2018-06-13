---
title: Dibujar, colocar y clonar imágenes en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: 5ff502884874e21e8f34acb2f15db4c651a0a273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521656"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="92cd5-102">Dibujar, colocar y clonar imágenes en GDI+</span><span class="sxs-lookup"><span data-stu-id="92cd5-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="92cd5-103">Puede usar el <xref:System.Drawing.Bitmap> clase para cargar y mostrar imágenes de trama y se puede utilizar el <xref:System.Drawing.Imaging.Metafile> clase para cargar y mostrar imágenes vectoriales.</span><span class="sxs-lookup"><span data-stu-id="92cd5-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="92cd5-104">El <xref:System.Drawing.Bitmap> y <xref:System.Drawing.Imaging.Metafile> clases heredan de la <xref:System.Drawing.Image> clase.</span><span class="sxs-lookup"><span data-stu-id="92cd5-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="92cd5-105">Para mostrar una imagen vectorial, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="92cd5-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="92cd5-106">Para mostrar una imagen de trama, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="92cd5-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="92cd5-107">La instancia de la <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.DrawImage%2A> método, que recibe el <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> como un argumento.</span><span class="sxs-lookup"><span data-stu-id="92cd5-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="92cd5-108">Tipos de archivos y clonación</span><span class="sxs-lookup"><span data-stu-id="92cd5-108">File Types and Cloning</span></span>  
 <span data-ttu-id="92cd5-109">En el ejemplo de código siguiente se muestra cómo construir un <xref:System.Drawing.Bitmap> desde el archivo Climber.jpg y se muestra el mapa de bits.</span><span class="sxs-lookup"><span data-stu-id="92cd5-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="92cd5-110">El punto de destino de la esquina superior izquierda de la imagen, (10, 10), se especifica en los parámetros segundo y tercero.</span><span class="sxs-lookup"><span data-stu-id="92cd5-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="92cd5-111">En la siguiente ilustración muestra la imagen.</span><span class="sxs-lookup"><span data-stu-id="92cd5-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="92cd5-112">![Ejemplo de la imagen](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="92cd5-112">![Image Sample](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="92cd5-113">Puede construir <xref:System.Drawing.Bitmap> formatos de archivo de objetos desde una variedad de gráficos: BMP, GIF, JPEG, EXIF, PNG, TIFF e icono.</span><span class="sxs-lookup"><span data-stu-id="92cd5-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="92cd5-114">En el ejemplo de código siguiente se muestra cómo construir <xref:System.Drawing.Bitmap> objetos desde una variedad de tipos de archivo y, a continuación, muestra los mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="92cd5-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="92cd5-115">El <xref:System.Drawing.Bitmap> clase proporciona un <xref:System.Drawing.Bitmap.Clone%2A> método que puede usar para realizar una copia de un miembro de <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="92cd5-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="92cd5-116">El <xref:System.Drawing.Bitmap.Clone%2A> método tiene un parámetro de rectángulo de origen que se puede utilizar para especificar la parte del mapa de bits original que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="92cd5-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="92cd5-117">En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Drawing.Bitmap> mediante la clonación de la mitad superior de un objeto <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="92cd5-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="92cd5-118">A continuación, se dibujan las imágenes.</span><span class="sxs-lookup"><span data-stu-id="92cd5-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="92cd5-119">La ilustración siguiente muestra las dos imágenes.</span><span class="sxs-lookup"><span data-stu-id="92cd5-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="92cd5-120">![Recortar](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="92cd5-120">![Cropping](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92cd5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="92cd5-121">See Also</span></span>  
 [<span data-ttu-id="92cd5-122">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="92cd5-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="92cd5-123">Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="92cd5-123">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="92cd5-124">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="92cd5-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
