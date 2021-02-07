---
description: 'Más información acerca de: nombre de usuario de seguridad de mensaje'
title: Nombre de usuario de seguridad de mensaje
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
ms.openlocfilehash: f02b1aecffddfc047cc96acc071ab5eefca91807
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752293"
---
# <a name="message-security-user-name"></a>Nombre de usuario de seguridad de mensaje

Este ejemplo muestra cómo implementar una aplicación que utiliza WS-Security con autenticación de nombre de usuario para el cliente y que requiere la autenticación del servidor mediante el certificado X.509v3 del servidor. Todos los mensajes de la aplicación entre el cliente y el servidor se firman y se cifran. De forma predeterminada, el nombre de usuario y contraseña proporcionadas por el cliente se utilizan para iniciar una sesión con una cuenta de Windows válida. Este ejemplo se basa en [wsHttpBinding](wshttpbinding.md). Este ejemplo está compuesto de un programa de consola de cliente (Client.exe) y una biblioteca de servicios (Service.dll) hospedada por Internet Information Services (IIS). El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo también muestra:  
  
- La asignación predeterminada a cuentas Windows, para que se pueda realizar autorización adicional.  
  
- Cómo tener acceso a la información de identidad del llamador desde el código del servicio.  
  
 El servicio expone un extremo único para comunicarse con el servicio, que se define mediante el archivo de configuración Web.config. El punto de conexión consta de una dirección, un enlace y un contrato. El enlace se configura con un estándar [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , que usa la seguridad de mensaje de forma predeterminada. Este ejemplo establece el estándar [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) para utilizar la autenticación de nombre de usuario de cliente. El comportamiento especifica que se van a usar las credenciales del usuario para la autenticación del servicio. El certificado de servidor debe contener el mismo valor para el nombre de sujeto que el `findValue` atributo en [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
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
</system.serviceModel>  
```  
  
 La configuración de punto de conexión de cliente está compuesta de una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato. El enlace del cliente se configura con el `securityMode` adecuado y `authenticationMode`. Cuando se utilice un escenario de varios equipos, la dirección del extremo de servicio debe cambiarse según corresponda.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 La implementación del cliente establece el nombre de usuario y la contraseña que utilizar.  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```

 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.  
  
```console  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 El archivo por lotes Setup.bat incluido con los ejemplos de MessageSecurity le permite configurar el servidor con un certificado pertinente para ejecutar una aplicación hospedada que exija seguridad basada en el certificado del servidor. El archivo por lotes se puede ejecutar en dos modos. Para ejecutar el archivo por lotes en modo de equipo único, escriba `setup.bat` en la línea de comandos. Para ejecutarlo en modo de servicio, escriba `setup.bat service`. Este modo se usa al ejecutar el ejemplo en varios equipos. Para obtener más detalles, vea el procedimiento de configuración al final de este tema.  
  
 A continuación se proporciona una información general breve de las diferentes secciones de los archivos por lotes.  
  
- Crear el certificado de servidor  
  
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
  
     La variable %SERVER_NAME% especifica el nombre del servidor. El certificado se almacena en el almacén LocalMachine. Si el archivo por lotes Setup.bat se ejecuta con un argumento de servicio (como `setup.bat service`), % SERVER_NAME% contiene el nombre de dominio completo del equipo.  De lo contrario, tiene como valor predeterminado el host local.  
  
- Instalar el certificado del servidor en el almacén de certificados de confianza de cliente.  
  
     La línea siguiente copia el certificado de servidor en el almacén de personas de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.  
  
    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- Conceder permisos sobre la clave privada del certificado.  
  
     Las líneas siguientes del archivo por lotes de Setup.bat hacen que el certificado de servidor almacenado en el almacén LocalMachine sea accesible para la cuenta de proceso de trabajo de ASP.NET.  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    > Si usa un valor que no es de U. S. Edición en Inglés de Windows debe modificar el archivo Setup.bat y reemplazar el `NT AUTHORITY\NETWORK SERVICE` nombre de cuenta por su equivalente regional.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo  
  
1. Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentran Makecert.exe y FindPrivateKey.exe.  
  
2. Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.  
  
    > [!NOTE]
    > El archivo por lotes Setup.bat está diseñado para ejecutarse desde un Símbolo del sistema para desarrolladores para Visual Studio. Requiere que la variable de entorno path señale al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de una Símbolo del sistema para desarrolladores para Visual Studio.  
  
3. Escriba la dirección para comprobar el acceso al servicio mediante un explorador `http://localhost/servicemodelsamples/service.svc` .
  
4. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
5. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Cree un directorio en el equipo del servicio. Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services.  
  
2. Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio. Asegúrese de que copia los archivos en el subdirectorio \bin. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3. Cree un directorio en el equipo cliente para los archivos binarios del cliente.  
  
4. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.  
  
5. En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. `setup.bat`Al ejecutar con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.  
  
6. Modifique el archivo Web.config para reflejar el nuevo nombre del certificado (en el atributo findValue del elemento serviceCertificate), que es igual que el nombre de dominio completo del equipo`.`  
  
7. Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.  
  
9. En el cliente, ejecute ImportServiceCert.bat en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.  
  
10. En el equipo cliente, inicie Client.exe desde un símbolo del sistema. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Ejecute Cleanup.bat en la carpeta de ejemplos después de que haya terminado de ejecutar el ejemplo.  
  
    > [!NOTE]
    > Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de Windows Communication Foundation (WCF) que usan certificados en los equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.
