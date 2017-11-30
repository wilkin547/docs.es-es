---
title: "Cómo: Animar la posición o color de un punto de degradado"
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
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 968d285d8a3345da9810f0ba4797bf8b2e33d36e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="52145-102">Cómo: Animar la posición o color de un punto de degradado</span><span class="sxs-lookup"><span data-stu-id="52145-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="52145-103">Este ejemplo muestra cómo animar la <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de <xref:System.Windows.Media.GradientStop> objetos.</span><span class="sxs-lookup"><span data-stu-id="52145-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52145-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52145-104">Example</span></span>  
 <span data-ttu-id="52145-105">En el ejemplo siguiente se anima tres puntos de degradado dentro de un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="52145-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="52145-106">El ejemplo utiliza tres animaciones, cada uno de los cuales anima un delimitador de degradado diferente:</span><span class="sxs-lookup"><span data-stu-id="52145-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
-   <span data-ttu-id="52145-107">La primera animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, anima la detención de degradado primera <xref:System.Windows.Media.GradientStop.Offset%2A> comprendido entre 0,0 y 1,0 y luego de nuevo a 0,0.</span><span class="sxs-lookup"><span data-stu-id="52145-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="52145-108">Como resultado, el primer color del degradado cambia del lado izquierdo a la derecha del rectángulo y luego de nuevo a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="52145-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
-   <span data-ttu-id="52145-109">La segunda animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, anima la detención de degradado segundo <xref:System.Windows.Media.GradientStop.Color%2A> de <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> y, a continuación, de nuevo a <xref:System.Windows.Media.Colors.Purple%2A>.</span><span class="sxs-lookup"><span data-stu-id="52145-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="52145-110">Como resultado, el color intermedio del degradado cambia del púrpura a amarillo y vuelve al púrpura.</span><span class="sxs-lookup"><span data-stu-id="52145-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
-   <span data-ttu-id="52145-111">La tercera animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad de la detención de degradado tercer <xref:System.Windows.Media.GradientStop.Color%2A> por -1 y luego de nuevo.</span><span class="sxs-lookup"><span data-stu-id="52145-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="52145-112">Como resultado, el tercer color del degradado se atenúa gradualmente y, a continuación, se convierte en opaco.</span><span class="sxs-lookup"><span data-stu-id="52145-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="52145-113">Aunque en este ejemplo se usa un <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar <xref:System.Windows.Media.GradientStop> objetos dentro de un <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="52145-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="52145-114">Para obtener ejemplos adicionales, consulte la [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="52145-114">For additional examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52145-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="52145-115">See Also</span></span>  
 <xref:System.Windows.Media.GradientStop>  
 [<span data-ttu-id="52145-116">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="52145-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="52145-117">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="52145-117">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
