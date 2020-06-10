---
title: Instalar Message Queuing (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: 1bf79ed5dbcb9f2ace903260cc440e77df3aef09
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592299"
---
# <a name="installing-message-queuing-msmq"></a>Instalar Message Queuing (MSMQ)
Los procedimientos siguientes muestran cómo instalar Message Queuing 4.0 y Message Queuing 3.0.  
  
> [!NOTE]
> Message Queue Server 4,0 no está disponible en Windows XP y Windows Server 2003.  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a>Para instalar Message Queuing 4.0 en Windows Server 2008 o Windows Server 2008 R2  
  
1. En Administrador del servidor, haga clic en **características**.  
  
2. En el panel derecho, en **Resumen de características**, haga clic en **Agregar características**.  
  
3. En la ventana resultante, expanda **Message Queue Server**.  
  
4. Expanda **servicios de Message Queue Server**.  
  
5. Haga clic en **integración de servicios de directorio** (para equipos Unidos a un dominio) y, a continuación, haga clic en **compatibilidad con http**.  
  
6. Haga clic en **siguiente**y, a continuación, en **instalar**.  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a>Para instalar Message Queuing 4.0 en Windows 7 o Windows Vista  
  
1. Abra el **Panel de control**.  
  
2. Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
3. Expanda Microsoft Message Queuing (MSMQ), expanda Núcleo de Microsoft Message Queuing (MSMQ) y, a continuación, active las casillas para que se instalen las siguientes características de Message Queuing:  
  
    - Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio).  
  
    - Compatibilidad con MSMQ HTTP.  
  
4. Haga clic en **OK**.  
  
5. Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a>Para instalar Message Queuing 3.0 en Windows XP y Windows Server 2003  
  
1. Abra el **Panel de control**.  
  
2. Haga clic en **Agregar o quitar programas** y, a continuación, haga clic en **agregar componentes de Windows**.  
  
3. Seleccione Message Queue Server y haga clic en **detalles**.  
  
    > [!NOTE]
    > Si está ejecutando Windows Server 2003, seleccione servidor de aplicaciones para tener acceso a Message Queue Server.  
  
4. Asegúrese de que la opción de compatibilidad HTTP con MSMQ está seleccionada en la página de detalles.  
  
5. Haga clic en **Aceptar** para salir de la página de detalles y, a continuación, haga clic en **siguiente**. Complete la instalación.  
  
6. Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de instalación](set-up-instructions.md)
