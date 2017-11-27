---
title: "Cómo: Dibujar una línea rellena con una textura"
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
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33374a16e6fee80dd45227acd4c5860d5bfc4545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Cómo: Dibujar una línea rellena con una textura
En lugar de dibujar una línea con un color sólido, puede dibujar una línea con una textura. Para dibujar líneas y curvas con una textura, cree un <xref:System.Drawing.TextureBrush> objeto y pasar ese <xref:System.Drawing.TextureBrush> el objeto a un <xref:System.Drawing.Pen.%23ctor%2A> constructor. El mapa de bits asociado con el pincel de textura se usa para el plano en mosaico (de manera invisible) y, cuando el lápiz dibuja una línea o una curva, el trazo del lápiz detecta determinadas píxeles de la textura de mosaico.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Bitmap> objeto desde el archivo `Texture1.jpg`. Ese mapa de bits se usa para construir un <xref:System.Drawing.TextureBrush> objeto y el <xref:System.Drawing.TextureBrush> objeto se usa para construir un <xref:System.Drawing.Pen> objeto. La llamada a <xref:System.Drawing.Graphics.DrawImage%2A> dibuja el mapa de bits con la esquina superior izquierda en (0, 0). La llamada a <xref:System.Drawing.Graphics.DrawEllipse%2A> utiliza la <xref:System.Drawing.Pen> objeto que se va a dibujar una elipse con textura.  
  
 En la siguiente ilustración muestra el mapa de bits y la elipse.  
  
 ![Lápices](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un formulario Windows Forms y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos. Pegue el código anterior en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `Texture.jpg` con una imagen válida en su sistema.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
