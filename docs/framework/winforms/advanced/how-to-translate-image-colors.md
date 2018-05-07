---
title: 'Cómo: Convertir colores de imágenes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 48f506f76ff6e9ca648822d073b6f6a852b9ca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-translate-image-colors"></a>Cómo: Convertir colores de imágenes
Una traducción, agrega un valor para uno o varios de los cuatro componentes de color. En la tabla siguiente se indican las entradas de la matriz de color que representan las traducciones.  
  
|Componente que se deben traducir|Entrada de matriz|  
|--------------------------------|------------------|  
|Rojo|[4][0]|  
|Verde|[4][1]|  
|Azul|[4][2]|  
|Alpha|[4][3]|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars.bmp. A continuación, el código agrega 0,75 al componente rojo de cada píxel de la imagen. Se dibuja la imagen original junto con la imagen transformada.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen transformada a la derecha.  
  
 ![Conversión de colores](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la conversión del rojo. Tenga en cuenta que dado que el valor máximo de un componente de color es 1, el componente rojo de la segunda fila no cambia. (De forma similar, el valor mínimo de un componente de color es 0).  
  
|Original|Texto traducido al|  
|--------------|----------------|  
|Negro (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rojo (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Verde (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Azul (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `ColorBars.bmp` con un nombre de archivo de imagen y la ruta de acceso que son válidos en el sistema.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)
