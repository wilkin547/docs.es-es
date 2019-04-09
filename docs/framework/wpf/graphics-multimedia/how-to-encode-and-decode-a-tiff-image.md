---
title: Filtrar Codificar y descodificar una imagen TIFF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 0b2b638d3aa81e48a1378794435d59da1b323aa2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107437"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="fedf2-102">Filtrar Codificar y descodificar una imagen TIFF</span><span class="sxs-lookup"><span data-stu-id="fedf2-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="fedf2-103">Los ejemplos siguientes muestran cómo descodificar y codificar una [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] específico de imagen <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> y <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objetos.</span><span class="sxs-lookup"><span data-stu-id="fedf2-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fedf2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fedf2-104">Example</span></span>  
 <span data-ttu-id="fedf2-105">En este ejemplo se muestra cómo descodificar un [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] imágenes que usan un <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> desde un <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="fedf2-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="fedf2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fedf2-106">Example</span></span>  
 <span data-ttu-id="fedf2-107">En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en un [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] imágenes que usan un <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="fedf2-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="fedf2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="fedf2-108">See also</span></span>

- [<span data-ttu-id="fedf2-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="fedf2-109">Imaging Overview</span></span>](imaging-overview.md)
