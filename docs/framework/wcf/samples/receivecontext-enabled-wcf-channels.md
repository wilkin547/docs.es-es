---
title: Canales de WCF habilitados para ReceiveContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ec3b161ec9dedc2cbf389d8ec5ac4629cf54e007
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="receivecontext-enabled-wcf-channels"></a>Canales de WCF habilitados para ReceiveContext
En este ejemplo se muestra la utilidad de los canales WCF habilitados para <xref:System.ServiceModel.Channels.ReceiveContext>. En el ejemplo se implementa un servicio para encontrar el producto de dos números utilizando un canal de NetMSMQ.  
  
 La clase <xref:System.ServiceModel.Channels.ReceiveContext> permite a una aplicación decidir si tener acceso al mensaje o dejarlo en la cola para continuar su procesamiento, incluso una vez inspeccionado el contenido del mensaje. En este ejemplo, un cliente envía números enteros aleatorios a una cola transaccional. El servicio `ProductCalculator` recibe los mensajes e inspecciona su contenido, que son números enteros, para determinar si se puede calcular el producto. Si la operación del servicio no calcula el producto, el mensaje se coloca en la cola y puede ser recibido de nuevo por el servicio que realiza escuchas en ella.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Asegúrese de que está instalado Microsoft Message Queuing (MSMQ).  
  
    1.  Para instalar MSMQ en [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:  
  
        1.  En **el administrador del servidor**, haga clic en **características**.  
  
        2.  En el panel derecho de **resumen de características**, haga clic en **agregar características**.  
  
        3.  En la ventana resultante, expanda **Message Queue Server**.  
  
        4.  Expanda **servicios puesta en cola de mensajes**.  
  
        5.  Haga clic en **integración de servicios de directorio** (para los equipos unidos a un dominio) y, a continuación, haga clic en **compatibilidad con HTTP**.  
  
        6.  Haga clic en **siguiente**y, a continuación, haga clic en **instalar**.  
  
    2.  Para instalar MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)]:  
  
        1.  Abra **Panel de Control**.  
  
        2.  Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar o desactivar las características de Windows**.  
  
        3.  Expanda **Microsoft Message Queue (MSMQ) Server**, expanda **Microsoft Message Queue (MSMQ) Server Core**y, a continuación, active las casillas de verificación de las siguientes características de Message Queue Server instalar:  
  
            -   Message Queuing Server  
  
            -   Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio)  
  
            -   Compatibilidad con MSMQ HTTP  
  
        4.  Haga clic en **Aceptar**.  
  
        5.  Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
2.  Asegúrese de que [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] esté instalado en el equipo.  
  
3.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de la solución ReceiveContextProductGenerator.sln.  
  
4.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
5.  Para ejecutar la solución, presione CTRL+F5.
