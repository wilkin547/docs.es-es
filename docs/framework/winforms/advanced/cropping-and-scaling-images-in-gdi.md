---
title: "Recortar y ajustar la escala de las imágenes en GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bbe7ac4b8c541ea76392f94f538e41816cf5c3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Recortar y ajustar la escala de las imágenes en GDI+
Puede usar el <xref:System.Drawing.Graphics.DrawImage%2A> método de la <xref:System.Drawing.Graphics> clase para dibujar y colocar imágenes vectoriales e imágenes de trama. <xref:System.Drawing.Graphics.DrawImage%2A>es un método sobrecargado, por lo que hay varias formas de proporcionar argumentos.  
  
## <a name="drawimage-variations"></a>Variaciones de DrawImage  
 Una variación de la <xref:System.Drawing.Graphics.DrawImage%2A> método recibe un <xref:System.Drawing.Bitmap> y <xref:System.Drawing.Rectangle>. El rectángulo especifica el destino de la operación de dibujo; es decir, especifica el rectángulo en el que se va a dibujar la imagen. Si el tamaño del rectángulo de destino es diferente del tamaño de la imagen original, la imagen se escala para ajustarse el rectángulo de destino. En el ejemplo de código siguiente se muestra cómo dibujar la misma imagen tres veces: una vez sin ajuste de escala, otra con una expansión y otra con una compresión:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 La siguiente ilustración muestra las tres imágenes.  
  
 ![Ajuste de escala](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Algunas variaciones de la <xref:System.Drawing.Graphics.DrawImage%2A> método tiene un parámetro de rectángulo de origen, así como un parámetro de rectángulo de destino. El parámetro de rectángulo de origen Especifica la parte de la imagen original para dibujar. El rectángulo de destino Especifica el rectángulo en el que se va a dibujar esa parte de la imagen. Si el tamaño del rectángulo de destino es diferente del tamaño del rectángulo de origen, la imagen se escala para ajustarse el rectángulo de destino.  
  
 En el ejemplo de código siguiente se muestra cómo construir un <xref:System.Drawing.Bitmap> partir del archivo Runner.jpg. Toda la imagen se dibuja sin ajuste de escala en (0, 0). A continuación, una pequeña parte de la imagen se dibuja dos veces: una vez con una compresión y otra con una expansión.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 En la siguiente ilustración muestra la imagen sin ajuste de escala y las partes de la imagen comprimida y expandida.  
  
 ![Recortar y ajustar la escala](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
