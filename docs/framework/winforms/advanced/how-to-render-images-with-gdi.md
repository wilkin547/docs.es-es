---
title: "C&#243;mo: Representar im&#225;genes con GDI+ | Microsoft Docs"
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
  - "GDI+, representar imágenes existentes"
  - "imágenes [Windows Forms], crear"
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Representar im&#225;genes con GDI+
La interfaz [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede usarse para representar imágenes que existan como archivos en las aplicaciones.  Para ello hay que crear un nuevo objeto de una clase <xref:System.Drawing.Image> \(como <xref:System.Drawing.Bitmap>\), crear un objeto <xref:System.Drawing.Graphics> que haga referencia a la superficie de dibujo que se desea utilizar y llamar al método <xref:System.Drawing.Graphics.DrawImage%2A> del objeto <xref:System.Drawing.Graphics>.  La imagen se pintará sobre la superficie de dibujo representada por la clase Graphics.  Los archivos de imagen se pueden crear y modificar mediante el Editor de imágenes en tiempo de diseño para representarlos posteriormente con la interfaz [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] en tiempo de ejecución.  Para obtener más información, vea [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md).  
  
### Para representar una imagen con GDI\+  
  
1.  Cree un objeto que represente a la imagen que desea mostrar.  Este objeto debe ser miembro de una clase que herede de <xref:System.Drawing.Image>, como <xref:System.Drawing.Bitmap> o <xref:System.Drawing.Imaging.Metafile>.  A continuación se muestra un ejemplo:  
  
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
  
2.  Cree un objeto <xref:System.Drawing.Graphics> que represente la superficie de dibujo que desea usar.  Para obtener más información, vea [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Llame al método <xref:System.Drawing.Graphics.DrawImage%2A> del objeto Graphics para representar la imagen.  Deberá especificar la imagen que desea que se dibuje y las coordenadas en las que se debe dibujar.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## Vea también  
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Lápices, líneas y rectángulos en GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)   
 [Cómo: Dibujar texto en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Drawing Lines or Closed Figures](../Topic/Drawing%20Lines%20or%20Closed%20Figures%20\(Image%20Editor%20for%20Icons\).md)   
 [Image Editor for Icons](../Topic/Image%20Editor%20for%20Icons.md)