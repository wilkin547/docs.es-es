---
title: 'Cómo: Girar, reflejar y sesgar imágenes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 7f580b4d3016f1ecedc33302fe57caeec5698aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Cómo: Girar, reflejar y sesgar imágenes
Puede girar, reflejar y sesgar una imagen especificando puntos de destino para las esquinas superior izquierda, superior derecha e inferior izquierda de la imagen original. Los tres puntos de destino determinan una transformación afín que asigna la imagen rectangular original a un paralelogramo.  
  
## <a name="example"></a>Ejemplo  
 Por ejemplo, supongamos que la imagen original es un rectángulo con la esquina superior izquierda en (0, 0), la esquina superior derecha en (100, 0) y la esquina inferior izquierda en (0, 50). Ahora suponga que se asignan esos tres puntos a puntos de destino como sigue:  
  
|Punto original|Punto de destino|  
|--------------------|-----------------------|  
|Superior izquierda (0, 0)|(200, 20)|  
|Superior derecha (100, 0)|(110, 100)|  
|Inferior izquierda (0, 50)|(250, 30)|  
  
 En la siguiente ilustración muestra la imagen original y la imagen asignada al paralelogramo. La imagen original se ha sesgado, refleja, giran y traducir. El eje x en el borde superior de la imagen original se asigna a la línea que se ejecuta a través de (200, 20) y (110, 100). El eje y en el borde izquierdo de la imagen original se asigna a la línea que se ejecuta a través de (200, 20) y (250, 30).  
  
 ![Secciona](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 En la siguiente ilustración muestra una transformación similar aplicada a una imagen fotográfica.  
  
 ![Transformar Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 En la siguiente ilustración muestra una transformación similar aplicada a un metarchivo.  
  
 ![Transformar metarchivo](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 En el ejemplo siguiente se produce las imágenes mostradas en la primera ilustración.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Asegúrese de reemplazar `Stripes.bmp` con la ruta de acceso a una imagen que es válida en el sistema.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
