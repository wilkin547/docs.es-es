---
title: "C&#243;mo: Enumerar los descodificadores instalados | Microsoft Docs"
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
  - "descodificadores de imágenes, mostrar"
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Enumerar los descodificadores instalados
Puede enumerar los descodificadores de imágenes disponibles en un equipo, para determinar si la aplicación puede leer un formato de archivo de imagen determinado.  La clase <xref:System.Drawing.Imaging.ImageCodecInfo> proporciona los métodos estáticos <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> para que pueda determinar qué descodificadores de imágenes están disponibles.  <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> devuelve una matriz de objetos <xref:System.Drawing.Imaging.ImageCodecInfo>.  
  
## Ejemplo  
 El ejemplo de código siguiente genera la lista de los descodificadores instalados y sus valores de propiedad.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de formularios Windows Forms.  
  
-   Un argumento <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Enumerar los codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)   
 [Usar codificadores y descodificadores de imagen en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)