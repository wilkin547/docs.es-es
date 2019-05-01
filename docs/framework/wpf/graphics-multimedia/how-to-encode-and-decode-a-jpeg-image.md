---
title: Procedimiento Codificar y descodificar una imagen JPEG
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
ms.openlocfilehash: 0f64ef8537f22ea996cbcf274885de1f3968267a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947516"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="43f10-102">Procedimiento Codificar y descodificar una imagen JPEG</span><span class="sxs-lookup"><span data-stu-id="43f10-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="43f10-103">Los ejemplos siguientes muestran cómo descodificar y codificar imágenes JPEG con específico del <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> y <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objetos.</span><span class="sxs-lookup"><span data-stu-id="43f10-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="43f10-104">Por ejemplo, descodificar una imagen JPEG</span><span class="sxs-lookup"><span data-stu-id="43f10-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="43f10-105">En este ejemplo se muestra cómo descodificar una imagen JPEG mediante un <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> desde un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="43f10-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="43f10-106">Ejemplo: codificar una imagen JPEG</span><span class="sxs-lookup"><span data-stu-id="43f10-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="43f10-107">En este ejemplo se muestra cómo codificar un <xref:System.Windows.Media.Imaging.BitmapSource> en formato JPEG de la imagen mediante un <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="43f10-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="43f10-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="43f10-108">See also</span></span>

- [<span data-ttu-id="43f10-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="43f10-109">Imaging Overview</span></span>](imaging-overview.md)
