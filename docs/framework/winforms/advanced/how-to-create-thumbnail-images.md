---
title: Procedimiento para crear imágenes en miniatura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 275041372bd5e7da5dd0b32dc0a3d70a38bd0dcd
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063764"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="607e6-102">Procedimiento para crear imágenes en miniatura</span><span class="sxs-lookup"><span data-stu-id="607e6-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="607e6-103">Una imagen en miniatura es una versión reducida de una imagen.</span><span class="sxs-lookup"><span data-stu-id="607e6-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="607e6-104">Puede crear una imagen en miniatura mediante una llamada a la <xref:System.Drawing.Image.GetThumbnailImage%2A> método de un <xref:System.Drawing.Image> objeto.</span><span class="sxs-lookup"><span data-stu-id="607e6-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="607e6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="607e6-105">Example</span></span>  
 <span data-ttu-id="607e6-106">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde un archivo JPG.</span><span class="sxs-lookup"><span data-stu-id="607e6-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="607e6-107">La imagen original tiene un ancho de 640 píxeles y un alto de 479 píxeles.</span><span class="sxs-lookup"><span data-stu-id="607e6-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="607e6-108">El código crea una imagen en miniatura que tiene un ancho de 100 píxeles y un alto de 100 píxeles.</span><span class="sxs-lookup"><span data-stu-id="607e6-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="607e6-109">La siguiente ilustración muestra la imagen en miniatura:</span><span class="sxs-lookup"><span data-stu-id="607e6-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![Captura de pantalla que muestra la miniatura de salida.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
>  <span data-ttu-id="607e6-111">En este ejemplo, un método de devolución de llamada se declara, pero nunca se utiliza.</span><span class="sxs-lookup"><span data-stu-id="607e6-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="607e6-112">Esto es compatible con todas las versiones de GDI +.</span><span class="sxs-lookup"><span data-stu-id="607e6-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="607e6-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="607e6-113">Compiling the Code</span></span>  
 <span data-ttu-id="607e6-114">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="607e6-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="607e6-115">Para ejecutar el ejemplo, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="607e6-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="607e6-116">Cree una nueva aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="607e6-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="607e6-117">Agregue el código de ejemplo al formulario.</span><span class="sxs-lookup"><span data-stu-id="607e6-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="607e6-118">Cree un controlador para el formulario <xref:System.Windows.Forms.Control.Paint> eventos</span><span class="sxs-lookup"><span data-stu-id="607e6-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="607e6-119">En el <xref:System.Windows.Forms.Control.Paint> controlador, llamada la `GetThumbnail` método y pase `e` para <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="607e6-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="607e6-120">Buscar un archivo de imagen que desea realizar una miniatura.</span><span class="sxs-lookup"><span data-stu-id="607e6-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="607e6-121">En el `GetThumbnail` método, especifique la ruta de acceso y nombre de la imagen de archivo.</span><span class="sxs-lookup"><span data-stu-id="607e6-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="607e6-122">Presione F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="607e6-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="607e6-123">Aparece una imagen en miniatura del 100 por 100 en el formulario.</span><span class="sxs-lookup"><span data-stu-id="607e6-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607e6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="607e6-124">See also</span></span>

- [<span data-ttu-id="607e6-125">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="607e6-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="607e6-126">Trabajar con imágenes, mapas de bits, iconos y metarchivos</span><span class="sxs-lookup"><span data-stu-id="607e6-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
