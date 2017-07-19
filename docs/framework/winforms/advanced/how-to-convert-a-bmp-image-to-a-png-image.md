---
title: "C&#243;mo: Convertir una imagen BMP en una imagen PNG | Microsoft Docs"
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
  - "imágenes BMP, convertir a PNG"
  - "formatos de imagen, convertir en"
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Convertir una imagen BMP en una imagen PNG
A menudo, deseará convertir de un formato a otro.  Puede hacer esta conversión fácilmente llamando al método <xref:System.Drawing.Image.Save%2A> de la clase <xref:System.Drawing.Image> y especificando <xref:System.Drawing.Imaging.ImageFormat> para el formato de archivo de imagen deseado.  
  
## Ejemplo  
 En el ejemplo siguiente, se carga una imagen BMP de un tipo y se guarda la imagen en formato PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de Windows Forms.  
  
-   Una referencia al espacio de nombres `System.Drawing.Imaging`.  
  
## Vea también  
 [Cómo: Enumerar los codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Usar codificadores y descodificadores de imagen en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)   
 [Tipos de mapas de bits](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)