---
title: "C&#243;mo: Utilizar una matriz de colores para establecer valores alfa en im&#225;genes | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], con matrices de color para semitransparentes"
  - "imágenes [Windows Forms], con matrices de color para semitransparentes"
  - "matrices, valores alfa"
  - "transparencia, matrices de color"
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Utilizar una matriz de colores para establecer valores alfa en im&#225;genes
La clase <xref:System.Drawing.Bitmap> \(que se hereda de la clase <xref:System.Drawing.Image>\) y la clase <xref:System.Drawing.Imaging.ImageAttributes> proporcionan funcionalidad para obtener y establecer valores de píxeles.  La clase <xref:System.Drawing.Imaging.ImageAttributes> puede utilizarse para modificar los valores alfa de toda una imagen o se puede llamar al método <xref:System.Drawing.Bitmap.SetPixel%2A> de la clase <xref:System.Drawing.Bitmap> para modificar valores de píxeles individuales.  
  
## Ejemplo  
 La clase <xref:System.Drawing.Imaging.ImageAttributes> tiene muchas propiedades que se pueden utilizar para modificar las imágenes durante la representación.  En el ejemplo siguiente se utiliza un objeto <xref:System.Drawing.Imaging.ImageAttributes> para establecer todos los valores alfa en el 80 por ciento de lo que eran anteriormente.  Esto se hace inicializando una matriz de colores y estableciendo el valor de escala alfa de la matriz en 0.8.  La dirección de la matriz de colores se pasa al método <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> del objeto <xref:System.Drawing.Imaging.ImageAttributes> y el objeto <xref:System.Drawing.Imaging.ImageAttributes> se pasa al método <xref:System.Drawing.Graphics.DrawString%2A> del objeto <xref:System.Drawing.Graphics>.  
  
 Durante la representación, los valores alfa del mapa de bits se convierten al 80 por ciento de lo que eran anteriormente.  Esto produce una imagen que se mezcla con el fondo.  Tal como muestra la imagen siguiente, la imagen del mapa de bits aparece transparente y la línea negra sólida se puede ver a través de ella.  
  
 ![Combinación alfa usando una matriz](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 En el lugar donde la imagen está sobre la parte blanca del fondo, la imagen se ha mezclado con el color blanco.  En el lugar donde la imagen cruza la línea negra, la imagen se mezcla con el color negro.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Líneas y rellenos con mezcla alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)