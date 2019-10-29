---
title: 'Cómo: Leer metadatos de imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: cd3b636f8f0058d4a8eacc656f95d5f46b8967e2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040750"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="21706-102">Cómo: Leer metadatos de imagen</span><span class="sxs-lookup"><span data-stu-id="21706-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="21706-103">Algunos archivos de imagen contienen metadatos que se pueden leer para determinar las características de la imagen.</span><span class="sxs-lookup"><span data-stu-id="21706-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="21706-104">Por ejemplo, una fotografía digital podría contener metadatos que puede leer para determinar la marca y el modelo de la cámara utilizada para capturar la imagen.</span><span class="sxs-lookup"><span data-stu-id="21706-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="21706-105">Con GDI+, puede leer los metadatos existentes y también puede escribir nuevos metadatos en archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="21706-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="21706-106">GDI+ almacena un elemento individual de metadatos en un objeto de <xref:System.Drawing.Imaging.PropertyItem>.</span><span class="sxs-lookup"><span data-stu-id="21706-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="21706-107">Puede leer la propiedad <xref:System.Drawing.Image.PropertyItems%2A> de un objeto <xref:System.Drawing.Image> para recuperar todos los metadatos de un archivo.</span><span class="sxs-lookup"><span data-stu-id="21706-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="21706-108">La propiedad <xref:System.Drawing.Image.PropertyItems%2A> devuelve una matriz de objetos <xref:System.Drawing.Imaging.PropertyItem>.</span><span class="sxs-lookup"><span data-stu-id="21706-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="21706-109">Un objeto <xref:System.Drawing.Imaging.PropertyItem> tiene las cuatro propiedades siguientes: `Id`, `Value`, `Len`y `Type`.</span><span class="sxs-lookup"><span data-stu-id="21706-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="21706-110">Id.</span><span class="sxs-lookup"><span data-stu-id="21706-110">Id</span></span>

<span data-ttu-id="21706-111">Etiqueta que identifica el elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="21706-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="21706-112">En la tabla siguiente se muestran algunos valores que se pueden asignar a <xref:System.Drawing.Imaging.PropertyItem.Id%2A>:</span><span class="sxs-lookup"><span data-stu-id="21706-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="21706-113">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="21706-113">Hexadecimal value</span></span>|<span data-ttu-id="21706-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="21706-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="21706-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="21706-115">0x0320</span></span><br /><br /> <span data-ttu-id="21706-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="21706-116">0x010F</span></span><br /><br /> <span data-ttu-id="21706-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="21706-117">0x0110</span></span><br /><br /> <span data-ttu-id="21706-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="21706-118">0x9003</span></span><br /><br /> <span data-ttu-id="21706-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="21706-119">0x829A</span></span><br /><br /> <span data-ttu-id="21706-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="21706-120">0x5090</span></span><br /><br /> <span data-ttu-id="21706-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="21706-121">0x5091</span></span>|<span data-ttu-id="21706-122">Título de la imagen</span><span class="sxs-lookup"><span data-stu-id="21706-122">Image title</span></span><br /><br /> <span data-ttu-id="21706-123">Fabricante de equipos</span><span class="sxs-lookup"><span data-stu-id="21706-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="21706-124">Modelo de equipo</span><span class="sxs-lookup"><span data-stu-id="21706-124">Equipment model</span></span><br /><br /> <span data-ttu-id="21706-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="21706-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="21706-126">Hora de exposición de Exif</span><span class="sxs-lookup"><span data-stu-id="21706-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="21706-127">Tabla de luminancia</span><span class="sxs-lookup"><span data-stu-id="21706-127">Luminance table</span></span><br /><br /> <span data-ttu-id="21706-128">Tabla de crominancia</span><span class="sxs-lookup"><span data-stu-id="21706-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="21706-129">Valor</span><span class="sxs-lookup"><span data-stu-id="21706-129">Value</span></span>

<span data-ttu-id="21706-130">Matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="21706-130">An array of values.</span></span> <span data-ttu-id="21706-131">El formato de los valores viene determinado por la propiedad <xref:System.Drawing.Imaging.PropertyItem.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="21706-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="21706-132">Len</span><span class="sxs-lookup"><span data-stu-id="21706-132">Len</span></span>

<span data-ttu-id="21706-133">La longitud (en bytes) de la matriz de valores a la que apunta la propiedad <xref:System.Drawing.Imaging.PropertyItem.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="21706-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="21706-134">Type</span><span class="sxs-lookup"><span data-stu-id="21706-134">Type</span></span>

<span data-ttu-id="21706-135">El tipo de datos de los valores de la matriz a la que apunta la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="21706-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="21706-136">Los formatos indicados por los valores de la propiedad `Type` se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="21706-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="21706-137">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="21706-137">Numeric value</span></span>|<span data-ttu-id="21706-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="21706-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="21706-139">1</span><span class="sxs-lookup"><span data-stu-id="21706-139">1</span></span>|<span data-ttu-id="21706-140">`Byte`.</span><span class="sxs-lookup"><span data-stu-id="21706-140">A `Byte`</span></span>|
|<span data-ttu-id="21706-141">2</span><span class="sxs-lookup"><span data-stu-id="21706-141">2</span></span>|<span data-ttu-id="21706-142">Matriz de objetos `Byte` codificados como ASCII</span><span class="sxs-lookup"><span data-stu-id="21706-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="21706-143">3</span><span class="sxs-lookup"><span data-stu-id="21706-143">3</span></span>|<span data-ttu-id="21706-144">Entero de 16 bits</span><span class="sxs-lookup"><span data-stu-id="21706-144">A 16-bit integer</span></span>|
|<span data-ttu-id="21706-145">4</span><span class="sxs-lookup"><span data-stu-id="21706-145">4</span></span>|<span data-ttu-id="21706-146">Un entero de 32 bits</span><span class="sxs-lookup"><span data-stu-id="21706-146">A 32-bit integer</span></span>|
|<span data-ttu-id="21706-147">5</span><span class="sxs-lookup"><span data-stu-id="21706-147">5</span></span>|<span data-ttu-id="21706-148">Matriz de dos objetos `Byte` que representan un número racional</span><span class="sxs-lookup"><span data-stu-id="21706-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="21706-149">6</span><span class="sxs-lookup"><span data-stu-id="21706-149">6</span></span>|<span data-ttu-id="21706-150">No se utiliza</span><span class="sxs-lookup"><span data-stu-id="21706-150">Not used</span></span>|
|<span data-ttu-id="21706-151">7</span><span class="sxs-lookup"><span data-stu-id="21706-151">7</span></span>|<span data-ttu-id="21706-152">Sin definir</span><span class="sxs-lookup"><span data-stu-id="21706-152">Undefined</span></span>|
|<span data-ttu-id="21706-153">8</span><span class="sxs-lookup"><span data-stu-id="21706-153">8</span></span>|<span data-ttu-id="21706-154">No se utiliza</span><span class="sxs-lookup"><span data-stu-id="21706-154">Not used</span></span>|
|<span data-ttu-id="21706-155">9</span><span class="sxs-lookup"><span data-stu-id="21706-155">9</span></span>|`SLong`|
|<span data-ttu-id="21706-156">10</span><span class="sxs-lookup"><span data-stu-id="21706-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="21706-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21706-157">Example</span></span>
  
<span data-ttu-id="21706-158">En el siguiente ejemplo de código se leen y muestran los siete fragmentos de metadatos del archivo `FakePhoto.jpg`.</span><span class="sxs-lookup"><span data-stu-id="21706-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="21706-159">El segundo elemento de propiedad (Índice 1) de la lista tiene <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (fabricante del equipo) y <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (matriz de bytes codificada en ASCII).</span><span class="sxs-lookup"><span data-stu-id="21706-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="21706-160">En el ejemplo de código se muestra el valor de ese elemento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="21706-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="21706-161">El código genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="21706-161">The code produces output similar to the following:</span></span>

```output
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```

## <a name="compiling-the-code"></a><span data-ttu-id="21706-162">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="21706-162">Compiling the Code</span></span>

<span data-ttu-id="21706-163">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="21706-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="21706-164">Controle el evento de <xref:System.Windows.Forms.Control.Paint> del formulario y péguelo en el controlador de eventos Paint.</span><span class="sxs-lookup"><span data-stu-id="21706-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="21706-165">Debe reemplazar `FakePhoto.jpg` por un nombre de imagen y una ruta de acceso válidas en el sistema e importar el espacio de nombres `System.Drawing.Imaging`.</span><span class="sxs-lookup"><span data-stu-id="21706-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="21706-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="21706-166">See also</span></span>

- [<span data-ttu-id="21706-167">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="21706-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="21706-168">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="21706-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
