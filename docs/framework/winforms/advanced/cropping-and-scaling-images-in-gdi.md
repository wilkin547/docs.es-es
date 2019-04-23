---
title: Recortar y ajustar la escala de las imágenes en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183734"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Recortar y ajustar la escala de las imágenes en GDI+
Puede usar el <xref:System.Drawing.Graphics.DrawImage%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar y colocar imágenes vectoriales e imágenes de trama. <xref:System.Drawing.Graphics.DrawImage%2A> es un método sobrecargado, por lo que hay varias maneras de proporcionar argumentos.  
  
## <a name="drawimage-variations"></a>Variaciones de DrawImage  
 Una variación de la <xref:System.Drawing.Graphics.DrawImage%2A> método recibe una <xref:System.Drawing.Bitmap> y un <xref:System.Drawing.Rectangle>. El rectángulo especifica el destino de la operación de dibujo; es decir, especifica el rectángulo en el que se va a dibujar la imagen. Si el tamaño del rectángulo de destino es diferente del tamaño de la imagen original, la imagen se escala para ajustarse el rectángulo de destino. En el ejemplo de código siguiente se muestra cómo dibujar la misma imagen tres veces: una vez sin ajuste de escala, una vez con una expansión y otra con una compresión:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 La siguiente ilustración muestra las tres imágenes.  
  
 ![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Algunas variaciones de la <xref:System.Drawing.Graphics.DrawImage%2A> método tiene un parámetro de rectángulo de origen, así como un parámetro de rectángulo de destino. El parámetro de rectángulo de origen Especifica la parte de la imagen original se va a dibujar. El rectángulo de destino Especifica el rectángulo en el que se va a dibujar esa parte de la imagen. Si el tamaño del rectángulo de destino es diferente del tamaño del rectángulo de origen, la imagen se escala para ajustarse el rectángulo de destino.  
  
 El ejemplo de código siguiente muestra cómo construir un <xref:System.Drawing.Bitmap> desde el archivo Runner.jpg. Toda la imagen se dibuja ningún ajuste de escala en (0, 0). A continuación, una pequeña parte de la imagen se dibuja dos veces: una vez con una compresión y otra vez con una expansión.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 La siguiente ilustración muestra la imagen sin escala y las partes de la imagen comprimida y expandida.  
  
 ![Recortar y escalar](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
