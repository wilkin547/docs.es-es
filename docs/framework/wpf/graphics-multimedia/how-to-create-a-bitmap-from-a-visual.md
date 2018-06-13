---
title: 'Cómo: Crear un mapa de bits desde un objeto Visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 4735474d00712598cb5e41fad289e8f568d83a48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559771"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Cómo: Crear un mapa de bits desde un objeto Visual
Este ejemplo muestra cómo puede crear un mapa de bits de un <xref:System.Windows.Media.Visual>. A <xref:System.Windows.Media.DrawingVisual> se representa con <xref:System.Windows.Media.FormattedText>. El <xref:System.Windows.Media.Visual> , a continuación, se representa en la <xref:System.Windows.Media.Imaging.RenderTargetBitmap> crear un mapa de bits del texto dado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.DrawingContext>  
 [Información general sobre imágenes](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Usar objetos DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
