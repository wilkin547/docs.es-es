---
title: "C&#243;mo: Convertir colores de im&#225;genes | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], cambiar colores"
  - "colores de imagen [formularios Windows Forms]"
  - "imágenes [Windows Forms], cambiar colores"
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Convertir colores de im&#225;genes
Las conversiones agregan un valor a uno o a varios de los cuatro componentes de color.  En la siguiente tabla se recogen las entradas de matriz de color que representan conversiones.  
  
|Componente que se va a convertir|Entrada de la matriz|  
|--------------------------------------|--------------------------|  
|Red|\[4\]\[0\]|  
|Verde|\[4\]\[1\]|  
|Azul|\[4\]\[2\]|  
|Alfabética|\[4\]\[3\]|  
  
## Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir del archivo ColorBars.bmp.  A continuación, el código agrega 0,75 al componente rojo de cada píxel de la imagen.  La imagen original se dibuja al lado de la imagen transformada.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen transformada a la derecha.  
  
 ![Conversión de colores](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 En la siguiente tabla se recogen los vectores de color de las cuatro barras antes y después de la conversión del rojo.  Dado que el valor máximo de un componente de color es 1, el componente rojo de la segunda fila no varía.  Del mismo modo, el valor mínimo de un componente de color es 0.  
  
|Original|Conversión|  
|--------------|----------------|  
|Negro \(0, 0, 0, 1\)|\(0.75, 0, 0, 1\)|  
|Rojo \(1, 0, 0, 1\)|\(1, 0, 0, 1\)|  
|Verde \(0, 1, 0, 1\)|\(0.75, 1, 0, 1\)|  
|Azul \(0, 0, 1, 1\)|\(0.75, 0, 1, 1\)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  Reemplace `ColorBars.bmp`  por un nombre de archivo de imagen y una ruta de acceso que sean válidos en su sistema.  
  
## Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)