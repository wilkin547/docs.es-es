---
title: Procedimiento Codificar un objeto visual en un archivo de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545293"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Procedimiento Codificar un objeto visual en un archivo de imagen
En este ejemplo se muestra cómo codificar <xref:System.Windows.Media.Visual> un objeto en un archivo de imagen <xref:System.Windows.Media.Imaging.RenderTargetBitmap> mediante y <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Ejemplo  
 Se crea <xref:System.Windows.Media.Imaging.RenderTargetBitmap>mediante y que<xref:System.Windows.Media.FormattedText> se representa en un. <xref:System.Windows.Media.Imaging.BitmapImage> <xref:System.Windows.Media.DrawingVisual> El mapa de bits representado se usa para crear un <xref:System.Windows.Media.Imaging.BitmapFrame> que se agrega <xref:System.Windows.Media.Imaging.PngBitmapEncoder> a para crear un nuevo archivo PNG (Portable Network Graphics).  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Se usó en este ejemplo, pero cualquiera de los objetos <xref:System.Windows.Media.Imaging.BitmapEncoder> derivados podría haberse utilizado para crear el archivo de imagen. <xref:System.Windows.Media.Imaging.PngBitmapEncoder>  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.DrawingContext>
- [Información general sobre imágenes](imaging-overview.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Usar objetos DrawingVisual](using-drawingvisual-objects.md)
