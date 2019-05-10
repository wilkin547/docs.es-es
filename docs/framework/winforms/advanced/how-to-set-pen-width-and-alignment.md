---
title: Procedimiento para establecer el ancho y la alineación del lápiz
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 1f1ea6e8ef0b94aa46a4bf8177d59e59297d6e3f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605837"
---
# <a name="how-to-set-pen-width-and-alignment"></a>Procedimiento para establecer el ancho y la alineación del lápiz
Cuando creas un <xref:System.Drawing.Pen>, puede proporcionar el ancho del lápiz como uno de los argumentos al constructor. También puede cambiar el ancho del lápiz con el <xref:System.Drawing.Pen.Width%2A> propiedad de la <xref:System.Drawing.Pen> clase.  
  
 Una línea teórica tiene un ancho de 0. Cuando se dibuja una línea de 1 píxel de ancho, los píxeles se centran en la línea teórica. Si dibuja una línea que tiene más de un píxel de ancho, los píxeles están centrados en la línea teórica o aparecen al lado de la línea teórica. Puede establecer la propiedad de alineación de un <xref:System.Drawing.Pen> para determinar cómo se ubicarán los píxeles dibujados con ese lápiz en relación con las líneas teóricas.  
  
 Los valores <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, y <xref:System.Drawing.Drawing2D.PenAlignment.Inset> que aparecen en los siguientes ejemplos de código son miembros de la <xref:System.Drawing.Drawing2D.PenAlignment> enumeración.  
  
 En el ejemplo de código siguiente se dibuja una línea dos veces: una vez con un lápiz negro de ancho 1 y otra vez con un lápiz verde de ancho 10.  
  
### <a name="to-vary-the-width-of-a-pen"></a>Para variar el ancho de un lápiz  
  
- Establezca el valor de la <xref:System.Drawing.Pen.Alignment%2A> propiedad <xref:System.Drawing.Drawing2D.PenAlignment.Center> (predeterminado) para especificar que los píxeles que se dibuja con el lápiz verde se centrará en la línea teórica. La siguiente ilustración muestra la línea resultante.  
  
     ![Una delgada línea negra con resaltado verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-line.gif)  
  
     En el ejemplo de código siguiente se dibuja un rectángulo dos veces: una vez con un lápiz negro de ancho 1 y otra vez con un lápiz verde de ancho 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>Para cambiar la alineación de un lápiz  
  
- Establezca el valor de la <xref:System.Drawing.Pen.Alignment%2A> propiedad <xref:System.Drawing.Drawing2D.PenAlignment.Center> para especificar que los píxeles que se dibuja con el lápiz verde se centrará en los límites del rectángulo.  
  
     La siguiente ilustración muestra el rectángulo resultante:
  
     ![Un rectángulo que se dibuja con líneas delgadas negras con resaltado verde.](./media/how-to-set-pen-width-and-alignment/green-pixels-centered-rectangle.gif)  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>Para crear un lápiz de bajorrelieve  
  
- Cambiar la alineación del lápiz verde modificando la tercera instrucción en el ejemplo de código anterior como sigue:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Los píxeles en la línea verde ancha aparecen ahora en el interior del rectángulo tal como se muestra en la ilustración siguiente:
  
     ![Un rectángulo que se dibuja con líneas negras con la línea verde ancha dentro.](./media/how-to-set-pen-width-and-alignment/green-pixels-inside-rectangle.gif)  
  
## <a name="see-also"></a>Vea también

- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
