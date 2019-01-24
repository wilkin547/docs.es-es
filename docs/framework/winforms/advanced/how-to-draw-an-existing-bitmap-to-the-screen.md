---
title: Procedimiento Dibujar un mapa de bits existente en la pantalla
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: d8c118d9561c0fe993228cb6bd8cebcd156d411d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586727"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Procedimiento Dibujar un mapa de bits existente en la pantalla
Puede dibujar fácilmente una imagen existente en la pantalla. En primer lugar, deberá crear un <xref:System.Drawing.Bitmap> objeto utilizando el constructor de mapa de bits que toma un nombre de archivo, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Este constructor acepta imágenes con distintos formatos de archivo, incluidos BMP, GIF, JPEG, PNG y TIFF. Después de haber creado el <xref:System.Drawing.Bitmap> de objetos, pasar ese <xref:System.Drawing.Bitmap> de objeto para el <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se crea un <xref:System.Drawing.Bitmap> objeto desde un archivo JPEG y, a continuación, se dibuja el mapa de bits con la esquina superior izquierda en (60, 10).  
  
 La siguiente ilustración muestra el mapa de bits dibujado en la ubicación especificada.  
  
 ![Posición de la imagen](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
