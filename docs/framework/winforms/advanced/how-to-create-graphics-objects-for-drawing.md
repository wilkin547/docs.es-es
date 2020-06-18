---
title: Procedimiento para crear objetos gráficos para dibujar
description: Obtenga información sobre cómo crear un objeto gráfico que necesite dibujar líneas y formas, representar texto o mostrar y manipular imágenes con GDI+.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903212"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="42200-103">Procedimiento para crear objetos gráficos para dibujar</span><span class="sxs-lookup"><span data-stu-id="42200-103">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="42200-104">Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular imágenes con GDI+, debe crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="42200-104">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="42200-105">El <xref:System.Drawing.Graphics> objeto representa una superficie de dibujo de GDI+ y es el objeto que se utiliza para crear imágenes gráficas.</span><span class="sxs-lookup"><span data-stu-id="42200-105">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="42200-106">Hay dos pasos para trabajar con gráficos:</span><span class="sxs-lookup"><span data-stu-id="42200-106">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="42200-107">Crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="42200-107">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="42200-108">Usar el <xref:System.Drawing.Graphics> objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="42200-108">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="42200-109">Crear un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="42200-109">Creating a Graphics Object</span></span>  
 <span data-ttu-id="42200-110">Un objeto de gráficos se puede crear de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="42200-110">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="42200-111">Para crear un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="42200-111">To create a graphics object</span></span>  
  
- <span data-ttu-id="42200-112">Recibe una referencia a un objeto Graphics como parte de <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> caso de un formulario o un control.</span><span class="sxs-lookup"><span data-stu-id="42200-112">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="42200-113">Normalmente, este es el modo en que se obtiene una referencia a un objeto Graphics al crear código de dibujo para un control.</span><span class="sxs-lookup"><span data-stu-id="42200-113">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="42200-114">Del mismo modo, también puede obtener un objeto de gráficos como una propiedad de <xref:System.Drawing.Printing.PrintPageEventArgs> cuando controla el <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento para un <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="42200-114">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="42200-115">O bien</span><span class="sxs-lookup"><span data-stu-id="42200-115">-or-</span></span>  
  
- <span data-ttu-id="42200-116">Llame al <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de ese control o formulario.</span><span class="sxs-lookup"><span data-stu-id="42200-116">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="42200-117">Utilice este método si desea dibujar en un formulario o control que ya existe.</span><span class="sxs-lookup"><span data-stu-id="42200-117">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="42200-118">O bien</span><span class="sxs-lookup"><span data-stu-id="42200-118">-or-</span></span>  
  
- <span data-ttu-id="42200-119">Cree un <xref:System.Drawing.Graphics> objeto a partir de cualquier objeto que herede de <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="42200-119">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="42200-120">Este enfoque es útil cuando se desea modificar una imagen ya existente.</span><span class="sxs-lookup"><span data-stu-id="42200-120">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="42200-121">En las secciones siguientes se proporcionan detalles sobre cada uno de estos procesos.</span><span class="sxs-lookup"><span data-stu-id="42200-121">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="42200-122">PaintEventArgs en el controlador de eventos Paint</span><span class="sxs-lookup"><span data-stu-id="42200-122">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="42200-123">Al programar el <xref:System.Windows.Forms.PaintEventHandler> para los controles de o <xref:System.Drawing.Printing.PrintDocument.PrintPage> para <xref:System.Drawing.Printing.PrintDocument> , se proporciona un objeto de gráficos como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="42200-123">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="42200-124">Para obtener una referencia a un objeto Graphics desde PaintEventArgs en el evento Paint</span><span class="sxs-lookup"><span data-stu-id="42200-124">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="42200-125">Declare el <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="42200-125">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="42200-126">Asigne la variable para hacer referencia al <xref:System.Drawing.Graphics> objeto que se pasa como parte de <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="42200-126">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="42200-127">Inserte el código para pintar el formulario o el control.</span><span class="sxs-lookup"><span data-stu-id="42200-127">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="42200-128">En el ejemplo siguiente se muestra cómo hacer referencia a un <xref:System.Drawing.Graphics> objeto de <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> evento:</span><span class="sxs-lookup"><span data-stu-id="42200-128">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="42200-129">CreateGraphics (método)</span><span class="sxs-lookup"><span data-stu-id="42200-129">CreateGraphics Method</span></span>  
 <span data-ttu-id="42200-130">También puede utilizar el <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de ese control o formulario.</span><span class="sxs-lookup"><span data-stu-id="42200-130">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="42200-131">Para crear un objeto Graphics con el método CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="42200-131">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="42200-132">Llame al <xref:System.Windows.Forms.Control.CreateGraphics%2A> método del formulario o control en el que desea representar los gráficos.</span><span class="sxs-lookup"><span data-stu-id="42200-132">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="42200-133">Crear a partir de un objeto Image</span><span class="sxs-lookup"><span data-stu-id="42200-133">Create from an Image Object</span></span>  
 <span data-ttu-id="42200-134">Además, puede crear un objeto gráfico a partir de cualquier objeto que se derive de la <xref:System.Drawing.Image> clase.</span><span class="sxs-lookup"><span data-stu-id="42200-134">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="42200-135">Para crear un objeto gráfico a partir de una imagen</span><span class="sxs-lookup"><span data-stu-id="42200-135">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="42200-136">Llame al <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> método y proporcione el nombre de la variable de imagen de la que desea crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="42200-136">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="42200-137">En el ejemplo siguiente se muestra cómo usar un <xref:System.Drawing.Bitmap> objeto:</span><span class="sxs-lookup"><span data-stu-id="42200-137">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> <span data-ttu-id="42200-138">Solo puede crear <xref:System.Drawing.Graphics> objetos a partir de archivos. bmp no indexados, como archivos de 16 bits, de 24 bits y de 32 bits. bmp.</span><span class="sxs-lookup"><span data-stu-id="42200-138">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="42200-139">Cada píxel de archivos. bmp no indexados contiene un color, a diferencia de los píxeles de los archivos. bmp indexados, que contienen un índice en una tabla de colores.</span><span class="sxs-lookup"><span data-stu-id="42200-139">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="42200-140">Dibujar y manipular formas e imágenes</span><span class="sxs-lookup"><span data-stu-id="42200-140">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="42200-141">Una vez creada, se <xref:System.Drawing.Graphics> puede usar un objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="42200-141">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="42200-142">Los objetos de entidad de seguridad que se usan con el <xref:System.Drawing.Graphics> objeto son:</span><span class="sxs-lookup"><span data-stu-id="42200-142">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="42200-143">La <xref:System.Drawing.Pen> clase: se usa para dibujar líneas, esquematizar formas o representar otras representaciones geométricas.</span><span class="sxs-lookup"><span data-stu-id="42200-143">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="42200-144">La <xref:System.Drawing.Brush> clase: se usa para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.</span><span class="sxs-lookup"><span data-stu-id="42200-144">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="42200-145">La <xref:System.Drawing.Font> clase: proporciona una descripción de las formas que se van a utilizar al representar texto.</span><span class="sxs-lookup"><span data-stu-id="42200-145">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="42200-146"><xref:System.Drawing.Color>Estructura: representa los diferentes colores que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="42200-146">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="42200-147">Para usar el objeto Graphics que ha creado</span><span class="sxs-lookup"><span data-stu-id="42200-147">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="42200-148">Trabaje con el objeto adecuado que se indicó anteriormente para dibujar lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="42200-148">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="42200-149">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="42200-149">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="42200-150">Para representar</span><span class="sxs-lookup"><span data-stu-id="42200-150">To render</span></span>|<span data-ttu-id="42200-151">Vea</span><span class="sxs-lookup"><span data-stu-id="42200-151">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="42200-152">Líneas</span><span class="sxs-lookup"><span data-stu-id="42200-152">Lines</span></span>|[<span data-ttu-id="42200-153">Procedimiento para dibujar una línea en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42200-153">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="42200-154">Formas</span><span class="sxs-lookup"><span data-stu-id="42200-154">Shapes</span></span>|[<span data-ttu-id="42200-155">Procedimiento para dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="42200-155">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="42200-156">Texto</span><span class="sxs-lookup"><span data-stu-id="42200-156">Text</span></span>|[<span data-ttu-id="42200-157">Procedimiento para dibujar texto en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42200-157">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="42200-158">Imágenes</span><span class="sxs-lookup"><span data-stu-id="42200-158">Images</span></span>|[<span data-ttu-id="42200-159">Procedimiento para representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="42200-159">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="42200-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42200-160">See also</span></span>

- [<span data-ttu-id="42200-161">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="42200-161">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="42200-162">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42200-162">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="42200-163">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="42200-163">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="42200-164">Procedimiento para representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="42200-164">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
