---
title: Filtrar para crear texto vertical
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 75f5d8faa4dc4b7e022cd6de2e6db49f4fa9030c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190228"
---
# <a name="how-to-create-vertical-text"></a>Filtrar para crear texto vertical
Puede usar un <xref:System.Drawing.StringFormat> objeto para especificar que se dibuja el texto verticalmente en lugar de horizontalmente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se asigna el valor <xref:System.Drawing.StringFormatFlags.DirectionVertical> a la <xref:System.Drawing.StringFormat.FormatFlags%2A> propiedad de un <xref:System.Drawing.StringFormat> objeto. Que <xref:System.Drawing.StringFormat> objeto se pasa a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase. El valor <xref:System.Drawing.StringFormatFlags.DirectionVertical> es un miembro de la <xref:System.Drawing.StringFormatFlags> enumeración.  
  
 La siguiente ilustración muestra el texto vertical: 
  
 ![Gráfico que muestra el texto de una fuente vertical.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e` , que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Filtrar para dibujar texto con GDI](how-to-draw-text-with-gdi.md)
