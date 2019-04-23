---
title: Procedimiento Agregar un valor de salida de animación a un valor inicial de animación
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102614"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="a76d5-102">Procedimiento Agregar un valor de salida de animación a un valor inicial de animación</span><span class="sxs-lookup"><span data-stu-id="a76d5-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="a76d5-103">En este ejemplo se muestra cómo agregar un valor de salida de animación a un valor inicial de animación.</span><span class="sxs-lookup"><span data-stu-id="a76d5-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a76d5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a76d5-104">Example</span></span>  
 <span data-ttu-id="a76d5-105">El <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad especifica si desea que el valor de salida de una animación que se agrega al valor inicial (valor base) de una propiedad animada.</span><span class="sxs-lookup"><span data-stu-id="a76d5-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="a76d5-106">Puede usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> propiedad con animaciones más básicas y la mayoría de las animaciones de fotogramas clave.</span><span class="sxs-lookup"><span data-stu-id="a76d5-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="a76d5-107">Para obtener más información, consulte [información general sobre animaciones](animation-overview.md) y [información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a76d5-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="a76d5-108">El ejemplo siguiente muestra el efecto de usar el <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimation> y el uso de la <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> propiedad con <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="a76d5-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a76d5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a76d5-109">See also</span></span>

- [<span data-ttu-id="a76d5-110">Acumular valores de animaciones durante la repetición de ciclos</span><span class="sxs-lookup"><span data-stu-id="a76d5-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="a76d5-111">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="a76d5-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a76d5-112">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="a76d5-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="a76d5-113">Temas de procedimientos de temporización y animación</span><span class="sxs-lookup"><span data-stu-id="a76d5-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
