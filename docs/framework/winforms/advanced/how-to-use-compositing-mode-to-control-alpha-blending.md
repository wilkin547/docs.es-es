---
title: Procedimiento Usar el modo de composición para controlar la mezcla alfa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 2e00b0b9b22bc8dcdd1c63494f1bc5854bc4f033
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632015"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Procedimiento Usar el modo de composición para controlar la mezcla alfa
Puede haber ocasiones en que desee crear un mapa de bits fuera de la pantalla que tiene las siguientes características:  
  
-   Colores tienen valores alfabéticos que son menos de 255.  
  
-   Colores no son alfabéticos mezclan entre sí al crear el mapa de bits.  
  
-   Cuando se muestra el mapa de bits terminado, los colores del mapa de bits son una combinación con los colores de fondo de la pantalla alfa.  
  
 Para crear un mapa de bits, construya un espacio en blanco <xref:System.Drawing.Bitmap> objeto y, a continuación, construya un <xref:System.Drawing.Graphics> objeto basado en ese mapa de bits. Establezca el modo de composición de la <xref:System.Drawing.Graphics> objeto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto según un <xref:System.Drawing.Bitmap> objeto. El código usa el <xref:System.Drawing.Graphics> objeto junto con dos pinceles semitransparentes (alfa = 160) para pintar en el mapa de bits. El código rellena una elipse roja y una elipse verde utilizando los pinceles semitransparentes. La elipse verde superpone el rojo, pero no se mezcla con el color rojo, verde porque el modo de composición de la <xref:System.Drawing.Graphics> objeto se establece en <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 El código dibuja el mapa de bits en la pantalla dos veces: una vez en un fondo blanco y una vez en un fondo de varios colores. Los píxeles del mapa de bits que forman parte de las dos elipses tienen un componente alfa de 160, por lo que los puntos suspensivos se mezclan con los colores de fondo en la pantalla.  
  
 La siguiente ilustración muestra el resultado del ejemplo de código. Tenga en cuenta que los puntos suspensivos se mezclan con el fondo, pero no se mezclan entre sí.  
  
 ![Copia de origen](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 El ejemplo de código contiene esta instrucción:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Si desea que los puntos suspensivos para que se mezclan entre sí, así como con el fondo, cambie esa instrucción a lo siguiente:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 La siguiente ilustración muestra el resultado del código revisado.  
  
 ![Origen a través de](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Color.FromArgb%2A>
- [Líneas y rellenos con combinación alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
