---
title: Configuración del Servicio de activación de procesos de Windows para el uso con Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 86e50b80d84479ca32b3d4d1fe3f205983640c76
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464167"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Configuración del Servicio de activación de procesos de Windows para el uso con Windows Communication Foundation
En este tema se describen los pasos necesarios para configurar el Servicio de activación de procesos de Windows (también conocido como WAS) en Windows Vista para hospedar servicios de Windows Communication Foundation (WCF) que no se comunican a través de protocolos de red HTTP. Las siguientes secciones describen los pasos para realizar esta configuración:  
  
- Instale (o confirme la instalación de) los componentes de activación de WCF necesarios.  
  
- Cree un sitio WAS con los enlaces de protocolos de red que desee utilizar o agregue un nuevo enlace de protocolo a un sitio existente.  
  
- Cree una aplicación para hospedar sus servicios y permita a esa aplicación utilizar los protocolos de red necesarios.  
  
- Compile un servicio WCF que exponga un extremo no HTTP.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>Configuración de un sitio con enlaces que no sean HTTP  
 Para utilizar un enlace no HTTP con WAS, el enlace del sitio se debe agregar a la configuración de WAS. El almacén de configuración para WAS es el archivo applicationHost.config, ubicado en el directorio %windir%\system32\inetsrv\config. WAS e IIS 7.0 comparten este almacén de configuración.  
  
 applicationHost.config es un archivo de texto XML que se puede abrir con cualquier editor de texto estándar (como el Bloc de notas). Sin embargo, la herramienta de configuración de línea de comandos de IIS 7.0 (appcmd.exe) es la forma preferida de agregar enlaces de sitio que no sean HTTP.  
  
 El siguiente comando agrega un enlace de sitio net.tcp al sitio web predeterminado utilizando appcmd.exe (este comando se escribe como una línea única).  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 Este comando agrega el nuevo enlace net.tcp al sitio web predeterminado agregando la línea indicada a continuación al archivo applicationHost.config.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a>Permitir a una aplicación que utilice protocolos no HTTP  
 Puede habilitar o deshabilitar protocolos de red individuales en el nivel de aplicación. El siguiente comando muestra cómo habilitar los protocolos HTTP y net.tcp para una aplicación que se ejecute en el `Default Web Site`.  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 La lista de protocolos habilitados también \<se puede establecer en el elemento applicationDefaults> de la configuración XML del sitio almacenada en ApplicationHost.config.  
  
 El siguiente código XML de applicationHost.config muestra un sitio enlazado a protocolos HTTP y no HTTP. Se llama a la configuración adicional necesaria para admitir protocolos no HTTP mediante comentarios.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
      <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
      </application>  
      <bindings>  
            <!-- The following two lines are added by the command. -->
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults
      applicationPool="DefaultAppPool"
      <!-- The following line is inserted by the command. -->
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 Si intenta activar un servicio mediante WAS para la activación no HTTP y no ha instalado y configurado WAS, puede ver el siguiente error:  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 Si ve este error, asegúrese de que WAS para la activación no HTTP está instalado y configurado correctamente. Para obtener más información, vea [Cómo: instalar y configurar componentes](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)de activación de WCF .  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>Creación de un servicio WCF que utiliza WAS para la activación no HTTP  
 Una vez que realice los pasos para instalar y configurar WAS (consulte [Cómo: instalar y configurar componentes](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)de activación de WCF ), configurar un servicio para usar WAS para la activación es similar a configurar un servicio que se hospeda en IIS.  
  
 Para obtener instrucciones detalladas sobre cómo crear un servicio WCF activado por WAS, vea [Cómo: hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="see-also"></a>Consulte también

- [Hospedaje en Servicio de activación de procesos de Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)
- [Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
