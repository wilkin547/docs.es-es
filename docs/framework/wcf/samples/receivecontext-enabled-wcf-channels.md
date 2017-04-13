---
title: "Canales de WCF habilitados para ReceiveContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Canales de WCF habilitados para ReceiveContext
En este ejemplo se muestra la utilidad de los canales WCF habilitados para <xref:System.ServiceModel.Channels.ReceiveContext>.  En el ejemplo se implementa un servicio para encontrar el producto de dos números utilizando un canal de NetMSMQ.  
  
 La clase <xref:System.ServiceModel.Channels.ReceiveContext> permite a una aplicación decidir si tener acceso al mensaje o dejarlo en la cola para continuar su procesamiento, incluso una vez inspeccionado el contenido del mensaje.  En este ejemplo, un cliente envía números enteros aleatorios a una cola transaccional.  El servicio `ProductCalculator` recibe los mensajes e inspecciona su contenido, que son números enteros, para determinar si se puede calcular el producto.  Si la operación del servicio no calcula el producto, el mensaje se coloca en la cola y puede ser recibido de nuevo por el servicio que realiza escuchas en ella.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.  Compruebe el siguiente directorio \(predeterminado\) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### Para utilizar este ejemplo  
  
1.  Asegúrese de que está instalado Microsoft Message Queuing \(MSMQ\).  
  
    1.  Para instalar MSMQ en [!INCLUDE[lserver](../../../../includes/lserver-md.md)]:  
  
        1.  En **Administrador del servidor**, haga clic en **Características**.  
  
        2.  En el panel derecho, en **Resumen de características**, haga clic en **Agregar características**.  
  
        3.  En la ventana resultante, expanda el nodo **Message Queuing**.  
  
        4.  Expanda el nodo **Servicios de Message Queuing**.  
  
        5.  Haga clic en **Integración de servicios de directorio** \(para los equipos asociados a un dominio\) y, a continuación, haga clic en **Compatibilidad con HTTP**.  
  
        6.  Haga clic en **Siguiente** y, a continuación, en **Instalar**.  
  
    2.  Para instalar MSMQ en [!INCLUDE[wv](../../../../includes/wv-md.md)]:  
  
        1.  Abra el **Panel de control**.  
  
        2.  Haga clic en **Programas** y, a continuación, en **Programas y características**, haga clic en **Activar o desactivar las características de Windows**.  
  
        3.  Expanda **Microsoft Message Queue \(MSMQ\) Server**, expanda **Núcleo de Microsoft Message Queuing \(MSMQ\)** y, a continuación, active las casillas para que se instalen las siguientes características de Message Queuing:  
  
            -   Message Queuing Server  
  
            -   Integración de Servicios de dominio de Active Directory MSMQ \(para los equipos unidos a un dominio\)  
  
            -   Compatibilidad con MSMQ HTTP  
  
        4.  Haga clic en **Aceptar**.  
  
        5.  Si se le solicita que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.  
  
2.  Asegúrese de que [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] esté instalado en el equipo.  
  
3.  Con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo de la solución ReceiveContextProductGenerator.sln.  
  
4.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
5.  Para ejecutar la solución, presione CTRL\+F5.