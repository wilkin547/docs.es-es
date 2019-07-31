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
# <a name="how-to-encode-and-decode-a-gif-image"></a>Procedimiento Codificar y descodificar una imagen GIF
En los siguientes ejemplos se muestra cómo descodificar y codificar una imagen de formato de intercambio de gráficos ( <xref:System.Windows.Media.Imaging.GifBitmapDecoder> GIF <xref:System.Windows.Media.Imaging.GifBitmapEncoder> ) mediante los objetos y específicos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo descodificar una imagen GIF <xref:System.Windows.Media.Imaging.GifBitmapDecoder> mediante un <xref:System.IO.FileStream>de.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo codificar <xref:System.Windows.Media.Imaging.BitmapSource> un en una imagen GIF <xref:System.Windows.Media.Imaging.GifBitmapEncoder>mediante.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre imágenes](imaging-overview.md)
