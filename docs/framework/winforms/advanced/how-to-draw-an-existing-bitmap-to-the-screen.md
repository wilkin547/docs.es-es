---
title: "C&#243;mo: Dibujar un mapa de bits existente en la pantalla | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], mostrar en Windows Forms"
  - "mapas de bits [Windows Forms], cargar en aplicaciones de formularios Windows Forms"
  - "imágenes [Windows Forms], mostrar en Windows Forms"
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Dibujar un mapa de bits existente en la pantalla
Puede dibujar con facilidad una imagen existente en la pantalla.  Primero necesita crear un objeto <xref:System.Drawing.Bitmap> utilizando el constructor de mapa de bits que toma un nombre de archivo, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.  Este constructor acepta imágenes con distintos formatos de archivo, incluidos BMP, GIF, JPEG, PNG y TIFF.  Después de haber creado el objeto <xref:System.Drawing.Bitmap>, pase el objeto <xref:System.Drawing.Bitmap> al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un objeto <xref:System.Drawing.Bitmap> a partir de un archivo JPEG y, a continuación, se dibuja el mapa de bits con la esquina superior izquierda en \(60, 10\):  
  
 En la siguiente ilustración se muestra el mapa de bits dibujado en la ubicación especificada.  
  
 ![Posición de la imagen](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)