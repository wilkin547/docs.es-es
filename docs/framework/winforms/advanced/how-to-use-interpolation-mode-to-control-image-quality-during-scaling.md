---
title: "C&#243;mo: Utilizar el modo de interpolaci&#243;n para controlar la calidad de imagen durante el ajuste de tama&#241;o | Microsoft Docs"
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
  - "imágenes [Windows Forms], controlar calidad"
  - "imágenes [Windows Forms], ajustar la escala"
  - "modo de interpolación, controlar calidad de imagen"
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Utilizar el modo de interpolaci&#243;n para controlar la calidad de imagen durante el ajuste de tama&#241;o
El modo de interpolación de un objeto <xref:System.Drawing.Graphics> influye en la manera en que [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ajusta el tamaño \(amplía y contrae\) de las imágenes.  La enumeración <xref:System.Drawing.Drawing2D.InterpolationMode> define varios modos de interpolación, algunos de los cuales se muestran en la siguiente lista:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
 Para ajustar una imagen, cada píxel de la imagen original se debe asignar a un grupo de píxeles de la imagen más grande.  Para encoger una imagen, se deben asignar grupos de píxeles de la imagen original a píxeles únicos de la imagen más pequeña.  La efectividad de los algoritmos que realizan estas asignaciones determina la calidad de una imagen cuyo tamaño se ha ajustado.  Los algoritmos que producen imágenes con el tamaño ajustado de mayor calidad suelen requerir más tiempo de procesamiento.  En la lista anterior, <xref:System.Drawing.Drawing2D.InterpolationMode> es el modo de menor calidad y <xref:System.Drawing.Drawing2D.InterpolationMode> es el modo de mayor calidad.  
  
 Para establecer el modo de interpolación, asigne uno de los miembros de la enumeración <xref:System.Drawing.Drawing2D.InterpolationMode> a la propiedad <xref:System.Drawing.Graphics.InterpolationMode%2A> de un objeto <xref:System.Drawing.Graphics>.  
  
## Ejemplo  
 En el ejemplo siguiente se dibuja una imagen que posteriormente se encoge con tres modos de interpolación distintos:  
  
 En la ilustración siguiente se muestran la imagen original y las tres imágenes más pequeñas.  
  
 ![Imagen con diversos valores de interpolación](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)