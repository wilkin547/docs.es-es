---
title: "Cómo: Especificar si una escala de tiempo se invierte automáticamente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da1330a8513f43e7543f97838ef8e9be788af396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="4541b-102">Cómo: Especificar si una escala de tiempo se invierte automáticamente</span><span class="sxs-lookup"><span data-stu-id="4541b-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="4541b-103">Una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad determina si reproduce en orden inverso después de completar una iteración de avance.</span><span class="sxs-lookup"><span data-stu-id="4541b-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="4541b-104">El ejemplo siguiente muestra varias animaciones con idéntica duración y valores de destino, pero con diferentes <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="4541b-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="4541b-105">Para demostrar cómo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad se comporta con diferentes <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , algunas animaciones están configurados para repetir.</span><span class="sxs-lookup"><span data-stu-id="4541b-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="4541b-106">La última animación se muestra cómo el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad funciona en escalas de tiempo anidadas.</span><span class="sxs-lookup"><span data-stu-id="4541b-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4541b-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4541b-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
