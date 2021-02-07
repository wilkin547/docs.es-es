---
description: 'Más información sobre: seguridad de transporte WS'
title: Seguridad de transporte WS
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
ms.openlocfilehash: 0fc09815e757e1cda1a7fd196e33fab4d56d2cde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668362"
---
# <a name="ws-transport-security"></a>Seguridad de transporte WS

Este ejemplo muestra el uso de la seguridad de transporte de SSL con el enlace <xref:System.ServiceModel.WSHttpBinding>. De forma predeterminada, el enlace `wsHttpBinding` proporciona la comunicación HTTP. Cuando se configura para la seguridad del transporte, el enlace admite la comunicación de HTTPS. Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora. `wsHttpBinding` se especifica y se configura en los archivos de configuración de la aplicación para el cliente y el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 El código del programa en el ejemplo es idéntico al del servicio [Introducción](getting-started-sample.md) . Debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web antes de compilar y ejecutar el ejemplo. La definición de extremo y de enlace en la configuración del archivo de configuración habilitan el modo de seguridad `Transport`, tal y como se muestra en la configuración de ejemplo siguiente para el cliente.  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 La dirección especificada usa el `https://` esquema. La configuración de enlace establece el modo de seguridad en `Transport`. Debe especificarse el mismo modo de seguridad en el archivo Web.config del servicio.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Instale ASP.NET 4,0 con el siguiente comando.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Asegúrese de que ha realizado las [instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).  
  
4. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
5. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
