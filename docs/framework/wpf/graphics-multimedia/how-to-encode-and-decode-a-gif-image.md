---
title: Procedimiento Codificar y descodificar una imagen GIF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: ec509a03d95e5f72af0b1f362e253799b07edc1f
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671692"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="df4f8-102">Procedimiento Codificar y descodificar una imagen GIF</span><span class="sxs-lookup"><span data-stu-id="df4f8-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="df4f8-103">En los siguientes ejemplos se muestra cómo descodificar y codificar una imagen de formato de intercambio de gráficos ( <xref:System.Windows.Media.Imaging.GifBitmapDecoder> GIF <xref:System.Windows.Media.Imaging.GifBitmapEncoder> ) mediante los objetos y específicos.</span><span class="sxs-lookup"><span data-stu-id="df4f8-103">The following examples show how to decode and encode a Graphics Interchange Format (GIF) image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df4f8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df4f8-104">Example</span></span>  
 <span data-ttu-id="df4f8-105">En este ejemplo se muestra cómo descodificar una imagen GIF <xref:System.Windows.Media.Imaging.GifBitmapDecoder> mediante un <xref:System.IO.FileStream>de.</span><span class="sxs-lookup"><span data-stu-id="df4f8-105">This example demonstrates how to decode a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="df4f8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df4f8-106">Example</span></span>  
 <span data-ttu-id="df4f8-107">En este ejemplo se muestra cómo codificar <xref:System.Windows.Media.Imaging.BitmapSource> un en una imagen GIF <xref:System.Windows.Media.Imaging.GifBitmapEncoder>mediante.</span><span class="sxs-lookup"><span data-stu-id="df4f8-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="df4f8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="df4f8-108">See also</span></span>

- [<span data-ttu-id="df4f8-109">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="df4f8-109">Imaging Overview</span></span>](imaging-overview.md)
