---
title: Procedimiento Aumentar o reducir la velocidad de una animación
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: d4fcaf4a684c37590f27d603ef5cb2c86a6fb854
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762168"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="5d676-102">Procedimiento Aumentar o reducir la velocidad de una animación</span><span class="sxs-lookup"><span data-stu-id="5d676-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="5d676-103">En este ejemplo se muestra cómo realizar una animación acelerar y reducir la velocidad con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="5d676-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="5d676-104">En el ejemplo siguiente, se animan los rectángulos varios por animaciones con diferentes <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> y <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> configuración.</span><span class="sxs-lookup"><span data-stu-id="5d676-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d676-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d676-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="5d676-106">Se ha omitido el código en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5d676-106">Code has been omitted from this example.</span></span> <span data-ttu-id="5d676-107">Para el código completo, vea el [comportamiento de tiempo de animación (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) o [comportamiento de tiempo de animación (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span><span class="sxs-lookup"><span data-stu-id="5d676-107">For the complete code, see the [Animation Timing Behavior (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp) or [Animation Timing Behavior (Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic).</span></span>
