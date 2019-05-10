---
title: Metarchivos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: f46c24b699aa49db2bc4b8467ce96a125602acec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645738"
---
# <a name="metafiles-in-gdi"></a>Metarchivos en GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona el <xref:System.Drawing.Imaging.Metafile> clase por lo que puede grabar y mostrar metarchivos. Un metarchivo, también denominado imagen vectorial, es una imagen que se almacena como una secuencia de comandos y valores de dibujo. Los comandos y valores que se registran en un <xref:System.Drawing.Imaging.Metafile> objeto se pueda almacenar en memoria o guardado en un archivo o secuencia.  
  
## <a name="metafile-formats"></a>Formatos de metarchivo  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede mostrar metarchivos que se han almacenado en los siguientes formatos:  
  
- Metarchivo de Windows (WMF)  
  
- Metarchivo mejorado (EMF)  
  
- EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede registrar metarchivos en los formatos EMF y EMF +, pero no en el formato WMF.  
  
 EMF + es una extensión EMF que permite [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros que se almacenará. Hay dos variaciones en formato EMF +: EMF + solo y EMF + Dual. Los metarchivos EMF + Only sólo contienen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros. Metarchivos de este tipo se pueden mostrar por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] pero no en [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Los metarchivos EMF + Dual contienen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] y [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] registros. Cada [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] registros en un archivo EMF + Dual metarchivo se empareja con alternativa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] registro. Metarchivos de este tipo se pueden mostrar por [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 El ejemplo siguiente muestra un metarchivo que se guardó previamente como un archivo. Metarchivo que se muestra con la esquina superior izquierda en (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
