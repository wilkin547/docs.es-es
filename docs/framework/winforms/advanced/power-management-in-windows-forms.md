---
title: "Administración de energía en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e12f39a63a4f81e6deec4512a4e18ad2bda7e5e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="3b6ab-102">Administración de energía en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b6ab-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="3b6ab-103">Las aplicaciones de formularios Windows Forms pueden aprovechar las ventajas de las características de administración de energía en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="3b6ab-104">Las aplicaciones pueden supervisar el estado de energía de un equipo y realizar una acción cuando se produce un cambio de estado.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="3b6ab-105">Por ejemplo, si la aplicación se ejecuta en un equipo portátil, puede deshabilitar determinadas características de la aplicación cuando la carga de la batería del equipo se encuentra en un nivel determinado.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="3b6ab-106">El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento que tiene lugar siempre que hay un cambio en el estado de energía, como cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de alimentación de CA o el estado de la batería.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="3b6ab-107">El <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad de la <xref:System.Windows.Forms.SystemInformation> clase puede ser usado para consultar el estado actual, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="3b6ab-108">Además el <xref:System.Windows.Forms.BatteryChargeStatus> enumeraciones, el <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad también contiene enumeraciones para determinar la capacidad de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) y porcentaje de carga de batería (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="3b6ab-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="3b6ab-109">Puede usar el <xref:System.Windows.Forms.Application.SetSuspendState%2A> método de la <xref:System.Windows.Forms.Application> para poner un equipo en hibernación o modo de suspensión.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="3b6ab-110">Si el `force` argumento está establecido en `false`, el sistema operativo difundirá un evento a todas las aplicaciones que solicite permiso para suspender.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="3b6ab-111">Si el `disableWakeEvent` argumento está establecido en `true`, el sistema operativo deshabilita todos los eventos de activación.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="3b6ab-112">En el ejemplo de código siguiente se muestra cómo poner un equipo en hibernación.</span><span class="sxs-lookup"><span data-stu-id="3b6ab-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3b6ab-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b6ab-113">See Also</span></span>  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
