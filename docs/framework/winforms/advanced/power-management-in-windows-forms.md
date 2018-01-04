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
ms.workload: dotnet
ms.openlocfilehash: a7600ae42194b3333c404d217c2605a226df99e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="power-management-in-windows-forms"></a>Administración de energía en formularios Windows Forms
Las aplicaciones de formularios Windows Forms pueden aprovechar las ventajas de las características de administración de energía en el sistema operativo Windows. Las aplicaciones pueden supervisar el estado de energía de un equipo y realizar una acción cuando se produce un cambio de estado. Por ejemplo, si la aplicación se ejecuta en un equipo portátil, puede deshabilitar determinadas características de la aplicación cuando la carga de la batería del equipo se encuentra en un nivel determinado.  
  
 El [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona un <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> evento que tiene lugar siempre que hay un cambio en el estado de energía, como cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de alimentación de CA o el estado de la batería. El <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad de la <xref:System.Windows.Forms.SystemInformation> clase puede ser usado para consultar el estado actual, tal como se muestra en el ejemplo de código siguiente.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Además el <xref:System.Windows.Forms.BatteryChargeStatus> enumeraciones, el <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> propiedad también contiene enumeraciones para determinar la capacidad de la batería (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) y porcentaje de carga de batería (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Puede usar el <xref:System.Windows.Forms.Application.SetSuspendState%2A> método de la <xref:System.Windows.Forms.Application> para poner un equipo en hibernación o modo de suspensión. Si el `force` argumento está establecido en `false`, el sistema operativo difundirá un evento a todas las aplicaciones que solicite permiso para suspender. Si el `disableWakeEvent` argumento está establecido en `true`, el sistema operativo deshabilita todos los eventos de activación.  
  
 En el ejemplo de código siguiente se muestra cómo poner un equipo en hibernación.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
