---
title: 'Cómo: Codificar y descodificar una imagen JPEG'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 8eb3c2573ba23fa62550e7e60489b13a37eb7cc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560017"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="a9809-102">Cómo: Codificar y descodificar una imagen JPEG</span><span class="sxs-lookup"><span data-stu-id="a9809-102">How to: Encode and Decode a JPEG Image</span></span>
<span data-ttu-id="a9809-103">Los ejemplos siguientes muestran cómo descodificar y codificar una [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] mediante la específica de la imagen <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> y <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objetos.</span><span class="sxs-lookup"><span data-stu-id="a9809-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9809-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9809-104">Example</span></span>  
 <span data-ttu-id="a9809-105">Este ejemplo muestra cómo descodificar un [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] imágenes que usan un <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> desde un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="a9809-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
 [!code-csharp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
 [!code-vb[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="a9809-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9809-106">Example</span></span>  
 <span data-ttu-id="a9809-107">Este ejemplo muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en un [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] imágenes que usan un <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="a9809-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
 [!code-cpp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
 [!code-csharp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
 [!code-vb[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="a9809-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9809-108">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9809-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9809-109">See Also</span></span>  
 [<span data-ttu-id="a9809-110">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="a9809-110">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
