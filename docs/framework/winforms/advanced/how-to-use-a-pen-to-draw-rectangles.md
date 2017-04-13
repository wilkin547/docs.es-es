---
title: "C&#243;mo: Utilizar l&#225;piz para dibujar rect&#225;ngulos | Microsoft Docs"
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
  - "lápices, dibujar rectángulos"
  - "rectángulos, dibujar"
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Utilizar l&#225;piz para dibujar rect&#225;ngulos
Para dibujar rectángulos son necesarios un objeto <xref:System.Drawing.Graphics> y un objeto <xref:System.Drawing.Pen>.  El objeto <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawRectangle%2A>, y el objeto <xref:System.Drawing.Pen> almacena características de la línea, como el color y el ancho.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja un rectángulo con la esquina superior izquierda en \(10, 10\).  El rectángulo tiene un ancho de 100 y un alto de 50.  El segundo argumento pasado al constructor <xref:System.Drawing.Pen.%23ctor%2A> indica que el ancho del lápiz es 5 píxeles.  
  
 Cuando se dibuja el rectángulo, el lápiz está centrado en el límite del rectángulo.  Puesto que el ancho del lápiz es 5, los laterales del rectángulo tienen un ancho de 5 píxeles, de manera que 1 píxel se dibuja en el límite mismo, 2 píxeles se dibujan en la parte interior y 2 en la parte exterior.  Para obtener más detalles sobre la alineación del lápiz, vea [Cómo: Establecer el ancho y la alineación del lápiz](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).  
  
 En la siguiente ilustración se muestra el rectángulo resultante.  Las líneas de puntos muestran el lugar donde se hubiera dibujado el rectángulo si el ancho del lápiz fuera de un píxel.  La vista ampliada de la esquina superior izquierda del rectángulo muestra que las líneas negras gruesas están centradas sobre dichas líneas de puntos.  
  
 ![Plumas](../../../../docs/framework/winforms/advanced/media/pens1.png "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)