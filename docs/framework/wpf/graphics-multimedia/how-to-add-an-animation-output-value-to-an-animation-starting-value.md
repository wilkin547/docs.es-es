---
title: Procedimiento Agregar un valor de salida de animación a un valor inicial de animación
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 820e03064d331e852a224e1f989685d7a77983db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603032"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="8cc19-102">Procedimiento Agregar un valor de salida de animación a un valor inicial de animación</span><span class="sxs-lookup"><span data-stu-id="8cc19-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="8cc19-103">En este ejemplo se muestra cómo agregar un valor de salida de animación a un valor inicial de animación.</span><span class="sxs-lookup"><span data-stu-id="8cc19-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc19-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cc19-104">Example</span></span>  
 <span data-ttu-id="8cc19-105">El <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad especifica si desea que el valor de salida de una animación que se agrega al valor inicial (valor base) de una propiedad animada.</span><span class="sxs-lookup"><span data-stu-id="8cc19-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="8cc19-106">Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad con animaciones más básicas y la mayoría de las animaciones de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="8cc19-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="8cc19-107">Para obtener más información, consulte [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) y [información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8cc19-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="8cc19-108">El ejemplo siguiente muestra el efecto de usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimation> y el uso de la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="8cc19-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8cc19-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cc19-109">See also</span></span>
- [<span data-ttu-id="8cc19-110">Acumular valores de animaciones durante la repetición de ciclos</span><span class="sxs-lookup"><span data-stu-id="8cc19-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="8cc19-111">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="8cc19-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="8cc19-112">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="8cc19-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="8cc19-113">Animación y temporización</span><span class="sxs-lookup"><span data-stu-id="8cc19-113">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [<span data-ttu-id="8cc19-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="8cc19-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
