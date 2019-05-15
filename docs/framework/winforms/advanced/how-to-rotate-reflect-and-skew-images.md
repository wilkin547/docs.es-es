---
title: Procedimiento para girar, reflejar y sesgar imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590322"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Procedimiento para girar, reflejar y sesgar imágenes
Puede girar, reflejar y sesgar una imagen mediante la especificación de puntos de destino para las esquinas superior izquierda, superior derecha e inferior izquierda de la imagen original. Los tres puntos de destino determinan una transformación afín que asigna la imagen rectangular original a un paralelogramo.  
  
## <a name="example"></a>Ejemplo  
 Por ejemplo, suponga que la imagen original es un rectángulo con la esquina superior izquierda en (0, 0), la esquina superior derecha en (100, 0) y en la esquina inferior izquierda en (0, 50). Ahora supongamos que asignan esos tres puntos a puntos de destino como sigue:  
  
|Punto original|Punto de destino|  
|--------------------|-----------------------|  
|Superior izquierda (0, 0)|(200, 20)|  
|Superior derecha (100, 0)|(110, 100)|  
|Inferior izquierda (0, 50)|(250, 30)|  
  
 La siguiente ilustración muestra la imagen original y la imagen asignada en el paralelogramo. La imagen original ha tiene sesgada, reflejan, girar y traducir. El eje x en el borde superior de la imagen original se asigna a la línea que se ejecuta a través (200, 20) y (110, 100). El eje y en el borde izquierdo de la imagen original se asigna a la línea que se ejecuta a través (200, 20) y (250, 30).  
  
 ![La imagen original y la imagen asignada en el paralelogramo.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 La siguiente ilustración muestra una transformación similar aplicada a una imagen fotográfica:  
  
 ![La imagen de un Escalador y la imagen asignada al paralelogramo.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 La siguiente ilustración muestra una transformación similar aplicada a un metarchivo:  
  
 ![Ilustración de formas, texto y se asignan en el paralelogramo.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 El ejemplo siguiente genera las imágenes que se muestra en la primera ilustración.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. No olvide reemplazar `Stripes.bmp` con la ruta de acceso a una imagen que sea válida en el sistema.  
  
## <a name="see-also"></a>Vea también

- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
