---
title: Limitaciones del componente Timer de formularios Windows Forms &#39; s intervalo propiedad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72af16b7dcb7709dd132a3748a454eda57acc168
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="4aecc-102">Limitaciones del componente Timer de formularios Windows Forms &#39; s intervalo propiedad</span><span class="sxs-lookup"><span data-stu-id="4aecc-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="4aecc-103">Los formularios Windows Forms <xref:System.Windows.Forms.Timer> componente tiene un <xref:System.Windows.Forms.Timer.Interval%2A> propiedad que especifica el número de milisegundos que transcurren entre un evento del temporizador y el siguiente.</span><span class="sxs-lookup"><span data-stu-id="4aecc-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="4aecc-104">A menos que se deshabilite el componente, un temporizador continúa recibiendo el <xref:System.Windows.Forms.Timer.Tick> eventos a intervalos de tiempo aproximadamente iguales.</span><span class="sxs-lookup"><span data-stu-id="4aecc-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="4aecc-105">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4aecc-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="4aecc-106">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="4aecc-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="4aecc-107">La propiedad Interval</span><span class="sxs-lookup"><span data-stu-id="4aecc-107">The Interval Property</span></span>  
 <span data-ttu-id="4aecc-108">El <xref:System.Windows.Forms.Timer.Interval%2A> propiedad tiene algunas limitaciones a tener en cuenta al programar un <xref:System.Windows.Forms.Timer> componente:</span><span class="sxs-lookup"><span data-stu-id="4aecc-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="4aecc-109">Si la aplicación u otra aplicación está realizando grandes exigencias en el sistema, como bucles largos, cálculos intensivos o unidad, red o acceso de puerto, la aplicación no puede obtener los eventos del temporizador con tanta frecuencia como el <xref:System.Windows.Forms.Timer.Interval%2A> especifica la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4aecc-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="4aecc-110">No se garantiza que el intervalo de transcurrir exactamente en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="4aecc-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="4aecc-111">Para garantizar la precisión, el temporizador debe comprobar el reloj del sistema según sea necesario, en lugar de intentar realizar un seguimiento del tiempo acumulado internamente.</span><span class="sxs-lookup"><span data-stu-id="4aecc-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="4aecc-112">La precisión de la <xref:System.Windows.Forms.Timer.Interval%2A> propiedad está en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="4aecc-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="4aecc-113">Algunos equipos proporcionan un contador de alta resolución con una resolución mayor que milisegundos.</span><span class="sxs-lookup"><span data-stu-id="4aecc-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="4aecc-114">La disponibilidad de este tipo de contador depende del hardware del procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="4aecc-114">The availability of such a counter depends on the processor hardware of your computer.</span></span> <span data-ttu-id="4aecc-115">Para obtener más información, vea el artículo 172338, "Cómo a Use QueryPerformanceCounter to Time Code," en Microsoft Knowledge Base en http://support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4aecc-115">For more information, see article 172338, "How To Use QueryPerformanceCounter to Time Code," in the Microsoft Knowledge Base at http://support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aecc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aecc-116">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="4aecc-117">Timer (componente)</span><span class="sxs-lookup"><span data-stu-id="4aecc-117">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="4aecc-118">Información general sobre el componente Timer</span><span class="sxs-lookup"><span data-stu-id="4aecc-118">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
