---
title: "C&#243;mo: Rotar colores | Microsoft Docs"
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
  - "colores, rotar"
  - "ejemplos [Windows Forms], rotar colores"
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Rotar colores
La rotación en un espacio de color cuatridimensional es difícil de visualizar.  Para poder ver la rotación fácilmente, se ha decidido mantener uno de los componentes de color fijo.  Supongamos que se decide fijar el componente alfa en 1 \(completamente opaco\).  Entonces se podrá ver un espacio de color tridimensional con los ejes rojo, verde y azul como se muestra en la siguiente ilustración.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Los colores se pueden considerar como puntos en un espacio tridimensional.  Por ejemplo, el punto \(1, 0, 0\) en un espacio representa el color rojo, mientras que el punto \(0, 1, 0\) en un espacio representa el color verde.  
  
 En la siguiente ilustración se muestra el resultado al rotar el color \(1, 0, 0\) en un ángulo de 60 grados en el plano Rojo\-Verde.  La rotación en un plano paralelo al plano Rojo\-Verde puede considerarse como una rotación sobre el eje azul.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 En la siguiente ilustración se muestra cómo inicializar una matriz de color para realizar rotaciones sobre cada uno de los tres ejes de coordenadas \(rojo, verde, azul\).  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## Ejemplo  
 En el siguiente ejemplo se toma una imagen de un solo color \(1, 0, 0,6\) y se aplica una rotación de 60 grados sobre el eje azul.  El ángulo de rotación se trazará en un plano paralelo al plano rojo\-verde.  
  
 En la siguiente ilustración se muestra la imagen original a la izquierda y la imagen con rotación de colores a la derecha.  
  
 ![Rotar colores](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 En la siguiente ilustración se muestra una visualización de la rotación de color realizada en el siguiente código.  
  
 ![Cambio de color](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  Reemplace `RotationInput.bmp` por un nombre de archivo de imagen y una ruta de acceso válidos en el sistema.  
  
## Vea también  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Cambiar el color de las imágenes](../../../../docs/framework/winforms/advanced/recoloring-images.md)