---
title: 'Cómo: Utilizar el modo de interpolación para controlar la calidad de imagen durante el ajuste de tamaño'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 72a9cb3a19f0d449dcb376a65f1734b79ed61ab9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Cómo: Utilizar el modo de interpolación para controlar la calidad de imagen durante el ajuste de tamaño
El modo de interpolación de un <xref:System.Drawing.Graphics> objeto influye en la forma [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imágenes escalas (se expande y se reduce). El <xref:System.Drawing.Drawing2D.InterpolationMode> enumeración define varios modos de interpolación, algunos de los cuales se muestran en la lista siguiente:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Para ajustar una imagen, cada píxel de la imagen original debe asignarse a un grupo de píxeles de la imagen más grande. Para reducir una imagen, grupos de píxeles de la imagen original deben asignarse a píxeles únicos de la imagen más pequeña. La eficacia de los algoritmos que realizan estas asignaciones determina la calidad de una imagen de escala. Los algoritmos que producen imágenes con escala mayor calidad tienden a necesitar más tiempo de procesamiento. En la lista anterior, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> es el modo de menor calidad y <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> es el modo de máxima calidad.  
  
 Para establecer el modo de interpolación, asigne uno de los miembros de la <xref:System.Drawing.Drawing2D.InterpolationMode> enumeración para la <xref:System.Drawing.Graphics.InterpolationMode%2A> propiedad de un <xref:System.Drawing.Graphics> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se dibuja una imagen y, a continuación, se reduce la imagen con tres modos de interpolación diferente.  
  
 En la siguiente ilustración muestra la imagen original y las tres imágenes más pequeñas.  
  
 ![Imagen con diversos valores de interpolación](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
