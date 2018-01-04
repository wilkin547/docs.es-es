---
title: "Cómo: Utilizar lápiz para dibujar líneas"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 156d7acbbf3f863e89ae2a5c303b2cf4140b3592
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Cómo: Utilizar lápiz para dibujar líneas
Para dibujar líneas, necesita un <xref:System.Drawing.Graphics> objeto y un <xref:System.Drawing.Pen> objeto. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawLine%2A> método y el <xref:System.Drawing.Pen> objeto almacena las características de la línea, como el color y ancho.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se dibuja una línea de (20, 10) a (300, 100). La primera instrucción se utiliza el <xref:System.Drawing.Pen.%23ctor%2A> constructor de clase para crear un lápiz de color negro. El argumento que se pasa a la <xref:System.Drawing.Pen.%23ctor%2A> constructor es un <xref:System.Drawing.Color> objeto creado con la <xref:System.Drawing.Color.FromArgb%2A> método. Los valores utilizados para crear el <xref:System.Drawing.Color> objeto: (255, 0, 0, 0), corresponden a los componentes alfabéticos, rojos, verde y azules del color. Estos valores definen un lápiz de color negro opaco.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Pen>  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Lápices, líneas y rectángulos en GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
