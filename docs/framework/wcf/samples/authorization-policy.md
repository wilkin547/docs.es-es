---
title: Directiva de autorización
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 5b93f7e05261d9770650335160ddb56404aed94d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585511"
---
# <a name="authorization-policy"></a>Directiva de autorización

Este ejemplo muestra cómo implementar una directiva de autorización de notificación personalizada y un administrador de autorización de servicio personalizado asociado. Esto es útil cuando el servicio realiza las comprobaciones de acceso basadas en las notificaciones para operaciones de servicio y antes de las comprobaciones de acceso, concede ciertos derechos al autor de la llamada. Este ejemplo muestra el proceso de agregar las notificaciones así como el proceso para hacer una comprobación de acceso con el conjunto finalizado de notificaciones. Todos los mensajes de la aplicación entre el cliente y el servidor se firman y se cifran. De forma predeterminada, con el enlace `wsHttpBinding`, se utiliza un nombre de usuario y una contraseña proporcionadas por el cliente para iniciar sesión con una cuenta válida de Windows NT. Este ejemplo muestra cómo utilizar un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizado para autenticar el cliente. Además, este ejemplo muestra el cliente que se autentica con el servicio utilizando un certificado X.509. Este ejemplo muestra una implementación de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y <xref:System.ServiceModel.ServiceAuthorizationManager>, que entre ellos conceden acceso a métodos concretos del servicio para usuarios específicos. Este ejemplo se basa en el [nombre de usuario de seguridad del mensaje](message-security-user-name.md), pero muestra cómo realizar una transformación de notificaciones antes de que <xref:System.ServiceModel.ServiceAuthorizationManager> se llame a.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

 En resumen, este ejemplo muestra cómo:

- El cliente se puede autenticar utilizando una contraseña de nombre de usuario.

- El cliente se puede autenticar utilizando un certificado X.509.

- El servidor valida las credenciales del cliente contra un validador `UsernamePassword` personalizado.

- El servidor se autentica utilizando el certificado X.509 del servidor.

- El servidor puede utilizar <xref:System.ServiceModel.ServiceAuthorizationManager> para controlar el acceso a ciertos métodos en el servicio.

- Cómo implementar <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.

El servicio expone dos puntos de conexión para comunicarse con el servicio, definidos mediante el archivo de configuración app. config. Cada punto de conexión consta de una dirección, un enlace y un contrato. Un enlace se configura con un enlace `wsHttpBinding` estándar que utiliza la autenticación de WS-Security y del nombre de usuario del cliente. El otro enlace se configura con un enlace `wsHttpBinding` estándar que utiliza la autenticación de WS-Security y del certificado de cliente. [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)Especifica que las credenciales de usuario se usarán para la autenticación del servicio. El certificado de servidor debe contener el mismo valor para la `SubjectName` propiedad que el `findValue` atributo en [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) .

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

Cada configuración de extremo de cliente está compuesta de un nombre de configuración, una dirección absoluta para el extremo de servicio, el enlace y el contrato. El enlace de cliente se configura con el modo de seguridad adecuado tal y como se especifica en este caso en [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) y `clientCredentialType` según se especifica en [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) .

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

Para el punto de conexión basado en el nombre de usuario, la implementación del cliente establece el nombre de usuario y la contraseña que se van a utilizar.

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

Para el punto de conexión basado en el certificado, la implementación del cliente establece el certificado de cliente que se va a usar.

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

Este ejemplo utiliza un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizado para validar nombres de usuario y contraseñas. El ejemplo implementa `MyCustomUserNamePasswordValidator`, derivado de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Consulte la documentación sobre <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> para obtener más información. Con el fin de mostrar la integración con <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, este ejemplo de validador personalizado implementa el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> para aceptar pares de nombre de usuario/contraseña donde el primero coincide con la contraseña tal y como se muestra en el código siguiente.

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

Una vez que se implementa el validador en el código de servicio, se debe informar al host de servicio sobre la instancia del validador que se va a usar. Esto se hace mediante el código siguiente:

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

O bien, puede hacer lo mismo en la configuración:

```xml
<behavior>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

Windows Communication Foundation (WCF) proporciona un modelo avanzado basado en notificaciones para realizar comprobaciones de acceso. El objeto <xref:System.ServiceModel.ServiceAuthorizationManager> se utiliza para realizar la comprobación de acceso y determinar si las notificaciones asociadas con el cliente satisfacen los requisitos necesarios para tener acceso al método de servicio.

Para fines de demostración, este ejemplo muestra una implementación de <xref:System.ServiceModel.ServiceAuthorizationManager> que implementa el <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> método para permitir el acceso de un usuario a los métodos según las notificaciones de tipo `http://example.com/claims/allowedoperation` cuyo valor es el URI de la acción que se permite llamar.

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

Una vez implementado el <xref:System.ServiceModel.ServiceAuthorizationManager> personalizado, se debe informar al host de servicio sobre el <xref:System.ServiceModel.ServiceAuthorizationManager> que se va a utilizar. Esto se hace tal y como se muestra en el código siguiente.

```xml
<behavior>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

El método <xref:System.IdentityModel.Policy.IAuthorizationPolicy> principal que implementar es el método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>.

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

El código anterior muestra cómo el método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> comprueba que no se ha añadido ninguna notificación que afecte al procesamiento y añade notificaciones específicas. Las notificaciones que se permiten se obtienen del método `GetAllowedOpList`, que se implementa para devolver una lista concreta de operaciones que el usuario puede realizar. La directiva de autorización agrega notificaciones para tener acceso a la operación determinada. <xref:System.ServiceModel.ServiceAuthorizationManager> lo utiliza después para realizar decisiones de comprobación de acceso.

Una vez implementado el <xref:System.IdentityModel.Policy.IAuthorizationPolicy> personalizado, se debe informar al host de servicio sobre las directivas de autorización que desee utilizar.

```xml
<serviceAuthorization>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. El cliente llama correctamente a los métodos Sumar, Restar y Multiplicar y obtiene un mensaje de acceso denegado al intentar llamar al método Dividir. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes

El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor.

A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar para su ejecución en la configuración adecuada:

- Crear el certificado de servidor.

    Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar. La variable %SERVER_NAME% especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado es el host local.

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.

    Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Se requiere este paso porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Crear el certificado del cliente.

    Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de cliente que se va a usar. La variable %USER_NAME% especifica el nombre del servidor. Este valor está establecido en "test1" porque se trata del nombre que `IAuthorizationPolicy` busca. Si cambia el valor de %USER_NAME%, debe cambiar el valor correspondiente en el método `IAuthorizationPolicy.Evaluate`.

    El certificado está almacenado en Mi almacén (Personal) debajo de la ubicación de almacén CurrentUser.

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- Instalar el certificado del cliente en el almacén de certificados de confianza del servidor.

    Las líneas siguientes del archivo por lotes Setup.bat copian el certificado del cliente en el almacén de los usuarios de confianza. Se requiere este paso porque el sistema servidor no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado del servidor con el certificado del cliente.

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo

1. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

2. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.

> [!NOTE]
> Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.

### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Abra Símbolo del sistema para desarrolladores para Visual Studio con privilegios de administrador y ejecute *setup. bat* desde la carpeta de instalación de ejemplo. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup. bat está diseñado para ejecutarse desde Símbolo del sistema para desarrolladores para Visual Studio. La variable de entorno PATH establecida en Símbolo del sistema para desarrolladores para Visual Studio apunta al directorio que contiene los archivos ejecutables requeridos por el script *setup. bat* .

1. Inicie Service. exe desde *service\bin*.

1. Inicie Client. exe desde *\client\bin\*. La actividad del cliente se muestra en la aplicación de consola del cliente.

Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos

1. Cree un directorio en el equipo del servicio.

2. Copie los archivos de programa de servicio de *\service\bin* en el directorio del equipo de servicio. Copie también los archivos Setup.bat, Cleanup.bat, GetComputerName.vbs e ImportClientCert.bat en el equipo de servicio.

3. Cree un directorio en el equipo cliente para los archivos binarios del cliente.

4. Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente. Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.

5. En el servidor, ejecute `setup.bat service` en símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.

    Al ejecutar `setup.bat` con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado *Service. cer*.

6. Edite *Service. exe. config* para reflejar el nuevo nombre del certificado (en el `findValue` atributo de [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo. Cambie también el **ComputerName** en el \<service> / \<baseAddresses> elemento de localhost al nombre completo de su equipo de servicio.

7. Copie el archivo *Service. cer* del directorio de servicio al directorio del cliente en el equipo cliente.

8. En el cliente, ejecute `setup.bat client` en símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.

    Al ejecutar `setup.bat` con el `client` argumento se crea un certificado de cliente denominado **Test1** y se exporta el certificado de cliente a un archivo denominado *Client. cer*.

9. En el archivo *Client. exe. config* del equipo cliente, cambie el valor de la dirección del extremo para que coincida con la nueva dirección del servicio. Para ello, reemplace **localhost** con el nombre de dominio completo del servidor.

10. Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.

11. En el cliente, ejecute *ImportServiceCert. bat* en símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.

    Esto importa el certificado de servicio del archivo Service. cer en el almacén **CurrentUser-TrustedPeople** .

12. En el servidor, ejecute *ImportClientCert. bat* en símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.

    Esto importa el certificado de cliente del archivo Client. cer en el almacén **LocalMachine-TrustedPeople** .

13. En el equipo servidor, inicie Service.exe desde la ventana de símbolo del sistema.

14. En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.

    Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).

### <a name="clean-up-after-the-sample"></a>Limpiar después del ejemplo

Para realizar la limpieza después del ejemplo, ejecute *Cleanup. bat* en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo. Esto quita los certificados de cliente y servidor del almacén de certificados.

> [!NOTE]
> Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos. Si ha ejecutado ejemplos de WCF que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople. Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.
