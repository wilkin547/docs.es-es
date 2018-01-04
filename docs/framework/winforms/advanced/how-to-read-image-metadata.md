---
title: "Cómo: Leer metadatos de imagen"
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
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b610e499ff980d2e705ad855ae98c1d54ff412e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="2f3f6-102">Cómo: Leer metadatos de imagen</span><span class="sxs-lookup"><span data-stu-id="2f3f6-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="2f3f6-103">Algunos archivos de imagen contienen metadatos que se pueden leer para determinar las características de la imagen.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="2f3f6-104">Por ejemplo, una fotografía digital podría contener metadatos que se pueden leer para determinar la marca y modelo de la cámara empleada para capturar la imagen.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="2f3f6-105">Con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede leer los metadatos existentes y también puede escribir metadatos nuevos en archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="2f3f6-106">almacena un dato de metadatos en un <xref:System.Drawing.Imaging.PropertyItem> objeto.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-106"> stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="2f3f6-107">Puede leer el <xref:System.Drawing.Image.PropertyItems%2A> propiedad de un <xref:System.Drawing.Image> objeto que se va a recuperar todos los metadatos de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="2f3f6-108">El <xref:System.Drawing.Image.PropertyItems%2A> propiedad devuelve una matriz de <xref:System.Drawing.Imaging.PropertyItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="2f3f6-109">A <xref:System.Drawing.Imaging.PropertyItem> objeto tiene las cuatro propiedades siguientes: `Id`, `Value`, `Len`, y `Type`.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="2f3f6-110">Id.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-110">Id</span></span>  
 <span data-ttu-id="2f3f6-111">Una etiqueta que identifica el elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="2f3f6-112">Algunos valores que pueden asignarse a <xref:System.Drawing.Imaging.PropertyItem.Id%2A> se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="2f3f6-113">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="2f3f6-113">Hexadecimal value</span></span>|<span data-ttu-id="2f3f6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f3f6-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="2f3f6-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="2f3f6-115">0x0320</span></span><br /><br /> <span data-ttu-id="2f3f6-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="2f3f6-116">0x010F</span></span><br /><br /> <span data-ttu-id="2f3f6-117">0 x 0110</span><span class="sxs-lookup"><span data-stu-id="2f3f6-117">0x0110</span></span><br /><br /> <span data-ttu-id="2f3f6-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="2f3f6-118">0x9003</span></span><br /><br /> <span data-ttu-id="2f3f6-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="2f3f6-119">0x829A</span></span><br /><br /> <span data-ttu-id="2f3f6-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="2f3f6-120">0x5090</span></span><br /><br /> <span data-ttu-id="2f3f6-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="2f3f6-121">0x5091</span></span>|<span data-ttu-id="2f3f6-122">Título de la imagen</span><span class="sxs-lookup"><span data-stu-id="2f3f6-122">Image title</span></span><br /><br /> <span data-ttu-id="2f3f6-123">Fabricante de equipos</span><span class="sxs-lookup"><span data-stu-id="2f3f6-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="2f3f6-124">Modelo del equipo</span><span class="sxs-lookup"><span data-stu-id="2f3f6-124">Equipment model</span></span><br /><br /> <span data-ttu-id="2f3f6-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="2f3f6-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="2f3f6-126">Tiempo de exposición de EXIF</span><span class="sxs-lookup"><span data-stu-id="2f3f6-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="2f3f6-127">Tabla de luminancia</span><span class="sxs-lookup"><span data-stu-id="2f3f6-127">Luminance table</span></span><br /><br /> <span data-ttu-id="2f3f6-128">Tabla cromática</span><span class="sxs-lookup"><span data-stu-id="2f3f6-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="2f3f6-129">Valor</span><span class="sxs-lookup"><span data-stu-id="2f3f6-129">Value</span></span>  
 <span data-ttu-id="2f3f6-130">Una matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-130">An array of values.</span></span> <span data-ttu-id="2f3f6-131">El formato de los valores se determina por la <xref:System.Drawing.Imaging.PropertyItem.Type%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="2f3f6-132">Len</span><span class="sxs-lookup"><span data-stu-id="2f3f6-132">Len</span></span>  
 <span data-ttu-id="2f3f6-133">La longitud (en bytes) de la matriz de valores que apunta el <xref:System.Drawing.Imaging.PropertyItem.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="2f3f6-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="2f3f6-134">Type</span></span>  
 <span data-ttu-id="2f3f6-135">El tipo de datos de los valores de la matriz indicada por el `Value` propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="2f3f6-136">Los formatos indican por la `Type` en la tabla siguiente se muestran los valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="2f3f6-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="2f3f6-137">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="2f3f6-137">Numeric value</span></span>|<span data-ttu-id="2f3f6-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f3f6-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="2f3f6-139">1</span><span class="sxs-lookup"><span data-stu-id="2f3f6-139">1</span></span>|<span data-ttu-id="2f3f6-140">`Byte`.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-140">A `Byte`</span></span>|  
|<span data-ttu-id="2f3f6-141">2</span><span class="sxs-lookup"><span data-stu-id="2f3f6-141">2</span></span>|<span data-ttu-id="2f3f6-142">Una matriz de `Byte` objetos codificados como ASCII</span><span class="sxs-lookup"><span data-stu-id="2f3f6-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="2f3f6-143">3</span><span class="sxs-lookup"><span data-stu-id="2f3f6-143">3</span></span>|<span data-ttu-id="2f3f6-144">Un entero de 16 bits</span><span class="sxs-lookup"><span data-stu-id="2f3f6-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="2f3f6-145">4</span><span class="sxs-lookup"><span data-stu-id="2f3f6-145">4</span></span>|<span data-ttu-id="2f3f6-146">Un entero de 32 bits</span><span class="sxs-lookup"><span data-stu-id="2f3f6-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="2f3f6-147">5</span><span class="sxs-lookup"><span data-stu-id="2f3f6-147">5</span></span>|<span data-ttu-id="2f3f6-148">Una matriz de dos `Byte` objetos que representan un número racional</span><span class="sxs-lookup"><span data-stu-id="2f3f6-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="2f3f6-149">6</span><span class="sxs-lookup"><span data-stu-id="2f3f6-149">6</span></span>|<span data-ttu-id="2f3f6-150">No se utiliza</span><span class="sxs-lookup"><span data-stu-id="2f3f6-150">Not used</span></span>|  
|<span data-ttu-id="2f3f6-151">7</span><span class="sxs-lookup"><span data-stu-id="2f3f6-151">7</span></span>|<span data-ttu-id="2f3f6-152">Sin definir</span><span class="sxs-lookup"><span data-stu-id="2f3f6-152">Undefined</span></span>|  
|<span data-ttu-id="2f3f6-153">8</span><span class="sxs-lookup"><span data-stu-id="2f3f6-153">8</span></span>|<span data-ttu-id="2f3f6-154">No se utiliza</span><span class="sxs-lookup"><span data-stu-id="2f3f6-154">Not used</span></span>|  
|<span data-ttu-id="2f3f6-155">9</span><span class="sxs-lookup"><span data-stu-id="2f3f6-155">9</span></span>|`SLong`|  
|<span data-ttu-id="2f3f6-156">10</span><span class="sxs-lookup"><span data-stu-id="2f3f6-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="2f3f6-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f3f6-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2f3f6-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f3f6-158">Description</span></span>  
 <span data-ttu-id="2f3f6-159">En el ejemplo de código siguiente se lee y muestra los siete elementos de metadatos en el archivo `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="2f3f6-160">El segundo elemento de la propiedad (índice 1) en la lista tiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (fabricante del equipo) y <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matriz de bytes codificada en ASCII).</span><span class="sxs-lookup"><span data-stu-id="2f3f6-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="2f3f6-161">El ejemplo de código muestra el valor de ese elemento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="2f3f6-162">El código produce un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f3f6-162">The code produces output similar to the following:</span></span>  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a><span data-ttu-id="2f3f6-163">Código</span><span class="sxs-lookup"><span data-stu-id="2f3f6-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f3f6-164">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2f3f6-164">Compiling the Code</span></span>  
 <span data-ttu-id="2f3f6-165">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="2f3f6-166">Controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos y pegue este código en el controlador de eventos de pintura.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="2f3f6-167">Debe reemplazar `FakePhoto.jpg` con un nombre de la imagen y la ruta de acceso válida en su sistema e importar el `System.Drawing.Imaging` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="2f3f6-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3f6-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f3f6-168">See Also</span></span>  
 [<span data-ttu-id="2f3f6-169">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="2f3f6-169">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="2f3f6-170">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="2f3f6-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
