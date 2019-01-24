---
title: Procedimiento Crear un mapa de bits desde un objeto Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: dbbf7691508e5e5ddf3ed3af768f757ee0c3f20c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705464"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Procedimiento Crear un mapa de bits desde un objeto Visual
En este ejemplo se muestra cómo puede crear un mapa de bits desde un <xref:System.Windows.Media.Visual>. Un <xref:System.Windows.Media.DrawingVisual> se presenta con <xref:System.Windows.Media.FormattedText>. El <xref:System.Windows.Media.Visual> , a continuación, se representa en el <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creación de un mapa de bits del texto dado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.DrawingContext>
- [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
- [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
