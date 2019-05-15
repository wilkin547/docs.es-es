---
title: Procedimiento para usar el modo de composición para controlar la combinación alfa
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590144"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Procedimiento para usar el modo de composición para controlar la combinación alfa
Puede haber ocasiones en que desee crear un mapa de bits fuera de la pantalla que tiene las siguientes características:  
  
- Colores tienen valores alfabéticos que son menos de 255.  
  
- Colores no son alfabéticos mezclan entre sí al crear el mapa de bits.  
  
- Cuando se muestra el mapa de bits terminado, los colores del mapa de bits son una combinación con los colores de fondo de la pantalla alfa.  
  
 Para crear un mapa de bits, construya un espacio en blanco <xref:System.Drawing.Bitmap> objeto y, a continuación, construya un <xref:System.Drawing.Graphics> objeto basado en ese mapa de bits. Establezca el modo de composición de la <xref:System.Drawing.Graphics> objeto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Graphics> objeto según un <xref:System.Drawing.Bitmap> objeto. El código usa el <xref:System.Drawing.Graphics> objeto junto con dos pinceles semitransparentes (alfa = 160) para pintar en el mapa de bits. El código rellena una elipse roja y una elipse verde utilizando los pinceles semitransparentes. La elipse verde superpone el rojo, pero no se mezcla con el color rojo, verde porque el modo de composición de la <xref:System.Drawing.Graphics> objeto se establece en <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 El código dibuja el mapa de bits en la pantalla dos veces: una vez en un fondo blanco y una vez en un fondo de varios colores. Los píxeles del mapa de bits que forman parte de las dos elipses tienen un componente alfa de 160, por lo que los puntos suspensivos se mezclan con los colores de fondo en la pantalla.  
  
 La siguiente ilustración muestra el resultado del ejemplo de código. Tenga en cuenta que los puntos suspensivos se mezclan con el fondo, pero no se mezclan entre sí.  
  
 ![Diagrama que muestra elipses se mezclan con el fondo, no entre sí.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 El ejemplo de código contiene esta instrucción:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Si desea que los puntos suspensivos para que se mezclan entre sí, así como con el fondo, cambie esa instrucción a lo siguiente:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 La siguiente ilustración muestra el resultado del código revisado.  
  
 ![Diagrama que muestra el botón de puntos suspensivos se mezcla entre sí y con el fondo.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Color.FromArgb%2A>
- [Líneas y rellenos con combinación alfa](alpha-blending-lines-and-fills.md)
