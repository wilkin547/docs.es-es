---
title: Host de servicio de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 83b40f467af933b5da69b859d990fbe4ba005928
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143530"
---
# <a name="windows-service-host"></a>Host de servicio de Windows
En este ejemplo se muestra un servicio de Windows Communication Foundation (WCF) hospedado en un servicio de Windows administrado. Los servicios de Windows se controlan mediante el subprograma Servicios en el Panel de **control** y se pueden configurar para que se inicien automáticamente después de reiniciar el sistema. El ejemplo está compuesto de un programa cliente y un programa de servicio de Windows. El servicio se implementa como un programa .exe y contiene su propio código de hospedaje. No es necesario que escriba el código de hospedaje en otros entornos de hospedaje, como los Servicios de activación de procesos de Windows (WAS) o Internet Information Services (IIS).

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Después de compilar este servicio, se debe instalar con la utilidad Installutil.exe como cualquier otro servicio de Windows. Si va a realizar cambios en el servicio, deberá desinstalarlo primero con `installutil /u`. Los archivos Setup.bat y Cleanup.bat incluidos en este ejemplo son los comandos para instalar e iniciar el servicio de Windows, y para apagar y desinstalar el servicio de Windows. El servicio WCF solo puede responder a los clientes si se está ejecutando el servicio de Windows. Si detiene el servicio de Windows mediante el subprograma Servicios <xref:System.ServiceModel.EndpointNotFoundException> del Panel de **control** y ejecuta el cliente, se produce una excepción cuando un cliente intenta tener acceso al servicio. Si reinicia el servicio de Windows y vuelve a ejecutar el cliente, la comunicación se produce correctamente.  
  
 El código de servicio incluye una clase de instalador, una clase de implementación de servicio WCF que implementa el contrato ICalculator y una clase de servicio de Windows que actúa como host en tiempo de ejecución. La clase del instalador, que hereda de <xref:System.Configuration.Install.Installer>, permite instalar el programa como un servicio de NT por la herramienta Installutil.exe. La clase de `WcfCalculatorService`implementación de servicio, , es un servicio WCF que implementa un contrato de servicio básico. Este servicio WCF se hospeda dentro `WindowsCalculatorService`de una clase de servicio de Windows denominada . Para que sea calificada como un servicio de Windows, la clase hereda de <xref:System.ServiceProcess.ServiceBase> e implementa los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> y <xref:System.ServiceProcess.ServiceBase.OnStop>. En <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, se crea un objeto <xref:System.ServiceModel.ServiceHost> para el tipo `WcfCalculatorService` y se abre. En <xref:System.ServiceProcess.ServiceBase.OnStop>, ServiceHost se cierra llamando al método <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> del objeto <xref:System.ServiceModel.ServiceHost>. La dirección base del host se configura [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) mediante el [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) elemento add>, que es un elemento secundario de [ \<baseAddresses>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), que es un elemento secundario del elemento>host, que es un elemento secundario del elemento de>de servicio.  
  
 El punto de conexión definido utiliza la dirección base y un [ \<>wsHttpBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). El ejemplo siguiente muestra la configuración de la dirección base así como el extremo que expone CalculatorService.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Una vez compilada la solución, ejecute Setup.bat desde un símbolo del sistema de Visual Studio 2012 con privilegios elevados para instalar el servicio de Windows mediante la herramienta Installutil.exe. El servicio debería aparecer en Servicios.  
  
4. Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de hospedaje y persistencia de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
