---
title: 'Cómo: Crear objetos Graphics para dibujar'
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
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142438"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="b5059-102">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="b5059-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="b5059-103">Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular <xref:System.Drawing.Graphics> imágenes con GDI+GDI+, debe crear un objeto.</span><span class="sxs-lookup"><span data-stu-id="b5059-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b5059-104">El <xref:System.Drawing.Graphics> objeto representa una superficie de dibujo GDI+GDI+ y es el objeto que se utiliza para crear imágenes gráficas.</span><span class="sxs-lookup"><span data-stu-id="b5059-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="b5059-105">Hay dos pasos para trabajar con gráficos:</span><span class="sxs-lookup"><span data-stu-id="b5059-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="b5059-106">Creación <xref:System.Drawing.Graphics> de un objeto.</span><span class="sxs-lookup"><span data-stu-id="b5059-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="b5059-107">Usar <xref:System.Drawing.Graphics> el objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="b5059-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="b5059-108">Creación de un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="b5059-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="b5059-109">Un objeto de gráficos se puede crear de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="b5059-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="b5059-110">Para crear un objeto gráfico</span><span class="sxs-lookup"><span data-stu-id="b5059-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="b5059-111">Recibir una referencia a un objeto <xref:System.Windows.Forms.PaintEventArgs> de <xref:System.Windows.Forms.Control.Paint> gráficos como parte de la en el caso de un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="b5059-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="b5059-112">Normalmente, esto es cómo se obtiene una referencia a un objeto de gráficos al crear código de pintura para un control.</span><span class="sxs-lookup"><span data-stu-id="b5059-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="b5059-113">Del mismo modo, también puede obtener un <xref:System.Drawing.Printing.PrintPageEventArgs> objeto <xref:System.Drawing.Printing.PrintDocument.PrintPage> de gráficos como una propiedad de la al controlar el evento para un <xref:System.Drawing.Printing.PrintDocument>archivo .</span><span class="sxs-lookup"><span data-stu-id="b5059-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="b5059-114">O bien</span><span class="sxs-lookup"><span data-stu-id="b5059-114">-or-</span></span>  
  
- <span data-ttu-id="b5059-115">Llame <xref:System.Windows.Forms.Control.CreateGraphics%2A> al método de un control o <xref:System.Drawing.Graphics> formulario para obtener una referencia a un objeto que representa la superficie de dibujo de ese control o formulario.</span><span class="sxs-lookup"><span data-stu-id="b5059-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="b5059-116">Utilice este método si desea dibujar en un formulario o control que ya existe.</span><span class="sxs-lookup"><span data-stu-id="b5059-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="b5059-117">O bien</span><span class="sxs-lookup"><span data-stu-id="b5059-117">-or-</span></span>  
  
- <span data-ttu-id="b5059-118">Cree <xref:System.Drawing.Graphics> un objeto a partir <xref:System.Drawing.Image>de cualquier objeto que herede de .</span><span class="sxs-lookup"><span data-stu-id="b5059-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="b5059-119">Este enfoque es útil cuando desea modificar una imagen ya existente.</span><span class="sxs-lookup"><span data-stu-id="b5059-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="b5059-120">En las secciones siguientes se proporcionan detalles sobre cada uno de estos procesos.</span><span class="sxs-lookup"><span data-stu-id="b5059-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="b5059-121">PaintEventArgs en el controlador de eventos Paint</span><span class="sxs-lookup"><span data-stu-id="b5059-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="b5059-122">Al programar <xref:System.Windows.Forms.PaintEventHandler> los controles <xref:System.Drawing.Printing.PrintDocument.PrintPage> for <xref:System.Drawing.Printing.PrintDocument>o for a , se proporciona <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>un objeto de gráficos como una de las propiedades de o .</span><span class="sxs-lookup"><span data-stu-id="b5059-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="b5059-123">Para obtener una referencia a un Graphics objeto de la PaintEventArgs en el Paint eventos</span><span class="sxs-lookup"><span data-stu-id="b5059-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="b5059-124">Declare <xref:System.Drawing.Graphics> el objeto.</span><span class="sxs-lookup"><span data-stu-id="b5059-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="b5059-125">Asigne la variable para <xref:System.Drawing.Graphics> hacer referencia al <xref:System.Windows.Forms.PaintEventArgs>objeto pasado como parte del archivo .</span><span class="sxs-lookup"><span data-stu-id="b5059-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="b5059-126">Inserte código para pintar el formulario o el control.</span><span class="sxs-lookup"><span data-stu-id="b5059-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="b5059-127">En el ejemplo siguiente <xref:System.Drawing.Graphics> se muestra <xref:System.Windows.Forms.PaintEventArgs> cómo <xref:System.Windows.Forms.Control.Paint> hacer referencia a un objeto desde el en el evento:</span><span class="sxs-lookup"><span data-stu-id="b5059-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="b5059-128">CreateGraphics Método</span><span class="sxs-lookup"><span data-stu-id="b5059-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="b5059-129">También puede utilizar <xref:System.Windows.Forms.Control.CreateGraphics%2A> el método de un control o <xref:System.Drawing.Graphics> formulario para obtener una referencia a un objeto que representa la superficie de dibujo de ese control o formulario.</span><span class="sxs-lookup"><span data-stu-id="b5059-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="b5059-130">Para crear un Graphics objeto con el CreateGraphics método</span><span class="sxs-lookup"><span data-stu-id="b5059-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="b5059-131">Llame <xref:System.Windows.Forms.Control.CreateGraphics%2A> al método del formulario o control en el que desea representar gráficos.</span><span class="sxs-lookup"><span data-stu-id="b5059-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="b5059-132">Crear a partir de un objeto de imagen</span><span class="sxs-lookup"><span data-stu-id="b5059-132">Create from an Image Object</span></span>  
 <span data-ttu-id="b5059-133">Además, puede crear un objeto de gráficos <xref:System.Drawing.Image> a partir de cualquier objeto que derive de la clase.</span><span class="sxs-lookup"><span data-stu-id="b5059-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="b5059-134">Para crear un Graphics objeto a partir de una imagen</span><span class="sxs-lookup"><span data-stu-id="b5059-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="b5059-135">Llame <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> al método, proporcionando el nombre de la Image <xref:System.Drawing.Graphics> variable desde la que desea crear un objeto.</span><span class="sxs-lookup"><span data-stu-id="b5059-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="b5059-136">En el ejemplo siguiente <xref:System.Drawing.Bitmap> se muestra cómo utilizar un objeto:</span><span class="sxs-lookup"><span data-stu-id="b5059-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="b5059-137">Solo puede <xref:System.Drawing.Graphics> crear objetos a partir de archivos .bmp no indexados, como archivos .bmp de 16 bits, 24 bits y 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b5059-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="b5059-138">Cada píxel de archivos .bmp no indexados contiene un color, a diferencia de los píxeles de los archivos .bmp indexados, que contienen un índice en una tabla de colores.</span><span class="sxs-lookup"><span data-stu-id="b5059-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="b5059-139">Dibujar y manipular formas e imágenes</span><span class="sxs-lookup"><span data-stu-id="b5059-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="b5059-140">Una vez creado, <xref:System.Drawing.Graphics> se puede utilizar un objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="b5059-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="b5059-141">Los objetos principales que <xref:System.Drawing.Graphics> se utilizan con el objeto son:</span><span class="sxs-lookup"><span data-stu-id="b5059-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="b5059-142">La <xref:System.Drawing.Pen> clase (Class): se utiliza para dibujar líneas, delineando formas o representando otras representaciones geométricas.</span><span class="sxs-lookup"><span data-stu-id="b5059-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="b5059-143">La <xref:System.Drawing.Brush> clase (Class): se utiliza para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.</span><span class="sxs-lookup"><span data-stu-id="b5059-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="b5059-144">La <xref:System.Drawing.Font> clase : proporciona una descripción de las formas que se utilizarán al renderizar texto.</span><span class="sxs-lookup"><span data-stu-id="b5059-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="b5059-145">La <xref:System.Drawing.Color> estructura (structure): representa los diferentes colores que se mostrarán.</span><span class="sxs-lookup"><span data-stu-id="b5059-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="b5059-146">Para utilizar el objeto Graphics que ha creado</span><span class="sxs-lookup"><span data-stu-id="b5059-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="b5059-147">Trabaje con el objeto apropiado mencionado anteriormente para dibujar lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="b5059-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="b5059-148">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5059-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="b5059-149">Para renderizar</span><span class="sxs-lookup"><span data-stu-id="b5059-149">To render</span></span>|<span data-ttu-id="b5059-150">Vea</span><span class="sxs-lookup"><span data-stu-id="b5059-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="b5059-151">Líneas</span><span class="sxs-lookup"><span data-stu-id="b5059-151">Lines</span></span>|[<span data-ttu-id="b5059-152">Dibujar una línea en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5059-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="b5059-153">Formas</span><span class="sxs-lookup"><span data-stu-id="b5059-153">Shapes</span></span>|[<span data-ttu-id="b5059-154">Cómo: Dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="b5059-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="b5059-155">Texto</span><span class="sxs-lookup"><span data-stu-id="b5059-155">Text</span></span>|[<span data-ttu-id="b5059-156">Cómo: Dibujar texto en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5059-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="b5059-157">Imágenes</span><span class="sxs-lookup"><span data-stu-id="b5059-157">Images</span></span>|[<span data-ttu-id="b5059-158">Cómo: Representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="b5059-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b5059-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5059-159">See also</span></span>

- [<span data-ttu-id="b5059-160">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="b5059-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="b5059-161">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5059-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="b5059-162">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="b5059-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="b5059-163">Cómo: Representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="b5059-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
