---
title: 'Cómo: Utilizar una matriz de colores para establecer valores alfa en imágenes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423736"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Cómo: Utilizar una matriz de colores para establecer valores alfa en imágenes
La clase <xref:System.Drawing.Bitmap> (que se hereda de la clase <xref:System.Drawing.Image>) y la clase <xref:System.Drawing.Imaging.ImageAttributes> proporcionan funcionalidad para obtener y establecer valores de píxeles. Puede usar la clase <xref:System.Drawing.Imaging.ImageAttributes> para modificar los valores alfa de una imagen completa, o puede llamar al método <xref:System.Drawing.Bitmap.SetPixel%2A> de la clase <xref:System.Drawing.Bitmap> para modificar valores de píxel individuales.  
  
## <a name="example"></a>Ejemplo  
 La clase <xref:System.Drawing.Imaging.ImageAttributes> tiene muchas propiedades que se pueden utilizar para modificar imágenes durante la representación. En el ejemplo siguiente, se usa un objeto <xref:System.Drawing.Imaging.ImageAttributes> para establecer todos los valores alfa en el 80 por ciento de lo que eran. Esto se hace inicializando una matriz de colores y estableciendo el valor de escala alfa en la matriz en 0,8. La dirección de la matriz de colores se pasa al método <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> del objeto <xref:System.Drawing.Imaging.ImageAttributes> y el objeto <xref:System.Drawing.Imaging.ImageAttributes> se pasa al método <xref:System.Drawing.Graphics.DrawString%2A> del objeto <xref:System.Drawing.Graphics>.  
  
 Durante la representación, los valores alfa del mapa de bits se convierten al 80 por ciento de lo que eran. Esto da como resultado una imagen que se combina con el fondo. Como se muestra en la siguiente ilustración, la imagen de mapa de bits es transparente; puede ver la línea negra sólida a través de ella.  
  
 ![Captura de pantalla de la combinación alfa mediante una matriz.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")  
  
 Cuando la imagen está sobre la parte blanca del fondo, la imagen se ha mezclado con el color blanco. Cuando la imagen cruza la línea negra, la imagen se combina con el color negro.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Líneas y rellenos con combinación alfa](alpha-blending-lines-and-fills.md)
