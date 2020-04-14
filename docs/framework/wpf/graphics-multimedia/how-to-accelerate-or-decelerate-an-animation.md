---
title: 'Cómo: Aumentar o reducir la velocidad de una animación'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: 7ab55ba44b866a992b9021284f170858f0108d15
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243016"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="f5ae6-102">Cómo: Acelerar o desacelerar una animación</span><span class="sxs-lookup"><span data-stu-id="f5ae6-102">How to: Accelerate or decelerate an animation</span></span>

<span data-ttu-id="f5ae6-103">En este ejemplo se muestra cómo hacer que una animación se acelere y desacelere con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f5ae6-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="f5ae6-104">En el ejemplo siguiente, varios rectángulos se <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> animan mediante animaciones con diferentes y ajustes.</span><span class="sxs-lookup"><span data-stu-id="f5ae6-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5ae6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5ae6-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="f5ae6-106">El código se ha omitido en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f5ae6-106">Code has been omitted from this example.</span></span> <span data-ttu-id="f5ae6-107">Para obtener el código completo, vea el comportamiento de [temporización](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) de animación (C) o el comportamiento de [temporización de animación (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="f5ae6-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
