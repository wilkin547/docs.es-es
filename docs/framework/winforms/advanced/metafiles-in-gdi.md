---
title: Metarchivos en GDI+
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b9d378f82b2a7edca00fedaacdcc0fca179c5a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="metafiles-in-gdi"></a>Metarchivos en GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]proporciona la <xref:System.Drawing.Imaging.Metafile> clase para que pueda registrar y mostrar metarchivos. Un metarchivo, también denominado imagen vectorial, es una imagen que se almacena como una secuencia de comandos y la configuración de dibujo. Los comandos y la configuración se registra en un <xref:System.Drawing.Imaging.Metafile> objeto se pueda almacenar en memoria o guardado en un archivo o secuencia.  
  
## <a name="metafile-formats"></a>Formatos de metarchivo  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]puede mostrar metarchivos que han sido almacenados en los siguientes formatos:  
  
-   Metarchivo de Windows (WMF)  
  
-   Metarchivo mejorado (EMF)  
  
-   EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]puede registrar metarchivos en los formatos EMF y EMF +, pero no tienen el formato WMF.  
  
 EMF + es una extensión de EMF que permite [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros que se va a almacenar. Hay dos variaciones en el formato EMF +: EMF + Only y EMF + Dual. Los metarchivos EMF + Only sólo contienen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros. Se pueden mostrar metarchivos de este tipo por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] , pero no en [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Los metarchivos EMF + Dual contienen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] registros. Cada [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros en un archivo EMF + Dual metarchivo se empareja con una alternativa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] registro. Se pueden mostrar metarchivos de este tipo por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 En el ejemplo siguiente se muestra un metarchivo que previamente se ha guardado como un archivo. Metarchivo se muestra con la esquina superior izquierda en (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
