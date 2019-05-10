---
title: Procedimiento para dibujar texto en un formulario Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: dc99a863765cd617c2ab4a636286f42f5e8daf79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626190"
---
# <a name="how-to-draw-text-on-a-windows-form"></a>Procedimiento para dibujar texto en un formulario Windows Forms
En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> para dibujar texto en un formulario. Como alternativa, puede usar <xref:System.Windows.Forms.TextRenderer> para dibujar texto en un formulario. Para obtener más información, vea [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 No se puede llamar a la <xref:System.Drawing.Graphics.DrawString%2A> método en el <xref:System.Windows.Forms.Form.Load> controlador de eventos. No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño u ocultado por otro formulario. Para que el contenido automáticamente volver a dibujar, se debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- La fuente Arial no está instalada.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)
