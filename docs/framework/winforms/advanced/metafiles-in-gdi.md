---
title: "Metarchivos en GDI+ | Microsoft Docs"
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
  - "GDI+, metarchivos"
  - "imágenes [Windows Forms], metarchivos"
  - "metarchivos"
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Metarchivos en GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona la clase <xref:System.Drawing.Imaging.Metafile> para que puedan registrarse y mostrarse metarchivos.  Un metarchivo, también denominado imagen vectorial, es una imagen que se almacena como una secuencia de comandos y valores de dibujo.  Los comandos y valores registrados en un objeto <xref:System.Drawing.Imaging.Metafile> pueden almacenarse en memoria, o pueden guardarse en un archivo o secuencia.  
  
## Formatos de metarchivo  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede mostrar metarchivos que se hayan almacenado en los siguientes formatos:  
  
-   WMF \(Metarchivo de Windows\)  
  
-   EMF \(Metarchivo mejorado\)  
  
-   EMF\+  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede registrar metarchivos en los formatos EMF y EMF\+, pero no en formato WMF.  
  
 EMF\+ es una extensión de EMF que permite el almacenamiento de los registros de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  Hay dos variaciones del formato EMF\+: EMF\+ Only y EMF\+ Dual.  Los metarchivos EMF\+ Only solo contienen registros de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede mostrar los metarchivos de este tipo, pero [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] no puede hacerlo.  Los metarchivos EMF\+ Dual contienen registros de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  Cada registro de [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] de un metarchivo EMF\+ Dual está emparejado con un registro de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] alternativo.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] pueden mostrar los metarchivos de este tipo.  
  
 En el siguiente ejemplo se muestra un metarchivo que se guardó previamente como un archivo.  El metarchivo se muestra con la esquina superior izquierda en \(100, 100\).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)