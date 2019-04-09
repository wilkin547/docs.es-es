---
title: Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 54782c4e0460ba1ba9b8a870b8f60f08a76340b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125177"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="37fca-102">Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37fca-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="37fca-103">Los formularios de Windows <xref:System.Windows.Forms.Timer> componente tiene un <xref:System.Windows.Forms.Timer.Interval%2A> propiedad que especifica el número de milisegundos que transcurren entre un evento del temporizador y el siguiente.</span><span class="sxs-lookup"><span data-stu-id="37fca-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="37fca-104">A menos que el componente está deshabilitado, un temporizador continúa recibiendo el <xref:System.Windows.Forms.Timer.Tick> eventos a intervalos de tiempo aproximadamente iguales.</span><span class="sxs-lookup"><span data-stu-id="37fca-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="37fca-105">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="37fca-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="37fca-106">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="37fca-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="37fca-107">La propiedad Interval</span><span class="sxs-lookup"><span data-stu-id="37fca-107">The Interval Property</span></span>  
 <span data-ttu-id="37fca-108">El <xref:System.Windows.Forms.Timer.Interval%2A> propiedad tiene algunas limitaciones a tener en cuenta al programar un <xref:System.Windows.Forms.Timer> componente:</span><span class="sxs-lookup"><span data-stu-id="37fca-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="37fca-109">Si la aplicación u otra aplicación está realizando fuertes exigencias del sistema, como bucles largos, cálculos intensivos o unidad, red o acceso a los puertos, la aplicación no es posible que obtenga los eventos del temporizador con tanta frecuencia como los <xref:System.Windows.Forms.Timer.Interval%2A> especifica la propiedad.</span><span class="sxs-lookup"><span data-stu-id="37fca-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="37fca-110">El intervalo no se garantiza que transcurran exactamente en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="37fca-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="37fca-111">Para garantizar la precisión, el temporizador debe comprobar el reloj del sistema según sea necesario, en lugar de intentar realizar un seguimiento del tiempo acumulado internamente.</span><span class="sxs-lookup"><span data-stu-id="37fca-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="37fca-112">La precisión de la <xref:System.Windows.Forms.Timer.Interval%2A> propiedad está en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="37fca-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="37fca-113">Algunos equipos proporcionan un contador de alta resolución que tenga una resolución mayor que milisegundos.</span><span class="sxs-lookup"><span data-stu-id="37fca-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="37fca-114">La disponibilidad de este tipo de contador depende del hardware del procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="37fca-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="37fca-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="37fca-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="37fca-116">Componente Timer</span><span class="sxs-lookup"><span data-stu-id="37fca-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="37fca-117">Información general sobre el componente Timer</span><span class="sxs-lookup"><span data-stu-id="37fca-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
