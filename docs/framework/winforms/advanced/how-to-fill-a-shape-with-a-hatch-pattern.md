---
title: 'Cómo: Rellenar una forma con un patrón de trama'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320051"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Cómo: Rellenar una forma con un patrón de trama
Un patrón de trama se realiza a partir de dos colores: uno para el fondo y otro para las líneas que forman el patrón en el fondo. Para rellenar una forma cerrada con un patrón de trama, use un objeto <xref:System.Drawing.Drawing2D.HatchBrush>. En el ejemplo siguiente se muestra cómo rellenar una elipse con un patrón de trama:  
  
## <a name="example"></a>Ejemplo  
 El constructor <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> toma tres argumentos: el estilo de trama, el color de la línea de sombreado y el color del fondo. El argumento de estilo de trama puede ser cualquier valor de la enumeración <xref:System.Drawing.Drawing2D.HatchStyle>. Hay más de 50 elementos en la enumeración <xref:System.Drawing.Drawing2D.HatchStyle>; algunos de esos elementos se muestran en la lista siguiente:  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 En la ilustración siguiente se muestra la elipse rellenada.  
  
  ![Captura de pantalla de la apariencia de una elipse con un patrón de trama.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel para rellenar formas](using-a-brush-to-fill-shapes.md)
