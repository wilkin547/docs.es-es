---
title: Filtrar Rellenar figuras abiertas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: c7d193fdad554048ecd0f2cca5a83cfccbc2a403
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654086"
---
# <a name="how-to-fill-open-figures"></a>Filtrar Rellenar figuras abiertas
Puede rellenar una ruta de acceso pasando un <xref:System.Drawing.Drawing2D.GraphicsPath> de objeto para el <xref:System.Drawing.Graphics.FillPath%2A> método. El <xref:System.Drawing.Graphics.FillPath%2A> método rellena la ruta de acceso según el modo de relleno (alternativo o de espirales) establecido para la ruta de acceso. Si la ruta de acceso tiene figuras abiertas, se rellena la ruta de acceso como si se cerraron esas cifras. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] cierra una figura, dibuje una línea recta desde su punto final para el punto de partida.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea una ruta de acceso que tiene una figura abierta (un arco) y una figura cerrada (una elipse). El <xref:System.Drawing.Graphics.FillPath%2A> método rellena la ruta de acceso según el modo de relleno predeterminado, que es <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 La siguiente ilustración muestra el resultado del código de ejemplo. Tenga en cuenta que se rellena la ruta de acceso (según <xref:System.Drawing.Drawing2D.FillMode.Alternate>) como si se cerraron la figura abierta mediante una línea recta desde su punto final para el punto de partida.  
  
 ![Diagrama que muestra la salida del método FillPath](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Trazados de gráficos en GDI+](graphics-paths-in-gdi.md)
