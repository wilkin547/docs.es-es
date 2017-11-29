---
title: "Cómo: Rellenar figuras abiertas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a8a2d5a13cac97063bf2a04969928c859a5954d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-fill-open-figures"></a>Cómo: Rellenar figuras abiertas
Una ruta de acceso se puede rellenar pasando un <xref:System.Drawing.Drawing2D.GraphicsPath> el objeto a la <xref:System.Drawing.Graphics.FillPath%2A> método. El <xref:System.Drawing.Graphics.FillPath%2A> método rellena el trazado según el modo de relleno (alternativo o generación) establecido actualmente para la ruta de acceso. Si la ruta de acceso tiene figuras abiertas, la ruta de acceso se rellena como si esas figuras estuvieran cerradas. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]cierra una figura dibujando una línea recta desde su punto final hasta su punto inicial.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una ruta de acceso que tiene una figura abierta (un arco) y una figura cerrada (una elipse). El <xref:System.Drawing.Graphics.FillPath%2A> método rellena el trazado según el modo de relleno predeterminado, que es <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 En la siguiente ilustración muestra el resultado del código de ejemplo. Tenga en cuenta que la ruta de acceso se rellena (según <xref:System.Drawing.Drawing2D.FillMode.Alternate>) como si la figura abierta estuviera cerrada con una línea recta desde su punto final hasta su punto inicial.  
  
 ![Rellenar trayecto abierto](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Trazados de gráficos en GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
