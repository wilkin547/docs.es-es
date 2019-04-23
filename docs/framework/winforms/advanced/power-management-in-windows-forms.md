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
ms.openlocfilehash: 6bb9b4f30a88ece93b17ff2510087b220d538738
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979724"
---
# <a name="power-management-in-windows-forms"></a>Administración de energía en formularios Windows Forms
Las aplicaciones de Windows Forms pueden aprovechar las ventajas de las características de administración de energía en el sistema operativo de Windows. Las aplicaciones pueden supervisar el estado de alimentación de un equipo y actuar cuando se produce un cambio de estado. Por ejemplo, si la aplicación se ejecuta en un equipo portátil, es posible que desee deshabilitar determinadas características de la aplicación cuando la carga de batería del equipo cae por debajo de un nivel determinado.  
  
 El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento que tiene lugar siempre que haya un cambio en el estado de energía, como cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de alimentación de CA o el estado de la batería. El <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad de la <xref:System.Windows.Forms.SystemInformation> puede ser la clase se usa para consultar el estado actual, tal como se muestra en el ejemplo de código siguiente.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Además el <xref:System.Windows.Forms.BatteryChargeStatus> enumeraciones, el <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad también contiene enumeraciones para determinar la capacidad de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) y porcentaje de carga de batería (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Puede usar el <xref:System.Windows.Forms.Application.SetSuspendState%2A> método de la <xref:System.Windows.Forms.Application> para poner un equipo en hibernación o modo de suspensión. Si el `force` argumento está establecido en `false`, el sistema operativo difundirá a todas las aplicaciones que solicite permiso para suspender un evento. Si el `disableWakeEvent` argumento está establecido en `true`, el sistema operativo deshabilita todos los eventos de activación.  
  
 El ejemplo de código siguiente muestra cómo poner un equipo en hibernación.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
