---
title: Activación UDP
ms.date: 03/30/2017
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
ms.openlocfilehash: c0b351adb0b45f42404e94c74bdcff7785c2d0ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143725"
---
# <a name="udp-activation"></a>Activación UDP
Este ejemplo se basa en el [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo. Extiende el [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo para admitir la activación de procesos mediante el servicio de activación de procesos de Windows (WAS).  
  
 El ejemplo está compuesto de tres partes principales:  
  
- Un activador del protocolo UDP, un proceso independiente que recibe los mensajes de UDP en nombre de las aplicaciones que se van a activar.  
  
- Un cliente que utiliza el transporte personalizado de UDP para enviar los mensajes.  
  
- Un servicio (hospedado en un proceso de trabajo activado por WAS) que recibe los mensajes sobre el transporte personalizado de UDP.  
  
## <a name="udp-protocol-activator"></a>Activador del protocolo UDP  
 El Activador de protocolo UDP es un puente entre el cliente WCF y el servicio WCF. Proporciona la comunicación de datos a través del protocolo UDP en el nivel de transporte. Tiene dos funciones principales:  
  
- El Adaptador del agente de escucha (LA) de WAS, que colabora con WAS para activar los procesos como respuesta a los mensajes entrantes.  
  
- El Agente de escucha del protocolo UDP, que acepta los mensajes de UDP en nombre de las aplicaciones que se van a activar.  
  
 El activador se debe estar ejecutando como un programa independiente en el equipo del servidor. Normalmente, los adaptadores del agente de escucha de WAS (como NetTcpActivator y NetPipeActivator) se implementan en servicios de Windows de ejecución prolongada. Sin embargo, por motivos de simplicidad y claridad, este ejemplo implementa el activador de protocolo como una aplicación independiente.  
  
### <a name="was-listener-adapter"></a>Adaptador del agente de escucha de WAS  
 El Adaptador del agente de escucha de WAS para UDP se implementa en la clase `UdpListenerAdapter`. Es el módulo que interactúa con WAS para realizar la activación de la aplicación para el protocolo UDP. Esto se logra llamando a las API de Webhost siguientes:  
  
- `WebhostRegisterProtocol`  
  
- `WebhostUnregisterProtocol`  
  
- `WebhostOpenListenerChannelInstance`  
  
- `WebhostCloseAllListenerChannelInstances`  
  
 Después de llamar inicialmente a `WebhostRegisterProtocol`, el adaptador del agente de escucha recibe `ApplicationCreated` de la devolución de la llamada desde WAS para todas las aplicaciones registradas en applicationHost.config (situado en %windir%\system32\inetsrv). En este ejemplo, administramos solo las aplicaciones con el protocolo UDP (con el id. de protocolo como "net.udp") habilitado. Otras implementaciones pueden administrar esto de manera diferente si tales implementaciones responden a los cambios de configuración dinámicos en la aplicación (por ejemplo, una transición de la aplicación de deshabilitada a habilitada).  
  
 Cuando se recibe `ConfigManagerInitializationCompleted` de devolución de llamada, indica que WAS ha terminado todas las notificaciones para la inicialización del protocolo. En este momento, el adaptador del agente de escucha está listo para procesar las solicitudes de activación del proceso.  
  
 Cuando una nueva solicitud entra por primera vez para una aplicación, el adaptador del agente de escucha llama a `WebhostOpenListenerChannelInstance` en WAS, lo que inicia el proceso de trabajo si no se ha iniciado aún. A continuación, se cargan los controladores de protocolo y se puede iniciar la comunicación entre el adaptador del agente de escucha y la aplicación virtual.  
  
 El adaptador de escucha se registra en la sección %SystemRoot%-System32-inetsrv-ApplicationHost.config en el <`listenerAdapters`> de la siguiente manera:  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a>Agente de escucha de protocolo  
 El agente de escucha del protocolo UDP es un módulo dentro del activador de protocolo que realiza escuchas en un extremo de UDP en nombre de la aplicación virtual. Se implementa en la clase `UdpSocketListener`. El punto de conexión se representa como `IPEndpoint` para lo que el número de puerto se extrae del enlace del protocolo para el sitio.  
  
### <a name="control-service"></a>Servicio de control  
 En este ejemplo, usamos WCF para comunicarse entre el activador y el proceso de trabajo WAS. El servicio que reside en el activador se denomina "servicio de control".  
  
## <a name="protocol-handlers"></a>Controladores de protocolo  
 Después de que el adaptador del agente de escucha llame a `WebhostOpenListenerChannelInstance`, el administrador del proceso de WAS inicia el proceso de trabajo si no comienza. El administrador de la aplicación dentro del proceso de trabajo carga a continuación el controlador de protocolo de proceso UDP (PPH) con la solicitud para ese `ListenerChannelId`. El PPH en `IAdphManager`vueltas llama .`StartAppDomainProtocolListenerChannel` para iniciar el controlador de protocolo UDP AppDomain (ADPH).  
  
## <a name="hostedudptransportconfiguration"></a>HostedUDPTransportConfiguration  
 La información se registra en Web.config de la siguiente manera:  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a>Instalación especial para este ejemplo  
 Este ejemplo solo se puede compilar y ejecutar en Windows Vista, Windows Server 2008 o Windows 7. Para ejecutar el ejemplo, debe tener primero todos los componentes configurados correctamente. Siga estos pasos para instalar el ejemplo.  
  
#### <a name="to-set-up-this-sample"></a>Para configurar este ejemplo  
  
1. Instale ASP.NET 4.0 con el siguiente comando.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Compile el proyecto en Windows Vista. Después de la compilación, realiza también las operaciones siguientes en la fase posterior a la compilación:  
  
    - Instala el enlace de UDP para "Sitio web predeterminado" del sitio.  
  
    - Crea "ServiceModelSamples" de la aplicación virtual para señalar a la ruta de acceso física: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples."  
  
    - También habilita el protocolo "net.udp" para esta aplicación virtual.  
  
3. Inicie "WasNetActivator.exe" de la aplicación de interfaz de usuario. Haga clic en la ficha **Configuración,** active las siguientes casillas de verificación y, a continuación, haga clic en **Instalar** para instalarlas:  
  
    - Adaptador del agente de escucha de UDP  
  
    - Controladores de protocolo UDP  
  
4. Haga clic en la pestaña **Activación** de la aplicación de interfaz de usuario "WasNetActivator.exe". Haga clic en el botón **Inicio** para iniciar el adaptador de escucha. Ahora ya está listo para ejecutar el programa.  
  
    > [!NOTE]
    > Cuando haya finalizado con este ejemplo, debe ejecutar Cleanup.bat para quitar el enlace net.udp del "Sitio Web predeterminado".  
  
## <a name="sample-usage"></a>Ejemplo de uso  
 Después de la compilación, se han generador cuatro binarios diferentes:  
  
- Client.exe: el código de cliente. App.config está compilado en el archivo de configuración del cliente Client.exe.config.  
  
- UDPActivation.dll: la biblioteca que contiene todas las implementaciones de UDP principales.  
  
- Service.dll: el código de servicio. Se copia en el directorio \bin de ServiceModelSamples de la aplicación virtual. El archivo de servicio es Service.svc y el archivo de configuración es Web.config. Después de la compilación, se copian en la siguiente ubicación: %SystemDrive%-Inetpub-wwwroot-ServiceModelSamples.  
  
- WasNetActivator: el programa activador de UDP.  
  
- Asegúrese de que todas las piezas necesarias se instalan correctamente. Los pasos siguientes muestran cómo ejecutar el ejemplo:  
  
1. Asegúrese que se hayan iniciado los siguientes servicios de Windows:  
  
    - Servicio de activación de procesos de Windows (WAS).  
  
    - Internet Information Services (IIS): W3SVC.  
  
2. A continuación, inicie el activador, WasNetActivator.exe. En la pestaña **Activación,** el único protocolo, **UDP**, se selecciona en la lista desplegable. Haga clic en el botón **Inicio** para iniciar el activador.  
  
3. Una vez iniciado el activador, puede ejecutar el código de cliente ejecutando Client.exe desde una ventana de comandos. A continuación, se incluye la salida del ejemplo.  
  
    ```console  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
