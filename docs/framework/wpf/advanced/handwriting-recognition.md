---
title: Reconocimiento de entradas manuscritas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 08cd9e0a167d1bef9bbe6437b22985082c80e5f9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365807"
---
# <a name="handwriting-recognition"></a>Reconocimiento de entradas manuscritas
En esta sección se explican los fundamentos del reconocimiento en relación con la entrada de lápiz digital en la plataforma WPF.  
  
## <a name="recognition-solutions"></a>Soluciones de reconocimiento  
 En el ejemplo siguiente se muestra cómo reconocer la entrada manuscrita utilizando la clase [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)).  
  
> [!NOTE]
>  Este ejemplo requiere que los reconocedores de escritura a mano estén instalados en el sistema.  
  
 Cree un nuevo proyecto de aplicación WPF en Visual Studio, denominado **InkRecognition**. Reemplace el contenido del archivo Window1.xaml por el siguiente código XAML. Este código representa la interfaz de usuario de la aplicación.  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Agregue una referencia al ensamblado de Microsoft Ink, Microsoft.Ink.dll, que se encuentra en \Archivos de programa\Microsoft Shared\Ink. Reemplace el contenido del código subyacente al archivo con el código siguiente.  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también
- [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))
