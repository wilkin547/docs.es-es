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
ms.workload: dotnet
ms.openlocfilehash: 384f21587c29e6afe82964fc28432f5a6be92b05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="handwriting-recognition"></a><span data-ttu-id="b2c99-102">Reconocimiento de entradas manuscritas</span><span class="sxs-lookup"><span data-stu-id="b2c99-102">Handwriting Recognition</span></span>
<span data-ttu-id="b2c99-103">En esta sección se explican los fundamentos del reconocimiento en relación con la entrada de lápiz digital en la plataforma WPF.</span><span class="sxs-lookup"><span data-stu-id="b2c99-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="b2c99-104">Soluciones de reconocimiento</span><span class="sxs-lookup"><span data-stu-id="b2c99-104">Recognition Solutions</span></span>  
 <span data-ttu-id="b2c99-105">En el ejemplo siguiente se muestra cómo reconocer la entrada manuscrita utilizando la clase [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx).</span><span class="sxs-lookup"><span data-stu-id="b2c99-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c99-106">Este ejemplo requiere que los reconocedores de escritura a mano estén instalados en el sistema.</span><span class="sxs-lookup"><span data-stu-id="b2c99-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="b2c99-107">Cree un nuevo proyecto de aplicación WPF en Visual Studio, denominado **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="b2c99-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="b2c99-108">Reemplace el contenido del archivo Window1.xaml por el siguiente código XAML.</span><span class="sxs-lookup"><span data-stu-id="b2c99-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="b2c99-109">Este código representa la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b2c99-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="b2c99-110">Agregue una referencia al ensamblado de Microsoft Ink, Microsoft.Ink.dll, que se encuentra en \Archivos de programa\Microsoft Shared\Ink.</span><span class="sxs-lookup"><span data-stu-id="b2c99-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="b2c99-111">Reemplace el contenido del código subyacente al archivo con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2c99-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="b2c99-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c99-112">See Also</span></span>  
 <span data-ttu-id="b2c99-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b2c99-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span></span>
