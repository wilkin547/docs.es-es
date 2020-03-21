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
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182500"
---
# <a name="how-to-render-images-with-gdi"></a>Cómo: Representar imágenes con GDI+
Puede utilizar GDI+GDI+ para representar imágenes que existen como archivos en las aplicaciones. Para ello, cree un nuevo <xref:System.Drawing.Image> objeto de <xref:System.Drawing.Bitmap>una <xref:System.Drawing.Graphics> clase (por ejemplo, ), creando un objeto <xref:System.Drawing.Graphics.DrawImage%2A> que <xref:System.Drawing.Graphics> haga referencia a la superficie de dibujo que desea utilizar y llamando al método del objeto. La imagen se pintará sobre la superficie de dibujo representada por la clase graphics. Puede utilizar el Editor de imágenes para crear y editar archivos de imagen en tiempo de diseño y representarlos con GDI+GDI+ en tiempo de ejecución. Para más información, consulte [Editor de imágenes para iconos](/cpp/windows/image-editor-for-icons).  
  
### <a name="to-render-an-image-with-gdi"></a>Para representar una imagen con GDI+  
  
1. Cree un objeto que represente la imagen que desee mostrar. Este objeto debe ser un miembro de <xref:System.Drawing.Image>una <xref:System.Drawing.Bitmap> clase <xref:System.Drawing.Imaging.Metafile>que herede de , como o . Se muestra un ejemplo:  
  
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
  
2. Cree <xref:System.Drawing.Graphics> un objeto que represente la superficie de dibujo que desea utilizar. Para más información, consulte [Cómo: Crear objetos Graphics para dibujar](how-to-create-graphics-objects-for-drawing.md).  
  
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
  
3. Llame <xref:System.Drawing.Graphics.DrawImage%2A> al objeto de gráficos para representar la imagen. Debe especificar la imagen que se va a dibujar y las coordenadas en las que se va a dibujar.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Cómo: Crear objetos Graphics para dibujar](how-to-create-graphics-objects-for-drawing.md)
- [Lápices, líneas y rectángulos en GDI+](pens-lines-and-rectangles-in-gdi.md)
- [Cómo: Dibujar texto en Windows Forms](how-to-draw-text-on-a-windows-form.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Dibujar líneas o figuras cerradas](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [Editor de imágenes para iconos](/cpp/windows/image-editor-for-icons)
