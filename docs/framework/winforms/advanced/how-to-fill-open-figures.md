---
title: Filtrar para rellenar figuras abiertas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: addcf959e429974b9306353abb743bb2bb3114e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174569"
---
# <a name="how-to-fill-open-figures"></a>Filtrar para rellenar figuras abiertas
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
