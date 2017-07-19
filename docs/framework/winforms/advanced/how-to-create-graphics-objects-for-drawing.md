---
title: "C&#243;mo: Crear objetos Graphics para dibujar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "GDI+, crear imágenes"
  - "gráficos [formularios Windows Forms], crear"
  - "Graphics (clase)"
  - "imágenes [Windows Forms], crear"
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Crear objetos Graphics para dibujar
Antes de dibujar líneas y formas, representar texto o mostrar y manipular imágenes con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es preciso crear un objeto <xref:System.Drawing.Graphics>.  El objeto <xref:System.Drawing.Graphics> representa una superficie de dibujo de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y se usa para crear imágenes gráficas.  
  
 Para trabajar con gráficos existen los dos pasos siguientes:  
  
1.  Crear un objeto <xref:System.Drawing.Graphics>.  
  
2.  Usar el objeto <xref:System.Drawing.Graphics> para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.  
  
## Crear un objeto Graphics  
 El objeto Graphics se puede crear de diversas formas.  
  
#### Para crear un objeto Graphics  
  
-   Reciba una referencia a un objeto Graphics como parte de <xref:System.Windows.Forms.PaintEventArgs> del evento <xref:System.Windows.Forms.Control.Paint> de un formulario o un control.  Este es el modo en que normalmente se obtiene una referencia a un objeto Graphics cuando se crea código de dibujo para un control.  De forma similar, también se puede obtener un objeto gráfico como una propiedad de <xref:System.Drawing.Printing.PrintPageEventArgs> al controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> de un objeto <xref:System.Drawing.Printing.PrintDocument>.  
  
     O bien  
  
-   Llame al método <xref:System.Windows.Forms.Control.CreateGraphics%2A> de un control o un formulario para obtener una referencia a un objeto <xref:System.Drawing.Graphics> que represente la superficie de dibujo de dicho control o formulario.  Utilice este método si desea dibujar en un formulario o en un control que ya existía con anterioridad.  
  
     O bien  
  
-   Cree un objeto <xref:System.Drawing.Graphics> a partir de cualquier objeto que herede de <xref:System.Drawing.Image>.  Este método resulta útil cuando se desea alterar una imagen que ya existe.  
  
     Las secciones siguientes proporcionan detalles sobre cada uno de estos procesos.  
  
## PaintEventArgs en el controlador de eventos Paint  
 Al programar <xref:System.Windows.Forms.PaintEventHandler> para controles o el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> de un objeto <xref:System.Drawing.Printing.PrintDocument>, se proporciona un objeto gráfico como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
#### Para obtener una referencia a un objeto Graphics a partir de PaintEventArgs en el evento Paint  
  
1.  Declare el objeto <xref:System.Drawing.Graphics>.  
  
2.  Asigne la variable que hará referencia al objeto <xref:System.Drawing.Graphics> pasado como parte de <xref:System.Windows.Forms.PaintEventArgs>.  
  
3.  Inserte código para dibujar en el formulario o control.  
  
     En el ejemplo siguiente se muestra cómo hacer referencia a un objeto <xref:System.Drawing.Graphics> desde <xref:System.Windows.Forms.PaintEventArgs> en el evento <xref:System.Windows.Forms.Control.Paint>:  
  
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
  
## CreateGraphics \(Método\)  
 También puede utilizar el método <xref:System.Windows.Forms.Control.CreateGraphics%2A> de un control o un formulario para obtener una referencia a un objeto <xref:System.Drawing.Graphics> que represente la superficie de dibujo de dicho control o formulario.  
  
#### Para crear un objeto Graphics con el método CreateGraphics  
  
-   Llame al método <xref:System.Windows.Forms.Control.CreateGraphics%2A> del formulario o del control en el que desee representar gráficos.  
  
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
  
## Crear un objeto Graphics a partir de un objeto Image  
 También se puede crear un objeto Graphics a partir de cualquier objeto que se derive de la clase <xref:System.Drawing.Image>.  
  
#### Para crear un objeto Graphics a partir de un objeto Image  
  
-   Llame al método <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=fullName>, suministrando el nombre de la variable Image a partir de la cual desea crear un objeto <xref:System.Drawing.Graphics>.  
  
     En el ejemplo siguiente se muestra cómo usar un objeto <xref:System.Drawing.Bitmap>:  
  
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
>  Sólo puede crear objetos <xref:System.Drawing.Graphics> a partir de archivos .bmp no indizados, como archivos .bmp de 16 bits, 24 bits y 32 bits.  Cada píxel de archivos .bmp no indizados alberga un color, a diferencia de los píxeles de los archivos .bmp indizados, que albergan un índice que hace referencia a una tabla de colores.  
  
## Dibujar y manipular formas e imágenes  
 Una vez creado el objeto <xref:System.Drawing.Graphics>, éste se puede usar para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.  Los objetos de entidad de seguridad que se usan con el objeto <xref:System.Drawing.Graphics> son:  
  
-   La clase <xref:System.Drawing.Pen>: se utiliza para dibujar líneas y contornos de formas o para representar otros elementos geométricos.  
  
-   La clase <xref:System.Drawing.Brush>: se utiliza para rellenar áreas de gráficos, como formas rellenas, imágenes o texto.  
  
-   La clase <xref:System.Drawing.Font>: proporciona una descripción de las formas que se utilizarán al representar texto.  
  
-   La estructura <xref:System.Drawing.Color>: representa los distintos colores para mostrar.  
  
#### Para utilizar el objeto Graphics que ha creado  
  
-   Trabaje con el objeto correspondiente enumerado anteriormente para dibujar lo que necesite.  
  
     Para obtener más información, vea los temas siguientes:  
  
    |Para representar|Vea|  
    |----------------------|---------|  
    |Líneas|[Cómo: Dibujar una línea en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-on-a-windows-form.md)|  
    |formas|[Cómo: Dibujar una forma con contorno](../../../../docs/framework/winforms/advanced/how-to-draw-an-outlined-shape.md)|  
    |Text|[Cómo: Dibujar texto en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)|  
    |Imágenes|[Cómo: Representar imágenes con GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)|  
  
## Vea también  
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Líneas, curvas y formas](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Cómo: Representar imágenes con GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)