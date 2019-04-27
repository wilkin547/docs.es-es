---
title: Trabajar con imágenes, mapas de bits, iconos y metarchivos
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
ms.openlocfilehash: 61d534f8299c920f656abe4280cc3ea5e609c0b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011923"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="ee8e5-102">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="ee8e5-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="ee8e5-103">proporciona la clase `Bitmap` para trabajar con imágenes de trama y la clase `Metafile` para trabajar con imágenes vectoriales.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-103">provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="ee8e5-104">Las clases `Bitmap` y `Metafile` heredan de la clase `Image`.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee8e5-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ee8e5-105">In This Section</span></span>  
 [<span data-ttu-id="ee8e5-106">Cómo: Dibujar un mapa de bits existente en la pantalla</span><span class="sxs-lookup"><span data-stu-id="ee8e5-106">How to: Draw an Existing Bitmap to the Screen</span></span>](how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="ee8e5-107">Describe cómo cargar y dibujar mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="ee8e5-108">Cómo: Cargar y mostrar metarchivos</span><span class="sxs-lookup"><span data-stu-id="ee8e5-108">How to: Load and Display Metafiles</span></span>](how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="ee8e5-109">Muestra cómo cargar y dibujar metarchivos.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="ee8e5-110">Recortar y ajustar la escala de las imágenes en GDI+</span><span class="sxs-lookup"><span data-stu-id="ee8e5-110">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="ee8e5-111">Explica cómo recortar y escalar imágenes vectoriales y de trama.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="ee8e5-112">Cómo: Girar, reflejar y sesgar imágenes</span><span class="sxs-lookup"><span data-stu-id="ee8e5-112">How to: Rotate, Reflect, and Skew Images</span></span>](how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="ee8e5-113">Describe cómo dibujar imágenes giradas, reflejadas y sesgadas.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="ee8e5-114">Cómo: Usar el modo de interpolación para controlar la calidad de imagen durante el escalado</span><span class="sxs-lookup"><span data-stu-id="ee8e5-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="ee8e5-115">Muestra cómo usar la enumeración <xref:System.Drawing.Drawing2D.InterpolationMode> para cambiar la calidad de la imagen.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="ee8e5-116">Cómo: Crear imágenes en miniatura</span><span class="sxs-lookup"><span data-stu-id="ee8e5-116">How to: Create Thumbnail Images</span></span>](how-to-create-thumbnail-images.md)  
 <span data-ttu-id="ee8e5-117">Describe cómo crear imágenes en miniatura.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="ee8e5-118">Cómo: Mejorar el rendimiento evitando el ajuste de escala automática</span><span class="sxs-lookup"><span data-stu-id="ee8e5-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="ee8e5-119">Explica cómo dibujar una imagen sin ajustar la escala automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="ee8e5-120">Cómo: Leer metadatos de imagen</span><span class="sxs-lookup"><span data-stu-id="ee8e5-120">How to: Read Image Metadata</span></span>](how-to-read-image-metadata.md)  
 <span data-ttu-id="ee8e5-121">Describe cómo leer metadatos de una imagen.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="ee8e5-122">Cómo: Crear un mapa de bits en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ee8e5-122">How to: Create a Bitmap at Run Time</span></span>](how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="ee8e5-123">Muestra cómo dibujar un mapa de bits en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="ee8e5-124">Cómo: Extraer el icono asociado a un archivo en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee8e5-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="ee8e5-125">Describe cómo extraer un icono que es un recurso incrustado de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ee8e5-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="ee8e5-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="ee8e5-127">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="ee8e5-128">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="ee8e5-129">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ee8e5-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ee8e5-130">Related Sections</span></span>  
 [<span data-ttu-id="ee8e5-131">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="ee8e5-131">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="ee8e5-132">Contiene vínculos a temas que describen distintos tipos de mapas de bits y cómo manipularlos en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ee8e5-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
