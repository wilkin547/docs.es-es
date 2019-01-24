---
title: Procedimiento Use una matriz de colores para establecer valores alfabéticos en imágenes
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
ms.openlocfilehash: 0e62bee55938e79d1555c463ac770f7b35be20f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578822"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Procedimiento Use una matriz de colores para establecer valores alfabéticos en imágenes
El <xref:System.Drawing.Bitmap> clase (que hereda de la <xref:System.Drawing.Image> clase) y la <xref:System.Drawing.Imaging.ImageAttributes> clase proporcionan funcionalidad para obtener y establecer valores de píxel. Puede usar el <xref:System.Drawing.Imaging.ImageAttributes> clase para modificar la versión alfa de los valores de una imagen completa, o bien puede llamar el <xref:System.Drawing.Bitmap.SetPixel%2A> método de la <xref:System.Drawing.Bitmap> clase para modificar valores de píxeles individuales.  
  
## <a name="example"></a>Ejemplo  
 La <xref:System.Drawing.Imaging.ImageAttributes> clase tiene muchas propiedades que puede usar para modificar las imágenes durante la representación. En el ejemplo siguiente, un <xref:System.Drawing.Imaging.ImageAttributes> objeto se usa para establecer todos los valores alfa en 80 por ciento de su estado original. Esto se hace al inicializar una matriz de colores y estableciendo el valor de la matriz en 0,8 de escala de alfa. La dirección de la matriz de colores se pasa a la <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> método de la <xref:System.Drawing.Imaging.ImageAttributes> objeto y el <xref:System.Drawing.Imaging.ImageAttributes> objeto se pasa a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> objeto.  
  
 Durante la representación, los valores alfa en el mapa de bits se convierten en 80 por ciento de su estado original. Esto da como resultado una imagen que se mezcla con el fondo. Como se muestra en la siguiente ilustración, la imagen de mapa de bits es transparente; puede ver la línea negra sólida a través de él.  
  
 ![Combinación alfa usando una matriz](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 Donde es la imagen a través de la parte del fondo en blanco, la imagen se ha mezclado con el color blanco. Donde la imagen cruza la línea negra, la imagen se mezcla con el color negro.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Líneas y rellenos con combinación alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
