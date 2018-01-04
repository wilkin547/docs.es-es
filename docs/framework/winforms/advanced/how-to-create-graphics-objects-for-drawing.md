---
title: "Cómo: Crear objetos Graphics para dibujar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b626d3d87c6537b74b6d28e086303474ea2c3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>Cómo: Crear objetos Graphics para dibujar
Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular imágenes con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], deberá crear un <xref:System.Drawing.Graphics> objeto. El <xref:System.Drawing.Graphics> objeto representa un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] superficie de dibujo, y es el objeto que se utiliza para crear imágenes gráficas.  
  
 Hay dos pasos para trabajar con gráficos:  
  
1.  Crear un <xref:System.Drawing.Graphics> objeto.  
  
2.  Mediante la <xref:System.Drawing.Graphics> objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.  
  
## <a name="creating-a-graphics-object"></a>Crear un objeto Graphics  
 Un objeto graphics puede crearse en una variedad de formas.  
  
#### <a name="to-create-a-graphics-object"></a>Para crear un objeto graphics  
  
-   Recibe una referencia a un objeto graphics como parte de la <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos de un formulario o control. Esto suele ser cómo obtener una referencia a un objeto gráfico al crear el código de dibujo de un control. Del mismo modo, también puede obtener un objeto gráfico como una propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> al controlar la <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos para un <xref:System.Drawing.Printing.PrintDocument>.  
  
     O bien  
  
-   Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario. Utilice este método si desea dibujar en un formulario o control que ya existe.  
  
     O bien  
  
-   Crear un <xref:System.Drawing.Graphics> objeto de cualquier objeto que hereda de <xref:System.Drawing.Image>. Este enfoque es útil cuando desea modificar una imagen ya existente.  
  
     En las secciones siguientes proporcionan detalles sobre cada uno de estos procesos.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>Objeto PaintEventArgs en el controlador de eventos de Paint  
 Al programar la <xref:System.Windows.Forms.PaintEventHandler> para los controles o el <xref:System.Drawing.Printing.PrintDocument.PrintPage> para un <xref:System.Drawing.Printing.PrintDocument>, se proporciona un objeto gráfico como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Para obtener una referencia a un objeto Graphics desde el objeto PaintEventArgs en el evento Paint  
  
1.  Declare el <xref:System.Drawing.Graphics> objeto.  
  
2.  Asigne la variable para hacer referencia a la <xref:System.Drawing.Graphics> objeto pasado como parte de la <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Inserte el código para pintar el formulario o control.  
  
     En el ejemplo siguiente se muestra cómo hacer referencia a un <xref:System.Drawing.Graphics> objeto desde el <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos:  
  
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
  
-   Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método del formulario o control en el que desea representar gráficos.  
  
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
 Además, puede crear un objeto graphics de cualquier objeto que se deriva de la <xref:System.Drawing.Image> clase.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>Para crear un objeto Graphics desde una imagen  
  
-   Llame a la <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> método, proporcionando el nombre de la variable de imagen desde el que desea crear un <xref:System.Drawing.Graphics> objeto.  
  
     En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Drawing.Bitmap> objeto:  
  
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
>  Solo se puede crear <xref:System.Drawing.Graphics> objetos desde archivos .bmp no indizados, como archivos .bmp de 16, 24 y 32 bits. Cada píxel de archivos .bmp no indizados alberga un color, a diferencia de los píxeles de los archivos .bmp indizados, que contiene un índice en una tabla de colores.  
  
-  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>Dibujar y manipular formas e imágenes  
 Una vez creado, un <xref:System.Drawing.Graphics> objeto puede utilizarse para dibujar líneas y formas, representar texto o mostrar y manipular imágenes. Los objetos principales que se usan con la <xref:System.Drawing.Graphics> objeto son:  
  
-   La <xref:System.Drawing.Pen> clase: utilizado para dibujar líneas, formas de esquematización o representar otros elementos geométricos.  
  
-   La <xref:System.Drawing.Brush> clase: utiliza para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.  
  
-   La <xref:System.Drawing.Font> clase: proporciona una descripción de las formas que se utilizarán al representar texto.  
  
-   El <xref:System.Drawing.Color> estructura: representa los distintos colores para mostrar.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>Para utilizar el objeto de gráficos que ha creado  
  
-   Trabajar con el objeto apropiado enumerado anteriormente para dibujar lo que necesita.  
  
     Para obtener más información, vea los temas siguientes:  
  
    |Para representar|Vea|  
    |---------------|---------|  
    |Líneas|[Dibujar una línea en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |Formas|[Dibujar una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Texto|[Dibujar texto en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Imágenes|[Representar imágenes con GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Representar imágenes con GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
