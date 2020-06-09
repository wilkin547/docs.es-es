---
title: Seguridad de mensaje anónima
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
ms.openlocfilehash: 95101b8ec4f5a7fc60d0233ab6685b5c6851b44e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584992"
---
# <a name="message-security-anonymous"></a>Seguridad de mensaje anónima
El ejemplo de seguridad anónima de mensajes muestra cómo implementar una aplicación Windows Communication Foundation (WCF) que usa la seguridad de nivel de mensaje sin autenticación de cliente, pero que requiere la autenticación de servidor mediante el certificado X. 509 del servidor. Todos los mensajes de la aplicación entre el cliente y el servidor se firman y se cifran. Este ejemplo se basa en el ejemplo [wsHttpBinding](wshttpbinding.md) . Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS). El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

 Este ejemplo agrega una nueva operación a la interfaz de calculadora que devuelve `True` si no se autenticó el cliente.

```csharp
public class CalculatorService : ICalculator
{
    public bool IsCallerAnonymous()
    {
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.
        return ServiceSecurityContext.Current.IsAnonymous;
    }
    ...
}
```

 El servicio expone un extremo único para comunicarse con el servicio, que se define utilizando el archivo de configuración (Web.config). El punto de conexión está compuesto por una dirección, un enlace y un contrato. El enlace se configura con un enlace `wsHttpBinding`. El modo de seguridad predeterminado para el enlace `wsHttpBinding`es`Message`. El atributo `clientCredentialType` está establecido en `None`.

```xml
<system.serviceModel>

  <protocolMapping>
    <add scheme="http" binding="wsHttpBinding" />
  </protocolMapping>

  <bindings>
    <wsHttpBinding>
     <!-- This configuration defines the security mode as Message and -->
     <!-- the clientCredentialType as None. This mode provides -->
     <!-- server authentication only using the service certificate. -->

     <binding>
       <security mode="Message">
         <message clientCredentialType="None" />
       </security>
     </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 Las credenciales que se van a utilizar para la autenticación del servicio se especifican en [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) . El certificado de servidor debe contener el mismo valor para `SubjectName` que el valor especificado para el atributo `findValue` como se muestra en el código muestra siguiente.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior>
      <!--
    The serviceCredentials behavior allows you to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
      <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
      </serviceCredentials>
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

 La configuración de punto de conexión de cliente está compuesta de una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato. El modo de seguridad del cliente para el enlace `wsHttpBinding`es`Message`. El atributo `clientCredentialType` está establecido en `None`.

```xml
<system.serviceModel>
  <client>
    <endpoint name=""
             address="http://localhost/servicemodelsamples/service.svc"
             binding="wsHttpBinding"
             behaviorConfiguration="ClientCredentialsBehavior"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </client>

  <bindings>
    <wsHttpBinding>
      <!--This configuration defines the security mode as -->
      <!--Message and the clientCredentialType as None. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="None"/>
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 El ejemplo establece <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> en <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> para autenticar el certificado del servicio. Esto se hace en el archivo App.config del cliente en la sección `behaviors`. Esto significa que si el certificado está en el almacén de personas de confianza del usuario, se confía sin realizar una validación de la cadena del emisor del certificado. Este valor se utiliza aquí por comodidad, para que el ejemplo se pueda ejecutar sin que sean precisos certificados emitidos por una entidad de certificación (CA). Este valor es menos seguro que el valor predeterminado, ChainTrust. Las implicaciones de seguridad de este valor deberían considerarse cuidadosamente antes de utilizar `PeerOrChainTrust` en código de producción.

 La implementación del cliente agrega una llamada al `IsCallerAnonymous` método y, de lo contrario, no difiere del ejemplo [wsHttpBinding](wshttpbinding.md) .

```csharp
// Create a client with a client endpoint configuration.
CalculatorClient client = new CalculatorClient();

// Call the GetCallerIdentity operation.
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

...

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

```console
IsCallerAnonymous returned: True
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 El archivo por lotes Setup.bat incluido con el ejemplo de Message Security Anonymous permite configurar el servidor con un certificado pertinente para ejecutar una aplicación hospedada que requiera seguridad basada en certificado. El archivo por lotes se puede ejecutar en dos modos. Para ejecutar el archivo por lotes en modo de equipo único, escriba `setup.bat` en la línea de comandos. Para ejecutarlo en modo de servicio, escriba `setup.bat service`. Utilice este modo al ejecutar el ejemplo en varios equipos. Para obtener más detalles, vea el procedimiento de configuración al final de este tema.

 A continuación se proporciona una información general breve de las diferentes secciones de los archivos por lotes:

- Crear el certificado de servidor.

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     La variable %SERVER_NAME% especifica el nombre del servidor. El certificado se almacena en el almacén LocalMachine. Si el archivo por lotes de instalación se ejecuta con un argumento de servicio (como `setup.bat service`), % SERVER_NAME% contiene el nombre de dominio completo del equipo. De lo contrario, tiene como valor predeterminado el host local.

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.

     La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Conceder permisos sobre la clave privada del certificado.

     Las líneas siguientes del archivo por lotes Setup. bat hacen que el certificado de servidor almacenado en el almacén LocalMachine sea accesible para la cuenta de proceso de trabajo ASP.NET.

    ```bat
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
> Si usa una edición de Windows que no es de Estados Unidos, debe modificar el archivo Setup. bat y reemplazar el `NT AUTHORITY\NETWORK SERVICE` nombre de cuenta por su equivalente regional.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentran Makecert.exe y FindPrivateKey.exe.

2. Ejecute setup. bat desde la carpeta de instalación de ejemplo en una Símbolo del sistema para desarrolladores para que Visual Studio se ejecute con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes de instalación está diseñado para ejecutarse desde un Símbolo del sistema para desarrolladores para Visual Studio. Requiere que la variable de entorno path señale al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de una Símbolo del sistema para desarrolladores para Visual Studio.  
  
3. Escriba la dirección para comprobar el acceso al servicio mediante un explorador `http://localhost/servicemodelsamples/service.svc` .  
  
4. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
5. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Cree un directorio en el equipo del servicio. Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).  
  
2. Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio. Asegúrese de que copia los archivos en el subdirectorio \bin. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3. Cree un directorio en el equipo cliente para los archivos binarios del cliente.  
  
4. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.  
  
5. En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. `setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.  
  
6. Edite el archivo Web. config para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.  
  
7. Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.  
  
9. En el cliente, ejecute ImportServiceCert. bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.  
  
10. En el equipo cliente, inicie Client.exe desde un símbolo del sistema. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.  
  
> [!NOTE]
> Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`.
