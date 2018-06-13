---
title: 'Cómo: Rellenar una forma con una textura de imagen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: c1eb090bebcced125193c1db16087b6165d27ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523295"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Cómo: Rellenar una forma con una textura de imagen
Puede rellenar una forma cerrada con una textura utilizando la <xref:System.Drawing.Image> clase y la <xref:System.Drawing.TextureBrush> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se rellena una elipse con una imagen. El código construye una <xref:System.Drawing.Image> objeto y, a continuación, pasa la dirección de ese <xref:System.Drawing.Image> objeto como argumento a un <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor. La tercera instrucción escala la imagen y la cuarta rellena la elipse con las copias repetidas de la imagen escalada.  
  
 En el código siguiente, la <xref:System.Drawing.TextureBrush.Transform%2A> propiedad contiene la transformación que se aplica a la imagen antes de dibujarlo. Suponga que la imagen original tiene un ancho de 640 píxeles y un alto de 480 píxeles. La transformación reduce la imagen a 75 × 75 estableciendo los valores de escalado horizontales y verticales.  
  
> [!NOTE]
>  En el ejemplo siguiente, el tamaño de la imagen es de 75 × 75 y el tamaño de la elipse es de 150 × 250. Dado que la imagen es más pequeña que la elipse que va a rellenar, la elipse se coloca en mosaico con la imagen. Se alcanzó la disposición en mosaico, que la imagen se repite horizontal y verticalmente hasta que el límite de la forma. Para obtener más información acerca de la segmentación, consulte [Cómo: colocar en mosaico una forma con una imagen](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
