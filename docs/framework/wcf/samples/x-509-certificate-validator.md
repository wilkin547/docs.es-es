---
title: Validador de certificado X.509
ms.date: 03/30/2017
ms.assetid: 3b042379-02c4-4395-b927-e57c842fd3e0
ms.openlocfilehash: ba73381bb6211dcbd1ddad1457f9ae8611008d43
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141210"
---
# <a name="x509-certificate-validator"></a>Validador de certificado X.509

Este ejemplo muestra cómo implementar un validador de certificado X.509 personalizado. Esto es útil en casos donde ninguno de los modos de validación de certificado X.509 integrado es adecuado para los requisitos de la aplicación. Este ejemplo muestra un servicio que tiene un validador personalizado que acepta certificados emitidos por sí mismos. El cliente utiliza un certificado para autenticar al servicio.

Nota: como cualquiera puede construir un certificado emitido por sí mismo, el validador personalizado utilizado por el servicio es menos seguro que el comportamiento predeterminado proporcionado por X509CertificateValidationMode de ChainTrust. Las implicaciones de seguridad que conlleva deberían considerarse cuidadosamente antes de utilizar esta lógica de validación en el código de producción.

En resumen, este ejemplo muestra cómo:

- El cliente se puede autenticar utilizando un certificado X.509.

- El servidor valida las credenciales del cliente contra un X509CertificateValidator personalizado.

- El servidor se autentica utilizando el certificado X.509 del servidor.

El servicio expone un punto de conexión único para comunicarse con el servicio, definido mediante el archivo de configuración app. config. El punto de conexión consta de una dirección, un enlace y un contrato. El enlace se configura con un estándar `wsHttpBinding` que tiene como valor predeterminado `WSSecurity` el uso de y la autenticación de certificado de cliente. El comportamiento del servicio especifica el modo Personalizado para validar los certificados X.509 junto con el tipo de la clase de validador. El comportamiento también especifica el certificado del servidor mediante el elemento serviceCertificate. El certificado de servidor debe contener el mismo valor para el `SubjectName` que `findValue` en el [ \<>serviceCertificate ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).

```xml
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- use host/baseAddresses to configure base address -->
        <!-- provided by host -->
        <host>
          <baseAddresses>
            <add baseAddress =
                "http://localhost:8001/servicemodelsamples/service" />
          </baseAddresses>
        </host>
        <!-- use base address specified above, provide one endpoint -->
        <endpoint address="certificate"
               binding="wsHttpBinding"
               bindingConfiguration="Binding"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <!-- X509 certificate binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults ="true"/>
          <serviceCredentials>
            <!-- The serviceCredentials behavior allows one -->
            <!-- to specify authentication constraints on -->
            <!-- client certificates. -->
            <clientCertificate>
              <!-- Setting the certificateValidationMode to -->
              <!-- Custom means that if the custom -->
              <!-- X509CertificateValidator does NOT throw -->
              <!-- an exception, then the provided certificate -->
              <!-- will be trusted without performing any -->
              <!-- validation beyond that performed by the custom -->
              <!-- validator. The security implications of this -->
              <!-- setting should be carefully considered before -->
              <!-- using Custom in production code. -->
              <authentication
                 certificateValidationMode="Custom"
                 customCertificateValidatorType =
"Microsoft.ServiceModel.Samples.CustomX509CertificateValidator, service" />
            </clientCertificate>
            <!-- The serviceCredentials behavior allows one to -->
            <!-- define a service certificate. -->
            <!-- A service certificate is used by a client to -->
            <!-- authenticate the service and provide message -->
            <!-- protection. This configuration references the -->
            <!-- "localhost" certificate installed during the setup -->
            <!-- instructions. -->
            <serviceCertificate findValue="localhost"
                 storeLocation="LocalMachine"
                 storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
      </system.serviceModel>
```

La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato. El enlace del cliente se configura con el modo adecuado y el `clientCredentialType` del mensaje.

```xml
<system.serviceModel>
    <client>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
        address=
        "http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>
    <bindings>
        <wsHttpBinding>
            <!-- X509 certificate binding -->
            <binding name="Binding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
               </security>
            </binding>
       </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!-- Setting the certificateValidationMode to -->
              <!-- PeerOrChainTrust means that if the certificate -->
              <!-- is in the user's Trusted People store, then it -->
              <!-- is trusted without performing a validation of -->
              <!-- the certificate's issuer chain. -->
              <!-- This setting is used here for convenience so -->
              <!-- that the sample can be run without having to -->
              <!-- have certificates issued by a certification -->
              <!-- authority (CA). This setting is less secure -->
              <!-- than the default, ChainTrust. The security -->
              <!-- implications of this setting should be -->
              <!-- carefully considered before using -->
              <!-- PeerOrChainTrust in production code.-->
              <authentication
                  certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>
```

La implementación del cliente establece el certificado de cliente que utilizar.

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client = new CalculatorClient("Certificate");
try
{
    client.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

    // Call the Subtract service operation.
    value1 = 145.00D;
    value2 = 76.54D;
    result = client.Subtract(value1, value2);
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

    // Call the Multiply service operation.
    value1 = 9.00D;
    value2 = 81.25D;
    result = client.Multiply(value1, value2);
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

    // Call the Divide service operation.
    value1 = 22.00D;
    value2 = 7.00D;
    result = client.Divide(value1, value2);
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
    client.Close();
}
catch (TimeoutException e)
{
    Console.WriteLine("Call timed out : {0}", e.Message);
    client.Abort();
}
catch (CommunicationException e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
    client.Abort();
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
    client.Abort();
}
```

Este ejemplo utiliza un X509CertificateValidator personalizado para validar los certificados. El ejemplo implementa CustomX509CertificateValidator, derivado de <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Consulte la documentación sobre <xref:System.IdentityModel.Selectors.X509CertificateValidator> para obtener más información. Este ejemplo de validador personalizado determinado implementa el método Validate para aceptar cualquier certificado X.509 que se emita por sí mismo tal y como se muestra en el código siguiente.

```csharp
public class CustomX509CertificateValidator : X509CertificateValidator
{
  public override void Validate ( X509Certificate2 certificate )
  {
   // Only accept self-issued certificates
   if (certificate.Subject != certificate.Issuer)
     throw new Exception("Certificate is not self-issued");
   }
}
```

 Una vez que se implementa el validador en el código de servicio, se debe informar al host de servicio sobre la instancia del validador que se va a usar. Esto se hace mediante el código siguiente.

```csharp
serviceHost.Credentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.Custom;
serviceHost.Credentials.ClientCertificate.Authentication.CustomCertificateValidator = new CustomX509CertificateValidator();
```

 O puede hacer lo mismo en la configuración tal y como se explica a continuación.

```xml
<behaviors>
    <serviceBehaviors>
     <behavior name="CalculatorServiceBehavior">
       ...
   <serviceCredentials>
    <!--The serviceCredentials behavior allows one to specify -->
    <!--authentication constraints on client certificates.-->
    <clientCertificate>
    <!-- Setting the certificateValidationMode to Custom means -->
    <!--that if the custom X509CertificateValidator does NOT -->
    <!--throw an exception, then the provided certificate will -->
    <!--be trusted without performing any validation beyond that -->
    <!--performed by the custom validator. The security -->
    <!--implications of this setting should be carefully -->
    <!--considered before using Custom in production code. -->
    <authentication certificateValidationMode="Custom"
       customCertificateValidatorType =
"Microsoft.ServiceModel.Samples. CustomX509CertificateValidator, service" />
   </clientCertificate>
   </serviceCredentials>
   ...
  </behavior>
 </serviceBehaviors>
</behaviors>
```

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. El cliente debería llamar correctamente a todos los métodos. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes

El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor. Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.

A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar para su ejecución en la configuración adecuada:

- Crear el certificado de servidor:

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar. La variable %SERVER_NAME% especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado es el host local.

    ```bash
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente:

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Se requiere este paso ya que los certificados generados por Makecert.exe no son de la confianza del sistema cliente. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

    ```bash
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Crear el certificado del cliente:

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de cliente que se va a usar. La variable %USER_NAME% especifica el nombre del cliente. Este valor está establecido en "test1" porque se trata del nombre que busca el código de cliente. Si cambia el valor de %USER_NAME% debe cambiar el valor correspondiente en el archivo de origen Client.cs y recompilar el cliente.

     El certificado está almacenado en Mi almacén (Personal) debajo de la ubicación de almacén CurrentUser.

    ```bash
    echo ************
    echo Client cert setup starting
    echo %USER_NAME%
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del cliente en el almacén de certificados de confianza del servidor:

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado del cliente en el almacén de los usuarios de confianza. Se requiere este paso porque el sistema servidor no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado del servidor con el certificado del cliente.

    ```bash
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo

1. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

2. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.

#### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Ejecute setup. bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 abierto con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!IMPORTANT]
    > El archivo por lotes Setup. bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup. bat.

2. Inicie Service.exe desde \service\bin.

3. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.

4. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

#### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos

1. Cree un directorio en el equipo del servicio.

2. Copie los archivos de programa de servicio desde \service\bin en el directorio virtual del equipo del servicio. Copie también los archivos Setup.bat, Cleanup.bat, GetComputerName.vbs e ImportClientCert.bat en el equipo de servicio.

3. Cree un directorio en el equipo cliente para los archivos binarios del cliente.

4. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.

5. En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Al `setup.bat` ejecutar con `service` el argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.

6. Edite Service. exe. config para reflejar el nuevo nombre del certificado ( `findValue` en el atributo en el [ \<>serviceCertificate ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), que es igual que el nombre de dominio completo del equipo. Cambie también el nombre del equipo en \<el elemento Service\<>/baseAddresses> de localhost al nombre completo de su equipo de servicio.

7. Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.

8. En el cliente, ejecute `setup.bat client` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.

9. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio. Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.

10. Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.

11. En el cliente, ejecute ImportServiceCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.

12. En el servidor, ejecute ImportClientCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. De esta forma se importa el certificado del cliente desde el archivo Client.cer al almacén LocalMachine - TrustedPeople.

13. En el equipo servidor, inicie Service.exe desde la ventana de símbolo del sistema.

14. En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo

1. Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo. Esto quita los certificados de cliente y servidor del almacén de certificados.

> [!NOTE]
> Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.
