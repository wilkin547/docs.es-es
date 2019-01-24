---
title: Procedimiento Usar el modo de interpolación para controlar la calidad de imagen durante el escalado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 0c295411418dabac74626c3c4ab43fb8210bbfa4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631432"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Procedimiento Usar el modo de interpolación para controlar la calidad de imagen durante el escalado
El modo de interpolación de una <xref:System.Drawing.Graphics> objeto influye en la forma [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imágenes escalas (estira y encoge). El <xref:System.Drawing.Drawing2D.InterpolationMode> enumeración define varios modos de interpolación, algunos de los cuales se muestran en la lista siguiente:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Para ajustar una imagen, cada píxel de la imagen original debe asignarse a un grupo de píxeles de la imagen más grande. Para comprimir una imagen, los grupos de píxeles de la imagen original deben asignarse a píxeles únicos de la imagen más pequeña. La eficacia de los algoritmos que realizan estas asignaciones determina la calidad de una imagen escalada. Los algoritmos que generan imágenes con escala mayor calidad tienden a necesitar más tiempo de procesamiento. En la lista anterior, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> es el modo de menor calidad y <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> es el modo de mayor calidad.  
  
 Para establecer el modo de interpolación, asigne uno de los miembros de la <xref:System.Drawing.Drawing2D.InterpolationMode> enumeración a la <xref:System.Drawing.Graphics.InterpolationMode%2A> propiedad de un <xref:System.Drawing.Graphics> objeto.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente dibuja una imagen y, a continuación, reduce la imagen con tres modos de interpolación diferente.  
  
 La siguiente ilustración muestra la imagen original y las tres imágenes más pequeñas.  
  
 ![Imagen con diversos valores de interpolación](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
