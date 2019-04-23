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
ms.openlocfilehash: d4bf72998c798040451b814a7f0287bca65f5300
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073330"
---
# <a name="how-to-draw-text-with-gdi"></a>Procedimiento para dibujar texto con GDI
Con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método en el <xref:System.Windows.Forms.TextRenderer> (clase), puede tener acceso a [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funcionalidad para dibujar texto en un formulario o control. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] representación de texto normalmente ofrece un mejor rendimiento y a medida que más precisa del texto [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.TextRenderer.DrawText%2A> métodos de la <xref:System.Windows.Forms.TextRenderer> clase no se admiten para la impresión. Al imprimir, use siempre la <xref:System.Drawing.Graphics.DrawString%2A> métodos de la <xref:System.Drawing.Graphics> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo dibujar texto en varias líneas dentro de un rectángulo mediante el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Para representar texto con el <xref:System.Windows.Forms.TextRenderer> (clase), necesita un <xref:System.Drawing.IDeviceContext>, como un <xref:System.Drawing.Graphics> y un <xref:System.Drawing.Font>, una ubicación para dibujar el texto y el color en el que debe dibujarse. Si lo desea, puede especificar el texto con formato mediante el uso de la <xref:System.Windows.Forms.TextFormatFlags> enumeración.  
  
 Para obtener más información acerca de cómo obtener un <xref:System.Drawing.Graphics>, vea [Cómo: Crear objetos Graphics para dibujar](how-to-create-graphics-objects-for-drawing.md). Para obtener más información sobre cómo construir un <xref:System.Drawing.Font>, vea [Cómo: Construir fuentes y familias de fuentes](how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo de código anterior está diseñado para su uso con Windows Forms y requiere la <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- <xref:System.Drawing.Color>
- [Utilizar fuentes y texto](using-fonts-and-text.md)
