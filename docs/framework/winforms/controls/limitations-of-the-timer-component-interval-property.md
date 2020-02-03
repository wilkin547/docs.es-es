---
title: Limitaciones de la propiedad Interval del componente Timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745231"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="0d496-102">Limitaciones de la propiedad Interval del componente Timer de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d496-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="0d496-103">El componente <xref:System.Windows.Forms.Timer> de Windows Forms tiene una propiedad <xref:System.Windows.Forms.Timer.Interval%2A> que especifica el número de milisegundos que transcurren entre un evento de temporizador y el siguiente.</span><span class="sxs-lookup"><span data-stu-id="0d496-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="0d496-104">A menos que el componente esté deshabilitado, un temporizador sigue recibiendo el evento <xref:System.Windows.Forms.Timer.Tick> a intervalos de tiempo aproximadamente iguales.</span><span class="sxs-lookup"><span data-stu-id="0d496-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="0d496-105">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0d496-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="0d496-106">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0d496-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="0d496-107">La propiedad Interval</span><span class="sxs-lookup"><span data-stu-id="0d496-107">The Interval Property</span></span>  
 <span data-ttu-id="0d496-108">La propiedad <xref:System.Windows.Forms.Timer.Interval%2A> tiene algunas limitaciones que se deben tener en cuenta al programar un componente <xref:System.Windows.Forms.Timer>:</span><span class="sxs-lookup"><span data-stu-id="0d496-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="0d496-109">Si su aplicación u otra aplicación está realizando demandas pesadas en el sistema (por ejemplo, bucles largos, cálculos intensivos o acceso de unidad, red o puerto), es posible que la aplicación no obtenga eventos de temporizador con la frecuencia que especifica la propiedad <xref:System.Windows.Forms.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d496-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="0d496-110">No se garantiza que el intervalo transcurra exactamente en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0d496-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="0d496-111">Para garantizar la precisión, el temporizador debe comprobar el reloj del sistema según sea necesario, en lugar de intentar realizar un seguimiento de la hora acumulada internamente.</span><span class="sxs-lookup"><span data-stu-id="0d496-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="0d496-112">La precisión de la propiedad <xref:System.Windows.Forms.Timer.Interval%2A> se encuentra en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="0d496-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="0d496-113">Algunos equipos proporcionan un contador de alta resolución que tiene una resolución superior a milisegundos.</span><span class="sxs-lookup"><span data-stu-id="0d496-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="0d496-114">La disponibilidad de este contador depende del hardware del procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="0d496-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d496-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d496-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="0d496-116">Timer (componente)</span><span class="sxs-lookup"><span data-stu-id="0d496-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="0d496-117">Información general sobre el componente Timer</span><span class="sxs-lookup"><span data-stu-id="0d496-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
