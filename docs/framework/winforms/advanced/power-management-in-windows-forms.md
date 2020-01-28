---
title: Administración de energía
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746853"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="437f6-102">Administración de energía en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="437f6-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="437f6-103">Las aplicaciones Windows Forms pueden beneficiarse de las características de administración de energía del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="437f6-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="437f6-104">Las aplicaciones pueden supervisar el estado de energía de un equipo y actuar cuando se produce un cambio de estado.</span><span class="sxs-lookup"><span data-stu-id="437f6-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="437f6-105">Por ejemplo, si la aplicación se ejecuta en un equipo portátil, es posible que desee deshabilitar ciertas características de la aplicación cuando la carga de la batería del equipo esté bajo un nivel determinado.</span><span class="sxs-lookup"><span data-stu-id="437f6-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="437f6-106">El .NET Framework proporciona un evento de <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> que tiene lugar siempre que se produce un cambio en el estado de la energía, como cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de alimentación o la batería de CA.</span><span class="sxs-lookup"><span data-stu-id="437f6-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="437f6-107">La propiedad <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> de la clase <xref:System.Windows.Forms.SystemInformation> se puede utilizar para consultar el estado actual, como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="437f6-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="437f6-108">Además de las enumeraciones de <xref:System.Windows.Forms.BatteryChargeStatus>, la propiedad <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> también contiene enumeraciones para determinar la capacidad de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) y el porcentaje de carga de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="437f6-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="437f6-109">Puede usar el método <xref:System.Windows.Forms.Application.SetSuspendState%2A> del <xref:System.Windows.Forms.Application> para poner un equipo en modo de hibernación o de suspensión.</span><span class="sxs-lookup"><span data-stu-id="437f6-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="437f6-110">Si el argumento `force` está establecido en `false`, el sistema operativo difundirá un evento a todas las aplicaciones que soliciten permiso para suspender.</span><span class="sxs-lookup"><span data-stu-id="437f6-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="437f6-111">Si el argumento `disableWakeEvent` está establecido en `true`, el sistema operativo deshabilita todos los eventos de reactivación.</span><span class="sxs-lookup"><span data-stu-id="437f6-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="437f6-112">En el ejemplo de código siguiente se muestra cómo poner un equipo en hibernación.</span><span class="sxs-lookup"><span data-stu-id="437f6-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="437f6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="437f6-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
