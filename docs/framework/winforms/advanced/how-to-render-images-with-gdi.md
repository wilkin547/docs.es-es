---
title: 'Cómo: Representar imágenes con GDI+'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: 6f5b139c6831a065c85e9d9889c259c859a649cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524611"
---
# <a name="how-to-render-images-with-gdi"></a>Cómo: Representar imágenes con GDI+
Puede usar [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] para representar imágenes que existan como archivos en las aplicaciones. Para ello, cree un nuevo objeto de un <xref:System.Drawing.Image> clase (como <xref:System.Drawing.Bitmap>), creando un <xref:System.Drawing.Graphics> objeto que hace referencia a la superficie de dibujo que desea usar y, al llamar a la <xref:System.Drawing.Graphics.DrawImage%2A> método de la <xref:System.Drawing.Graphics> objeto. La imagen se pintará sobre la superficie de dibujo representada por la clase graphics. Puede usar el Editor de imágenes para crear y editar archivos de imagen en tiempo de diseño y representarlos con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] en tiempo de ejecución. Para más información, consulte [Editor de imágenes para iconos](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>Para representar una imagen con GDI+  
  
1.  Cree un objeto que represente la imagen que desee mostrar. Este objeto debe ser un miembro de una clase que hereda de <xref:System.Drawing.Image>, como <xref:System.Drawing.Bitmap> o <xref:System.Drawing.Imaging.Metafile>. Se muestra un ejemplo:  
  
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
  
2.  Crear un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo que desea usar. Para más información, consulte [Cómo: Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3.  Llame a la <xref:System.Drawing.Graphics.DrawImage%2A> del objeto graphics para representar la imagen. Debe especificar la imagen que se va a dibujar y las coordenadas en las que se va a dibujar.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Lápices, líneas y rectángulos en GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)  
 [Dibujar texto en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-draw-text-on-a-windows-form.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Dibujar líneas o figuras cerradas](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)  
 [Editor de imágenes para iconos](/cpp/windows/image-editor-for-icons)
