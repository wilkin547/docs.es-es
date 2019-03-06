---
title: Filtrar Animar un control Popup
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: ed5edf298e59d6a9adddc03fc21de1900c7ee8e9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372846"
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="72263-102">Procedimiento Animar un control Popup</span><span class="sxs-lookup"><span data-stu-id="72263-102">How to: Animate a Popup</span></span>
<span data-ttu-id="72263-103">En este ejemplo se muestra dos maneras de animar una <xref:System.Windows.Controls.Primitives.Popup> control.</span><span class="sxs-lookup"><span data-stu-id="72263-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72263-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72263-104">Example</span></span>  
 <span data-ttu-id="72263-105">El ejemplo siguiente se establece la <xref:System.Windows.Controls.Primitives.PopupAnimation> propiedad con un valor de <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, lo que hace que el <xref:System.Windows.Controls.Primitives.Popup> a "diapositiva en" cuando aparezca.</span><span class="sxs-lookup"><span data-stu-id="72263-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="72263-106">Para girar el <xref:System.Windows.Controls.Primitives.Popup>, este ejemplo se asigna un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad en el <xref:System.Windows.Controls.Canvas>, que es el elemento secundario de la <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="72263-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="72263-107">Para que la transformación funcione correctamente, debe establecer en el ejemplo el <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="72263-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="72263-108">Además, el <xref:System.Windows.FrameworkElement.Margin%2A> en el <xref:System.Windows.Controls.Canvas> contenido debe especificar el espacio suficiente para el <xref:System.Windows.Controls.Primitives.Popup> se va a girar.</span><span class="sxs-lookup"><span data-stu-id="72263-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="72263-109">El ejemplo siguiente se muestra cómo un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, que se produce cuando un <xref:System.Windows.Controls.Button> se hace clic en, los desencadenadores del <xref:System.Windows.Media.Animation.Storyboard> que comienza la animación.</span><span class="sxs-lookup"><span data-stu-id="72263-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="72263-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="72263-110">See also</span></span>
- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="72263-111">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="72263-111">How-to Topics</span></span>](popup-how-to-topics.md)
- [<span data-ttu-id="72263-112">Información general sobre el control Popup</span><span class="sxs-lookup"><span data-stu-id="72263-112">Popup Overview</span></span>](popup-overview.md)
