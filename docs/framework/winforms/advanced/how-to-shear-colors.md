---
title: 'Cómo: Recortar colores'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142399"
---
# <a name="how-to-shear-colors"></a>Cómo: Recortar colores
El cizallamiento aumenta o disminuye un componente de color en una cantidad proporcional a otro componente de color. Por ejemplo, considere la transformación en la que el componente rojo se incrementa en la mitad del valor del componente azul. En tal transformación, el color (0,2, 0,5, 1) se convertiría en (0,7, 0,5, 1). El nuevo componente rojo es 0,2 + (1/2)(1) a 0,7.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Drawing.Image> siguiente se construye un objeto a partir del archivo ColorBars4.bmp. A continuación, el código aplica la transformación de cizallamiento descrita en el párrafo anterior a cada píxel de la imagen.  
  
 La siguiente ilustración muestra la imagen original a la izquierda y la imagen cizallada a la derecha:
  
 ![Dos cuadrados con rayas de colores lado a lado ilustrando la imagen original y la imagen cizallada.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 En la tabla siguiente se enumeran los vectores de color de las cuatro barras antes y después de la transformación de cizallamiento.  
  
|Original|Esquilada|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e`con formularios Windows Forms, y requiere , que es un parámetro del <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace `ColorBars.bmp` por un nombre de imagen y una ruta de acceso válidas en el sistema.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Cambiar el color de las imágenes](recoloring-images.md)
