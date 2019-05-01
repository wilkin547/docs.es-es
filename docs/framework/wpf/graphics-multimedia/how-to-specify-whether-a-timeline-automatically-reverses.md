---
title: Procedimiento Especificar si una escala de tiempo se invierte automáticamente
ms.date: 03/30/2017
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
ms.openlocfilehash: 0fe2d337d8afa5197475e5b9ee40950226596e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024669"
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="19fe5-102">Procedimiento Especificar si una escala de tiempo se invierte automáticamente</span><span class="sxs-lookup"><span data-stu-id="19fe5-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="19fe5-103">Una escala de tiempo <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad determina si reproduce en orden inverso después de completar una iteración de avance.</span><span class="sxs-lookup"><span data-stu-id="19fe5-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="19fe5-104">El ejemplo siguiente muestra varias animaciones con duración idéntico y los valores de destino, pero con diferentes <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="19fe5-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="19fe5-105">Para demostrar cómo el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad se comporta con diferentes <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> , algunas animaciones están configurados para repetir.</span><span class="sxs-lookup"><span data-stu-id="19fe5-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="19fe5-106">La última animación se muestra cómo el <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> propiedad funciona en escalas de tiempo anidadas.</span><span class="sxs-lookup"><span data-stu-id="19fe5-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19fe5-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19fe5-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
