---
title: Procedimiento para rellenar una forma con un patrón de sombreado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: f5399c4151b335090f4b93be041375b8c2781afa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781354"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Procedimiento para rellenar una forma con un patrón de sombreado
Un patrón de trama está formado por dos colores: uno para el fondo y otro para las líneas que forman el modelo sobre el fondo. Para rellenar una forma cerrada con un patrón de trama, utilice un <xref:System.Drawing.Drawing2D.HatchBrush> objeto. El ejemplo siguiente muestra cómo rellenar una elipse con un patrón de trama:  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor toma tres argumentos: el estilo de sombreado, el color de la línea de trama y el color del fondo. El argumento de estilo de trama puede ser cualquier valor de la <xref:System.Drawing.Drawing2D.HatchStyle> enumeración. Hay más de cincuenta elementos en el <xref:System.Drawing.Drawing2D.HatchStyle> enumeración; algunos de estos elementos se muestran en la lista siguiente:  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 La siguiente ilustración muestra la elipse rellena.  
  
 ![El patrón de trama](./media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también

- [Utilizar un pincel para rellenar formas](using-a-brush-to-fill-shapes.md)
