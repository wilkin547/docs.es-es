---
title: Procedimiento Aplicar animaciones a texto
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 38aa432fecc5b5e10d8eb90be9c1c596728ed613
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108217"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="f7ea3-102">Procedimiento Aplicar animaciones a texto</span><span class="sxs-lookup"><span data-stu-id="f7ea3-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="f7ea3-103">Las animaciones pueden modificar la presentación y la apariencia del texto en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="f7ea3-104">En los ejemplos siguientes usan diferentes tipos de animaciones para influir en la presentación del texto en un <xref:System.Windows.Controls.TextBlock> control.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ea3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7ea3-105">Example</span></span>  
 <span data-ttu-id="f7ea3-106">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el ancho del bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="f7ea3-107">El valor del ancho cambia del ancho del bloque de texto a 0 durante 10 segundos y, a continuación, invierte los valores de ancho y continúa.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="f7ea3-108">Este tipo de animación crea un efecto de barrido.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="f7ea3-109">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la opacidad del bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="f7ea3-110">El valor de opacidad cambia de 1,0 a 0 durante 5 segundos y, a continuación, invierte los valores de opacidad y continúa.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="f7ea3-111">El siguiente diagrama muestra el efecto de la <xref:System.Windows.Controls.TextBlock> control cambia su opacidad de `1.00` a `0.00` durante el intervalo de 5 segundos definido por el <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 ![Texto cuya opacidad cambia de 1,00 a 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  
   
 <span data-ttu-id="f7ea3-113">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.ColorAnimation> para animar el color de primer plano del bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-113">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="f7ea3-114">El valor de color de primer plano cambia de un color a un segundo color durante 5 segundos y, a continuación, invierte los valores de color y continúa.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-114">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="f7ea3-115">En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para girar el bloque de texto.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-115">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="f7ea3-116">El bloque de texto realiza una rotación completa durante 20 segundos y, a continuación, sigue repitiendo la rotación.</span><span class="sxs-lookup"><span data-stu-id="f7ea3-116">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="f7ea3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7ea3-117">See also</span></span>

- [<span data-ttu-id="f7ea3-118">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="f7ea3-118">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
