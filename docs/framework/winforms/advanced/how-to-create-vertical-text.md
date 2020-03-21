---
title: 'Cómo: Crear texto vertical'
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
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182562"
---
# <a name="how-to-create-vertical-text"></a>Cómo: Crear texto vertical
Puede utilizar <xref:System.Drawing.StringFormat> un objeto para especificar que el texto se dibuje verticalmente en lugar de horizontalmente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente <xref:System.Drawing.StringFormatFlags.DirectionVertical> se <xref:System.Drawing.StringFormat.FormatFlags%2A> asigna <xref:System.Drawing.StringFormat> el valor a la propiedad de un objeto. Ese <xref:System.Drawing.StringFormat> objeto se <xref:System.Drawing.Graphics.DrawString%2A> pasa al <xref:System.Drawing.Graphics> método de la clase. El <xref:System.Drawing.StringFormatFlags.DirectionVertical> valor es un <xref:System.Drawing.StringFormatFlags> miembro de la enumeración.  
  
 La siguiente ilustración muestra el texto vertical:
  
 ![Gráfico que muestra el texto de fuente vertical.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- El ejemplo anterior está diseñado para su uso <xref:System.Windows.Forms.PaintEventArgs> `e` con formularios Windows <xref:System.Windows.Forms.PaintEventHandler>Forms y requiere , que es un parámetro de .  
  
## <a name="see-also"></a>Consulte también

- [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)
