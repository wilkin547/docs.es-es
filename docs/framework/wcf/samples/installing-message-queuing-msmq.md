---
title: "Instalar Message Queuing (MSMQ) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Instalar Message Queuing (MSMQ)
Los procedimientos siguientes muestran cómo instalar Message Queuing 4.0 y Message Queuing 3.0.  
  
> [!NOTE]
>  Message Queuing 4.0 no está disponible en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] ni [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
#### Para instalar Message Queuing 4.0 en Windows Server 2008 o Windows Server 2008 R2  
  
1.  En Administrador del servidor, haga clic en **Características**.  
  
2.  En el panel derecho, en **Resumen de características**, haga clic en **Agregar características**.  
  
3.  En la ventana resultante, expanda el nodo **Message Queuing**.  
  
4.  Expanda el nodo **Servicios de Message Queuing**.  
  
5.  Haga clic en **Integración de servicios de directorio** \(para los equipos asociados a un dominio\), a continuación haga clic en **Compatibilidad con HTTP**.  
  
6.  Haga clic en **Siguiente**,y, a continuación, en **Instalar**.  
  
#### Para instalar Message Queuing 4.0 en Windows 7 o Windows Vista  
  
1.  Abra el **Panel de control**.  
  
2.  Haga clic en **Programas** y, a continuación, en **Programas y características**, haga clic en **Activar o desactivar las características de Windows**.  
  
3.  Expanda Microsoft Message Queuing \(MSMQ\), expanda Núcleo de Microsoft Message Queuing \(MSMQ\) y, a continuación, active las casillas para que se instalen las siguientes características de Message Queuing:  
  
    -   Integración de Servicios de dominio de Active Directory MSMQ \(para los equipos unidos a un dominio\).  
  
    -   Compatibilidad con MSMQ HTTP.  
  
4.  Haga clic en **Aceptar**.  
  
5.  Si se le solicita que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
#### Para instalar Message Queuing 3.0 en Windows XP y Windows Server 2003  
  
1.  Abra el **Panel de control**.  
  
2.  Haga clic en **Agregar o quitar programas** y, a continuación, haga clic en **Agregar componentes de Windows**.  
  
3.  Seleccione Message Queuing y haga clic en **Detalles**.  
  
    > [!NOTE]
    >  Si ejecuta [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], seleccione Servidor de aplicaciones para obtener acceso a Message Queuing.  
  
4.  Asegúrese de que la opción de compatibilidad HTTP con MSMQ está seleccionada en la página de detalles.  
  
5.  Haga clic en **Aceptar** para salir de la página de detalles y, a continuación, haga clic en **Siguiente**.Complete la instalación.  
  
6.  Si se le solicita que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
## Vea también  
 [Instrucciones de instalación](../../../../docs/framework/wcf/samples/set-up-instructions.md)