---
description: 'Más información acerca de: seguridad de mensajes en Message Queue Server'
title: Seguridad de mensajes mediante Message Queuing
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: bfbec02dec11d4f4eb153db942eb12ce4cb595e4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752332"
---
# <a name="message-security-over-message-queuing"></a>Seguridad de mensajes mediante Message Queuing

Este ejemplo muestra cómo implementar una aplicación que utiliza WS-Security con autenticación de certificado X.509v3 para el cliente y que requiere la autenticación del servidor mediante el certificado X.509v3 del servidor sobre MSMQ. En ocasiones es más apropiado utilizar la seguridad del mensaje para garantizar que los mensajes en el almacén de MSMQ permanezcan cifrados y la aplicación pueda realizar su propia autenticación del mensaje.

 Este ejemplo se basa en el ejemplo de [enlace de MSMQ de transacciones](transacted-msmq-binding.md) . Los mensajes se cifran y firman.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.

    1. Abra Administrador del servidor en Visual Studio 2012.

    2. Expanda la pestaña **características** .

    3. Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nuevo**, **cola privada**.

    4. Active la casilla **transaccional** .

    5. Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.

3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Asegúrese de que la ruta de acceso incluye la carpeta que contiene Makecert.exe y FindPrivateKey.exe.

2. Ejecute Setup.bat desde la carpeta de instalación del ejemplo. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > Asegúrese de que quita los certificados ejecutando Cleanup.bat cuando haya terminado con el ejemplo. Otros ejemplos de seguridad usan los mismos certificados.  
  
3. Inicie Service.exe desde \service\bin.  
  
4. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
5. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el equipo del servicio.  
  
2. Cree un directorio en el equipo cliente para los archivos binarios del cliente.  
  
3. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.  
  
4. En el servidor, ejecute `setup.bat service`. `setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.  
  
5. Edite el service.exe.config del servicio para que refleje el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.  
  
6. Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.  
  
7. En el cliente, ejecute `setup.bat client`. Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio. Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.  También debe cambiar el nombre del certificado del servicio para que sea igual que el nombre de dominio completo del equipo del servicio (en el atributo `findValue` del elemento `defaultCertificate` de `serviceCertificate`, bajo `clientCredentials`).  
  
9. Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.  
  
10. En el cliente, ejecute `ImportServiceCert.bat`. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.  
  
11. En el servidor, ejecute `ImportClientCert.bat`. De esta manera se importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine - TrustedPeople.  
  
12. En el equipo del servicio, inicie Service.exe desde el símbolo del sistema.  
  
13. En el equipo cliente, inicie Client.exe desde el símbolo del sistema. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
    > [!NOTE]
    > Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.

## <a name="requirements"></a>Requisitos

 Este ejemplo exige que MSMQ se instale y se ejecute.

## <a name="demonstrates"></a>Muestra

 El cliente cifra el mensaje mediante la clave pública del servicio y firma el mensaje con su propio certificado. El servicio que lee el mensaje de la cola autentica el certificado de cliente con el certificado en su almacén de personas de confianza. Después descifra el mensaje y lo envía a la operación de servicio.

 Dado que el mensaje de Windows Communication Foundation (WCF) se lleva como una carga en el cuerpo del mensaje de MSMQ, el cuerpo permanece cifrado en el almacén de MSMQ. Esto protege el mensaje de la divulgación no deseada del mensaje. Tenga en cuenta que el propio MSMQ no sabe si el mensaje que transporta está cifrado.

 El ejemplo muestra cómo se puede utilizar la autenticación mutua en el nivel de mensaje con MSMQ. Los certificados se intercambian fuera de banda. Siempre es el caso de la aplicación con cola porque el servicio y el cliente no tienen que estar al mismo tiempo conectados y ejecutándose.

## <a name="description"></a>Descripción

 El cliente de ejemplo y el código de servicio son los mismos que el ejemplo de [enlace de MSMQ de transacción](transacted-msmq-binding.md) con una diferencia. En el contrato de operación se anota el nivel de protección, que sugiere que el mensaje se debe firmar y cifrar.

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Para asegurarse de que el mensaje se protege utilizando el token necesario para identificar el servicio y el cliente, App.config contiene la información de la credencial.

 La configuración del cliente especifica el certificado de servicio para autenticar el servicio. Utiliza su almacén LocalMachine como almacén de confianza para confiar en la validez del servicio. También especifica el certificado de cliente que está asociado con el mensaje para la autenticación del servicio del cliente.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
</configuration>
```

 Observe que el modo de seguridad se ha definido en "Message" y que ClientCredentialType se ha establecido en "Certificate".

 La configuración de servicio incluye un comportamiento de servicio que especifica las credenciales del servicio que se utilizan cuando el cliente autentica el servicio. El nombre de sujeto del certificado de servidor se especifica en el `findValue` atributo en [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </clientCertificate>
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

 El ejemplo muestra cómo controlar la autenticación mediante la configuración y cómo obtener la identidad del autor de la llamada desde el contexto de seguridad, tal y como se muestra en el siguiente código de ejemplo:

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 Cuando se ejecuta, el código de servicio muestra la identificación del cliente. Se proporciona a continuación la siguiente salida de ejemplo desde el código de servicio:

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a>Comentarios

- Crear el certificado del cliente.

     La línea siguiente en el archivo por lotes crea el certificado de cliente. El nombre de cliente especificado se utiliza en el nombre del asunto del certificado creado. El certificado se guarda en el almacén `My`, en la ubicación de almacenamiento `CurrentUser`.

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- Instalar el certificado del cliente en el almacén de certificados de confianza del servidor.

     La línea siguiente del archivo por lotes copia el certificado de cliente en el almacén TrustedPeople del servidor para que el servidor pueda tomar decisiones basadas en la confianza o la ausencia de la misma. Para que un servicio de Windows Communication Foundation (WCF) confíe en un certificado instalado en el almacén TrustedPeople, el modo de validación del certificado de cliente debe establecerse en `PeerOrChainTrust` o en `PeerTrust` valor. Vea el ejemplo de configuración de servicio anterior para obtener información sobre cómo puede hacerse usando un archivo de configuración.

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- Crear el certificado de servidor.

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar:

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     La variable %SERVER_NAME% especifica el nombre del servidor. El certificado se almacena en el almacén LocalMachine. Si el archivo por lotes de instalación se ejecuta con un argumento de servicio (como `setup.bat service` ), el% SERVER_NAME% contiene el nombre de dominio completo del equipo. De lo contrario, el valor predeterminado es localhost.

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.

     La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > Si usa un valor que no es de U. S. Edición en Inglés de Microsoft Windows debe modificar el archivo Setup.bat y reemplazar el nombre de cuenta "NT AUTHORITY\NETWORK SERVICE" con su equivalente regional.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`
