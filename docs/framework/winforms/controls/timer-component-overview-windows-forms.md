---
title: Información general sobre el componente Timer (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 5bef0ba87d6a496acf7575965128be2b20b437ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962622"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="f9b40-102">Información general sobre el componente Timer (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f9b40-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="f9b40-103">El componente <xref:System.Windows.Forms.Timer> de Windows Forms produce un evento a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="f9b40-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="f9b40-104">Este componente está diseñado para un entorno de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f9b40-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="f9b40-105">Si necesita un temporizador que sea adecuado para un entorno de servidor, consulte [Introducción a los temporizadores basados en servidor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="f9b40-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="f9b40-106">Los eventos, métodos y propiedades de clave</span><span class="sxs-lookup"><span data-stu-id="f9b40-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="f9b40-107">La longitud de los intervalos se define mediante el <xref:System.Windows.Forms.Timer.Interval%2A> propiedad, cuyo valor se expresa en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="f9b40-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="f9b40-108">Cuando el componente está habilitado, el <xref:System.Windows.Forms.Timer.Tick> evento se desencadena cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="f9b40-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="f9b40-109">Esto es donde puede agregar código que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="f9b40-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="f9b40-110">Para obtener más información, vea [Cómo: Ejecutar procedimientos a intervalos establecidos con el componente Timer de Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="f9b40-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="f9b40-111">Los métodos clave de la <xref:System.Windows.Forms.Timer> componente son <xref:System.Windows.Forms.Timer.Start%2A> y <xref:System.Windows.Forms.Timer.Stop%2A>, que activa el temporizador y desactiva.</span><span class="sxs-lookup"><span data-stu-id="f9b40-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="f9b40-112">Cuando el temporizador está desactivado, lo reinicia; No hay ninguna manera de pausar una <xref:System.Windows.Forms.Timer> componente.</span><span class="sxs-lookup"><span data-stu-id="f9b40-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b40-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9b40-113">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="f9b40-114">Timer (componente)</span><span class="sxs-lookup"><span data-stu-id="f9b40-114">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="f9b40-115">Limitaciones de la propiedad Interval del componente Timer de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f9b40-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](limitations-of-the-timer-component-interval-property.md)
