---
title: Estructura de la interfaz gráfica
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: 625bd5818d58fd659af69d4985d629f055123e54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="structure-of-the-graphics-interface"></a>Estructura de la interfaz gráfica
La interfaz de clases administradas a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contiene aproximadamente 60 clases, 50 enumeraciones y 8 estructuras. El <xref:System.Drawing.Graphics> clase es el núcleo de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funcionalidad; es la clase que realmente dibuja líneas, curvas, figuras, imágenes y texto.  
  
## <a name="important-classes"></a>Clases importantes  
 Muchas clases trabajan junto con la <xref:System.Drawing.Graphics> clase. Por ejemplo, el <xref:System.Drawing.Graphics.DrawLine%2A> método recibe un <xref:System.Drawing.Pen> objeto, que contiene los atributos (color, ancho, estilo de guión etc.) de la línea para dibujar. El <xref:System.Drawing.Graphics.FillRectangle%2A> método puede recibir un puntero a un <xref:System.Drawing.Drawing2D.LinearGradientBrush> objeto, que funciona con la <xref:System.Drawing.Graphics> objeto para rellenar un rectángulo con un color que cambia gradualmente. <xref:System.Drawing.Font> y <xref:System.Drawing.StringFormat> objetos influir en la forma un <xref:System.Drawing.Graphics> objeto dibuja texto. A <xref:System.Drawing.Drawing2D.Matrix> objeto almacena y manipula la transformación universal de un <xref:System.Drawing.Graphics> objeto, que se utiliza para girar, escalar y voltear imágenes.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varias estructuras (por ejemplo, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, y <xref:System.Drawing.Size>) para organizar los datos de gráficos. Además, algunas clases sirven estructurados principalmente como tipos de datos. Por ejemplo, el <xref:System.Drawing.Imaging.BitmapData> clase es una aplicación auxiliar para la <xref:System.Drawing.Bitmap> (clase) y el <xref:System.Drawing.Drawing2D.PathData> clase es una aplicación auxiliar para la <xref:System.Drawing.Drawing2D.GraphicsPath> clase.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] define varias enumeraciones, que son colecciones de constantes relacionadas. Por ejemplo, el <xref:System.Drawing.Drawing2D.LineJoin> enumeración contiene los elementos <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, y <xref:System.Drawing.Drawing2D.LineJoin.Round>, que especifican estilos que pueden utilizarse para combinar dos líneas.  
  
## <a name="see-also"></a>Vea también  
 [Graphics Overview](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])  
 [About GDI+ Managed Code](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md) (Acerca del código administrado de GDI+)  
 [Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md) (Usar clases gráficas administradas)
