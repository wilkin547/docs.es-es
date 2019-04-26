---
title: Procedimiento Crear un mapa de bits desde un objeto visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910265"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Procedimiento Crear un mapa de bits desde un objeto visual
En este ejemplo se muestra cómo puede crear un mapa de bits desde un <xref:System.Windows.Media.Visual>. Un <xref:System.Windows.Media.DrawingVisual> se presenta con <xref:System.Windows.Media.FormattedText>. El <xref:System.Windows.Media.Visual> , a continuación, se representa en el <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creación de un mapa de bits del texto dado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.DrawingContext>
- [Información general sobre imágenes](imaging-overview.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Usar objetos DrawingVisual](using-drawingvisual-objects.md)
