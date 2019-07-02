---
title: Procedimiento para mejorar el rendimiento evitando el ajuste de tamaño automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506206"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Procedimiento para mejorar el rendimiento evitando el ajuste de tamaño automático
GDI + puede escalar automáticamente una imagen como dibujar, lo que reduciría el rendimiento. Como alternativa, puede controlar la escala de la imagen pasando las dimensiones del rectángulo de destino para el <xref:System.Drawing.Graphics.DrawImage%2A> método.  
  
 Por ejemplo, la llamada siguiente a la <xref:System.Drawing.Graphics.DrawImage%2A> método especifica una esquina superior izquierda de (50, 30) pero no especifica un rectángulo de destino.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Aunque esta es la versión más sencilla de la <xref:System.Drawing.Graphics.DrawImage%2A> método en cuanto al número de argumentos necesarios, no es necesariamente el más eficaz. Si la resolución utilizada por GDI + (normalmente 96 puntos por pulgada) es diferente de la resolución almacenada en el <xref:System.Drawing.Image> objeto, el <xref:System.Drawing.Graphics.DrawImage%2A> método escala la imagen. Por ejemplo, suponga un <xref:System.Drawing.Image> objeto tiene un ancho de 216 píxeles y un valor almacenado resolución horizontal de 72 puntos por pulgada. Como 216/72 es 3, <xref:System.Drawing.Graphics.DrawImage%2A> escala la imagen para que tenga un ancho de 3 pulgadas con una resolución de 96 puntos por pulgada. Es decir, <xref:System.Drawing.Graphics.DrawImage%2A> mostrará una imagen que tiene un ancho de 96 x 3 = 288 píxeles.  
  
 Incluso si difiere la resolución de pantalla de 96 puntos por pulgada, GDI + ajustará probablemente la imagen como si tratara de la resolución de pantalla de 96 puntos por pulgada. Eso es porque GDI + <xref:System.Drawing.Graphics> objeto está asociado con un contexto de dispositivo, y cuando GDI + consulta en el contexto de dispositivo para la resolución de pantalla, el resultado suele ser 96, independientemente de la resolución de pantalla real. Puede evitar el escalado automático mediante la especificación de rectángulo de destino en el <xref:System.Drawing.Graphics.DrawImage%2A> método.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente dibuja la misma imagen dos veces. En el primer caso, no se especifican el ancho y alto del rectángulo de destino y la imagen se escala automáticamente. En el segundo caso, el ancho y alto (medido en píxeles) del rectángulo de destino se especifican para ser igual que el ancho y alto de la imagen original. La siguiente ilustración muestra la imagen representada dos veces:  
  
 ![Captura de pantalla que muestra imágenes con textura ajustada.](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Reemplace Texture.jpg por un nombre de la imagen y la ruta de acceso que son válidos en el sistema.  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
