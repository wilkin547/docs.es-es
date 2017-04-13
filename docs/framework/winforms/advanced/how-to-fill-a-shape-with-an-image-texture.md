---
title: "C&#243;mo: Rellenar una forma con una textura de imagen | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], con textura"
  - "imágenes [Windows Forms], con pinceles"
  - "formas, relleno con imágenes"
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Rellenar una forma con una textura de imagen
Las formas cerradas se pueden rellenar con una textura utilizando las clases <xref:System.Drawing.Image> y <xref:System.Drawing.TextureBrush>.  
  
## Ejemplo  
 En el siguiente ejemplo se rellena una elipse con una imagen.  El código construye un objeto <xref:System.Drawing.Image> y, a continuación, pasa la dirección de ese objeto <xref:System.Drawing.Image> como argumento a un constructor <xref:System.Drawing.TextureBrush.%23ctor%2A>.  La tercera instrucción ajusta el tamaño de la imagen y la cuarta rellena la elipse con varias copias de la imagen con ese tamaño.  
  
 En el código siguiente, la propiedad <xref:System.Drawing.TextureBrush.Transform%2A> contiene la transformación que se aplica a la imagen antes de que se dibuje.  Imaginemos que la imagen original tiene un ancho de 640 píxeles y un alto de 480 píxeles.  La transformación encoge la imagen a 75×75 estableciendo los valores de tamaño horizontal y vertical.  
  
> [!NOTE]
>  En el ejemplo siguiente, el tamaño de la imagen es de 75×75 y el tamaño de la elipse es de 150×250.  Dado que la imagen es más pequeña que la elipse que se va a rellenar, la imagen se dispone en mosaico dentro de la elipse.  En una disposición en mosaico, la imagen se repite horizontal y verticalmente hasta alcanzar los límites de la forma.  Para obtener más información sobre la disposición en mosaico, vea [Cómo: Disponer una forma en mosaico con una imagen](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)