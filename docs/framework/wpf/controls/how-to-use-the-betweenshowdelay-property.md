---
title: Procedimiento Usar la propiedad BetweenShowDelay
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: ee9c532f8b2eeddb2c798df53e1864e8f543638b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564069"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="4d010-102">Procedimiento Usar la propiedad BetweenShowDelay</span><span class="sxs-lookup"><span data-stu-id="4d010-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="4d010-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> propiedad de tiempo para que la información sobre herramientas aparece rápidamente, con poco o ningún retraso, cuando el usuario mueve el puntero del mouse en una información sobre herramientas directamente a otro.</span><span class="sxs-lookup"><span data-stu-id="4d010-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d010-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d010-104">Example</span></span>  
 <span data-ttu-id="4d010-105">En el ejemplo siguiente, la <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> propiedad está establecida en un segundo (1000 milisegundos) y el <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> se establece en dos segundos (2.000 milisegundos) para la información sobre herramientas de ambos <xref:System.Windows.Shapes.Ellipse> controles.</span><span class="sxs-lookup"><span data-stu-id="4d010-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="4d010-106">Si se muestra la información sobre herramientas para uno de los puntos suspensivos y, a continuación, mueva el puntero del mouse a otra elipse dentro de dos segundos y pausar en él, la información sobre herramientas de la elipse de la segunda muestra inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4d010-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="4d010-107">En cualquiera de los siguientes escenarios, el <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> se aplica, lo que hace que la segunda elipse espera un segundo antes de que aparezca la información sobre herramientas:</span><span class="sxs-lookup"><span data-stu-id="4d010-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="4d010-108">Si el tiempo se tarda en pasar al segundo botón es más de dos segundos.</span><span class="sxs-lookup"><span data-stu-id="4d010-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="4d010-109">Si la información sobre herramientas no está visible al principio del intervalo de tiempo para la primera elipse.</span><span class="sxs-lookup"><span data-stu-id="4d010-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="4d010-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d010-110">See also</span></span>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [<span data-ttu-id="4d010-111">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="4d010-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
- [<span data-ttu-id="4d010-112">Información general de información sobre herramientas</span><span class="sxs-lookup"><span data-stu-id="4d010-112">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
