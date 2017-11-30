---
title: Reconocimiento de entradas manuscritas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f8a202d4698c968a91a3d930138290cedfe3a83b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="handwriting-recognition"></a>Reconocimiento de entradas manuscritas
En esta sección se explican los fundamentos del reconocimiento en relación con la entrada de lápiz digital en la plataforma WPF.  
  
## <a name="recognition-solutions"></a>Soluciones de reconocimiento  
 En el ejemplo siguiente se muestra cómo reconocer la entrada manuscrita utilizando la clase [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx).  
  
> [!NOTE]
>  Este ejemplo requiere que los reconocedores de escritura a mano estén instalados en el sistema.  
  
 Cree un nuevo proyecto de aplicación WPF en Visual Studio, denominado **InkRecognition**. Reemplace el contenido del archivo Window1.xaml por el siguiente código XAML. Este código representa la interfaz de usuario de la aplicación.  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Agregue una referencia al ensamblado de Microsoft Ink, Microsoft.Ink.dll, que se encuentra en \Archivos de programa\Microsoft Shared\Ink. Reemplace el contenido del código subyacente al archivo con el código siguiente.  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)
