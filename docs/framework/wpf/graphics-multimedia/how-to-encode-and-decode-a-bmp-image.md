---
title: 'Cómo: Codificar y descodificar una imagen BMP'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: d8815a6f52a4033ec2d7dc19b0f97c5e65f1e2b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558857"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="82895-102">Cómo: Codificar y descodificar una imagen BMP</span><span class="sxs-lookup"><span data-stu-id="82895-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="82895-103">Los ejemplos siguientes muestran cómo descodificar y codificar una [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] mediante la específica de la imagen <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> y <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objetos.</span><span class="sxs-lookup"><span data-stu-id="82895-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82895-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82895-104">Example</span></span>  
 <span data-ttu-id="82895-105">Este ejemplo muestra cómo descodificar un [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] imágenes que usan un <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> desde un <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="82895-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="82895-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82895-106">Example</span></span>  
 <span data-ttu-id="82895-107">Este ejemplo muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en un [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] imágenes que usan un <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="82895-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="82895-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="82895-108">See Also</span></span>  
 [<span data-ttu-id="82895-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="82895-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
