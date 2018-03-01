---
title: "Información general del control TrackBar (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="2dd35-102">Información general del control TrackBar (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="2dd35-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="2dd35-103">Los formularios Windows Forms <xref:System.Windows.Forms.TrackBar> control (a veces denominado control "deslizante") se utiliza para navegar por una gran cantidad de información o para ajustar visualmente una configuración numérica.</span><span class="sxs-lookup"><span data-stu-id="2dd35-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="2dd35-104">El <xref:System.Windows.Forms.TrackBar> control tiene dos partes: el control de posición, también conocido como control deslizante y las marcas de graduación.</span><span class="sxs-lookup"><span data-stu-id="2dd35-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="2dd35-105">El cuadro de desplazamiento es la parte que se puede ajustar.</span><span class="sxs-lookup"><span data-stu-id="2dd35-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="2dd35-106">Su posición corresponde a la <xref:System.Windows.Forms.TrackBar.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2dd35-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="2dd35-107">Las marcas de graduación son indicadores visuales que se llevan a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="2dd35-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="2dd35-108">La barra de seguimiento se mueve en incrementos que se especifiquen y puede alinearse horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="2dd35-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="2dd35-109">Por ejemplo, puede usar la barra de seguimiento para controlar la velocidad de velocidad o el mouse de parpadeo de cursor para un sistema.</span><span class="sxs-lookup"><span data-stu-id="2dd35-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="2dd35-110">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="2dd35-110">Key Properties</span></span>  
 <span data-ttu-id="2dd35-111">Las propiedades de clave de la <xref:System.Windows.Forms.TrackBar> control son <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, y <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span><span class="sxs-lookup"><span data-stu-id="2dd35-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="2dd35-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A>es el espaciado de las marcas de paso.</span><span class="sxs-lookup"><span data-stu-id="2dd35-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="2dd35-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A>y <xref:System.Windows.Forms.TrackBar.Maximum%2A> son los valores mínimo y máximo que se pueden representar en la barra de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2dd35-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="2dd35-114">Otras dos propiedades importantes son <xref:System.Windows.Forms.TrackBar.SmallChange%2A> y <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span><span class="sxs-lookup"><span data-stu-id="2dd35-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="2dd35-115">El valor de la <xref:System.Windows.Forms.TrackBar.SmallChange%2A> propiedad es el número de posiciones que se desplaza el control de posición en respuesta a la presionar la tecla flecha izquierda o derecha.</span><span class="sxs-lookup"><span data-stu-id="2dd35-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="2dd35-116">El valor de la <xref:System.Windows.Forms.TrackBar.LargeChange%2A> propiedad es el número de posiciones en el cuadro de desplazamiento mueve como respuesta a la presionar la tecla RE PÁG o AV PÁG, o en respuesta a mouse (ratón) haga clic en la barra de seguimiento a ambos lados del control.</span><span class="sxs-lookup"><span data-stu-id="2dd35-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd35-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dd35-117">See Also</span></span>  
 <xref:System.Windows.Forms.TrackBar>  
 [<span data-ttu-id="2dd35-118">TrackBar (control)</span><span class="sxs-lookup"><span data-stu-id="2dd35-118">TrackBar Control</span></span>](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
