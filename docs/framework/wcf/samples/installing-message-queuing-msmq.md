---
title: Instalar Message Queuing (MSMQ)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a7ee646c2f6b20410c493ee139f08d11fc55d54
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="installing-message-queuing-msmq"></a>Instalar Message Queuing (MSMQ)
Los procedimientos siguientes muestran cómo instalar Message Queuing 4.0 y Message Queuing 3.0.  
  
> [!NOTE]
>  Message Queuing 4.0 no está disponible en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] ni [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Para instalar Message Queuing 4.0 en Windows Server 2008 o Windows Server 2008 R2  
  
1.  En el administrador del servidor, haga clic en **características**.  
  
2.  En el panel derecho, en **resumen de características**, haga clic en **agregar características**.  
  
3.  En la ventana resultante, expanda **Message Queue Server**.  
  
4.  Expanda **servicios puesta en cola de mensajes**.  
  
5.  Haga clic en **integración de servicios de directorio** (para los equipos unidos a un dominio), a continuación, haga clic en **compatibilidad con HTTP**.  
  
6.  Haga clic en **siguiente**, a continuación, haga clic en **instalar**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Para instalar Message Queuing 4.0 en Windows 7 o Windows Vista  
  
1.  Abra **Panel de Control**.  
  
2.  Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
3.  Expanda Microsoft Message Queuing (MSMQ), expanda Núcleo de Microsoft Message Queuing (MSMQ) y, a continuación, active las casillas para que se instalen las siguientes características de Message Queuing:  
  
    -   Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio).  
  
    -   Compatibilidad con MSMQ HTTP.  
  
4.  Haga clic en **Aceptar**.  
  
5.  Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Para instalar Message Queuing 3.0 en Windows XP y Windows Server 2003  
  
1.  Abra **Panel de Control**.  
  
2.  Haga clic en **agregar o quitar programas** y, a continuación, haga clic en **agregar componentes de Windows**.  
  
3.  Seleccione Message Queue Server y haga clic en **detalles**.  
  
    > [!NOTE]
    >  Si ejecuta [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], seleccione Servidor de aplicaciones para obtener acceso a Message Queuing.  
  
4.  Asegúrese de que la opción de compatibilidad HTTP con MSMQ está seleccionada en la página de detalles.  
  
5.  Haga clic en **Aceptar** para salir de la página de detalles y, a continuación, haga clic en **siguiente**. Complete la instalación.  
  
6.  Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de instalación](../../../../docs/framework/wcf/samples/set-up-instructions.md)
