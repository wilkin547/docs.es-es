---
title: Dibujar, colocar y clonar imágenes en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: 5ff502884874e21e8f34acb2f15db4c651a0a273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>Dibujar, colocar y clonar imágenes en GDI+
Puede usar el <xref:System.Drawing.Bitmap> clase para cargar y mostrar imágenes de trama y se puede utilizar el <xref:System.Drawing.Imaging.Metafile> clase para cargar y mostrar imágenes vectoriales. El <xref:System.Drawing.Bitmap> y <xref:System.Drawing.Imaging.Metafile> clases heredan de la <xref:System.Drawing.Image> clase. Para mostrar una imagen vectorial, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Imaging.Metafile>. Para mostrar una imagen de trama, necesita una instancia de la <xref:System.Drawing.Graphics> clase y un <xref:System.Drawing.Bitmap>. La instancia de la <xref:System.Drawing.Graphics> clase proporciona el <xref:System.Drawing.Graphics.DrawImage%2A> método, que recibe el <xref:System.Drawing.Imaging.Metafile> o <xref:System.Drawing.Bitmap> como un argumento.  
  
## <a name="file-types-and-cloning"></a>Tipos de archivos y clonación  
 En el ejemplo de código siguiente se muestra cómo construir un <xref:System.Drawing.Bitmap> desde el archivo Climber.jpg y se muestra el mapa de bits. El punto de destino de la esquina superior izquierda de la imagen, (10, 10), se especifica en los parámetros segundo y tercero.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 En la siguiente ilustración muestra la imagen.  
  
 ![Ejemplo de la imagen](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 Puede construir <xref:System.Drawing.Bitmap> formatos de archivo de objetos desde una variedad de gráficos: BMP, GIF, JPEG, EXIF, PNG, TIFF e icono.  
  
 En el ejemplo de código siguiente se muestra cómo construir <xref:System.Drawing.Bitmap> objetos desde una variedad de tipos de archivo y, a continuación, muestra los mapas de bits.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 El <xref:System.Drawing.Bitmap> clase proporciona un <xref:System.Drawing.Bitmap.Clone%2A> método que puede usar para realizar una copia de un miembro de <xref:System.Drawing.Bitmap>. El <xref:System.Drawing.Bitmap.Clone%2A> método tiene un parámetro de rectángulo de origen que se puede utilizar para especificar la parte del mapa de bits original que se van a copiar. En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Drawing.Bitmap> mediante la clonación de la mitad superior de un objeto <xref:System.Drawing.Bitmap>. A continuación, se dibujan las imágenes.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 La ilustración siguiente muestra las dos imágenes.  
  
 ![Recortar](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
