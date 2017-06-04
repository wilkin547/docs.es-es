---
title: "C&#243;mo: Cargar y mostrar metarchivos | Microsoft Docs"
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
  - "ejemplos [Windows Forms], metarchivos"
  - "metarchivos, mostrar"
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Cargar y mostrar metarchivos
La clase <xref:System.Drawing.Imaging.Metafile>, que se hereda de la clase <xref:System.Drawing.Image>, proporciona métodos para registrar, mostrar y examinar imágenes vectoriales.  
  
## Ejemplo  
 Para mostrar una imagen vectorial \(metarchivo\) en la pantalla, son necesarios un objeto <xref:System.Drawing.Imaging.Metafile> y un objeto <xref:System.Drawing.Graphics>.  Pase el nombre de un archivo \(o una secuencia\) a un constructor <xref:System.Drawing.Imaging.Metafile>.  Después de haber creado un objeto <xref:System.Drawing.Imaging.Metafile>, pase el objeto <xref:System.Drawing.Imaging.Metafile> al método <xref:System.Drawing.Graphics.DrawImage%2A> de un objeto <xref:System.Drawing.Graphics>.  
  
 En el ejemplo siguiente se crea un objeto <xref:System.Drawing.Imaging.Metafile> a partir de un archivo EMF \(metarchivo mejorado\) y, a continuación, se dibuja la imagen con la esquina superior izquierda en \(60, 10\):  
  
 En la siguiente ilustración se muestra el metarchivo dibujado en la ubicación especificada.  
  
 ![Posición de la imagen](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## Vea también  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)