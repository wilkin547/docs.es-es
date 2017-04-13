---
title: "D&#250;plex duradero | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# D&#250;plex duradero
En este ejemplo se muestra cómo instalar y configurar el intercambio de mensajes dúplex duradero utilizando las actividades de mensajería de [!INCLUDE[wf](../../../../includes/wf-md.md)].Un intercambio de mensajes dúplex duradero es un intercambio de mensajes bidireccional que tiene lugar a lo largo de un período largo de tiempo.La duración del intercambio de mensajes puede ser mayor que la duración del canal de comunicación y la duración en memoria de las instancias de servicio.  
  
## Detalles del ejemplo  
 En este ejemplo, se configuran dos servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementados utilizando [!INCLUDE[wf2](../../../../includes/wf2-md.md)] para tener un intercambio de mensajes dúplex duradero.El intercambio de mensajes dúplex duradero está compuesto por dos mensajes unidireccionales que se envían a través de MSMQ y se correlacionan con el [intercambio de contexto de .NET](http://go.microsoft.com/fwlink/?LinkID=166059).Los mensajes se envían mediante las actividades de mensajería <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Receive>.El intercambio de contexto de .NET se utiliza para especificar la dirección de devolución de llamada en los mensajes enviados.Ambos servicios se hospedan mediante Windows Process Activation Services \(WAS\) y se configuran para habilitar la persistencia de las instancias de los servicios.  
  
 El primer servicio \(Service1.xamlx\) envía una solicitud al servicio de envío \(Service2.xamlx\) para que realice algún trabajo.Una vez completado el trabajo, Service2.xamlx devuelve una notificación a Service1.xamlx para indicar que se ha completado el trabajo.Una aplicación de consola de flujo de trabajo prepara las colas donde están realizando escuchas los servicios y envía al mensaje Start inicial para activar Service1.xamlx.Cuando Service1.xamlx recibe la notificación de Service2.xamlx que indica que se ha completado el trabajo solicitado, Service1.xamlx guarda el resultado en un archivo XML.Mientras espera el mensaje de devolución de llamada, Service1.xamlx conserva su estado de la instancia mediante la clase <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> predeterminada.Service2.xamlx conserva su estado de instancia como parte de la finalización del trabajo solicitado por Service1.xamlx.  
  
 Para configurar los servicios y que usen el intercambio de contexto de .NET en MSMQ, ambos servicios se configuran para utilizar un enlace personalizado que consta de <xref:System.ServiceModel.Channels.ContextBindingElement> y <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.Una dirección de devolución de llamada se especifica con <xref:System.ServiceModel.Channels.ContextBindingElement> y se incluye en un encabezado de contexto de devolución de llamada con todos los mensajes enviados mediante un enlace personalizado.El siguiente ejemplo de código define el enlace personalizado.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
  
```  
  
> [!NOTE]
>  El enlace utilizado por este ejemplo no es seguro.Al implementar su aplicación, debería configurar el enlace en función de los requisitos de seguridad de la aplicación.  
  
> [!NOTE]
>  Las colas utilizadas en este ejemplo no son transaccionales.Para obtener un ejemplo que muestra cómo preparar intercambios de mensajes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante colas de la transacción, vea el ejemplo de [Activación MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md).  
  
 El mensaje enviado por Service1.xamlx a Service2.xamlx se envía mediante un extremo de cliente configurado con la dirección de Service2.xamlx y el enlace personalizado definido previamente.La devolución de llamada de Service2.xamlx a Service1.xamlx se envía mediante un extremo de cliente sin ninguna dirección configurada explícitamente, ya que la dirección se toma del contexto de devolución de llamada enviado por Service1.xamlx.El siguiente ejemplo de código define los extremos de cliente.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
  
```  
  
 El siguiente ejemplo de código expone los extremos que usan este enlace personalizado cambiando la asignación de protocolo predeterminado para que las direcciones base de net.msmq utilicen este enlace personalizado.  
  
```  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
  
```  
  
 El siguiente ejemplo de código habilita la persistencia para ambos servicios agregando el comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> a ambos servicios y especificando la cadena de conexión para la base de datos de persistencia.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
  
```  
  
## Requisitos del sistema  
 Este ejemplo requiere los componentes siguientes.  
  
1.  Internet Information Services.  
  
2.  Internet Information Services \-\> Compatibilidad con la administración de IIS 6.0 \-\> Compatibilidad con la configuración de metabase de IIS e IIS 6.0.  
  
3.  Servicios World Wide Web \-\> Características de desarrollo de aplicaciones \-\> ASP.NET.  
  
4.  Microsoft Message Queues \(MSMQ\) Server.  
  
#### Para utilizar este ejemplo  
  
1.  Configure la base de datos de persistencia y el directorio de resultados.  
  
    1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Navegue hasta la carpeta de este ejemplo y ejecute Setup.cmd.  
  
2.  Configure la aplicación virtual.  
  
    1.  Desde un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registre ASP.NET ejecutando el siguiente comando.  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  Ejecute [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos de administrador haciendo clic con el botón secundario en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y seleccionando **Ejecutar como administrador**.  
  
    3.  Mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo DurableDuplex.sln.  
  
3.  Configure las colas de servicio.  
  
    1.  Para ejecutar el cliente de DurableDuplex, presione F5.  
  
    2.  En un símbolo del sistema, ejecute `Compmgmt.msc` para abrir la consola **Administración de equipos**.  
  
    3.  Expanda **Servicio y Aplicaciones**, **Message Queuing**,**Colas privadas**.  
  
    4.  Haga clic con el botón secundario en las colas durableduplex\/service1.xamlx y durableduplex\/service2.xamlx y seleccione **Propiedades**.  
  
    5.  Seleccione la pestaña **Seguridad** y otorgue al grupo Todos los permisos **Recibir mensaje**, **Inspeccionar mensaje** y **Enviar mensaje** para ambas colas.  
  
    6.  Abra el Administrador de Internet Information Services \(IIS\).  
  
    7.  Navegue hasta **Servidor**, **Sitios**, **Sitio web predeterminado**, **Privado**, **Dúplex duradero** y seleccione **Opciones avanzadas**.  
  
    8.  Cambie **Protocolos habilitados** a **http,net.msmq**.  
  
4.  Ejecute el ejemplo.  
  
    1.  Vaya a http:\/\/localhost\/private\/durableduplex\/service1.xamlx y http:\/\/localhost\/private\/durableduplex\/service2.xamlx para asegurarse de que ambos servicios se están ejecutando.  
  
    2.  Presione F5 para ejecutar DurableDuplexClient.  
  
         Cuando el intercambio de mensajes dúplex duradero se completa, se guarda un archivo result.xml en la carpeta C:\\Inbox que contiene el resultado del intercambio de mensajes.  
  
#### Para realizar la limpieza \(Opcional\)  
  
1.  Ejecute Cleanup.cmd.  
  
    1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Navegue hasta la carpeta de este ejemplo y ejecute Cleanup.cmd.  
  
2.  Quite la aplicación virtual para los servicios.  
  
    1.  Abra el Administrador de Internet Information Services \(IIS\) ejecutando `Inetmgr.exe` desde un símbolo del sistema.  
  
    2.  Busque el sitio web predeterminado y quite el directorio virtual **private**.  
  
3.  Quite las colas preparadas para este ejemplo.  
  
    1.  En un símbolo del sistema, ejecute `Compmgmt.msc` para abrir la consola Administración de equipos.  
  
    2.  Expanda **Servicios y Aplicaciones**, **Message Queuing**, **Colas privadas**.  
  
    3.  Elimine las colas durableduplex\/service1.xamlx y durableduplex\/service2.xamlx.  
  
4.  Quite el directorio C:\\Inbox.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`  
  
## Vea también