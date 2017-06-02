---
title: "C&#243;mo: Determinar los par&#225;metros admitidos por un codificador | Microsoft Docs"
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
  - "parámetros de codificador, determinación compatible"
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Determinar los par&#225;metros admitidos por un codificador
Puede ajustar parámetros de imagen como la calidad y el nivel de compresión, pero debe conocer qué parámetros admite un codificador de imágenes determinado.  La clase <xref:System.Drawing.Image> proporciona el método <xref:System.Drawing.Image.GetEncoderParameterList%2A> para que pueda determinar qué parámetros de imagen se admiten para un codificador determinado.  El codificador se especifica con un GUID.  El método <xref:System.Drawing.Image.GetEncoderParameterList%2A> devuelve una matriz de objetos <xref:System.Drawing.Imaging.EncoderParameter>.  
  
## Ejemplo  
 El siguiente código de ejemplo genera los parámetros compatibles para el codificador de JPEG.  Utilice la lista de categorías de parámetro y GUID asociados en la información general de la clase <xref:System.Drawing.Imaging.Encoder> para determinar la categoría de cada parámetro.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de formularios Windows Forms.  
  
-   Un argumento <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Enumerar los codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Tipos de mapas de bits](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [Usar codificadores y descodificadores de imagen en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)