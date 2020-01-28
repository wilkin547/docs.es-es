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
# <a name="power-management-in-windows-forms"></a>Administración de energía en Windows Forms
Las aplicaciones Windows Forms pueden beneficiarse de las características de administración de energía del sistema operativo Windows. Las aplicaciones pueden supervisar el estado de energía de un equipo y actuar cuando se produce un cambio de estado. Por ejemplo, si la aplicación se ejecuta en un equipo portátil, es posible que desee deshabilitar ciertas características de la aplicación cuando la carga de la batería del equipo esté bajo un nivel determinado.  
  
 El .NET Framework proporciona un evento de <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> que tiene lugar siempre que se produce un cambio en el estado de la energía, como cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de alimentación o la batería de CA. La propiedad <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> de la clase <xref:System.Windows.Forms.SystemInformation> se puede utilizar para consultar el estado actual, como se muestra en el ejemplo de código siguiente.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Además de las enumeraciones de <xref:System.Windows.Forms.BatteryChargeStatus>, la propiedad <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> también contiene enumeraciones para determinar la capacidad de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) y el porcentaje de carga de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Puede usar el método <xref:System.Windows.Forms.Application.SetSuspendState%2A> del <xref:System.Windows.Forms.Application> para poner un equipo en modo de hibernación o de suspensión. Si el argumento `force` está establecido en `false`, el sistema operativo difundirá un evento a todas las aplicaciones que soliciten permiso para suspender. Si el argumento `disableWakeEvent` está establecido en `true`, el sistema operativo deshabilita todos los eventos de reactivación.  
  
 En el ejemplo de código siguiente se muestra cómo poner un equipo en hibernación.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
