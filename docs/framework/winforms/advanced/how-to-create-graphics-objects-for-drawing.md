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
# <a name="how-to-create-graphics-objects-for-drawing"></a>Procedimiento para crear objetos gráficos para dibujar
Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular imágenes con GDI+, debe crear un <xref:System.Drawing.Graphics> objeto. El <xref:System.Drawing.Graphics> objeto representa una superficie de dibujo de GDI+ y es el objeto que se utiliza para crear imágenes gráficas.  
  
 Hay dos pasos para trabajar con gráficos:  
  
1. Crear un <xref:System.Drawing.Graphics> objeto.  
  
2. Usar el <xref:System.Drawing.Graphics> objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.  
  
## <a name="creating-a-graphics-object"></a>Crear un objeto Graphics  
 Un objeto de gráficos se puede crear de varias maneras.  
  
#### <a name="to-create-a-graphics-object"></a>Para crear un objeto Graphics  
  
- Recibe una referencia a un objeto Graphics como parte de <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> caso de un formulario o un control. Normalmente, este es el modo en que se obtiene una referencia a un objeto Graphics al crear código de dibujo para un control. Del mismo modo, también puede obtener un objeto de gráficos como una propiedad de <xref:System.Drawing.Printing.PrintPageEventArgs> cuando controla el <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento para un <xref:System.Drawing.Printing.PrintDocument> .  
  
     O bien  
  
- Llame al <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de ese control o formulario. Utilice este método si desea dibujar en un formulario o control que ya existe.  
  
     O bien  
  
- Cree un <xref:System.Drawing.Graphics> objeto a partir de cualquier objeto que herede de <xref:System.Drawing.Image> . Este enfoque es útil cuando se desea modificar una imagen ya existente.  
  
     En las secciones siguientes se proporcionan detalles sobre cada uno de estos procesos.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs en el controlador de eventos Paint  
 Al programar el <xref:System.Windows.Forms.PaintEventHandler> para los controles de o <xref:System.Drawing.Printing.PrintDocument.PrintPage> para <xref:System.Drawing.Printing.PrintDocument> , se proporciona un objeto de gráficos como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs> .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Para obtener una referencia a un objeto Graphics desde PaintEventArgs en el evento Paint  
  
1. Declare el <xref:System.Drawing.Graphics> objeto.  
  
2. Asigne la variable para hacer referencia al <xref:System.Drawing.Graphics> objeto que se pasa como parte de <xref:System.Windows.Forms.PaintEventArgs> .  
  
3. Inserte el código para pintar el formulario o el control.  
  
     En el ejemplo siguiente se muestra cómo hacer referencia a un <xref:System.Drawing.Graphics> objeto de <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> evento:  
  
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
  
## <a name="creategraphics-method"></a>CreateGraphics (método)  
 También puede utilizar el <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de ese control o formulario.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Para crear un objeto Graphics con el método CreateGraphics  
  
- Llame al <xref:System.Windows.Forms.Control.CreateGraphics%2A> método del formulario o control en el que desea representar los gráficos.  
  
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
  
## <a name="create-from-an-image-object"></a>Crear a partir de un objeto Image  
 Además, puede crear un objeto gráfico a partir de cualquier objeto que se derive de la <xref:System.Drawing.Image> clase.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Para crear un objeto gráfico a partir de una imagen  
  
- Llame al <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> método y proporcione el nombre de la variable de imagen de la que desea crear un <xref:System.Drawing.Graphics> objeto.  
  
     En el ejemplo siguiente se muestra cómo usar un <xref:System.Drawing.Bitmap> objeto:  
  
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
> Solo puede crear <xref:System.Drawing.Graphics> objetos a partir de archivos. bmp no indexados, como archivos de 16 bits, de 24 bits y de 32 bits. bmp. Cada píxel de archivos. bmp no indexados contiene un color, a diferencia de los píxeles de los archivos. bmp indexados, que contienen un índice en una tabla de colores.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Dibujar y manipular formas e imágenes  
 Una vez creada, se <xref:System.Drawing.Graphics> puede usar un objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes. Los objetos de entidad de seguridad que se usan con el <xref:System.Drawing.Graphics> objeto son:  
  
- La <xref:System.Drawing.Pen> clase: se usa para dibujar líneas, esquematizar formas o representar otras representaciones geométricas.  
  
- La <xref:System.Drawing.Brush> clase: se usa para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.  
  
- La <xref:System.Drawing.Font> clase: proporciona una descripción de las formas que se van a utilizar al representar texto.  
  
- <xref:System.Drawing.Color>Estructura: representa los diferentes colores que se van a mostrar.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Para usar el objeto Graphics que ha creado  
  
- Trabaje con el objeto adecuado que se indicó anteriormente para dibujar lo que necesita.  
  
     Para obtener más información, vea los temas siguientes:  
  
    |Para representar|Vea|  
    |---------------|---------|  
    |Líneas|[Procedimiento para dibujar una línea en un formulario Windows Forms](how-to-draw-a-line-on-a-windows-form.md)|  
    |Formas|[Procedimiento para dibujar una forma con contorno](how-to-draw-an-outlined-shape.md)|  
    |Texto|[Procedimiento para dibujar texto en un formulario Windows Forms](how-to-draw-text-on-a-windows-form.md)|  
    |Imágenes|[Procedimiento para representar imágenes con GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Consulte también

- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Procedimiento para representar imágenes con GDI+](how-to-render-images-with-gdi.md)
