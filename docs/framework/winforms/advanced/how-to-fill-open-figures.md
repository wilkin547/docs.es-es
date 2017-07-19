---
title: "C&#243;mo: Rellenar figuras abiertas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "figuras, rellenar"
  - "abrir figuras, rellenar"
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Rellenar figuras abiertas
Se puede rellenar un trazado si se pasa un objeto <xref:System.Drawing.Drawing2D.GraphicsPath> al método <xref:System.Drawing.Graphics.FillPath%2A>.  El método <xref:System.Drawing.Graphics.FillPath%2A> rellena el trazado según el modo de relleno \(alternativo o de espirales\) establecido en la actualidad para el trazado.  Si el trazado tiene figuras abiertas, se rellenará como si esas figuras fueran cerradas.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] cierra una figura dibujando una línea recta desde su extremo hasta su punto inicial.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un trazado que tiene una figura abierta \(un arco\) y otra cerrada \(una elipse\).  El método <xref:System.Drawing.Graphics.FillPath%2A> rellena el trazado según el modo de relleno predeterminado, que es <xref:System.Drawing.Drawing2D.FillMode>.  
  
 En la siguiente ilustración se muestra el resultado del código de ejemplo.  Observe que el trazado se rellena \(según el modo <xref:System.Drawing.Drawing2D.FillMode>\) como si la figura abierta estuviera cerrada con una línea recta desde su extremo hasta su punto inicial.  
  
 ![Rellenar trayecto abierto](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [Trazados de gráficos en GDI\+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)