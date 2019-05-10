---
title: Procedimiento Establecer una propiedad después de animarla con un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: 593d3fcefe3bb81518d0886afde82f9a172874ba
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912384"
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="ffd94-102">Procedimiento Establecer una propiedad después de animarla con un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="ffd94-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="ffd94-103">En algunos casos, es posible que parece que no se puede cambiar el valor de una propiedad después de que se ha animado.</span><span class="sxs-lookup"><span data-stu-id="ffd94-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffd94-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffd94-104">Example</span></span>  
 <span data-ttu-id="ffd94-105">En el ejemplo siguiente, un <xref:System.Windows.Media.Animation.Storyboard> sirve para animar el color de un <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="ffd94-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="ffd94-106">El guión gráfico se desencadena cuando se hace clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="ffd94-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="ffd94-107">El <xref:System.Windows.Media.Animation.Timeline.Completed> se controla el evento para que el programa recibe una notificación cuando el <xref:System.Windows.Media.Animation.ColorAnimation> se complete.</span><span class="sxs-lookup"><span data-stu-id="ffd94-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="ffd94-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffd94-108">Example</span></span>  
 <span data-ttu-id="ffd94-109">Después de la <xref:System.Windows.Media.Animation.ColorAnimation> finalice, el programa intenta cambiar el color del pincel a azul.</span><span class="sxs-lookup"><span data-stu-id="ffd94-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="ffd94-110">El código anterior no parece hacer nada: la permanece pincel amarillo, que es el valor proporcionado por el <xref:System.Windows.Media.Animation.ColorAnimation> que anima el pincel.</span><span class="sxs-lookup"><span data-stu-id="ffd94-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="ffd94-111">El valor de propiedad subyacente (el valor base) realmente se cambia a azul.</span><span class="sxs-lookup"><span data-stu-id="ffd94-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="ffd94-112">Sin embargo, el valor efectivo o actual, sigue siendo amarillo porque la <xref:System.Windows.Media.Animation.ColorAnimation> continúa invalidando el valor base.</span><span class="sxs-lookup"><span data-stu-id="ffd94-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="ffd94-113">Si desea que el valor base vuelva a ser el valor efectivo, debe detener la animación de influir en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ffd94-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="ffd94-114">Hay tres maneras de hacer esto con animaciones de guión gráfico:</span><span class="sxs-lookup"><span data-stu-id="ffd94-114">There are three ways to do this with storyboard animations:</span></span>  
  
- <span data-ttu-id="ffd94-115">Establecer la animación <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad <xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="ffd94-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
- <span data-ttu-id="ffd94-116">Quitar el guión gráfico.</span><span class="sxs-lookup"><span data-stu-id="ffd94-116">Remove the entire Storyboard.</span></span>  
  
- <span data-ttu-id="ffd94-117">Quitar la animación de la propiedad individual.</span><span class="sxs-lookup"><span data-stu-id="ffd94-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="ffd94-118">Establecer FillBehavior (propiedad) de la animación en Stop</span><span class="sxs-lookup"><span data-stu-id="ffd94-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="ffd94-119">Estableciendo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> a <xref:System.Windows.Media.Animation.FillBehavior.Stop>, indica a la animación deje de afectar a su propiedad de destino una vez que llega al final de su período activo.</span><span class="sxs-lookup"><span data-stu-id="ffd94-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="ffd94-120">Quitar el guión gráfico</span><span class="sxs-lookup"><span data-stu-id="ffd94-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="ffd94-121">Mediante el uso de un <xref:System.Windows.Media.Animation.RemoveStoryboard> desencadenador o la <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> método, indicar a las animaciones de guión gráfico para que dejen de afectar a sus propiedades de destino.</span><span class="sxs-lookup"><span data-stu-id="ffd94-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="ffd94-122">La diferencia entre este enfoque y la configuración de la <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad es que puede quitar el guión gráfico en cualquier momento, mientras el <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> propiedad sólo tiene efecto cuando la animación alcanza el final de su período activo.</span><span class="sxs-lookup"><span data-stu-id="ffd94-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="ffd94-123">Quitar una animación de una propiedad individual</span><span class="sxs-lookup"><span data-stu-id="ffd94-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="ffd94-124">Otra técnica para detener una animación que afecte a una propiedad es usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> método del objeto que se anima.</span><span class="sxs-lookup"><span data-stu-id="ffd94-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="ffd94-125">Especifique la propiedad animada como primer parámetro y `null` como el segundo.</span><span class="sxs-lookup"><span data-stu-id="ffd94-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="ffd94-126">Esta técnica también funciona para las animaciones sin guiones gráficos.</span><span class="sxs-lookup"><span data-stu-id="ffd94-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd94-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffd94-127">See also</span></span>

- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.Animation.RemoveStoryboard>
- [<span data-ttu-id="ffd94-128">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="ffd94-128">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="ffd94-129">Información general sobre técnicas de animación de propiedades</span><span class="sxs-lookup"><span data-stu-id="ffd94-129">Property Animation Techniques Overview</span></span>](property-animation-techniques-overview.md)
