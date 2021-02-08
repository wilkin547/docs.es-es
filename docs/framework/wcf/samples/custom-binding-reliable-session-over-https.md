---
description: 'Más información sobre: la sesión confiable de enlace personalizado a través de HTTPS'
title: Sesión confiable de enlace personalizado mediante HTTPS
ms.date: 03/30/2017
ms.assetid: 16aaa80d-3ffe-47c4-8b16-ec65c4d25f8d
ms.openlocfilehash: ed02ce8ea199b5e7ae744fb0eacf168ea5fa85df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778300"
---
# <a name="custom-binding-reliable-session-over-https"></a>Sesión confiable de enlace personalizado mediante HTTPS

Este ejemplo muestra el uso de seguridad de transporte de SSL con sesiones confiables. Las sesiones confiables implementan el protocolo WS-Reliable Messaging. Puede tener una sesión confiable segura creando WS-Security sobre sesiones confiables. Pero a veces, puede decidir utilizar en su lugar la seguridad del transporte HTTP con SSL.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSessionOverHttps`  
  
## <a name="sample-details"></a>Detalles del ejemplo  

 SSL garantiza que los paquetes se protegen. Es importante tener en cuenta que esto es diferente de proteger la sesión confiable mediante WS-Secure Conversation.  
  
 Para utilizar la sesión confiable sobre HTTPS, debe crear un enlace personalizado. Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora. Un enlace personalizado se crea mediante el elemento de enlace de la sesión confiable y el [\<httpsTransport>](../../configure-apps/file-schema/wcf/httpstransport.md) . La configuración siguiente es del enlace personalizado.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="reliableSessionOverHttps"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed as http://localhost/servicemodelsamples/service.svc/mex-->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="reliableSessionOverHttps">  
          <reliableSession />  
          <httpsTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="true" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 El código del programa en el ejemplo es idéntico al del servicio [Introducción](getting-started-sample.md) . Debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web antes de compilar y ejecutar el ejemplo. La definición de extremo y del enlace en los valores de archivo de configuración habilita el uso de enlace personalizado tal y como se muestra en la siguiente configuración de ejemplo para el cliente.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint name=""  
                address="https://localhost/servicemodelsamples/service.svc"
                binding="customBinding"
                bindingConfiguration="reliableSessionOverHttps"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
      <bindings>  
        <customBinding>  
          <binding name="reliableSessionOverHttps">  
            <reliableSession />  
            <httpsTransport />  
          </binding>  
        </customBinding>
    </bindings>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
 La dirección especificada usa el `https://` esquema.  
  
 Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, aparece una alerta de seguridad al intentar obtener acceso a una dirección https:, como `https://localhost/servicemodelsamples/service.svc` , desde el explorador. Para permitir que el cliente de Windows Communication Foundation (WCF) funcione con un certificado de prueba en contexto, se ha agregado código adicional al cliente para suprimir la alerta de seguridad. Este código, y la clase que lo acompaña, no son necesarios cuando se usan certificados de producción.  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Instale ASP.NET 4,0 con el siguiente comando.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Asegúrese de que ha realizado las [instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).  
  
4. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
5. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
