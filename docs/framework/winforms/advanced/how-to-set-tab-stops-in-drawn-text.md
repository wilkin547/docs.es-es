---
title: Procedimiento para establecer posiciones de tabulación en texto dibujado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947817"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Procedimiento para establecer posiciones de tabulación en texto dibujado
Puede establecer las tabulaciones para el texto llamando al <xref:System.Drawing.StringFormat.SetTabStops%2A> método de un <xref:System.Drawing.StringFormat> objeto y, a continuación <xref:System.Drawing.StringFormat> , <xref:System.Drawing.Graphics.DrawString%2A> pasando ese objeto al método <xref:System.Drawing.Graphics> de la clase.  
  
> [!NOTE]
> No <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> admite la adición de tabulaciones al texto dibujado, aunque se pueden expandir las tabulaciones existentes mediante <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> la marca.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se establecen tabulaciones en 150, 250 y 350. Después, el código muestra una lista con pestañas de nombres y puntuaciones de pruebas.  
  
 En la ilustración siguiente se muestra el texto con pestañas:  
  
 ![Captura de pantalla que muestra una lista con pestañas de nombres y puntuaciones.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 En el código siguiente se pasan dos argumentos <xref:System.Drawing.StringFormat.SetTabStops%2A> al método. El segundo argumento es una matriz que contiene desplazamientos de tabulación. El primer argumento pasado a <xref:System.Drawing.StringFormat.SetTabStops%2A> es 0, que indica que el primer desplazamiento de la matriz se mide desde la posición 0, el borde izquierdo del rectángulo delimitador.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Utilizar fuentes y texto](using-fonts-and-text.md)
- [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)
