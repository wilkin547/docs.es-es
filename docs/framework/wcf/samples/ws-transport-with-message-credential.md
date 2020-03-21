---
title: Transporte WS con credencial de mensaje
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: 076d4490f6edc6efa8eeb50ae8baa23d5c4e369a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183145"
---
# <a name="ws-transport-with-message-credential"></a>Transporte WS con credencial de mensaje
Este ejemplo muestra el uso de la seguridad de transporte de SSL en combinación con la credencial del cliente que se lleva en el mensaje. El ejemplo usa el enlace `wsHttpBinding`.  
  
 De forma predeterminada, el enlace `wsHttpBinding` proporciona la comunicación HTTP. Cuando se configura para la seguridad del transporte, el enlace admite la comunicación de HTTPS. HTTPS proporciona confidencialidad y protección de integridad para los mensajes que se transmiten a través de la conexión. Sin embargo, el conjunto de mecanismos de autenticación que se pueden usar para autenticar el cliente en el servicio está limitado a lo que admite el transporte HTTPS. Windows Communication Foundation (WCF) ofrece un `TransportWithMessageCredential` modo de seguridad diseñado para superar esta limitación. Cuando se configura este modo de seguridad, la seguridad de transporte se utiliza para proporcionar confidencialidad e integridad para los mensajes transmitidos y realizar la autenticación del servicio. Sin embargo, la autenticación de cliente se realiza colocando la credencial de cliente directamente en el mensaje. Esto le permite usar cualquier tipo de credencial que sea compatible con el modo de seguridad de mensajes para la autenticación de cliente mientras mantiene la ventaja de rendimiento del modo de seguridad de transporte.  
  
 En este ejemplo, se utiliza un tipo de credencial `UserName` para autenticar el cliente con el servicio.  
  
 Este ejemplo se basa en la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora. Se especifica y se configura el enlace `wsHttpBinding` en los archivos de configuración de la aplicación para el cliente y el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El código del programa en el ejemplo es casi idéntico al del servicio [de introducción.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Hay una operación adicional proporcionada por el contrato de servicios: `GetCallerIdentity`. Esta operación devuelve el nombre de la identidad del autor de la llamada a éste.  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 Debe crear un certificado y asignarlo utilizando el Asistente para certificados de servidor web antes de compilar y ejecutar el ejemplo. La definición de extremo y de enlace en la configuración del archivo de configuración habilitan el modo de seguridad `TransportWithMessageCredential`, tal y como se muestra en la configuración de ejemplo siguiente para el cliente.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 La dirección especificada utiliza el esquema https://. La configuración de enlace establece el modo de seguridad en `TransportWithMessageCredential`. Debe especificarse el mismo modo de seguridad en el archivo Web.config del servicio.  
  
 Dado que el certificado utilizado en este ejemplo es un certificado de prueba creado con Makecert.exe, aparece una alerta de seguridad cuando intenta acceder a una dirección https:, como `https://localhost/servicemodelsamples/service.svc`, desde el explorador. Para permitir que el cliente WCF trabaje con un certificado de prueba en su lugar, se ha agregado código adicional al cliente para suprimir la alerta de seguridad. Este código, y la clase que lo acompaña, no son necesarios cuando se usan certificados de producción.  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:
YourDomainName\YourAccountName  
   Enter password:
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Asegúrese de que ha realizado las instrucciones de instalación de certificados de servidor de [Internet Information Services (IIS).](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)  
  
3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
