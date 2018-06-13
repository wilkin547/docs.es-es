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
ms.openlocfilehash: 3c25ddcfb3a566055afd5e233c2a69b3b7a8c66e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526493"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="cb256-102">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="cb256-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="cb256-103">Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular imágenes con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], deberá crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="cb256-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="cb256-104">El <xref:System.Drawing.Graphics> objeto representa un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] superficie de dibujo, y es el objeto que se utiliza para crear imágenes gráficas.</span><span class="sxs-lookup"><span data-stu-id="cb256-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="cb256-105">Hay dos pasos para trabajar con gráficos:</span><span class="sxs-lookup"><span data-stu-id="cb256-105">There are two steps in working with graphics:</span></span>  
  
1.  <span data-ttu-id="cb256-106">Crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="cb256-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="cb256-107">Mediante la <xref:System.Drawing.Graphics> objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="cb256-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="cb256-108">Crear un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="cb256-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="cb256-109">Un objeto graphics puede crearse en una variedad de formas.</span><span class="sxs-lookup"><span data-stu-id="cb256-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="cb256-110">Para crear un objeto graphics</span><span class="sxs-lookup"><span data-stu-id="cb256-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="cb256-111">Recibe una referencia a un objeto graphics como parte de la <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos de un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="cb256-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="cb256-112">Esto suele ser cómo obtener una referencia a un objeto gráfico al crear el código de dibujo de un control.</span><span class="sxs-lookup"><span data-stu-id="cb256-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="cb256-113">Del mismo modo, también puede obtener un objeto gráfico como una propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> al controlar la <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos para un <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="cb256-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="cb256-114">-o bien-</span><span class="sxs-lookup"><span data-stu-id="cb256-114">-or-</span></span>  
  
-   <span data-ttu-id="cb256-115">Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario.</span><span class="sxs-lookup"><span data-stu-id="cb256-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="cb256-116">Utilice este método si desea dibujar en un formulario o control que ya existe.</span><span class="sxs-lookup"><span data-stu-id="cb256-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="cb256-117">-o bien-</span><span class="sxs-lookup"><span data-stu-id="cb256-117">-or-</span></span>  
  
-   <span data-ttu-id="cb256-118">Crear un <xref:System.Drawing.Graphics> objeto de cualquier objeto que hereda de <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="cb256-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="cb256-119">Este enfoque es útil cuando desea modificar una imagen ya existente.</span><span class="sxs-lookup"><span data-stu-id="cb256-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="cb256-120">En las secciones siguientes proporcionan detalles sobre cada uno de estos procesos.</span><span class="sxs-lookup"><span data-stu-id="cb256-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="cb256-121">Objeto PaintEventArgs en el controlador de eventos de Paint</span><span class="sxs-lookup"><span data-stu-id="cb256-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="cb256-122">Al programar la <xref:System.Windows.Forms.PaintEventHandler> para los controles o el <xref:System.Drawing.Printing.PrintDocument.PrintPage> para un <xref:System.Drawing.Printing.PrintDocument>, se proporciona un objeto gráfico como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cb256-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="cb256-123">Para obtener una referencia a un objeto Graphics desde el objeto PaintEventArgs en el evento Paint</span><span class="sxs-lookup"><span data-stu-id="cb256-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1.  <span data-ttu-id="cb256-124">Declare el <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="cb256-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2.  <span data-ttu-id="cb256-125">Asigne la variable para hacer referencia a la <xref:System.Drawing.Graphics> objeto pasado como parte de la <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="cb256-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3.  <span data-ttu-id="cb256-126">Inserte el código para pintar el formulario o control.</span><span class="sxs-lookup"><span data-stu-id="cb256-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="cb256-127">En el ejemplo siguiente se muestra cómo hacer referencia a un <xref:System.Drawing.Graphics> objeto desde el <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos:</span><span class="sxs-lookup"><span data-stu-id="cb256-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="cb256-128">Método CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="cb256-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="cb256-129">También puede usar el <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario.</span><span class="sxs-lookup"><span data-stu-id="cb256-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="cb256-130">Para crear un objeto de gráficos con el método CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="cb256-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="cb256-131">Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método del formulario o control en el que desea representar gráficos.</span><span class="sxs-lookup"><span data-stu-id="cb256-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="cb256-132">Crear a partir de un objeto de imagen</span><span class="sxs-lookup"><span data-stu-id="cb256-132">Create from an Image Object</span></span>  
 <span data-ttu-id="cb256-133">Además, puede crear un objeto graphics de cualquier objeto que se deriva de la <xref:System.Drawing.Image> clase.</span><span class="sxs-lookup"><span data-stu-id="cb256-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="cb256-134">Para crear un objeto Graphics desde una imagen</span><span class="sxs-lookup"><span data-stu-id="cb256-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="cb256-135">Llame a la <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> método, proporcionando el nombre de la variable de imagen desde el que desea crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="cb256-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="cb256-136">En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Drawing.Bitmap> objeto:</span><span class="sxs-lookup"><span data-stu-id="cb256-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
>  <span data-ttu-id="cb256-137">Solo se puede crear <xref:System.Drawing.Graphics> objetos desde archivos .bmp no indizados, como archivos .bmp de 16, 24 y 32 bits.</span><span class="sxs-lookup"><span data-stu-id="cb256-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="cb256-138">Cada píxel de archivos .bmp no indizados alberga un color, a diferencia de los píxeles de los archivos .bmp indizados, que contiene un índice en una tabla de colores.</span><span class="sxs-lookup"><span data-stu-id="cb256-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="cb256-139">Dibujar y manipular formas e imágenes</span><span class="sxs-lookup"><span data-stu-id="cb256-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="cb256-140">Una vez creado, un <xref:System.Drawing.Graphics> objeto puede utilizarse para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="cb256-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="cb256-141">Los objetos principales que se usan con la <xref:System.Drawing.Graphics> objeto son:</span><span class="sxs-lookup"><span data-stu-id="cb256-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="cb256-142">La <xref:System.Drawing.Pen> clase: utilizado para dibujar líneas, formas de esquematización o representar otros elementos geométricos.</span><span class="sxs-lookup"><span data-stu-id="cb256-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="cb256-143">La <xref:System.Drawing.Brush> clase: utiliza para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.</span><span class="sxs-lookup"><span data-stu-id="cb256-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="cb256-144">La <xref:System.Drawing.Font> clase: proporciona una descripción de las formas que se utilizarán al representar texto.</span><span class="sxs-lookup"><span data-stu-id="cb256-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="cb256-145">El <xref:System.Drawing.Color> estructura: representa los distintos colores para mostrar.</span><span class="sxs-lookup"><span data-stu-id="cb256-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="cb256-146">Para utilizar el objeto de gráficos que ha creado</span><span class="sxs-lookup"><span data-stu-id="cb256-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="cb256-147">Trabajar con el objeto apropiado enumerado anteriormente para dibujar lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="cb256-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="cb256-148">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cb256-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="cb256-149">Para representar</span><span class="sxs-lookup"><span data-stu-id="cb256-149">To render</span></span>|<span data-ttu-id="cb256-150">Vea</span><span class="sxs-lookup"><span data-stu-id="cb256-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="cb256-151">Líneas</span><span class="sxs-lookup"><span data-stu-id="cb256-151">Lines</span></span>|[<span data-ttu-id="cb256-152">Dibujar una línea en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb256-152">How to: Draw a Line on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="cb256-153">Formas</span><span class="sxs-lookup"><span data-stu-id="cb256-153">Shapes</span></span>|[<span data-ttu-id="cb256-154">Dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="cb256-154">How to: Draw an Outlined Shape</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="cb256-155">Texto</span><span class="sxs-lookup"><span data-stu-id="cb256-155">Text</span></span>|[<span data-ttu-id="cb256-156">Dibujar texto en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb256-156">How to: Draw Text on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="cb256-157">Imágenes</span><span class="sxs-lookup"><span data-stu-id="cb256-157">Images</span></span>|[<span data-ttu-id="cb256-158">Representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="cb256-158">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="cb256-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb256-159">See Also</span></span>  
 [<span data-ttu-id="cb256-160">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="cb256-160">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="cb256-161">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb256-161">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="cb256-162">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="cb256-162">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="cb256-163">Representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="cb256-163">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
