---
title: Procedimiento para rellenar una forma con una textura de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911686"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Procedimiento para rellenar una forma con una textura de imagen
Puede rellenar una forma cerrada con una textura mediante la <xref:System.Drawing.Image> clase y la <xref:System.Drawing.TextureBrush> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se rellena una elipse con una imagen. El código crea un <xref:System.Drawing.Image> objeto y, a continuación, pasa la dirección de ese <xref:System.Drawing.Image> objeto como un argumento a <xref:System.Drawing.TextureBrush.%23ctor%2A> un constructor. La tercera instrucción escala la imagen y la cuarta instrucción rellena la elipse con copias repetidas de la imagen escalada.  
  
 En el código siguiente, la <xref:System.Drawing.TextureBrush.Transform%2A> propiedad contiene la transformación que se aplica a la imagen antes de dibujarse. Supongamos que la imagen original tiene un ancho de 640 píxeles y un alto de 480 píxeles. La transformación reduce la imagen a 75 × 75 estableciendo los valores de escalado horizontal y vertical.  
  
> [!NOTE]
> En el ejemplo siguiente, el tamaño de la imagen es 75 × 75 y el tamaño de la elipse es 150 × 250. Dado que la imagen es más pequeña que la elipse que está rellenando, la elipse se coloca en mosaico con la imagen. La disposición en mosaico significa que la imagen se repite horizontal y verticalmente hasta que se alcanza el límite de la forma. Para obtener más información acerca de la [disposición en mosaico, consulte Cómo: Colocar una forma en mosaico con](how-to-tile-a-shape-with-an-image.md)una imagen.  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que <xref:System.Windows.Forms.Control.Paint> es un parámetro del controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel para rellenar formas](using-a-brush-to-fill-shapes.md)
