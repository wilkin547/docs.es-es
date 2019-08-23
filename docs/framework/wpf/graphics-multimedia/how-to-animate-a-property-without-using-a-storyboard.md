---
title: Procedimiento Animar una propiedad sin usar un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 71711c0392576930e97986078ec5926ff6ca9813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963018"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="57368-102">Procedimiento Animar una propiedad sin usar un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="57368-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="57368-103">En este ejemplo se muestra una manera de aplicar una animación a una propiedad sin <xref:System.Windows.Media.Animation.Storyboard>usar.</span><span class="sxs-lookup"><span data-stu-id="57368-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57368-104">Esta funcionalidad no está disponible en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="57368-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="57368-105">Para información sobre cómo animar una propiedad en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vea [Animar una propiedad utilizando un guión gráfico](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="57368-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="57368-106">Para aplicar una animación local a una propiedad, use el <xref:System.Windows.UIElement.BeginAnimation%2A> método.</span><span class="sxs-lookup"><span data-stu-id="57368-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="57368-107">Este método toma dos parámetros: un <xref:System.Windows.DependencyProperty> que especifica la propiedad que se va a animar y la animación que se va a aplicar a esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="57368-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57368-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57368-108">Example</span></span>  
 <span data-ttu-id="57368-109">En el ejemplo siguiente se muestra cómo animar el ancho y el color <xref:System.Windows.Controls.Button>de fondo de un.</span><span class="sxs-lookup"><span data-stu-id="57368-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="57368-110">Existe una variedad de clases de animación <xref:System.Windows.Media.Animation> en el espacio de nombres para animar diferentes tipos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="57368-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="57368-111">Para más información sobre la animación de propiedades, vea [Información general sobre animaciones](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="57368-111">For more information about animating properties, see [Animation Overview](animation-overview.md).</span></span> <span data-ttu-id="57368-112">Para más información sobre las propiedades de dependencia (el tipo de propiedades que se muestran en estos ejemplos) y sus características, vea [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="57368-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="57368-113">Hay otras maneras de animar sin utilizar <xref:System.Windows.Media.Animation.Storyboard> objetos; para obtener más información, vea [información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="57368-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57368-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="57368-114">See also</span></span>

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="57368-115">Información general sobre técnicas de animación de propiedades</span><span class="sxs-lookup"><span data-stu-id="57368-115">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
- [<span data-ttu-id="57368-116">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="57368-116">Animation Overview</span></span>](animation-overview.md)
