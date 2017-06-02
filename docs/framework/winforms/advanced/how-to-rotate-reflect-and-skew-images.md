---
title: "C&#243;mo: Girar, reflejar y sesgar im&#225;genes | Microsoft Docs"
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
  - "imágenes [Windows Forms], reflejar"
  - "imágenes [Windows Forms], rotar"
  - "imágenes [Windows Forms], inclinación"
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Girar, reflejar y sesgar im&#225;genes
Las imágenes se pueden rotar, reflejar y sesgar especificando puntos de destino para las esquinas superior izquierda, superior derecha e inferior izquierda de la imagen original.  Los tres puntos de destino determinan una transformación afín que asigna la imagen rectangular original a un paralelogramo.  
  
## Ejemplo  
 Por ejemplo, supongamos que la imagen original es un rectángulo con la esquina superior izquierda en \(0, 0\), la esquina superior derecha en \(100, 0\) y la esquina inferior izquierda en \(0, 50\).  Supongamos ahora que se asignan esos tres puntos a puntos de destino de la siguiente manera:  
  
|Punto original|Punto de destino|  
|--------------------|----------------------|  
|Superior izquierdo \(0, 0\)|\(200, 20\)|  
|Superior derecho \(100, 0\)|\(110, 100\)|  
|Inferior izquierdo \(0, 50\)|\(250, 30\)|  
  
 En la ilustración siguiente se muestran la imagen original y la imagen asignada al paralelogramo.  La imagen original se ha sesgado, reflejado, rotado y trasladado.  El eje x situado a lo largo del borde superior de la imagen original se asigna a la línea que va de \(200, 20\) a \(110, 100\).  El eje y situado a lo largo del borde izquierdo de la imagen original se asigna a la línea que va de \(200, 20\) a \(250, 30\).  
  
 ![Franjas](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 La siguiente ilustración muestra una transformación similar aplicada a una imagen fotográfica.  
  
 ![Climber transformado](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 La siguiente ilustración muestra una transformación similar aplicada a un metarchivo.  
  
 ![Metarchivo transformado](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 En el ejemplo siguiente se producen las imágenes mostradas en la primera ilustración.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  Asegúrese de reemplazar `Stripes.bmp` por la ruta de acceso a una imagen que sea válida en su sistema.  
  
## Vea también  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)