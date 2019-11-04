---
title: 'Cómo: Cargar y mostrar metarchivos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424815"
---
# <a name="how-to-load-and-display-metafiles"></a>Cómo: Cargar y mostrar metarchivos
La clase <xref:System.Drawing.Imaging.Metafile>, que hereda de la clase <xref:System.Drawing.Image>, proporciona métodos para grabar, mostrar y examinar imágenes vectoriales.  
  
## <a name="example"></a>Ejemplo  
 Para mostrar una imagen vectorial (metarchivo) en la pantalla, necesita un objeto <xref:System.Drawing.Imaging.Metafile> y un objeto <xref:System.Drawing.Graphics>. Pase el nombre de un archivo (o una secuencia) a un constructor de <xref:System.Drawing.Imaging.Metafile>. Después de crear un objeto de <xref:System.Drawing.Imaging.Metafile>, pase ese <xref:System.Drawing.Imaging.Metafile> objeto al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics>.  
  
 En el ejemplo se crea un objeto <xref:System.Drawing.Imaging.Metafile> a partir de un archivo EMF (metarchivo mejorado) y, a continuación, se dibuja la imagen con la esquina superior izquierda en (60, 10).  
  
 En la ilustración siguiente se muestra el metarchivo dibujado en la ubicación especificada.  
  
 ![Captura de pantalla que muestra la posición de la imagen.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también

- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
