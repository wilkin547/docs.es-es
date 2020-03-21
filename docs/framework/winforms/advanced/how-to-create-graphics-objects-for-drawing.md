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
# <a name="how-to-create-graphics-objects-for-drawing"></a>Cómo: Crear objetos Graphics para dibujar
Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular <xref:System.Drawing.Graphics> imágenes con GDI+GDI+, debe crear un objeto. El <xref:System.Drawing.Graphics> objeto representa una superficie de dibujo GDI+GDI+ y es el objeto que se utiliza para crear imágenes gráficas.  
  
 Hay dos pasos para trabajar con gráficos:  
  
1. Creación <xref:System.Drawing.Graphics> de un objeto.  
  
2. Usar <xref:System.Drawing.Graphics> el objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.  
  
## <a name="creating-a-graphics-object"></a>Creación de un objeto Graphics  
 Un objeto de gráficos se puede crear de varias maneras.  
  
#### <a name="to-create-a-graphics-object"></a>Para crear un objeto gráfico  
  
- Recibir una referencia a un objeto <xref:System.Windows.Forms.PaintEventArgs> de <xref:System.Windows.Forms.Control.Paint> gráficos como parte de la en el caso de un formulario o control. Normalmente, esto es cómo se obtiene una referencia a un objeto de gráficos al crear código de pintura para un control. Del mismo modo, también puede obtener un <xref:System.Drawing.Printing.PrintPageEventArgs> objeto <xref:System.Drawing.Printing.PrintDocument.PrintPage> de gráficos como una propiedad de la al controlar el evento para un <xref:System.Drawing.Printing.PrintDocument>archivo .  
  
     O bien  
  
- Llame <xref:System.Windows.Forms.Control.CreateGraphics%2A> al método de un control o <xref:System.Drawing.Graphics> formulario para obtener una referencia a un objeto que representa la superficie de dibujo de ese control o formulario. Utilice este método si desea dibujar en un formulario o control que ya existe.  
  
     O bien  
  
- Cree <xref:System.Drawing.Graphics> un objeto a partir <xref:System.Drawing.Image>de cualquier objeto que herede de . Este enfoque es útil cuando desea modificar una imagen ya existente.  
  
     En las secciones siguientes se proporcionan detalles sobre cada uno de estos procesos.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>PaintEventArgs en el controlador de eventos Paint  
 Al programar <xref:System.Windows.Forms.PaintEventHandler> los controles <xref:System.Drawing.Printing.PrintDocument.PrintPage> for <xref:System.Drawing.Printing.PrintDocument>o for a , se proporciona <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>un objeto de gráficos como una de las propiedades de o .  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Para obtener una referencia a un Graphics objeto de la PaintEventArgs en el Paint eventos  
  
1. Declare <xref:System.Drawing.Graphics> el objeto.  
  
2. Asigne la variable para <xref:System.Drawing.Graphics> hacer referencia al <xref:System.Windows.Forms.PaintEventArgs>objeto pasado como parte del archivo .  
  
3. Inserte código para pintar el formulario o el control.  
  
     En el ejemplo siguiente <xref:System.Drawing.Graphics> se muestra <xref:System.Windows.Forms.PaintEventArgs> cómo <xref:System.Windows.Forms.Control.Paint> hacer referencia a un objeto desde el en el evento:  
  
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
  
## <a name="creategraphics-method"></a>CreateGraphics Método  
 También puede utilizar <xref:System.Windows.Forms.Control.CreateGraphics%2A> el método de un control o <xref:System.Drawing.Graphics> formulario para obtener una referencia a un objeto que representa la superficie de dibujo de ese control o formulario.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>Para crear un Graphics objeto con el CreateGraphics método  
  
- Llame <xref:System.Windows.Forms.Control.CreateGraphics%2A> al método del formulario o control en el que desea representar gráficos.  
  
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
 Además, puede crear un objeto de gráficos <xref:System.Drawing.Image> a partir de cualquier objeto que derive de la clase.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Para crear un Graphics objeto a partir de una imagen  
  
- Llame <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> al método, proporcionando el nombre de la Image <xref:System.Drawing.Graphics> variable desde la que desea crear un objeto.  
  
     En el ejemplo siguiente <xref:System.Drawing.Bitmap> se muestra cómo utilizar un objeto:  
  
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
> Solo puede <xref:System.Drawing.Graphics> crear objetos a partir de archivos .bmp no indexados, como archivos .bmp de 16 bits, 24 bits y 32 bits. Cada píxel de archivos .bmp no indexados contiene un color, a diferencia de los píxeles de los archivos .bmp indexados, que contienen un índice en una tabla de colores.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Dibujar y manipular formas e imágenes  
 Una vez creado, <xref:System.Drawing.Graphics> se puede utilizar un objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes. Los objetos principales que <xref:System.Drawing.Graphics> se utilizan con el objeto son:  
  
- La <xref:System.Drawing.Pen> clase (Class): se utiliza para dibujar líneas, delineando formas o representando otras representaciones geométricas.  
  
- La <xref:System.Drawing.Brush> clase (Class): se utiliza para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.  
  
- La <xref:System.Drawing.Font> clase : proporciona una descripción de las formas que se utilizarán al renderizar texto.  
  
- La <xref:System.Drawing.Color> estructura (structure): representa los diferentes colores que se mostrarán.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Para utilizar el objeto Graphics que ha creado  
  
- Trabaje con el objeto apropiado mencionado anteriormente para dibujar lo que necesita.  
  
     Para obtener más información, vea los temas siguientes:  
  
    |Para renderizar|Vea|  
    |---------------|---------|  
    |Líneas|[Dibujar una línea en Windows Forms](how-to-draw-a-line-on-a-windows-form.md)|  
    |Formas|[Cómo: Dibujar una forma con contorno](how-to-draw-an-outlined-shape.md)|  
    |Texto|[Cómo: Dibujar texto en Windows Forms](how-to-draw-text-on-a-windows-form.md)|  
    |Imágenes|[Cómo: Representar imágenes con GDI+](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Consulte también

- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Representar imágenes con GDI+](how-to-render-images-with-gdi.md)
