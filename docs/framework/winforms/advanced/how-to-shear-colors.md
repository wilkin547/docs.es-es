---
title: "C&#243;mo: Recortar colores | Microsoft Docs"
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
  - "colores, transformación"
  - "colores, transformar con matrices de colores"
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Recortar colores
El recorte aumenta o disminuye un componente de color en una cantidad proporcional a otro componente de color.  Pongamos, por ejemplo, la transformación en la que el componente rojo se incrementa en la mitad del valor del componente azul.  Con dicha transformación, el color \(0.2, 0.5, 1\) se convertiría en \(0.7, 0.5, 1\).  El nuevo componente rojo es 0,2 \+ \(1\/2\)\(1\) \= 0,7.  
  
## Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir del archivo ColorBars4.bmp.  A continuación, el código aplica la transformación de recorte descrita en el párrafo anterior a cada píxel de la imagen.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen sesgada a la derecha.  
  
 ![Sesgar colores](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 La siguiente tabla recoge los vectores de color de las cuatro barras antes y después de la transformación de recorte.  
  
|Original|Recorte|  
|--------------|-------------|  
|\(0, 0, 1, 1\)|\(0.5, 0, 1, 1\)|  
|\(0.5, 1, 0.5, 1\)|\(0.75, 1, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(1, 1, 0, 1\)|  
|\(0.4, 0.4, 0.4, 1\)|\(0.6, 0.4, 0.4, 1\)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  Reemplace `ColorBars.bmp` por un nombre de imagen y una ruta de acceso válidos en el sistema.  
  
## Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)