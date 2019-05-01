---
title: Procedimiento para obtener métricas de fuentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 24cada3962339cae0608bbe01e070a0b8e256e73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948241"
---
# <a name="how-to-obtain-font-metrics"></a>Procedimiento para obtener métricas de fuentes
La <xref:System.Drawing.FontFamily> clase proporciona los siguientes métodos que recuperan diversas métricas para una combinación de familia y estilo concreta:  
  
- <xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)  
  
 Los números devueltos por estos métodos están en unidades de diseño de fuente, por lo que son independientes del tamaño y las unidades de una determinada <xref:System.Drawing.Font> objeto.  
  
 La siguiente ilustración muestra las distintas métricas.  
  
 ![Texto de las fuentes](./media/fontstext7a.png "fontstext7A")  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra las métricas para el estilo normal de la familia de fuentes Arial. El código también crea un <xref:System.Drawing.Font> objeto (basado en la familia Arial) con el tamaño de 16 píxeles y muestra las métricas (en píxeles) para ese <xref:System.Drawing.Font> objeto.  
  
 La siguiente ilustración muestra el resultado del código de ejemplo.  
  
 ![Fonts Text](./media/csfontstext8.png "csFontsText8")  
  
 Tenga en cuenta las dos primeras líneas de salida en la ilustración anterior. El <xref:System.Drawing.Font> objeto devuelve un tamaño de 16 y el <xref:System.Drawing.FontFamily> objeto devuelve un alto em de 2048. Estos dos números (16 y 2.048) son la clave para la conversión entre unidades de diseño de fuente y las unidades (en este caso, píxeles) de la <xref:System.Drawing.Font> objeto.  
  
 Por ejemplo, puede convertir el ascenso de unidades de diseño a píxeles como sigue:  
  
 ![Fonts Text](./media/fontstext9.png "FontsText9")  
  
 El siguiente código coloca el texto verticalmente estableciendo el <xref:System.Drawing.PointF.Y%2A> miembro de datos de un <xref:System.Drawing.PointF> objeto. La coordenada y se incrementa en `font.Height` para cada nueva línea de texto. El <xref:System.Drawing.Font.Height%2A> propiedad de un <xref:System.Drawing.Font> objeto devuelve el interlineado (en píxeles) para ese <xref:System.Drawing.Font> objeto. En este ejemplo, el número devuelto por <xref:System.Drawing.Font.Height%2A> es 19. Tenga en cuenta que es el mismo que el número (redondeado a un entero) obtenido mediante la conversión de la métrica de espaciado de línea en píxeles.  
  
 Tenga en cuenta que el alto em (también llamado tamaño o tamaño em) no es la suma de ascenso y el descenso. La suma de ascenso y el descenso se denomina el alto de celda. El alto de celda menos el espacio interno es igual que el alto em. El alto de celda más la inicial externa es igual que el espaciado de línea.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Utilizar fuentes y texto](using-fonts-and-text.md)
