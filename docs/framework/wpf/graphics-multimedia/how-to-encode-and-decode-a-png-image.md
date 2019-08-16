---
title: Procedimiento Codificar y descodificar una imagen PNG
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
ms.openlocfilehash: 0a0a2f2625901f7ee32ba9fe70e71681a1b9ccd3
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545275"
---
# <a name="how-to-encode-and-decode-a-png-image"></a>Procedimiento Codificar y descodificar una imagen PNG
En los siguientes ejemplos se muestra cómo descodificar y codificar una imagen PNG (Portable Network Graphics) <xref:System.Windows.Media.Imaging.PngBitmapDecoder> mediante <xref:System.Windows.Media.Imaging.PngBitmapEncoder> los objetos y específicos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo descodificar una imagen PNG <xref:System.Windows.Media.Imaging.PngBitmapDecoder> con un <xref:System.IO.FileStream>de.  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo codificar <xref:System.Windows.Media.Imaging.BitmapSource> un en una imagen PNG <xref:System.Windows.Media.Imaging.PngBitmapEncoder>mediante.  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre imágenes](imaging-overview.md)
