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
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504584"
---
# <a name="metafiles-in-gdi"></a>Metarchivos en GDI+
GDI + proporciona la <xref:System.Drawing.Imaging.Metafile> clase por lo que puede grabar y mostrar metarchivos. Un metarchivo, también denominado imagen vectorial, es una imagen que se almacena como una secuencia de comandos y valores de dibujo. Los comandos y valores que se registran en un <xref:System.Drawing.Imaging.Metafile> objeto se pueda almacenar en memoria o guardado en un archivo o secuencia.  
  
## <a name="metafile-formats"></a>Formatos de metarchivo  
 GDI + puede mostrar metarchivos que se han almacenado en los siguientes formatos:  
  
- Metarchivo de Windows (WMF)  
  
- Metarchivo mejorado (EMF)  
  
- EMF +  
  
 GDI + puede registrar metarchivos en los formatos EMF y EMF +, pero no en el formato WMF.  
  
 EMF + es una extensión EMF que permite que se almacenen registros GDI +. Hay dos variaciones en formato EMF +: EMF + solo y EMF + Dual. Metarchivos EMF + sólo contienen únicamente registros GDI +. Metarchivos de este tipo pueden mostrarse en GDI + pero no en GDI. Los metarchivos EMF + Dual contienen registros GDI + y GDI. Cada registro GDI + de un metarchivo EMF + Dual está emparejado con un registro GDI alternativo. Metarchivos de este tipo pueden mostrarse mediante GDI + o GDI.  
  
 El ejemplo siguiente muestra un metarchivo que se guardó previamente como un archivo. Metarchivo que se muestra con la esquina superior izquierda en (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
