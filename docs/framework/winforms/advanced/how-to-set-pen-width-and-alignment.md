---
title: "C&#243;mo: Establecer el ancho y la alineaci&#243;n del l&#225;piz | Microsoft Docs"
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
  - "lápices, establecer alineación"
  - "lápices, establecer ancho"
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Establecer el ancho y la alineaci&#243;n del l&#225;piz
Cuando se crea un objeto <xref:System.Drawing.Pen>, se puede proporcionar al constructor el ancho del lápiz como uno de los argumentos.  También se puede cambiar el ancho del lápiz con la propiedad <xref:System.Drawing.Pen.Width%2A> de la clase <xref:System.Drawing.Pen>.  
  
 Una línea teórica tiene un ancho de 0.  Cuando se dibuja una línea que tiene 1 píxel de ancho, los píxeles están centrados en la línea teórica.  Si se dibuja una línea que tiene un ancho de más de un píxel, los píxeles están centrados en la línea teórica o aparecen a un lado de dicha línea.  Se puede establecer la propiedad de alineación del lápiz de un objeto <xref:System.Drawing.Pen> para determinar cómo se ubicarán los píxeles dibujados con ese lápiz en relación con las líneas teóricas.  
  
 Los valores <xref:System.Drawing.Drawing2D.PenAlignment>, <xref:System.Drawing.Drawing2D.PenAlignment> y <xref:System.Drawing.Drawing2D.PenAlignment> que aparecen en los ejemplos de código siguientes son miembros de la enumeración <xref:System.Drawing.Drawing2D.PenAlignment>.  
  
 En el ejemplo de código siguiente se dibuja una línea dos veces: una vez con un lápiz negro de ancho 1 y otra vez con un lápiz verde de ancho 10.  
  
### Para cambiar el ancho de un lápiz  
  
-   Establezca el valor de la propiedad <xref:System.Drawing.Pen.Alignment%2A> en <xref:System.Drawing.Drawing2D.PenAlignment> \(el valor predeterminado\) para especificar que los píxeles dibujados con el lápiz verde se centrarán en la línea teórica.  En la siguiente ilustración se muestra la línea resultante.  
  
     ![Plumas](../../../../docs/framework/winforms/advanced/media/pens1a.png "pens1A")  
  
     En el ejemplo de código siguiente se dibuja un rectángulo dos veces: una vez con un lápiz negro de ancho 1 y otra vez con un lápiz verde de ancho 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### Para cambiar la alineación de un lápiz  
  
-   Establezca el valor de la propiedad <xref:System.Drawing.Pen.Alignment%2A> en <xref:System.Drawing.Drawing2D.PenAlignment> para especificar que los píxeles dibujados con el lápiz verde se centrarán en el borde del rectángulo.  
  
     En la siguiente ilustración se muestra el rectángulo resultante.  
  
     ![Plumas](../../../../docs/framework/winforms/advanced/media/pens2.png "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### Para crear un lápiz de bajorrelieve  
  
-   La alineación del lápiz verde se puede cambiar modificando la tercera instrucción del ejemplo de código anterior de la siguiente manera:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Ahora, los píxeles de la línea verde ancha aparecen en la parte interior del rectángulo, tal como se muestra en la ilustración siguiente.  
  
     ![Plumas](../../../../docs/framework/winforms/advanced/media/pens3.png "pens3")  
  
## Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)