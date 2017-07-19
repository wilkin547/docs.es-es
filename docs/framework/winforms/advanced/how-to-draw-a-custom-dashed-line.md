---
title: "C&#243;mo: Dibujar una l&#237;nea discontinua personalizada | Microsoft Docs"
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
  - "líneas, personalizadas"
  - "líneas, con guión"
  - "líneas, dibujar"
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Dibujar una l&#237;nea discontinua personalizada
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona varios estilos de guión en la enumeración <xref:System.Drawing.Drawing2D.DashStyle>.  Si esos estilos de guión estándar no se ajustan a sus necesidades, puede crear un modelo de guión personalizado.  
  
## Ejemplo  
 Para dibujar una línea discontinua personalizada, ponga la longitud de los guiones y de los espacios en una matriz, y asigne la matriz como valor de la propiedad <xref:System.Drawing.Pen.DashPattern%2A> de un objeto <xref:System.Drawing.Pen>.  En el ejemplo siguiente se dibuja una línea discontinua personalizada basada en la matriz  `{5, 2, 15, 4}`.  Si se multiplican los elementos de la matriz por el ancho de lápiz 5, se obtiene `{25, 10, 75, 20}`.  Los guiones que se muestran alternan las longitudes de 25 y 75 y los espacios alternan las longitudes de 10 y 20.  
  
 En la siguiente ilustración se muestra la línea discontinua resultante.  Tenga en cuenta que el último guión debe tener menos de 25 unidades para que la línea pueda terminar en \(405, 5\).  
  
 ![Plumas](../../../../docs/framework/winforms/advanced/media/pens6.png "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## Compilar el código  
 Cree un Windows Form y controle el evento <xref:System.Windows.Forms.Control.Paint> del formulario.  Pegue el código anterior en el controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)