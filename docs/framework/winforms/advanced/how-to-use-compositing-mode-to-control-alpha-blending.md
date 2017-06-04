---
title: "C&#243;mo: Utilizar el modo de composici&#243;n para controlar la mezcla alfa | Microsoft Docs"
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
  - "combinación alfa, componer"
  - "colores, combinación"
  - "colores, controlar transparencia"
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Utilizar el modo de composici&#243;n para controlar la mezcla alfa
Puede haber ocasiones en las que se desee crear un mapa de bits fuera de la pantalla con las siguientes características:  
  
-   Los colores tienen valores alfa menores que 255.  
  
-   Los colores no mezclan sus valores alfa cuando se crea el mapa de bits.  
  
-   Cuando se muestra el mapa de bits terminado, los colores del mapa de bits mezclan sus valores alfa con los colores de fondo del dispositivo de presentación.  
  
 Para crear dicho mapa de bits, construya un objeto <xref:System.Drawing.Bitmap> en blanco y, a continuación, construya un objeto <xref:System.Drawing.Graphics> basado en ese mapa de bits.  Establezca el modo de composición del objeto <xref:System.Drawing.Graphics> en <xref:System.Drawing.Drawing2D.CompositingMode?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un objeto <xref:System.Drawing.Graphics> basado en un objeto <xref:System.Drawing.Bitmap>.  El código utiliza el objeto <xref:System.Drawing.Graphics> junto con dos pinceles semitransparentes \(alfa \= 160\) para pintar en el mapa de bits.  El código rellena una elipse roja y otra verde utilizando los pinceles semitransparentes.  La elipse verde se superpone a la roja, pero el verde y el rojo no se mezclan porque el modo de composición del objeto <xref:System.Drawing.Graphics> está establecido en <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 El código dibuja dos veces el mapa de bits en la pantalla: una sobre un fondo blanco y otra sobre un fondo multicolor.  Los píxeles del mapa de bits que forman parte de las dos elipses tienen un componente alfa de 160, por lo que las elipses se mezclan con los colores de fondo de la pantalla.  
  
 En la siguiente ilustración se muestra el resultado del código de ejemplo.  Tenga en cuenta que las elipses se mezclan con el color de fondo, pero no se mezclan las elipses una con otra.  
  
 ![Copia del código fuente](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 El ejemplo de código contiene esta instrucción:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Si desea que las elipses se mezclen una con otra además de mezclarse con el fondo, cambie esa instrucción a:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 En la siguiente ilustración se muestra el resultado del código revisado.  
  
 ![Información de código de origen](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 <xref:System.Drawing.Color.FromArgb%2A>   
 [Líneas y rellenos con mezcla alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)