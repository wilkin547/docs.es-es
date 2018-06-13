---
title: 'Cómo: Establecer posiciones de tabulación en texto dibujado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: e7f3fe9757db26bcc9dc9735f3d3d854edb7c099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523642"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Cómo: Establecer posiciones de tabulación en texto dibujado
Puede establecer tabulaciones para el texto mediante una llamada a la <xref:System.Drawing.StringFormat.SetTabStops%2A> método de un <xref:System.Drawing.StringFormat> objeto y, a continuación, pasar que <xref:System.Drawing.StringFormat> el objeto a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> hace que no admiten la agregación de tabulaciones para representar texto, aunque puede expandir ficha existente deja de usar la <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> marca.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se establece tabulaciones en 150, 250 y 350. A continuación, el código muestra una lista con pestañas de nombres y las puntuaciones de prueba.  
  
 La ilustración siguiente muestra el texto con pestañas.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 El código siguiente pasa dos argumentos a la <xref:System.Drawing.StringFormat.SetTabStops%2A> método. El segundo argumento es una matriz que contiene los desplazamientos de pestaña. El primer argumento pasado a <xref:System.Drawing.StringFormat.SetTabStops%2A> es 0, lo que indica que el primer desplazamiento de la matriz se mide desde la posición 0, el borde izquierdo del rectángulo delimitador.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
