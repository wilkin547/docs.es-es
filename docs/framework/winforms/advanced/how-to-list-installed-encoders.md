---
title: "C&#243;mo: Enumerar los codificadores instalados | Microsoft Docs"
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
  - "códecs de imagen, mostrar"
  - "codificadores de imágenes, mostrar"
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Enumerar los codificadores instalados
Puede enumerar los codificadores de imágenes disponibles en un equipo, para determinar si la aplicación puede guardar en un formato de archivo de imagen determinado.  La clase <xref:System.Drawing.Imaging.ImageCodecInfo> proporciona los métodos estáticos <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> para que pueda determinar qué codificadores de imágenes están disponibles.  <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> devuelve una matriz de objetos <xref:System.Drawing.Imaging.ImageCodecInfo>.  
  
## Ejemplo  
 El ejemplo de código siguiente genera la lista de los codificadores instalados y sus valores de propiedad.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de formularios Windows Forms.  
  
-   Un argumento <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Enumerar los descodificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)   
 [Usar codificadores y descodificadores de imagen en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)