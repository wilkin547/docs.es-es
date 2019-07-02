---
title: Imágenes, mapas de bits y metarchivos
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
ms.openlocfilehash: 5f50d21f4793efb497eb5b030d96a7dc3ab54a04
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505700"
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="cf5c6-102">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="cf5c6-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="cf5c6-103">La clase `Image` es una clase base abstracta que proporciona métodos para trabajar con imágenes de trama (mapas de bits) e imágenes vectoriales (metarchivos).</span><span class="sxs-lookup"><span data-stu-id="cf5c6-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="cf5c6-104">Las clases `Bitmap` y <xref:System.Drawing.Imaging.Metafile> se heredan de la clase `Image`.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="cf5c6-105">La clase `Bitmap` amplía las capacidades de la clase `Image` al proporcionar métodos adicionales para cargar, guardar y manipular imágenes de trama.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="cf5c6-106">La clase <xref:System.Drawing.Imaging.Metafile> amplía las capacidades de la clase `Image` al proporcionar métodos adicionales para grabar y examinar imágenes vectoriales.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf5c6-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf5c6-107">In This Section</span></span>  
 [<span data-ttu-id="cf5c6-108">Tipos de mapas de bits</span><span class="sxs-lookup"><span data-stu-id="cf5c6-108">Types of Bitmaps</span></span>](types-of-bitmaps.md)  
 <span data-ttu-id="cf5c6-109">Describe los distintos formatos de imagen.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="cf5c6-110">Metarchivos en GDI+</span><span class="sxs-lookup"><span data-stu-id="cf5c6-110">Metafiles in GDI+</span></span>](metafiles-in-gdi.md)  
 <span data-ttu-id="cf5c6-111">Explica la compatibilidad con GDI + metarchivos.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-111">Discusses GDI+ support for metafiles.</span></span>  
  
 [<span data-ttu-id="cf5c6-112">Dibujar, colocar y clonar imágenes en GDI+</span><span class="sxs-lookup"><span data-stu-id="cf5c6-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="cf5c6-113">Describe los métodos para dibujar imágenes de trama y vectoriales con código administrado.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="cf5c6-114">Recortar y ajustar la escala de las imágenes en GDI+</span><span class="sxs-lookup"><span data-stu-id="cf5c6-114">Cropping and Scaling Images in GDI+</span></span>](cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="cf5c6-115">Describe los métodos para recortar y ajustar la escala de imágenes de trama y vectoriales con código administrado.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cf5c6-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="cf5c6-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="cf5c6-117">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="cf5c6-118">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cf5c6-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cf5c6-119">Related Sections</span></span>  
 [<span data-ttu-id="cf5c6-120">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="cf5c6-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="cf5c6-121">Contiene vínculos a temas que muestran cómo utilizar imágenes en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cf5c6-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
