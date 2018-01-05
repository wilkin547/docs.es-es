---
title: "Cómo: Animar en un estilo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2aabe24b77a9016b5b8119646c80ea84eb73acb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="26501-102">Cómo: Animar en un estilo</span><span class="sxs-lookup"><span data-stu-id="26501-102">How to: Animate in a Style</span></span>
<span data-ttu-id="26501-103">En este ejemplo se muestra cómo animar propiedades dentro de un estilo.</span><span class="sxs-lookup"><span data-stu-id="26501-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="26501-104">Al animar dentro de un estilo, se puede destinar solo el elemento de marco de trabajo para el que se define el estilo directamente.</span><span class="sxs-lookup"><span data-stu-id="26501-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="26501-105">Que tenga como destino un objeto freezable, debe "establecer una relación" desde una propiedad del elemento de estilo.</span><span class="sxs-lookup"><span data-stu-id="26501-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>  
  
 <span data-ttu-id="26501-106">En el ejemplo siguiente, se define dentro de un estilo varias animaciones y se aplican a un <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="26501-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="26501-107">Cuando el usuario mueve el mouse sobre el botón, fundido de opaco a parcialmente translúcido y viceversa, repetidamente.</span><span class="sxs-lookup"><span data-stu-id="26501-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="26501-108">Cuando el usuario mueve el mouse fuera del botón, se vuelve completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="26501-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="26501-109">Cuando se hace clic en el botón, su color de fondo cambia de color naranja en blanco y vuelva a hacer.</span><span class="sxs-lookup"><span data-stu-id="26501-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="26501-110">Dado que la <xref:System.Windows.Media.SolidColorBrush> utilizado para pintar el botón no se puede establecer como destino directamente, se tiene acceso estableciendo una relación en el botón <xref:System.Windows.Controls.Control.Background%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="26501-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26501-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26501-111">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 <span data-ttu-id="26501-112">Tenga en cuenta que al animar dentro de un estilo, es posible a los objetos de destino que no existen.</span><span class="sxs-lookup"><span data-stu-id="26501-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="26501-113">Por ejemplo, supongamos que usa su estilo de un <xref:System.Windows.Media.SolidColorBrush> establecer la propiedad de fondo de un botón, pero en algún momento el estilo se invalida y se establece el fondo del botón con un <xref:System.Windows.Media.LinearGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="26501-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="26501-114">Si intenta animar el <xref:System.Windows.Media.SolidColorBrush> , no se iniciará una excepción; la animación simplemente se producirá un error en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="26501-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>  
  
 <span data-ttu-id="26501-115">Para obtener más información acerca de la sintaxis de destino de guión gráfico, vea el [información general de guiones gráficos](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="26501-115">Fore more information about storyboard targeting syntax, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span> <span data-ttu-id="26501-116">Para obtener más información acerca de la animación, consulte el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="26501-116">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="26501-117">Para obtener más información sobre los estilos, vea el [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="26501-117">For more information about styles, see the [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>
