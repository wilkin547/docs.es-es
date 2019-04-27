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
ms.openlocfilehash: 417af272514ac9ce68c8faa72339f2befc2dd7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923388"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="d77d7-102">Reconocimiento de entradas manuscritas</span><span class="sxs-lookup"><span data-stu-id="d77d7-102">Handwriting Recognition</span></span>
<span data-ttu-id="d77d7-103">En esta sección se explican los fundamentos del reconocimiento en relación con la entrada de lápiz digital en la plataforma WPF.</span><span class="sxs-lookup"><span data-stu-id="d77d7-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="d77d7-104">Soluciones de reconocimiento</span><span class="sxs-lookup"><span data-stu-id="d77d7-104">Recognition Solutions</span></span>  
 <span data-ttu-id="d77d7-105">En el ejemplo siguiente se muestra cómo reconocer la entrada manuscrita utilizando la clase [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="d77d7-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d77d7-106">Este ejemplo requiere que los reconocedores de escritura a mano estén instalados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="d77d7-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="d77d7-107">Cree un nuevo proyecto de aplicación WPF en Visual Studio, denominado **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="d77d7-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="d77d7-108">Reemplace el contenido del archivo Window1.xaml por el siguiente código XAML.</span><span class="sxs-lookup"><span data-stu-id="d77d7-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="d77d7-109">Este código representa la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d77d7-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="d77d7-110">Agregue una referencia al ensamblado de Microsoft Ink, Microsoft.Ink.dll, que se encuentra en \Archivos de programa\Microsoft Shared\Ink.</span><span class="sxs-lookup"><span data-stu-id="d77d7-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="d77d7-111">Reemplace el contenido del código subyacente al archivo con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d77d7-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d77d7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d77d7-112">See also</span></span>

- <span data-ttu-id="d77d7-113">[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d77d7-113">[Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))</span></span>
