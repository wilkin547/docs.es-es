---
title: Procedimiento Cargar y mostrar metarchivos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: d0835d7f2c5ffea44f22661a765ab16b1d0130c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619563"
---
# <a name="how-to-load-and-display-metafiles"></a>Procedimiento Cargar y mostrar metarchivos
El <xref:System.Drawing.Imaging.Metafile> (clase), que hereda de la <xref:System.Drawing.Image> de clases, que proporciona métodos para registrar, mostrar y examinar imágenes vectoriales.  
  
## <a name="example"></a>Ejemplo  
 Para mostrar una imagen vectorial (metarchivo) en la pantalla, necesita un <xref:System.Drawing.Imaging.Metafile> objeto y un <xref:System.Drawing.Graphics> objeto. Pasar el nombre de un archivo (o una secuencia) a un <xref:System.Drawing.Imaging.Metafile> constructor. Después de haber creado un <xref:System.Drawing.Imaging.Metafile> de objetos, pasar ese <xref:System.Drawing.Imaging.Metafile> de objeto para el <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto.  
  
 El ejemplo se crea un <xref:System.Drawing.Imaging.Metafile> objeto desde un archivo EMF (metarchivo mejorado) y, a continuación, dibuja la imagen con la esquina superior izquierda en (60, 10).  
  
 La siguiente ilustración muestra el metarchivo dibujado en la ubicación especificada.  
  
 ![Posición de la imagen](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
