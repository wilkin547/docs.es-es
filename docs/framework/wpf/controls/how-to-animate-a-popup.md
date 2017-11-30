---
title: "Cómo: Animar un control Popup"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 276c1a54cfdddcde84c0702f4e84f1dc6174bbda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="df098-102">Cómo: Animar un control Popup</span><span class="sxs-lookup"><span data-stu-id="df098-102">How to: Animate a Popup</span></span>
<span data-ttu-id="df098-103">Este ejemplo muestra dos maneras de animar un <xref:System.Windows.Controls.Primitives.Popup> control.</span><span class="sxs-lookup"><span data-stu-id="df098-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df098-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df098-104">Example</span></span>  
 <span data-ttu-id="df098-105">El ejemplo siguiente se establece la <xref:System.Windows.Controls.Primitives.PopupAnimation> en un valor de <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, lo que hace que la <xref:System.Windows.Controls.Primitives.Popup> en "presentación" cuando aparezca.</span><span class="sxs-lookup"><span data-stu-id="df098-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="df098-106">Para girar el <xref:System.Windows.Controls.Primitives.Popup>, este ejemplo se asigna un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad en el <xref:System.Windows.Controls.Canvas>, que es el elemento secundario de la <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="df098-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="df098-107">Para que la transformación funcione correctamente, debe establecer en el ejemplo el <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="df098-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="df098-108">Además, el <xref:System.Windows.FrameworkElement.Margin%2A> en el <xref:System.Windows.Controls.Canvas> contenido debe especificar el suficiente espacio para el <xref:System.Windows.Controls.Primitives.Popup> va a girar.</span><span class="sxs-lookup"><span data-stu-id="df098-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="df098-109">El siguiente ejemplo se muestra cómo un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, que se produce cuando un <xref:System.Windows.Controls.Button> se hace clic, desencadenadores el <xref:System.Windows.Media.Animation.Storyboard> que comienza la animación.</span><span class="sxs-lookup"><span data-stu-id="df098-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="df098-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="df098-110">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="df098-111">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="df098-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [<span data-ttu-id="df098-112">Información general sobre el control Popup</span><span class="sxs-lookup"><span data-stu-id="df098-112">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)
