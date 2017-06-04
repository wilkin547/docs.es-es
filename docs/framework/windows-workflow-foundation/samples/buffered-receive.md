---
title: "Recepci&#243;n almacenada en b&#250;fer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Recepci&#243;n almacenada en b&#250;fer
En este ejemplo se muestra cómo preparar y configurar la característica de recepción almacenada en búfer en [!INCLUDE[wf](../../../../includes/wf-md.md)].La recepción almacenada en búfer permite al autor del flujo de trabajo crear un flujo de trabajo sin tener que preocuparse por el orden en el que se reciben los mensajes.Este tipo de recepción almacena en búfer los mensajes localmente y los entrega cuando el flujo de trabajo está listo para recibirlos.  
  
## Demostraciones  
 Procesamiento desordenado de mensajes utilizando la recepción almacenada en búfer con actividades de mensajería.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>: \WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## Análisis  
 En este ejemplo, un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se implementa utilizando [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y tiene una secuencia de las actividades <xref:System.ServiceModel.Activities.Receive>.Este flujo de trabajo modela un proceso de aprobación de préstamos simple en el que el flujo de trabajo espera tres notificaciones para que se apruebe un préstamo.Una aplicación cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] envía tres notificaciones puestas en correlación en el orden inverso al que el servicio espera.Dado que la característica de recepción almacenada en búfer está activada en el servicio, cada mensaje desordenado se almacena en búfer en el servicio y se procesa cuando el flujo de trabajo está listo para recibirlo.  
  
 La característica de recepción almacenada en búfer requiere la compatibilidad con <xref:System.ServiceModel.Activities.ReceiveContent> por parte del enlace; por consiguiente, el servicio utiliza <xref:System.ServiceModel.NetMsmqBinding>.No se requiere ninguna configuración especial para el enlace, por lo que se utilizan los valores predeterminados.  
  
```  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
  
```  
  
 El servicio también expone metadatos para el servicio utilizando <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
 De igual forma, el extremo del cliente se configura utilizando <xref:System.ServiceModel.NetMsmqBinding>.El código de cliente y la configuración se generan utilizando la característica **Agregar referencia de servicio** de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].El siguiente ejemplo muestra el extremo de cliente generado en el archivo App.config.  
  
```  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
  
```  
  
 En este ejemplo se requiere que los siguientes componentes de Windows estén habilitados:  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Compatibilidad con la administración, Metabase y Compatibilidad con la configuración  
  
3.  Servicios World Wide Web, Características de desarrollo de aplicaciones y ASP.NET  
  
4.  Microsoft Message Queuing \(MSMQ\)  
  
#### Para configurar y compilar el ejemplo  
  
1.  En un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registre ASP.NET escribiendo `aspnet_regiis –I` y presione ENTRAR.  
  
2.  Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] como administrador.  
  
3.  Abra LoanService.sln.  
  
4.  Cuando se le pregunte si desea crear los directorios virtuales del proyecto LoanService, seleccione **Sí**.  
  
#### Para configurar las colas de servicio  
  
1.  Presione F5 para ejecutar la aplicación LoanClient que crea las colas y activa el servicio definido en Service1.xamlx.  
  
2.  Abra la consola **Administración del equipo** ejecutando Compmgmt.msc desde un símbolo del sistema.  
  
3.  En la consola **Administración del equipo**, expanda **Serviciosy Aplicaciones**, **Message Queuing**, **Colas privadas**.  
  
4.  Haga clic con el botón secundario del mouse en la cola loanservice\/service1.xamlx y seleccione **Propiedades**.  
  
5.  Seleccione la pestaña **Seguridad** y agregue los permisos **Todos reciben mensaje**, **Inspeccionar mensaje** y **Enviar mensaje**.  
  
6.  Abra el Administrador de [!INCLUDE[iis60](../../../../includes/iis60-md.md)].  
  
7.  Navegue hasta **Servidor**, **Sitios**, **Sitio web predeterminado**, **Privado**, **LoanService** y seleccione **Opciones avanzadas**  
  
8.  Cambie los **Protocolos habilitados** para que sean **http**, **net.msmq**.  
  
#### Para ejecutar el ejemplo  
  
1.  Vaya a http:\/\/localhost\/private\/loanservice\/service1.xamlx para asegurarse de que el servicio se está ejecutando.  
  
2.  Presione F5 para ejecutar la aplicación LoanClient.Cuando el flujo de trabajo finaliza, se debe guardar un archivo out.txt en C:\\Inbox que contenga el resultado del intercambio de mensajes.  
  
#### Para realizar una limpieza  
  
1.  Abra la consola **Administración del equipo** ejecutando Compmgmt.msc desde un símbolo del sistema.  
  
2.  Expanda **Servicios y Aplicaciones**, **Message Queuing**, **Colas privadas**.  
  
3.  Elimine la cola loanservice\/service1 .xamlx.  
  
4.  Quite el directorio C:\\Inbox.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>: \WF_WCF_Samples\WF\Basic\Services\BufferedReceive`