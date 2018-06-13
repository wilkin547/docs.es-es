---
title: 'Cómo: Utilizar el modo de composición para controlar la mezcla alfa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 55c6db1029c6823652ac29fca46f6f8dc4ec40d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527007"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Cómo: Utilizar el modo de composición para controlar la mezcla alfa
Puede haber ocasiones cuando desee crear un mapa de bits fuera de la pantalla que tiene las siguientes características:  
  
-   Colores tienen valores alfabéticos menor que 255.  
  
-   Colores no son alfabéticos combinar entre sí para crear el mapa de bits.  
  
-   Cuando se muestra el mapa de bits terminado, colores del mapa de bits son alfa mezclado con los colores de fondo en el dispositivo de pantalla.  
  
 Para crear un mapa de bits, construya un espacio en blanco <xref:System.Drawing.Bitmap> objeto y, a continuación, construya un <xref:System.Drawing.Graphics> objeto basado en ese mapa de bits. Establezca el modo de composición de la <xref:System.Drawing.Graphics> el objeto a <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto basado en un <xref:System.Drawing.Bitmap> objeto. El código usa el <xref:System.Drawing.Graphics> objeto junto con dos pinceles semitransparentes (alfa = 160) para pintar en el mapa de bits. El código, rellena una elipse roja y una elipse verde utilizando los pinceles semitransparentes. La elipse verde superpone la red, pero no se mezcla con el color rojo, verde porque el modo de composición de la <xref:System.Drawing.Graphics> objeto se establece en <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 El código dibuja el mapa de bits en la pantalla dos veces: una vez sobre un fondo blanco y otra sobre un fondo multicolor. Los píxeles del mapa de bits que forman parte de las dos elipses tienen un componente alfa de 160, por lo que las elipses se mezclan con los colores de fondo en la pantalla.  
  
 En la siguiente ilustración muestra el resultado del ejemplo de código. Tenga en cuenta que las elipses se mezclan con el fondo, pero no se mezclan entre sí.  
  
 ![Copia de origen](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 El ejemplo de código contiene esta instrucción:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Si desea que el botón de puntos suspensivos que deben mezclarse entre sí, así como con el fondo, cambie esa instrucción a la siguiente:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 En la siguiente ilustración muestra el resultado del código revisado.  
  
 ![Origen sobre](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Líneas y rellenos con combinación alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
