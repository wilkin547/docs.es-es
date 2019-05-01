---
title: Procedimiento para sesgar colores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bf645cf88c4905cd5cf47c2a6c7af088fa428c8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954666"
---
# <a name="how-to-shear-colors"></a>Procedimiento para sesgar colores
Distorsión aumenta o disminuye un componente de color en una cantidad proporcional a otro componente de color. Por ejemplo, considere la posibilidad de la transformación donde el componente rojo se incrementa por la mitad del valor del componente azul. En este tipo de transformación, el color (0.2, 0.5, 1) se convertiría en (0,7, 0,5, 1). El nuevo componente rojo es 0,2 + (1/2)(1) = 0,7.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde el archivo ColorBars4.bmp. A continuación, el código aplica la transformación de recorte que se describe en el párrafo anterior a cada píxel de la imagen.  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen recortada de la derecha: 
  
 ![Dos cuadrados con barras de colores por en paralelo que ilustra la imagen original y la imagen recortada.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la transformación de recorte.  
  
|Original|Recorta|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>. Reemplace `ColorBars.bmp` con un nombre de la imagen y la ruta de acceso válida en su sistema.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Cambiar el color de las imágenes](recoloring-images.md)
