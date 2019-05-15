---
title: Administración de energía en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 36c152a9e388fe61b1c82a8783bf74bbe6c8f123
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592516"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="93ae6-102">Administración de energía en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93ae6-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="93ae6-103">Las aplicaciones de Windows Forms pueden aprovechar las ventajas de las características de administración de energía en el sistema operativo de Windows.</span><span class="sxs-lookup"><span data-stu-id="93ae6-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="93ae6-104">Las aplicaciones pueden supervisar el estado de alimentación de un equipo y actuar cuando se produce un cambio de estado.</span><span class="sxs-lookup"><span data-stu-id="93ae6-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="93ae6-105">Por ejemplo, si la aplicación se ejecuta en un equipo portátil, es posible que desee deshabilitar determinadas características de la aplicación cuando la carga de batería del equipo cae por debajo de un nivel determinado.</span><span class="sxs-lookup"><span data-stu-id="93ae6-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="93ae6-106">.NET Framework proporciona un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento que tiene lugar siempre que haya un cambio en el estado de energía, como cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de alimentación de CA o el estado de la batería.</span><span class="sxs-lookup"><span data-stu-id="93ae6-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="93ae6-107">El <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad de la <xref:System.Windows.Forms.SystemInformation> puede ser la clase se usa para consultar el estado actual, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="93ae6-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="93ae6-108">Además el <xref:System.Windows.Forms.BatteryChargeStatus> enumeraciones, el <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad también contiene enumeraciones para determinar la capacidad de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) y porcentaje de carga de batería (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="93ae6-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="93ae6-109">Puede usar el <xref:System.Windows.Forms.Application.SetSuspendState%2A> método de la <xref:System.Windows.Forms.Application> para poner un equipo en hibernación o modo de suspensión.</span><span class="sxs-lookup"><span data-stu-id="93ae6-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="93ae6-110">Si el `force` argumento está establecido en `false`, el sistema operativo difundirá a todas las aplicaciones que solicite permiso para suspender un evento.</span><span class="sxs-lookup"><span data-stu-id="93ae6-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="93ae6-111">Si el `disableWakeEvent` argumento está establecido en `true`, el sistema operativo deshabilita todos los eventos de activación.</span><span class="sxs-lookup"><span data-stu-id="93ae6-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="93ae6-112">El ejemplo de código siguiente muestra cómo poner un equipo en hibernación.</span><span class="sxs-lookup"><span data-stu-id="93ae6-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="93ae6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="93ae6-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
