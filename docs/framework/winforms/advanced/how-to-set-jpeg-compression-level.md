---
title: "C&#243;mo: Establecer el nivel de compresi&#243;n de im&#225;genes JPEG | Microsoft Docs"
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
  - "imágenes [Windows Forms], cambiar parámetros de codificadores"
  - "imágenes JPEG, establecer nivel de calidad"
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Establecer el nivel de compresi&#243;n de im&#225;genes JPEG
Puede modificar los parámetros de una imagen al guardar la imagen en disco para minimizar el tamaño de archivo o mejorar su calidad.  Puede ajustar la calidad de una imagen JPEG modificando su nivel de compresión.  Para especificar el nivel de compresión al guardar una imagen JPEG, debe crear un objeto <xref:System.Drawing.Imaging.EncoderParameters> y pasarlo al método <xref:System.Drawing.Image.Save%2A> de la clase <xref:System.Drawing.Image>.  Inicialice el objeto <xref:System.Drawing.Imaging.EncoderParameters> para que tenga una matriz compuesta por <xref:System.Drawing.Imaging.EncoderParameter>.  Al crear <xref:System.Drawing.Imaging.EncoderParameter>, especifique el codificador <xref:System.Drawing.Imaging.Encoder.Quality> y el nivel de compresión que desee.  
  
## Ejemplo  
 El código de ejemplo siguiente crea un objeto <xref:System.Drawing.Imaging.EncoderParameter> y guarda tres imágenes JPEG.  Cada imagen JPEG se guarda con un nivel de calidad diferente, modificando el valor `long` pasado al constructor <xref:System.Drawing.Imaging.EncoderParameter>.  Un nivel de calidad de 0 corresponde a la compresión máxima y un nivel de calidad de 100 corresponde a la compresión menor.  
  
 [!code-csharp[UsingImageEncodersDecoders#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#8)]
 [!code-vb[UsingImageEncodersDecoders#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#8)]  
[!code-csharp[UsingImageEncodersDecoders#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#6)]
[!code-vb[UsingImageEncodersDecoders#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#6)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de formularios Windows Forms.  
  
-   Un argumento <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
-   Un archivo de imagen denominado `TestPhoto.jpg` y situado en **c:\\**.  
  
## Vea también  
 [Cómo: Determinar los parámetros admitidos por un codificador](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)   
 [Tipos de mapas de bits](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [Usar codificadores y descodificadores de imagen en la interfaz GDI\+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)