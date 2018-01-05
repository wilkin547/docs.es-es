---
title: "Cómo: Aumentar o reducir la velocidad de una animación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c06518e3eada30bd4e22549a9ee3c8f16070f5ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="0b5aa-102">Cómo: Aumentar o reducir la velocidad de una animación</span><span class="sxs-lookup"><span data-stu-id="0b5aa-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="0b5aa-103">Este ejemplo muestra cómo realizar una animación acelerar y reducir la velocidad con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0b5aa-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="0b5aa-104">En el ejemplo siguiente, se animan varios rectángulos por animaciones con diferentes <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> y <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="0b5aa-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b5aa-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b5aa-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="0b5aa-106">Se ha omitido el código de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0b5aa-106">Code has been omitted from this example.</span></span> <span data-ttu-id="0b5aa-107">Para obtener el código completo, vea el [ejemplo de comportamiento de tiempo de animación](http://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="0b5aa-107">For the complete code, see the [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>
