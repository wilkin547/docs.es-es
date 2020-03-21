---
title: 'Cómo: Aplicar animaciones a texto'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174633"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="2e4f0-102">Cómo: Aplicar animaciones a texto</span><span class="sxs-lookup"><span data-stu-id="2e4f0-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="2e4f0-103">Las animaciones pueden modificar la presentación y la apariencia del texto en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="2e4f0-104">En los ejemplos siguientes se utilizan diferentes tipos de <xref:System.Windows.Controls.TextBlock> animaciones para afectar a la visualización de texto en un control.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e4f0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e4f0-105">Example</span></span>  
 <span data-ttu-id="2e4f0-106">En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente se utiliza a para animar el ancho del bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="2e4f0-107">El valor del ancho cambia del ancho del bloque de texto a 0 durante 10 segundos y, a continuación, invierte los valores de ancho y continúa.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="2e4f0-108">Este tipo de animación crea un efecto de barrido.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="2e4f0-109">En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente se utiliza a para animar la opacidad del bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="2e4f0-110">El valor de opacidad cambia de 1,0 a 0 durante 5 segundos y, a continuación, invierte los valores de opacidad y continúa.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="2e4f0-111">El diagrama siguiente muestra <xref:System.Windows.Controls.TextBlock> el efecto del `1.00` control `0.00` cambiando su opacidad de <xref:System.Windows.Media.Animation.Timeline.Duration%2A>a durante el intervalo de 5 segundos definido por el archivo .</span><span class="sxs-lookup"><span data-stu-id="2e4f0-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![Texto cambiando la opacidad de 1.00 a 0.00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 <span data-ttu-id="2e4f0-113">En el ejemplo <xref:System.Windows.Media.Animation.ColorAnimation> siguiente se utiliza a para animar el color de primer plano del bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="2e4f0-114">El valor de color de primer plano cambia de un color a un segundo color durante 5 segundos y, a continuación, invierte los valores de color y continúa.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="2e4f0-115">En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente se utiliza a para rotar el bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="2e4f0-116">El bloque de texto realiza una rotación completa durante 20 segundos y, a continuación, sigue repitiendo la rotación.</span><span class="sxs-lookup"><span data-stu-id="2e4f0-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="2e4f0-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e4f0-117">See also</span></span>

- [<span data-ttu-id="2e4f0-118">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="2e4f0-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
