---
title: "Cómo: Mejorar el rendimiento evitando el ajuste de tamaño automático"
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
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f49fc4b1e59879b9ecc67295610187fa2e5e80d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Cómo: Mejorar el rendimiento evitando el ajuste de tamaño automático
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]puede escalar automáticamente una imagen como dibujarlo, por lo que reduciría el rendimiento. O bien, puede controlar la escala de la imagen pasando las dimensiones del rectángulo de destino para la <xref:System.Drawing.Graphics.DrawImage%2A> método.  
  
 Por ejemplo, la siguiente llamada a la <xref:System.Drawing.Graphics.DrawImage%2A> método especifica una esquina superior izquierda de (50, 30) pero no especifica un rectángulo de destino.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Aunque esta es la versión más sencilla de la <xref:System.Drawing.Graphics.DrawImage%2A> método en cuanto al número de argumentos necesarios, no es necesariamente el más eficaz. Si usa la resolución [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (normalmente 96 puntos por pulgada) es diferente de la resolución que se almacenan en la <xref:System.Drawing.Image> objeto, la <xref:System.Drawing.Graphics.DrawImage%2A> método escalará la imagen. Por ejemplo, suponga que un <xref:System.Drawing.Image> objeto tiene un ancho de 216 píxeles y un valor de resolución horizontal almacenado de 72 puntos por pulgada. Como 216/72 es 3, <xref:System.Drawing.Graphics.DrawImage%2A> escalará la imagen para que tenga un ancho de 3 pulgadas con una resolución de 96 puntos por pulgada. Es decir, <xref:System.Drawing.Graphics.DrawImage%2A> mostrará una imagen que tiene un ancho de 96 x 3 = 288 píxeles.  
  
 Aunque la resolución de pantalla sea distinta de 96 puntos por pulgada, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] probablemente escala la imagen como si la resolución de pantalla fuera 96 puntos por pulgada. Eso es porque una [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> objeto está asociado a un contexto de dispositivo y cuándo [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] consultas el contexto de dispositivo para la resolución de pantalla, el resultado suele ser 96, sea cual sea la resolución de pantalla real. Puede evitar el escalado automático especificando el rectángulo de destino en la <xref:System.Drawing.Graphics.DrawImage%2A> método.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se dibuja la misma imagen dos veces. En el primer caso, el ancho y alto del rectángulo de destino no se especifican, y la imagen se escala automáticamente. En el segundo caso, el ancho y alto (expresado en píxeles) del rectángulo de destino se especifican para ser igual que el ancho y alto de la imagen original. En la siguiente ilustración muestra la imagen representada dos veces.  
  
 ![Escala de textura](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>. Reemplace Texture.jpg por un nombre de la imagen y la ruta de acceso que son válidos en el sistema.  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
