---
title: "C&#243;mo: Recortar y ajustar la escala de las im&#225;genes | Microsoft Docs"
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
  - "imágenes [Windows Forms], recortar"
  - "imágenes [Windows Forms], ajustar la escala"
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Recortar y ajustar la escala de las im&#225;genes
La clase <xref:System.Drawing.Graphics> proporciona varios métodos <xref:System.Drawing.Graphics.DrawImage%2A>, algunos de los cuales tienen parámetros de rectángulo de origen y de destino que se pueden utilizar para recortar y ajustar la escala de las imágenes.  
  
## Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Image> a partir del archivo de disco Apple.gif.  Con este código se dibuja toda la imagen de la manzana con su tamaño original.  A continuación, el código llama al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics> para dibujar una parte de la imagen de la manzana en un rectángulo de destino de mayor tamaño que la imagen original.  
  
 El método <xref:System.Drawing.Graphics.DrawImage%2A> determina qué parte de la manzana se va a dibujar observando el rectángulo de origen, especificado por los argumentos tercero, cuarto, quinto y sexto.  En este caso, la manzana se recorta a un 75 por ciento de su ancho y un 75 por ciento de su alto.  
  
 El método <xref:System.Drawing.Graphics.DrawImage%2A> determina dónde se va a dibujar la manzana recortada y con qué tamaño observando el rectángulo de destino, especificado por el segundo argumento.  En este caso, el rectángulo de destino es un 30 por ciento más ancho y un 30 por ciento más alto que la imagen original.  
  
 En la imagen siguiente se muestran la manzana original y la manzana recortada con escala ajustada.  
  
 ![Recortar y ajustar la escala](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  Asegúrese de reemplazar `Apple.gif` por un nombre de archivo de imagen y una ruta de acceso que sean válidos en su sistema.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)