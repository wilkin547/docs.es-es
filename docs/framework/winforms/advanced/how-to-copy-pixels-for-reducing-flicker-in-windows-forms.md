---
title: "C&#243;mo: Copiar p&#237;xeles para reducir el parpadeo en formularios Windows Forms | Microsoft Docs"
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
  - "transferencia de bloques de bits"
  - "bitblt"
  - "parpadeo"
  - "parpadeo, reducir en formularios Windows Forms"
  - "gráficos, copiar"
  - "gráficos, reducir parpadeo"
  - "píxeles, copiar"
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Copiar p&#237;xeles para reducir el parpadeo en formularios Windows Forms
Cuando anima un gráfico simple, los usuarios a veces pueden notar parpadeos u otros efectos visuales no deseados.  Una manera de limitar este problema es utilizar un proceso "bitblt" en el gráfico.  Bitblt es la transferencia de bloque de bits de los datos de color de un rectángulo de origen de píxeles a un rectángulo de destino de píxeles.  
  
 Con formularios Windows Forms, bitblt se realiza utilizando el método <xref:System.Drawing.Graphics.CopyFromScreen%2A> de la clase <xref:System.Drawing.Graphics>.  En los parámetros del método, puede especificar el origen y el destino \(como puntos\), el tamaño del área que se va a copiar y el objeto Graphics utilizado para dibujar la nueva forma.  
  
 En el ejemplo siguiente, se arrastra una forma del formulario a su controlador del evento <xref:System.Windows.Forms.Control.Paint>.  A continuación, el método <xref:System.Drawing.Graphics.CopyFromScreen%2A> se utiliza para duplicar la forma.  
  
> [!NOTE]
>  Establecer la propiedad <xref:System.Windows.Forms.Control.DoubleBuffered%2A> del formulario en `true` hará que el código basado en gráficos en el evento <xref:System.Windows.Forms.Control.Paint> sea de doble búfer.  Mientras que esto no suponga mejoras de rendimiento apreciables al utilizar el código que se muestra a continuación, simplemente sirve para tener en cuenta cuando se trabaja con ejemplos de manipulación de gráficos más complejos.  
  
## Ejemplo  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## Compilar el código  
 El código anterior se ejecuta en el controlador de eventos del formulario <xref:System.Windows.Forms.Control.Paint> para que conservar los gráficos cuando se vuelve a diseñar el formulario.  Por ello, no llame a métodos relacionados con gráficos del controlador de eventos <xref:System.Windows.Forms.Form.Load>, puesto que el contenido dibujado no se vuelve a dibujar si otro formulario cambia su tamaño o lo oscurece  
  
## Vea también  
 <xref:System.Drawing.CopyPixelOperation>   
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=fullName>   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)