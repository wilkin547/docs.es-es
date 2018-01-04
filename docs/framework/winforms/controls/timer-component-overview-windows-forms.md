---
title: "Información general sobre el componente Timer (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a467cb266f284e2bfdedbb5061f26231736af2b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="32de9-102">Información general sobre el componente Timer (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="32de9-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="32de9-103">El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="32de9-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="32de9-104">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="32de9-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="32de9-105">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="32de9-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="32de9-106">Eventos, métodos y propiedades clave</span><span class="sxs-lookup"><span data-stu-id="32de9-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="32de9-107">La longitud de los intervalos está definida por el <xref:System.Windows.Forms.Timer.Interval%2A> propiedad, cuyo valor se expresa en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="32de9-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="32de9-108">Cuando el componente está habilitado, el <xref:System.Windows.Forms.Timer.Tick> evento se desencadena cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="32de9-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="32de9-109">Esto es donde puede agregar código que se ejecute.</span><span class="sxs-lookup"><span data-stu-id="32de9-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="32de9-110">Para obtener más información, consulte [Cómo: ejecutar procedimientos a intervalos establecido con el componente Timer de formularios Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="32de9-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="32de9-111">Los métodos principales de la <xref:System.Windows.Forms.Timer> componente <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, que activar el temporizador y desactivar.</span><span class="sxs-lookup"><span data-stu-id="32de9-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="32de9-112">Cuando el temporizador está desactivado, se reinicia; No hay ninguna manera de poner en pausa un <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="32de9-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32de9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="32de9-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="32de9-114">Timer (componente)</span><span class="sxs-lookup"><span data-stu-id="32de9-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="32de9-115">Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="32de9-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
