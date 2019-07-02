---
title: Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505092"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="60043-102">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="60043-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="60043-103">El <xref:System.Drawing> espacio de nombres proporciona la <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> clases para almacenar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="60043-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="60043-104">Mediante el uso de codificadores de imágenes en GDI +, puede escribir imágenes de la memoria en el disco.</span><span class="sxs-lookup"><span data-stu-id="60043-104">By using image encoders in GDI+, you can write images from memory to disk.</span></span> <span data-ttu-id="60043-105">Mediante el uso de descodificadores de imágenes en GDI +, puede cargar imágenes desde el disco en la memoria.</span><span class="sxs-lookup"><span data-stu-id="60043-105">By using image decoders in GDI+, you can load images from disk into memory.</span></span> <span data-ttu-id="60043-106">Un codificador convierte los datos en un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> objeto en un formato de archivo de disco designado.</span><span class="sxs-lookup"><span data-stu-id="60043-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="60043-107">Un descodificador convierte los datos en un archivo de disco al formato requerido por el <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> objetos.</span><span class="sxs-lookup"><span data-stu-id="60043-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="60043-108">GDI + tiene integrados codificadores y descodificadores que admiten los siguientes tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="60043-108">GDI+ has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="60043-109">BMP</span><span class="sxs-lookup"><span data-stu-id="60043-109">BMP</span></span>  
  
- <span data-ttu-id="60043-110">GIF</span><span class="sxs-lookup"><span data-stu-id="60043-110">GIF</span></span>  
  
- <span data-ttu-id="60043-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="60043-111">JPEG</span></span>  
  
- <span data-ttu-id="60043-112">PNG</span><span class="sxs-lookup"><span data-stu-id="60043-112">PNG</span></span>  
  
- <span data-ttu-id="60043-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="60043-113">TIFF</span></span>  
  
 <span data-ttu-id="60043-114">GDI + también tiene descodificadores integrados que admiten los siguientes tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="60043-114">GDI+ also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="60043-115">WMF</span><span class="sxs-lookup"><span data-stu-id="60043-115">WMF</span></span>  
  
- <span data-ttu-id="60043-116">EMF</span><span class="sxs-lookup"><span data-stu-id="60043-116">EMF</span></span>  
  
- <span data-ttu-id="60043-117">ICON</span><span class="sxs-lookup"><span data-stu-id="60043-117">ICON</span></span>  
  
 <span data-ttu-id="60043-118">Los temas siguientes describen los codificadores y descodificadores con más detalle:</span><span class="sxs-lookup"><span data-stu-id="60043-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60043-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="60043-119">In This Section</span></span>  
 [<span data-ttu-id="60043-120">Cómo: Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="60043-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="60043-121">Describe cómo enumerar los codificadores disponibles en un equipo.</span><span class="sxs-lookup"><span data-stu-id="60043-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="60043-122">Cómo: Enumerar los descodificadores instalados</span><span class="sxs-lookup"><span data-stu-id="60043-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="60043-123">Describe cómo enumerar los descodificadores disponibles en un equipo.</span><span class="sxs-lookup"><span data-stu-id="60043-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="60043-124">Cómo: Determinar los parámetros admitidos por un codificador</span><span class="sxs-lookup"><span data-stu-id="60043-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="60043-125">Describe cómo enumerar los <xref:System.Drawing.Imaging.EncoderParameters> admitidos por un codificador.</span><span class="sxs-lookup"><span data-stu-id="60043-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="60043-126">Cómo: Convertir una imagen BMP en una imagen PNG</span><span class="sxs-lookup"><span data-stu-id="60043-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="60043-127">Describe cómo guardar una imagen en un formato de imagen diferente.</span><span class="sxs-lookup"><span data-stu-id="60043-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="60043-128">Cómo: Establecer el nivel de compresión de JPEG</span><span class="sxs-lookup"><span data-stu-id="60043-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="60043-129">Describe cómo cambiar el nivel de calidad de una imagen.</span><span class="sxs-lookup"><span data-stu-id="60043-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="60043-130">Referencia</span><span class="sxs-lookup"><span data-stu-id="60043-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="60043-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="60043-131">Related Sections</span></span>  
 <span data-ttu-id="60043-132">[About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)</span><span class="sxs-lookup"><span data-stu-id="60043-132">[About GDI+ Managed Code](about-gdi-managed-code.md)</span></span>  
  
 [<span data-ttu-id="60043-133">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="60043-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
