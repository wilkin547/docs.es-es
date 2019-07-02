---
title: Procedimiento para crear objetos gráficos para dibujar
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
ms.openlocfilehash: ee57b0409d7bb7574c965ff098e7f86c8332536d
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505506"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Procedimiento para crear objetos gráficos para dibujar
Antes de que puede dibujar líneas y formas, representar texto o mostrar y manipular imágenes con GDI +, deberá crear un <xref:System.Drawing.Graphics> objeto. La <xref:System.Drawing.Graphics> objeto representa una superficie de dibujo de GDI + y es el objeto que se usa para crear imágenes gráficas.  
  
 Trabajar con gráficos, hay dos pasos:  
  
1. Creación de un <xref:System.Drawing.Graphics> objeto.  
  
2. Mediante el <xref:System.Drawing.Graphics> objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.  
  
## <a name="creating-a-graphics-object"></a>Creación de un objeto Graphics  
 Un objeto graphics puede crearse en una variedad de formas.  
  
#### <a name="to-create-a-graphics-object"></a>Para crear un objeto graphics  
  
- Reciba una referencia a un objeto graphics como parte de la <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos de un formulario o control. Normalmente, esto es cómo obtener una referencia a un objeto graphics al crear el código de dibujo de un control. De forma similar, también se puede obtener un objeto graphics como una propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> al controlar la <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos para un <xref:System.Drawing.Printing.PrintDocument>.  
  
     -o bien-  
  
- Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario. Utilice este método si desea que se va a dibujar en un formulario o control que ya existe.  
  
     -o bien-  
  
- Crear un <xref:System.Drawing.Graphics> objeto de cualquier objeto que hereda de <xref:System.Drawing.Image>. Este enfoque es útil cuando desea modificar una imagen ya existente.  
  
     Las secciones siguientes proporcionan detalles sobre cada uno de estos procesos.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs en el controlador de eventos Paint  
 Al programar el <xref:System.Windows.Forms.PaintEventHandler> para los controles o el <xref:System.Drawing.Printing.PrintDocument.PrintPage> para un <xref:System.Drawing.Printing.PrintDocument>, un objeto graphics se proporciona como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Para obtener una referencia a un objeto Graphics desde PaintEventArgs en el evento Paint  
  
1. Declare el <xref:System.Drawing.Graphics> objeto.  
  
2. Asigne la variable para hacer referencia a la <xref:System.Drawing.Graphics> objeto pasado como parte de la <xref:System.Windows.Forms.PaintEventArgs>.  
  
3. Inserte código para dibujar el formulario o control.  
  
     El ejemplo siguiente muestra cómo hacer referencia a un <xref:System.Drawing.Graphics> objeto desde el <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos:  
  
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
  
## <a name="creategraphics-method"></a>Método CreateGraphics  
 También puede usar el <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Para crear un objeto de gráficos con el método CreateGraphics  
  
- Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método del formulario o control en el que desea representar gráficos.  
  
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
  
## <a name="create-from-an-image-object"></a>Crear a partir de un objeto de imagen  
 Además, puede crear un objeto graphics de cualquier objeto que se deriva el <xref:System.Drawing.Image> clase.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Para crear un objeto de gráficos desde una imagen  
  
- Llame a la <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> método, proporcionando el nombre de la variable de la imagen desde el que desea crear un <xref:System.Drawing.Graphics> objeto.  
  
     El ejemplo siguiente muestra cómo usar un <xref:System.Drawing.Bitmap> objeto:  
  
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
>  Solo se puede crear <xref:System.Drawing.Graphics> objetos desde los archivos .bmp no indizados, como los archivos .bmp 16, 24 y 32 bits. Cada píxel de archivos .bmp no indizada contiene un color, a diferencia de píxeles de los archivos .bmp indizados, que contienen un índice a una tabla de colores.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Dibujar y manipular formas e imágenes  
 Después de crearlo, un <xref:System.Drawing.Graphics> objeto puede utilizarse para dibujar líneas y formas, representar texto o mostrar y manipular imágenes. Los objetos principales que se usan con el <xref:System.Drawing.Graphics> objeto son:  
  
- La <xref:System.Drawing.Pen> clase, utilizado para dibujar líneas, formas de esquematización o representar otros elementos geométricos.  
  
- La <xref:System.Drawing.Brush> clase, utiliza para rellenar las áreas de gráficos, como formas rellenas, imágenes o texto.  
  
- La <xref:System.Drawing.Font> clase, proporciona una descripción de las formas que se utilizan al representar texto.  
  
- El <xref:System.Drawing.Color> estructura, representa los distintos colores para mostrar.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Para usar el objeto Graphics que ha creado  
  
- Trabajar con el objeto apropiado enumerado anteriormente para dibujar lo que necesita.  
  
     Para obtener más información, vea los temas siguientes:  
  
    |Para representar|Vea|  
    |---------------|---------|  
    |Líneas|[Cómo: Dibujar una línea en un formulario de Windows](how-to-draw-a-line-on-a-windows-form.md)|  
    |Formas|[Cómo: Dibujar una forma con contorno](how-to-draw-an-outlined-shape.md)|  
    |Texto|[Cómo: Dibujar texto en un formulario de Windows](how-to-draw-text-on-a-windows-form.md)|  
    |Imágenes|[Cómo: Representar imágenes con GDI +](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Vea también

- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Representar imágenes con GDI +](how-to-render-images-with-gdi.md)
