---
title: Estructura de la interfaz gráfica
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: 33be9d4d4e5a1aca933bb84e948b2200cd96b152
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708124"
---
# <a name="structure-of-the-graphics-interface"></a>Estructura de la interfaz gráfica
La interfaz de clase administrada para [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contiene clases de aproximadamente 60, 50 enumeraciones y estructuras de 8. El <xref:System.Drawing.Graphics> clase es el núcleo de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funcionalidad; es la clase que realmente dibuja líneas, curvas, figuras, imágenes y texto.  
  
## <a name="important-classes"></a>Clases importantes  
 Muchas clases trabajan junto con la <xref:System.Drawing.Graphics> clase. Por ejemplo, el <xref:System.Drawing.Graphics.DrawLine%2A> método recibe un <xref:System.Drawing.Pen> objeto, que contiene los atributos (color, ancho, estilo de guión y similares) de la línea que se va a dibujar. El <xref:System.Drawing.Graphics.FillRectangle%2A> método puede recibir un puntero a un <xref:System.Drawing.Drawing2D.LinearGradientBrush> objeto, que funciona con el <xref:System.Drawing.Graphics> objeto para rellenar un rectángulo con un color cambio gradualmente. <xref:System.Drawing.Font> y <xref:System.Drawing.StringFormat> objetos influyen en el modo un <xref:System.Drawing.Graphics> objeto dibuja texto. Un <xref:System.Drawing.Drawing2D.Matrix> objeto almacena y manipula la transformación de un <xref:System.Drawing.Graphics> objeto, que se utiliza para girar, escalar y girar las imágenes.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varias estructuras (por ejemplo, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, y <xref:System.Drawing.Size>) para organizar los datos de gráficos. Además, algunas clases sirven principalmente como estructurada de los tipos de datos. Por ejemplo, el <xref:System.Drawing.Imaging.BitmapData> clase es una aplicación auxiliar para el <xref:System.Drawing.Bitmap> (clase) y el <xref:System.Drawing.Drawing2D.PathData> clase es una aplicación auxiliar para el <xref:System.Drawing.Drawing2D.GraphicsPath> clase.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] define varias enumeraciones, que son colecciones de constantes relacionadas. Por ejemplo, el <xref:System.Drawing.Drawing2D.LineJoin> enumeración contiene los elementos <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, y <xref:System.Drawing.Drawing2D.LineJoin.Round>, que especifica los estilos que pueden utilizarse para combinar dos líneas.  
  
## <a name="see-also"></a>Vea también
- [Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])
- [About GDI+ Managed Code](about-gdi-managed-code.md) (Acerca del código administrado de GDI+)
- [Using Managed Graphics Classes](using-managed-graphics-classes.md) (Usar clases gráficas administradas)
