---
title: "Cómo: Unir líneas"
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
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d12cc7b4b4c878ec812190fd56a1face64118ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-join-lines"></a>Cómo: Unir líneas
Una unión de líneas es el área común que está formado por dos líneas cuyos extremos se encuentran o se superponen. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]proporciona tres estilos de unión de línea: ángulo, bisel y redondo. Estilo de unión de línea es una propiedad de la <xref:System.Drawing.Pen> clase. Cuando se especifica un estilo de unión de línea para un <xref:System.Drawing.Pen> objeto, que se aplicará a todas las líneas conectadas en cualquier estilo de unión <xref:System.Drawing.Drawing2D.GraphicsPath> objeto dibujado con ese lápiz.  
  
 La ilustración siguiente muestra los resultados del ejemplo de unión de línea biselada.  
  
 ![Lápices](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>Ejemplo  
 Puede especificar el estilo de unión de línea mediante la <xref:System.Drawing.Pen.LineJoin%2A> propiedad de la <xref:System.Drawing.Pen> clase. En el ejemplo se muestra una unión de línea biselada entre una línea horizontal y una línea vertical. En el código siguiente, el valor <xref:System.Drawing.Drawing2D.LineJoin.Bevel> asignado a la <xref:System.Drawing.Pen.LineJoin%2A> propiedad es un miembro de la <xref:System.Drawing.Drawing2D.LineJoin> enumeración. Los demás miembros de la <xref:System.Drawing.Drawing2D.LineJoin> enumeración son <xref:System.Drawing.Drawing2D.LineJoin.Miter> y <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
