---
title: Información general sobre el componente Timer
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742774"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="cc155-102">Información general sobre el componente Timer (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cc155-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="cc155-103">El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="cc155-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="cc155-104">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cc155-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="cc155-105">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="cc155-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="cc155-106">Propiedades, métodos y eventos clave</span><span class="sxs-lookup"><span data-stu-id="cc155-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="cc155-107">La longitud de los intervalos se define mediante la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>, cuyo valor se encuentra en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="cc155-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="cc155-108">Cuando el componente está habilitado, el evento de <xref:System.Windows.Forms.Timer.Tick> se genera cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="cc155-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="cc155-109">Aquí es donde agregaría el código que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="cc155-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="cc155-110">Para obtener más información, consulte [Cómo: ejecutar procedimientos a intervalos establecidos con el componente Timer de Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="cc155-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="cc155-111">Los métodos clave del componente <xref:System.Windows.Forms.Timer> son <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, lo que activa y desactiva el temporizador.</span><span class="sxs-lookup"><span data-stu-id="cc155-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="cc155-112">Cuando el temporizador se desactiva, se restablece; no hay ninguna manera de pausar un componente de <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="cc155-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc155-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc155-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="cc155-114">Timer (componente)</span><span class="sxs-lookup"><span data-stu-id="cc155-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="cc155-115">Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc155-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
