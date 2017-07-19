---
title: "Power Management in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "battery states"
  - "power states"
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Power Management in Windows Forms
Las aplicaciones de Windows Forms pueden aprovecharse de las características de administración de energía del sistema operativo Windows.  Las aplicaciones pueden supervisar el estado energético de un equipo y realizar una acción cuando se produzca un cambio de estado.  Por ejemplo, si la aplicación se ejecuta en un equipo portátil, conviene deshabilitar algunas características de la aplicación si la carga de la batería del equipo queda por debajo de un nivel determinado.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona un evento <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> que tiene lugar siempre que haya un cambio en el estado de energía, ya sea cuando un usuario suspende o reanuda el sistema operativo, o cuando cambia el estado de la alimentación de CA o el estado de la batería.  La propiedad <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> de la clase <xref:System.Windows.Forms.SystemInformation> se puede utilizar para consultar el estado actual, tal como se muestra en el código siguiente:  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Además de las enumeraciones <xref:System.Windows.Forms.BatteryChargeStatus>, la propiedad <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> también contiene enumeraciones para determinar la capacidad de la batería \(<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>\) y el porcentaje de carga de la batería \(<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>\).  
  
 Puede utilizar el método <xref:System.Windows.Forms.Application.SetSuspendState%2A> de <xref:System.Windows.Forms.Application> para poner un equipo en hibernación o en el modo de suspensión.  Si el argumento `force` se establece en `false`, el sistema operativo difundirá un evento a todas las aplicaciones que soliciten permiso para suspender.  Si el argumento `disableWakeEvent` se establece en `true`, el sistema operativo deshabilitará todos los eventos de activación.  
  
 El ejemplo de código siguiente muestra cómo poner un equipo en hibernación.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## Vea también  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>   
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>   
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>   
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>