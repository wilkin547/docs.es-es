---
title: Procedimiento para leer metadatos de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 8294bc6596c408160a50d9d7d5e6154f66025c73
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988569"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="3dac0-102">Procedimiento para leer metadatos de imagen</span><span class="sxs-lookup"><span data-stu-id="3dac0-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="3dac0-103">Algunos archivos de imagen contienen metadatos que se pueden leer para determinar las características de la imagen.</span><span class="sxs-lookup"><span data-stu-id="3dac0-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="3dac0-104">Por ejemplo, una fotografía digital podría contener metadatos que puede leer para determinar la marca y el modelo de la cámara utilizada para capturar la imagen.</span><span class="sxs-lookup"><span data-stu-id="3dac0-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="3dac0-105">Con GDI+, puede leer los metadatos existentes y también puede escribir nuevos metadatos en archivos de imagen.</span><span class="sxs-lookup"><span data-stu-id="3dac0-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 <span data-ttu-id="3dac0-106">GDI+ almacena un elemento individual de metadatos en <xref:System.Drawing.Imaging.PropertyItem> un objeto.</span><span class="sxs-lookup"><span data-stu-id="3dac0-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="3dac0-107">Puede leer la <xref:System.Drawing.Image.PropertyItems%2A> propiedad de un <xref:System.Drawing.Image> objeto para recuperar todos los metadatos de un archivo.</span><span class="sxs-lookup"><span data-stu-id="3dac0-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="3dac0-108">La <xref:System.Drawing.Image.PropertyItems%2A> propiedad devuelve una matriz de <xref:System.Drawing.Imaging.PropertyItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="3dac0-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="3dac0-109">Un <xref:System.Drawing.Imaging.PropertyItem> objeto tiene las cuatro propiedades siguientes: `Id`, `Value`, `Len`y `Type`.</span><span class="sxs-lookup"><span data-stu-id="3dac0-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="3dac0-110">Id</span><span class="sxs-lookup"><span data-stu-id="3dac0-110">Id</span></span>  
 <span data-ttu-id="3dac0-111">Etiqueta que identifica el elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="3dac0-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="3dac0-112">En la tabla siguiente se muestran algunos <xref:System.Drawing.Imaging.PropertyItem.Id%2A> valores que se pueden asignar a.</span><span class="sxs-lookup"><span data-stu-id="3dac0-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="3dac0-113">Valor hexadecimal</span><span class="sxs-lookup"><span data-stu-id="3dac0-113">Hexadecimal value</span></span>|<span data-ttu-id="3dac0-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3dac0-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="3dac0-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="3dac0-115">0x0320</span></span><br /><br /> <span data-ttu-id="3dac0-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="3dac0-116">0x010F</span></span><br /><br /> <span data-ttu-id="3dac0-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="3dac0-117">0x0110</span></span><br /><br /> <span data-ttu-id="3dac0-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="3dac0-118">0x9003</span></span><br /><br /> <span data-ttu-id="3dac0-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="3dac0-119">0x829A</span></span><br /><br /> <span data-ttu-id="3dac0-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="3dac0-120">0x5090</span></span><br /><br /> <span data-ttu-id="3dac0-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="3dac0-121">0x5091</span></span>|<span data-ttu-id="3dac0-122">Título de la imagen</span><span class="sxs-lookup"><span data-stu-id="3dac0-122">Image title</span></span><br /><br /> <span data-ttu-id="3dac0-123">Fabricante de equipos</span><span class="sxs-lookup"><span data-stu-id="3dac0-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="3dac0-124">Modelo de equipo</span><span class="sxs-lookup"><span data-stu-id="3dac0-124">Equipment model</span></span><br /><br /> <span data-ttu-id="3dac0-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="3dac0-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="3dac0-126">Hora de exposición de Exif</span><span class="sxs-lookup"><span data-stu-id="3dac0-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="3dac0-127">Tabla de luminancia</span><span class="sxs-lookup"><span data-stu-id="3dac0-127">Luminance table</span></span><br /><br /> <span data-ttu-id="3dac0-128">Tabla de crominancia</span><span class="sxs-lookup"><span data-stu-id="3dac0-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="3dac0-129">Valor</span><span class="sxs-lookup"><span data-stu-id="3dac0-129">Value</span></span>  
 <span data-ttu-id="3dac0-130">Matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="3dac0-130">An array of values.</span></span> <span data-ttu-id="3dac0-131">El formato de los valores viene determinado por la <xref:System.Drawing.Imaging.PropertyItem.Type%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="3dac0-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="3dac0-132">Len</span><span class="sxs-lookup"><span data-stu-id="3dac0-132">Len</span></span>  
 <span data-ttu-id="3dac0-133">La longitud (en bytes) de la matriz de valores a la que apunta <xref:System.Drawing.Imaging.PropertyItem.Value%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3dac0-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="3dac0-134">Type</span><span class="sxs-lookup"><span data-stu-id="3dac0-134">Type</span></span>  
 <span data-ttu-id="3dac0-135">El tipo de datos de los valores de la matriz a la que `Value` apunta la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3dac0-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="3dac0-136">Los formatos indicados por `Type` los valores de propiedad se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3dac0-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="3dac0-137">Valor numérico</span><span class="sxs-lookup"><span data-stu-id="3dac0-137">Numeric value</span></span>|<span data-ttu-id="3dac0-138">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3dac0-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="3dac0-139">1</span><span class="sxs-lookup"><span data-stu-id="3dac0-139">1</span></span>|<span data-ttu-id="3dac0-140">`Byte`.</span><span class="sxs-lookup"><span data-stu-id="3dac0-140">A `Byte`</span></span>|  
|<span data-ttu-id="3dac0-141">2</span><span class="sxs-lookup"><span data-stu-id="3dac0-141">2</span></span>|<span data-ttu-id="3dac0-142">Matriz de `Byte` objetos codificados como ASCII</span><span class="sxs-lookup"><span data-stu-id="3dac0-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="3dac0-143">3</span><span class="sxs-lookup"><span data-stu-id="3dac0-143">3</span></span>|<span data-ttu-id="3dac0-144">Entero de 16 bits</span><span class="sxs-lookup"><span data-stu-id="3dac0-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="3dac0-145">4</span><span class="sxs-lookup"><span data-stu-id="3dac0-145">4</span></span>|<span data-ttu-id="3dac0-146">Un entero de 32 bits</span><span class="sxs-lookup"><span data-stu-id="3dac0-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="3dac0-147">5</span><span class="sxs-lookup"><span data-stu-id="3dac0-147">5</span></span>|<span data-ttu-id="3dac0-148">Matriz de dos `Byte` objetos que representan un número racional</span><span class="sxs-lookup"><span data-stu-id="3dac0-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="3dac0-149">6</span><span class="sxs-lookup"><span data-stu-id="3dac0-149">6</span></span>|<span data-ttu-id="3dac0-150">No se utiliza</span><span class="sxs-lookup"><span data-stu-id="3dac0-150">Not used</span></span>|  
|<span data-ttu-id="3dac0-151">7</span><span class="sxs-lookup"><span data-stu-id="3dac0-151">7</span></span>|<span data-ttu-id="3dac0-152">Sin definir</span><span class="sxs-lookup"><span data-stu-id="3dac0-152">Undefined</span></span>|  
|<span data-ttu-id="3dac0-153">8</span><span class="sxs-lookup"><span data-stu-id="3dac0-153">8</span></span>|<span data-ttu-id="3dac0-154">No se utiliza</span><span class="sxs-lookup"><span data-stu-id="3dac0-154">Not used</span></span>|  
|<span data-ttu-id="3dac0-155">9</span><span class="sxs-lookup"><span data-stu-id="3dac0-155">9</span></span>|`SLong`|  
|<span data-ttu-id="3dac0-156">10</span><span class="sxs-lookup"><span data-stu-id="3dac0-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="3dac0-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dac0-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3dac0-158">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3dac0-158">Description</span></span>  
 <span data-ttu-id="3dac0-159">En el ejemplo de código siguiente se lee y se muestran los siete fragmentos de `FakePhoto.jpg`metadatos del archivo.</span><span class="sxs-lookup"><span data-stu-id="3dac0-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="3dac0-160">El segundo elemento de propiedad (Índice 1) de la lista <xref:System.Drawing.Imaging.PropertyItem.Id%2A> tiene 0x010F (fabricante del equipo <xref:System.Drawing.Imaging.PropertyItem.Type%2A> ) y 2 (matriz de bytes codificada en ASCII).</span><span class="sxs-lookup"><span data-stu-id="3dac0-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="3dac0-161">En el ejemplo de código se muestra el valor de ese elemento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="3dac0-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="3dac0-162">El código genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3dac0-162">The code produces output similar to the following:</span></span>  
 
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
  
### <a name="code"></a><span data-ttu-id="3dac0-163">Código</span><span class="sxs-lookup"><span data-stu-id="3dac0-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3dac0-164">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3dac0-164">Compiling the Code</span></span>  
 <span data-ttu-id="3dac0-165">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que <xref:System.Windows.Forms.Control.Paint> es un parámetro del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="3dac0-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="3dac0-166">Controle el evento <xref:System.Windows.Forms.Control.Paint> del formulario y péguelo en el controlador de eventos Paint.</span><span class="sxs-lookup"><span data-stu-id="3dac0-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="3dac0-167">Debe reemplazar `FakePhoto.jpg` por un nombre de imagen y una ruta de acceso válidas en el `System.Drawing.Imaging` sistema e importar el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3dac0-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dac0-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dac0-168">See also</span></span>

- [<span data-ttu-id="3dac0-169">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="3dac0-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="3dac0-170">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="3dac0-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
