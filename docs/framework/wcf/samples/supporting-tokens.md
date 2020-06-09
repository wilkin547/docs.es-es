---
title: Tokens auxiliares
ms.date: 03/30/2017
ms.assetid: 65a8905d-92cc-4ab0-b6ed-1f710e40784e
ms.openlocfilehash: 9c8ee4b11cd61e51e91c2e116ab3c20448fc1a58
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575048"
---
# <a name="supporting-tokens"></a>Tokens auxiliares
El ejemplo de los tokens auxiliares muestra cómo agregar tokens adicionales a un mensaje que utiliza WS-Security. El ejemplo agrega un token de seguridad binario de X.509 además de un token de seguridad del nombre de usuario. El token se pasa en un encabezado de mensaje de WS-Security desde el cliente al servicio y parte del mensaje se firma con una clave privada asociada con el token de seguridad de X.509 para demostrar la posesión del certificado X.509 al receptor. Esto es útil cuando es un requisito tener varias solicitudes asociadas con un mensaje para autenticar o autorizar el remitente. El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.

## <a name="demonstrates"></a>Muestra
 El ejemplo explica:

- Cómo un cliente puede pasar los tokens de seguridad adicionales a un servicio.

- Cómo el servidor puede tener acceso a las notificaciones asociadas a tokens de seguridad adicionales.

- Cómo el certificado X.509 del servidor se utiliza para proteger la clave simétrica utilizada para el cifrado y firma de mensajes.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

## <a name="client-authenticates-with-username-token-and-supporting-x509-security-token"></a>El cliente se autentica con el token del nombre de usuario y el token de seguridad X.509 compatible
 El servicio expone un punto de conexión único para comunicarse que se crea mediante programación usando las clases `BindingHelper` y `EchoServiceHost`. El punto de conexión está compuesto por una dirección, un enlace y un contrato. El enlace se configura con un enlace personalizado utilizando `SymmetricSecurityBindingElement` y `HttpTransportBindingElement`. Este ejemplo establece `SymmetricSecurityBindingElement` para utilizar un certificado X.509 de servicio para proteger la clave simétrica durante la transmisión y pasar `UserNameToken` junto con el `X509SecurityToken` compatible en un encabezado de mensaje de WS-Security. La clave simétrica se utiliza para cifrar el cuerpo del mensaje y el token de seguridad del nombre de usuario. El token auxiliar se pasa como un token de seguridad binario adicional en el encabezado de mensaje de WS-Security. La autenticidad del token auxiliar se demuestra firmando parte del mensaje con la clave privada asociada con el token de seguridad X.509 compatible.

```csharp
public static Binding CreateMultiFactorAuthenticationBinding()
{
    HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();

    // the message security binding element will be configured to require 2 tokens:
    // 1) A username-password encrypted with the service token
    // 2) A client certificate used to sign the message

    // Instantiate a binding element that will require the username/password token in the message (encrypted with the server cert)
    SymmetricSecurityBindingElement messageSecurity = SecurityBindingElement.CreateUserNameForCertificateBindingElement();

    // Create supporting token parameters for the client X509 certificate.
    X509SecurityTokenParameters clientX509SupportingTokenParameters = new X509SecurityTokenParameters();
    // Specify that the supporting token is passed in message send by the client to the service
    clientX509SupportingTokenParameters.InclusionMode = SecurityTokenInclusionMode.AlwaysToRecipient;
    // Turn off derived keys
    clientX509SupportingTokenParameters.RequireDerivedKeys = false;
    // Augment the binding element to require the client's X509 certificate as an endorsing token in the message
    messageSecurity.EndpointSupportingTokenParameters.Endorsing.Add(clientX509SupportingTokenParameters);

    // Create a CustomBinding based on the constructed security binding element.
    return new CustomBinding(messageSecurity, httpTransport);
}
```

 El comportamiento especifica las credenciales del servicio que se van a utilizar para la autenticación del cliente además de la información sobre el certificado X.509 del servicio. El ejemplo utiliza `CN=localhost` como un nombre de asunto en el certificado X.509 del servicio.

```csharp
override protected void InitializeRuntime()
{
    // Extract the ServiceCredentials behavior or create one.
    ServiceCredentials serviceCredentials =
        this.Description.Behaviors.Find<ServiceCredentials>();
    if (serviceCredentials == null)
    {
        serviceCredentials = new ServiceCredentials();
        this.Description.Behaviors.Add(serviceCredentials);
    }

    // Set the service certificate
    serviceCredentials.ServiceCertificate.SetCertificate(
                                       "CN=localhost");

/*
Setting the CertificateValidationMode to PeerOrChainTrust means that if the certificate is in the Trusted People store, then it will be trusted without performing a validation of the certificate's issuer chain. This setting is used here for convenience so that the sample can be run without having to have certificates issued by a certification authority (CA).
This setting is less secure than the default, ChainTrust. The security implications of this setting should be carefully considered before using PeerOrChainTrust in production code.
*/
    serviceCredentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;

    // Create the custom binding and add an endpoint to the service.
    Binding multipleTokensBinding =
         BindingHelper.CreateMultiFactorAuthenticationBinding();
    this.AddServiceEndpoint(typeof(IEchoService),
                          multipleTokensBinding, string.Empty);
    base.InitializeRuntime();
}
```

 Código del servicio:

```csharp
[ServiceBehavior(IncludeExceptionDetailInFaults = true)]
public class EchoService : IEchoService
{
    public string Echo()
    {
        string userName;
        string certificateSubjectName;
        GetCallerIdentities(
            OperationContext.Current.ServiceSecurityContext,
            out userName,
            out certificateSubjectName);
            return $"Hello {userName}, {certificateSubjectName}";
    }

    public void Dispose()
    {
    }

    bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet,
            string claimType, out TClaimResource resourceValue)
            where TClaimResource : class
    {
        resourceValue = default(TClaimResource);
        IEnumerable<Claim> matchingClaims =
            claimSet.FindClaims(claimType, Rights.PossessProperty);
        if(matchingClaims == null)
            return false;
        IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
        if (enumerator.MoveNext())
        {
            resourceValue =
              (enumerator.Current.Resource == null) ? null :
              (enumerator.Current.Resource as TClaimResource);
            return true;
        }
        else
        {
            return false;
        }
    }

    // Returns the username and certificate subject name provided by
    //the client
    void GetCallerIdentities(ServiceSecurityContext
        callerSecurityContext,
        out string userName, out string certificateSubjectName)
    {
        userName = null;
        certificateSubjectName = null;

       // Look in all the claimsets in the authorization context
       foreach (ClaimSet claimSet in
               callerSecurityContext.AuthorizationContext.ClaimSets)
       {
            if (claimSet is WindowsClaimSet)
            {
                // Try to find a Name claim. This will have been
                // generated from the windows username.
                string tmpName;
                if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,
                                                      out tmpName))
                {
                    userName = tmpName;
                }
            }
            else if (claimSet is X509CertificateClaimSet)
            {
                // Try to find an X500DistinguishedName claim. This will
                // have been generated from the client certificate.
                X500DistinguishedName tmpDistinguishedName;
                if (TryGetClaimValue<X500DistinguishedName>(claimSet,
                               ClaimTypes.X500DistinguishedName,
                               out tmpDistinguishedName))
                {
                    certificateSubjectName = tmpDistinguishedName.Name;
                }
            }
        }
    }
}
```

 El extremo del cliente se configura de una manera similar al extremo de servicio. El cliente utiliza la misma clase `BindingHelper` para crear un enlace. El resto de la instalación se encuentra en la clase `Client`. El cliente establece información sobre el token de seguridad del nombre de usuario, el token de seguridad X.509 compatible y la información sobre el certificado X.509 de servicio en el código de configuración en la colección de comportamientos del extremo del cliente.

```csharp
 static void Main()
 {
     // Create the custom binding and an endpoint address for
     // the service.
     Binding multipleTokensBinding =
         BindingHelper.CreateMultiFactorAuthenticationBinding();
         EndpointAddress serviceAddress = new EndpointAddress(
         "http://localhost/servicemodelsamples/service.svc");
       ChannelFactory<IEchoService> channelFactory = null;
       IEchoService client = null;

       Console.WriteLine("Username authentication required.");
       Console.WriteLine(
         "Provide a valid machine or domain account. [domain\\user]");
       Console.WriteLine("   Enter username:");
       string username = Console.ReadLine();
       Console.WriteLine("   Enter password:");
       string password = "";
       ConsoleKeyInfo info = Console.ReadKey(true);
       while (info.Key != ConsoleKey.Enter)
       {
           if (info.Key != ConsoleKey.Backspace)
           {
               if (info.KeyChar != '\0')
               {
                   password += info.KeyChar;
                }
                info = Console.ReadKey(true);
            }
            else if (info.Key == ConsoleKey.Backspace)
            {
                if (password != "")
                {
                    password =
                       password.Substring(0, password.Length - 1);
                }
                info = Console.ReadKey(true);
            }
         }
         for (int i = 0; i < password.Length; i++)
            Console.Write("*");
         Console.WriteLine();
         try
         {
           // Create a proxy with the previously create binding and
           // endpoint address
              channelFactory =
                 new ChannelFactory<IEchoService>(
                     multipleTokensBinding, serviceAddress);
           // configure the username credentials, the client
           // certificate and the server certificate on the channel
           // factory
           channelFactory.Credentials.UserName.UserName = username;
           channelFactory.Credentials.UserName.Password = password;
           channelFactory.Credentials.ClientCertificate.SetCertificate(
           "CN=client.com", StoreLocation.CurrentUser, StoreName.My);
              channelFactory.Credentials.ServiceCertificate.SetDefaultCertificate(
           "CN=localhost", StoreLocation.LocalMachine, StoreName.My);
           client = channelFactory.CreateChannel();
           Console.WriteLine("Echo service returned: {0}",
                                           client.Echo());

           ((IChannel)client).Close();
           channelFactory.Close();
        }
        catch (CommunicationException e)
        {
         Abort((IChannel)client, channelFactory);
         // if there is a fault then print it out
         FaultException fe = null;
         Exception tmp = e;
         while (tmp != null)
         {
            fe = tmp as FaultException;
            if (fe != null)
            {
                break;
            }
            tmp = tmp.InnerException;
        }
        if (fe != null)
        {
           Console.WriteLine("The server sent back a fault: {0}",
         fe.CreateMessageFault().Reason.GetMatchingTranslation().Text);
        }
        else
        {
         Console.WriteLine("The request failed with exception: {0}",e);
        }
    }
    catch (TimeoutException)
    {
        Abort((IChannel)client, channelFactory);
        Console.WriteLine("The request timed out");
    }
    catch (Exception e)
    {
         Abort((IChannel)client, channelFactory);
          Console.WriteLine(
          "The request failed with unexpected exception: {0}", e);
    }
    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();
}
```

## <a name="displaying-callers-information"></a>Visualización de la información de los autores de la llamada
 Para mostrar la información del autor de la llamada, puede usar `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` tal y como se muestra en el código siguiente. `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contiene notificaciones de autorización asociadas con el autor de la llamada actual. Windows Communication Foundation (WCF) suministra automáticamente esas notificaciones para cada token recibido en el mensaje.

```csharp
bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet, string
                         claimType, out TClaimResource resourceValue)
    where TClaimResource : class
{
    resourceValue = default(TClaimResource);
    IEnumerable<Claim> matchingClaims =
    claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
          return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    if (enumerator.MoveNext())
    {
        resourceValue = (enumerator.Current.Resource == null) ? null : (enumerator.Current.Resource as TClaimResource);
        return true;
    }
    else
    {
         return false;
    }
}

// Returns the username and certificate subject name provided by the client
void GetCallerIdentities(ServiceSecurityContext callerSecurityContext, out string userName, out string certificateSubjectName)
{
    userName = null;
    certificateSubjectName = null;

    // Look in all the claimsets in the authorization context
    foreach (ClaimSet claimSet in
      callerSecurityContext.AuthorizationContext.ClaimSets)
    {
        if (claimSet is WindowsClaimSet)
        {
            // Try to find a Name claim. This will have been generated
            //from the windows username.
            string tmpName;
            if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,
                                                     out tmpName))
            {
                userName = tmpName;
            }
        }
        else if (claimSet is X509CertificateClaimSet)
         {
            //Try to find an X500DistinguishedName claim.
            //This will have been generated from the client
            //certificate.
            X500DistinguishedName tmpDistinguishedName;
            if (TryGetClaimValue<X500DistinguishedName>(claimSet,
               ClaimTypes.X500DistinguishedName,
               out tmpDistinguishedName))
            {
                    certificateSubjectName = tmpDistinguishedName.Name;
            }
        }
    }
}
```

## <a name="running-the-sample"></a>Ejecutar el ejemplo
 Al ejecutar el ejemplo, el cliente le pide primero que proporcione el nombre de usuario y la contraseña para el token del nombre de usuario. Asegúrese de proporcionar los valores correctos para la cuenta del sistema, porque WCF en el servicio asigna los valores proporcionados en el token de nombre de usuario a la identidad proporcionada por el sistema. Después de esto, el cliente muestra la respuesta del servicio. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes
 El archivo por lotes Setup.bat incluido con este ejemplo le permite configurar el servidor con certificados pertinentes para ejecutar la aplicación hospedada por Internet Information Services (IIS) que necesita la seguridad basada en el certificado del servidor. Este archivo por lotes debe modificarse para que funcione a través de los equipos o en un caso no hospedado.

 A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.

### <a name="creating-the-client-certificate"></a>Crear el certificado del cliente
 Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de cliente que se va a usar. La variable `%CLIENT_NAME%` especifica el asunto del certificado de cliente. Este ejemplo utiliza "client.com" como el nombre del asunto.

 El certificado está almacenado en Mi almacén (Personal) en la ubicación de almacén `CurrentUser`.

```console
echo ************
echo making client cert
echo ************
makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
```

### <a name="installing-the-client-certificate-into-the-servers-trusted-store"></a>Instalar el certificado del cliente en el almacén de confianza del servidor
 La línea siguiente del archivo por lotes Setup.bat copia el certificado de cliente en el almacén de confianza del servidor. Este paso es necesario porque el sistema del servidor no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

```console
echo ************
echo copying client cert to server's CurrentUserstore
echo ************
certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
```

### <a name="creating-the-server-certificate"></a>Crear el certificado de servidor
 Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar. La variable `%SERVER_NAME%`especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado en este archivo por lotes es el host local.

 El certificado se almacena en el almacén My (Personal), en la ubicación de almacenamiento LocalMachine. El certificado está almacenado en el almacén LocalMachine para los servicios hospedados por IIS. En el caso de servicios autohospedados, debería modificar el archivo por lotes para almacenar el certificado de servidor en la ubicación de almacén CurrentUser reemplazando la cadena LocalMachine con CurrentUser.

```console
echo ************
echo Server cert setup starting
echo %SERVER_NAME%
echo ************
echo making server cert
echo ************
makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
```

### <a name="installing-server-certificate-into-clients-trusted-certificate-store"></a>Instalar el certificado del servidor en un almacén de certificados de confianza del cliente
 Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

```console
echo ************
echo copying server cert to client's TrustedPeople store
echo ************certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
```

### <a name="enabling-access-to-the-certificates-private-key"></a>Cómo permitir el acceso a la clave privada del certificado
 Para permitir el acceso a la clave privada del certificado del servicio hospedado por IIS, la cuenta de usuario bajo la que se ejecuta el proceso hospedado por IIS debe tener los permisos adecuados para la clave privada. Esto se logra con los últimos pasos del script Setup.bat.

```console
echo ************
echo setting privileges on server certificates
echo ************
for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i
set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
(ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
iisreset
```

##### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.

##### <a name="to-run-the-sample-on-the-same-machine"></a>Para ejecutar el ejemplo en el mismo equipo

1. Ejecute setup. bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 y ejecute con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup. bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup. bat. Asegúrese de quitar los certificados ejecutando Cleanup.bat cuando termine con el ejemplo. Otros ejemplos de seguridad usan los mismos certificados.  
  
2. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
3. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
##### <a name="to-run-the-sample-across-machines"></a>Para ejecutar el ejemplo en los equipos  
  
1. Cree un directorio en el equipo del servicio. Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).  
  
2. Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio. Asegúrese de que copia los archivos en el subdirectorio \bin. Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el equipo de servicio.  
  
3. Cree un directorio en el equipo cliente para los archivos binarios del cliente.  
  
4. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.  
  
5. En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Al ejecutar `setup.bat` con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.  
  
6. Edite el archivo Web. config para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.  
  
7. Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.  
  
8. En el cliente, ejecute `setup.bat client` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador. Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.  
  
9. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio. Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.  
  
10. Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.  
  
11. En el cliente, ejecute ImportServiceCert.bat. Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.  
  
12. En el servidor, ejecute ImportClientCert.bat. Esto importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine - TrustedPeople.  
  
13. En el equipo cliente, inicie Client.exe desde la ventana de símbolo del sistema. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
##### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
- Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
  
> [!NOTE]
> Este script no quita los certificados del servicio en un cliente cuando se ejecuta este ejemplo en los equipos. Si ha ejecutado ejemplos de WCF que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.
