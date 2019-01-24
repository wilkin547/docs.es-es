---
title: Procedimiento Dibujar una línea rellenada con una textura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 65d830ca2d01c63288ef73b6b3a3a94f328fe32b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676251"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Procedimiento Dibujar una línea rellenada con una textura
En lugar de dibujar una línea con un color sólido, puede dibujar una línea con una textura. Para dibujar líneas y curvas con una textura, cree un <xref:System.Drawing.TextureBrush> de objetos y pasar ese <xref:System.Drawing.TextureBrush> objeto a un <xref:System.Drawing.Pen.%23ctor%2A> constructor. El mapa de bits asociado con el pincel de textura se usa para el plano de mosaico (de manera invisible) y, cuando el lápiz dibuja una línea o curva, el trazo del lápiz revela ciertas píxeles de la textura en mosaico.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Bitmap> objeto desde el archivo `Texture1.jpg`. Ese mapa de bits se usa para construir un <xref:System.Drawing.TextureBrush> objeto y el <xref:System.Drawing.TextureBrush> objeto se usa para construir un <xref:System.Drawing.Pen> objeto. La llamada a <xref:System.Drawing.Graphics.DrawImage%2A> dibuja el mapa de bits con la esquina superior izquierda en (0, 0). La llamada a <xref:System.Drawing.Graphics.DrawEllipse%2A> usa el <xref:System.Drawing.Pen> objeto para dibujar una elipse con textura.  
  
 La siguiente ilustración muestra el mapa de bits y la elipse.  
  
 ![Lápices](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un formulario de Windows y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos. Pegue el código anterior en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `Texture.jpg` con una imagen válida en su sistema.  
  
## <a name="see-also"></a>Vea también
- [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
