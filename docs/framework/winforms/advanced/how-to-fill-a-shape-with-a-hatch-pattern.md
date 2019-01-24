---
title: Procedimiento Rellenar una forma con un patrón de trama
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: 3fb5b443aac710a5490a238e2a571ed899dec463
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512403"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Procedimiento Rellenar una forma con un patrón de trama
Un patrón de trama está formado por dos colores: uno para el fondo y otro para las líneas que forman el modelo sobre el fondo. Para rellenar una forma cerrada con un patrón de trama, utilice un <xref:System.Drawing.Drawing2D.HatchBrush> objeto. El ejemplo siguiente muestra cómo rellenar una elipse con un patrón de trama:  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor toma tres argumentos: el estilo de sombreado, el color de la línea de trama y el color del fondo. El argumento de estilo de trama puede ser cualquier valor de la <xref:System.Drawing.Drawing2D.HatchStyle> enumeración. Hay más de cincuenta elementos en el <xref:System.Drawing.Drawing2D.HatchStyle> enumeración; algunos de estos elementos se muestran en la lista siguiente:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 La siguiente ilustración muestra la elipse rellena.  
  
 ![El patrón de trama](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también
- [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
