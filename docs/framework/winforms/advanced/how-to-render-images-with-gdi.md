---
title: Procedimiento para representar imágenes con GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: e038da545bb3f56cc757710bcaa93aa2c86bfa67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342555"
---
# <a name="how-to-render-images-with-gdi"></a><span data-ttu-id="1acbf-102">Procedimiento para representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="1acbf-102">How to: Render Images with GDI+</span></span>
<span data-ttu-id="1acbf-103">Puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar imágenes que existan como archivos en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1acbf-103">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render images that exist as files in your applications.</span></span> <span data-ttu-id="1acbf-104">Hacerlo mediante la creación de un nuevo objeto de un <xref:System.Drawing.Image> clase (como <xref:System.Drawing.Bitmap>), creando un <xref:System.Drawing.Graphics> objeto que hace referencia a la superficie de dibujo que desea usar y llamar a la <xref:System.Drawing.Graphics.DrawImage%2A> método de la <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="1acbf-104">You do this by creating a new object of an <xref:System.Drawing.Image> class (such as <xref:System.Drawing.Bitmap>), creating a <xref:System.Drawing.Graphics> object that refers to the drawing surface you want to use, and calling the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="1acbf-105">La imagen se pintará sobre la superficie de dibujo representada por la clase graphics.</span><span class="sxs-lookup"><span data-stu-id="1acbf-105">The image will be painted onto the drawing surface represented by the graphics class.</span></span> <span data-ttu-id="1acbf-106">Puede usar el Editor de imágenes para crear y editar archivos de imagen en tiempo de diseño y representarlos con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1acbf-106">You can use the Image Editor to create and edit image files at design time, and render them with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] at run time.</span></span> <span data-ttu-id="1acbf-107">Para más información, consulte [Editor de imágenes para iconos](/cpp/windows/image-editor-for-icons).</span><span class="sxs-lookup"><span data-stu-id="1acbf-107">For more information, see [Image Editor for Icons](/cpp/windows/image-editor-for-icons).</span></span>  
  
### <a name="to-render-an-image-with-gdi"></a><span data-ttu-id="1acbf-108">Para representar una imagen con GDI+</span><span class="sxs-lookup"><span data-stu-id="1acbf-108">To render an image with GDI+</span></span>  
  
1. <span data-ttu-id="1acbf-109">Cree un objeto que represente la imagen que desee mostrar.</span><span class="sxs-lookup"><span data-stu-id="1acbf-109">Create an object representing the image you want to display.</span></span> <span data-ttu-id="1acbf-110">Este objeto debe ser un miembro de una clase que hereda de <xref:System.Drawing.Image>, tales como <xref:System.Drawing.Bitmap> o <xref:System.Drawing.Imaging.Metafile>.</span><span class="sxs-lookup"><span data-stu-id="1acbf-110">This object must be a member of a class that inherits from <xref:System.Drawing.Image>, such as <xref:System.Drawing.Bitmap> or <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="1acbf-111">Se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1acbf-111">An example is shown:</span></span>  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the   
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the   
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. <span data-ttu-id="1acbf-112">Crear un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo que desea usar.</span><span class="sxs-lookup"><span data-stu-id="1acbf-112">Create a <xref:System.Drawing.Graphics> object that represents the drawing surface you want to use.</span></span> <span data-ttu-id="1acbf-113">Para obtener más información, vea [Cómo: Crear objetos Graphics para dibujar](how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="1acbf-113">For more information, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of   
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of   
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. <span data-ttu-id="1acbf-114">Llame a la <xref:System.Drawing.Graphics.DrawImage%2A> del objeto graphics para representar la imagen.</span><span class="sxs-lookup"><span data-stu-id="1acbf-114">Call the <xref:System.Drawing.Graphics.DrawImage%2A> of your graphics object to render the image.</span></span> <span data-ttu-id="1acbf-115">Debe especificar la imagen que se va a dibujar y las coordenadas en las que se va a dibujar.</span><span class="sxs-lookup"><span data-stu-id="1acbf-115">You must specify both the image to be drawn, and the coordinates where it is to be drawn.</span></span>  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1acbf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1acbf-116">See also</span></span>

- [<span data-ttu-id="1acbf-117">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="1acbf-117">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="1acbf-118">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="1acbf-118">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="1acbf-119">Lápices, líneas y rectángulos en GDI+</span><span class="sxs-lookup"><span data-stu-id="1acbf-119">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
- [<span data-ttu-id="1acbf-120">Cómo: Dibujar texto en un formulario de Windows</span><span class="sxs-lookup"><span data-stu-id="1acbf-120">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)
- [<span data-ttu-id="1acbf-121">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1acbf-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="1acbf-122">Dibujar líneas o figuras cerradas</span><span class="sxs-lookup"><span data-stu-id="1acbf-122">Drawing Lines or Closed Figures</span></span>](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [<span data-ttu-id="1acbf-123">Editor de imágenes para iconos</span><span class="sxs-lookup"><span data-stu-id="1acbf-123">Image Editor for Icons</span></span>](/cpp/windows/image-editor-for-icons)
