---
title: Procedimiento para dibujar texto con GDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956539"
---
# <a name="how-to-draw-text-with-gdi"></a>Procedimiento para dibujar texto con GDI
Con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método en la <xref:System.Windows.Forms.TextRenderer> clase, puede tener acceso a la funcionalidad de GDI para dibujar texto en un formulario o control. La representación de texto GDI suele ofrecer un mejor rendimiento y una medida de texto más precisa que GDI+.  
  
> [!NOTE]
> No <xref:System.Windows.Forms.TextRenderer.DrawText%2A> se admiten <xref:System.Windows.Forms.TextRenderer> los métodos de la clase para imprimir. Al imprimir, use siempre los <xref:System.Drawing.Graphics.DrawString%2A> métodos de la <xref:System.Drawing.Graphics> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo dibujar texto en varias líneas dentro de un <xref:System.Windows.Forms.TextRenderer.DrawText%2A> rectángulo mediante el método.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Para representar texto con la <xref:System.Windows.Forms.TextRenderer> clase, se necesita un <xref:System.Drawing.IDeviceContext>, <xref:System.Drawing.Font>como <xref:System.Drawing.Graphics> y, una ubicación para dibujar el texto y el color en el que se debe dibujar. Opcionalmente, puede especificar el formato de texto mediante la <xref:System.Windows.Forms.TextFormatFlags> enumeración.  
  
 Para obtener más información acerca de <xref:System.Drawing.Graphics>cómo obtener [una, consulte Cómo: Crear objetos gráficos para dibujar](how-to-create-graphics-objects-for-drawing.md). Para obtener más información acerca de cómo <xref:System.Drawing.Font>crear un [, consulte Cómo: Construya familias y fuentes](how-to-construct-font-families-and-fonts.md)de fuentes.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [Utilizar fuentes y texto](using-fonts-and-text.md)
