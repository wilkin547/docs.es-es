---
title: "C&#243;mo: Utilizar l&#225;piz para dibujar l&#237;neas | Microsoft Docs"
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
  - "líneas, dibujar"
  - "lápices, dibujar líneas"
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Utilizar l&#225;piz para dibujar l&#237;neas
Para dibujar líneas son necesarios un objeto <xref:System.Drawing.Graphics> y un objeto <xref:System.Drawing.Pen>.  El objeto <xref:System.Drawing.Graphics> proporciona el método <xref:System.Drawing.Graphics.DrawLine%2A>, y el objeto <xref:System.Drawing.Pen> almacena características de la línea, como el color y el ancho.  
  
## Ejemplo  
 En el siguiente ejemplo se dibuja una línea de \(20, 10\) a \(300, 100\).  En la primera instrucción se utiliza el constructor de la clase <xref:System.Drawing.Pen.%23ctor%2A> para crear un lápiz de color negro.  El argumento pasado al constructor <xref:System.Drawing.Pen.%23ctor%2A> es un objeto <xref:System.Drawing.Color> creado con el método <xref:System.Drawing.Color.FromArgb%2A>.  Los valores utilizados para crear el objeto <xref:System.Drawing.Color>, \(255, 0, 0, 0\), corresponden a los componentes alfa, rojo, verde y azul del color.  Estos valores definen un lápiz de color negro opaco.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 <xref:System.Drawing.Pen>   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Lápices, líneas y rectángulos en GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)