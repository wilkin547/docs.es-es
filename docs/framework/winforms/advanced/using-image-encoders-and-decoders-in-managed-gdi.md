---
title: "Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada | Microsoft Docs"
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
  - "descodificadores de imágenes, utilizar"
  - "codificadores de imágenes, utilizar"
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada
El espacio de nombres <xref:System.Drawing> proporciona las clases <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> para almacenar y manipular imágenes.  Con los codificadores de imagen de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede escribir imágenes desde la memoria en el disco. Con los descodificadores de imagen de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede cargar imágenes desde el disco en la memoria.  Un codificador traduce los datos de un objeto <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> en un formato de archivo de disco designado.  Un descodificador traduce los datos de un archivo de disco al formato que requieren los objetos <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap>.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] tiene codificadores y descodificadores integrados que admiten los siguientes tipos de archivo:  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] también tiene descodificadores integrados que admiten los siguientes tipos de archivo:  
  
-   WMF  
  
-   EMF  
  
-   ICON  
  
 Los temas siguientes describen los codificadores y descodificadores con más detalle:  
  
## En esta sección  
 [Cómo: Enumerar los codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 Describe cómo enumerar los codificadores disponibles en un equipo.  
  
 [Cómo: Enumerar los descodificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 Describe cómo enumerar los decodificadores disponibles en un equipo.  
  
 [Cómo: Determinar los parámetros admitidos por un codificador](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Describe cómo enumerar los <xref:System.Drawing.Imaging.EncoderParameters> admitidos por un codificador.  
  
 [Cómo: Convertir una imagen BMP en una imagen PNG](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 Describe cómo guardar una imagen en un formato de imagen diferente.  
  
 [Cómo: Establecer el nivel de compresión de imágenes JPEG](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 Describe cómo cambiar el nivel de calidad de una imagen.  
  
## Referencia  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## Secciones relacionadas  
 [Código administrado de GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)