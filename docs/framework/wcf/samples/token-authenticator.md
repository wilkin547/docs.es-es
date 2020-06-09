---
title: Autenticador de tokens
ms.date: 03/30/2017
ms.assetid: 84382f2c-f6b1-4c32-82fa-aebc8f6064db
ms.openlocfilehash: f4b49edd3b5a2cecd203feed713c7694450f7497
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596557"
---
# <a name="token-authenticator"></a>Autenticador de tokens
Este ejemplo muestra cómo implementar un autenticador de tokens personalizado. Un autenticador de tokens en Windows Communication Foundation (WCF) se usa para validar el token utilizado con el mensaje, comprobar que es autocoherente y autenticar la identidad asociada con el token.

 Los autenticadores de tokens personalizados son útiles en diversos casos, como:

- Cuando desee reemplazar el mecanismo de autenticación predeterminado asociado a un token.

- Cuando está creando un token personalizado.

 En este ejemplo se muestra lo siguiente:

- Cómo un cliente puede autenticar utilizando un par de nombre de usuario y contraseña.

- Cómo el servidor puede validar las credenciales del cliente mediante un autenticador de tokens personalizado.

- Cómo se vincula el código de servicio WCF con el autenticador de tokens personalizado.

- Cómo el servidor se puede autenticar utilizando el certificado X.509 del servidor.

 En este ejemplo también se muestra cómo se puede tener acceso a la identidad del llamador desde WCF después del proceso de autenticación de tokens personalizado.

 El servicio expone un extremo único para comunicarse con el servicio, definido mediante el archivo de configuración App.config. El punto de conexión está compuesto por una dirección, un enlace y un contrato. El enlace se configura con un `wsHttpBinding`estándar, con el conjunto de modo de seguridad en mensaje - el modo predeterminado de `wsHttpBinding`. Este ejemplo establece el `wsHttpBinding` estándar para utilizar la autenticación mediante el nombre de usuario del cliente. El servicio también configura el certificado del servicio utilizando comportamiento`serviceCredentials`. El comportamiento `securityCredentials` le permite especificar un certificado del servicio. Un cliente utiliza un certificado de servicio para autenticar el servicio y proporcionar protección al mensaje. La configuración siguiente hace referencia al certificado del host local instalado durante la configuración del ejemplo tal y como se describe en las siguientes instrucciones de configuración.

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service" />
          </baseAddresses>
        </host>
        <!-- use base address provided by host -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults="False" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
....        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

 La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato. El enlace del cliente se configura con el `Mode` adecuado y `clientCredentialType`.

```xml
<system.serviceModel>
    <client>
      <endpoint name=""
                address="http://localhost:8000/servicemodelsamples/service"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
```

 La implementación del cliente establece el nombre de usuario y la contraseña que utilizar.

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a>autenticador de tokens personalizado
 Siga los siguientes pasos para crear un autenticador de tokens personalizado:

1. Escriba un autenticador de tokens personalizado.

     El ejemplo implementa un autenticador de tokens personalizado que valida que el nombre de usuario tiene un formato de correo electrónico válido. Deriva <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>. El método más importante en esta clase es <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>. En este método, el autenticador valida el formato del nombre de usuario y también que el nombre de host no es de un dominio no autorizado. Si se cumplen ambas condiciones, a continuación, devuelve una colección de solo lectura de instancias <xref:System.IdentityModel.Policy.IAuthorizationPolicy> que se utiliza a continuación para proporcionar indicaciones que representan la información almacenada dentro del token del nombre de usuario.

    ```csharp
    protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateUserNamePasswordCore(string userName, string password)
    {
        if (!ValidateUserNameFormat(userName))
            throw new SecurityTokenValidationException("Incorrect UserName format");

        ClaimSet claimSet = new DefaultClaimSet(ClaimSet.System, new Claim(ClaimTypes.Name, userName, Rights.PossessProperty));
        List<IIdentity> identities = new List<IIdentity>(1);
        identities.Add(new GenericIdentity(userName));
        List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
        policies.Add(new UnconditionalPolicy(ClaimSet.System, claimSet, DateTime.MaxValue.ToUniversalTime(), identities));
        return policies.AsReadOnly();
    }
    ```

2. Proporcione una directiva de autorización que es devuelta por un autenticador de tokens personalizado.

     Este ejemplo proporciona su propia implementación de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> llamada `UnconditionalPolicy` que devuelve un conjunto de indicaciones e identidades que se pasaron a él en su constructor.

    ```csharp
    class UnconditionalPolicy : IAuthorizationPolicy
    {
        String id = Guid.NewGuid().ToString();
        ClaimSet issuer;
        ClaimSet issuance;
        DateTime expirationTime;
        IList<IIdentity> identities;

        public UnconditionalPolicy(ClaimSet issuer, ClaimSet issuance, DateTime expirationTime, IList<IIdentity> identities)
        {
            if (issuer == null)
                throw new ArgumentNullException("issuer");
            if (issuance == null)
                throw new ArgumentNullException("issuance");

            this.issuer = issuer;
            this.issuance = issuance;
            this.identities = identities;
            this.expirationTime = expirationTime;
        }

        public string Id
        {
            get { return this.id; }
        }

        public ClaimSet Issuer
        {
            get { return this.issuer; }
        }

        public DateTime ExpirationTime
        {
            get { return this.expirationTime; }
        }

        public bool Evaluate(EvaluationContext evaluationContext, ref object state)
        {
            evaluationContext.AddToTarget(this, this.issuance);

            if (this.identities != null)
            {
                object value;
                IList<IIdentity> contextIdentities;
                if (!evaluationContext.Properties.TryGetValue("Identities", out value))
                {
                    contextIdentities = new List<IIdentity>(this.identities.Count);
                    evaluationContext.Properties.Add("Identities", contextIdentities);
                }
                else
                {
                    contextIdentities = value as IList<IIdentity>;
                }
                foreach (IIdentity identity in this.identities)
                {
                    contextIdentities.Add(identity);
                }
            }

            evaluationContext.RecordExpirationTime(this.expirationTime);
            return true;
        }
    }
    ```

3. Escribir un administrador de tokens de seguridad personalizado.

     <xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> para objetos <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concretos que se pasan en el método `CreateSecurityTokenAuthenticator`. El administrador de tokens de seguridad también se utiliza para crear proveedores de tokens y serializadores de tokens, aunque en este ejemplo no se explica. En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenAuthenticator` para devolver el autenticador de tokens de nombre de usuario personalizado cuando los requisitos de token pasados indican que se solicita el autenticador de nombre de usuario.

    ```csharp
    public class MySecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        MyUserNameCredential myUserNameCredential;

        public MySecurityTokenManager(MyUserNameCredential myUserNameCredential)
            : base(myUserNameCredential)
        {
            this.myUserNameCredential = myUserNameCredential;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType ==  SecurityTokenTypes.UserName)
            {
                outOfBandTokenResolver = null;
                return new MyTokenAuthenticator();
            }
            else
            {
                return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
            }
        }
    }
    ```

4. Escribir una credencial de servicio personalizada.

     Se usa una clase de credenciales de servicio para representar las credenciales que se configuran para el servicio y crear el administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y serializadores de tokens.

    ```csharp
    public class MyUserNameCredential : ServiceCredentials
    {

        public MyUserNameCredential()
            : base()
        {
        }

        protected override ServiceCredentials CloneCore()
        {
            return new MyUserNameCredential();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new MySecurityTokenManager(this);
        }

    }
    ```

5. Configurar el servicio para utilizar la credencial de servicio personalizada.

     Para que el servicio utilice la credencial de servicio personalizada, eliminamos la clase de credencial de servicio predeterminada después de capturar el certificado del servicio que ya está preconfigurado en la credencial del servicio predeterminada y configuramos la nueva instancia de credencial de servicio para utilizar los certificados del servicio preconfigurados y agregar esta nueva instancia de credencial de servicio a los comportamientos del servicio.

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 Para mostrar la información del autor de la llamada, puede usar <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> tal y como se muestra en el código siguiente. <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene información de las notificaciones sobre el llamador actual.

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes
 El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor. Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.

 A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.

- Crear el certificado de servidor.

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar. La variable `%SERVER_NAME%`especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado en este archivo por lotes es el host local.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > El archivo por lotes de instalación está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK. Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK. Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.

#### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Ejecute setup. bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 abierto con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup. bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup. bat.  
  
2. Inicie service.exe desde \service\bin.  
  
3. Inicie client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
4. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Cree un directorio en el equipo del servicio para los binarios del servicio.  
  
2. Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3. Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo. El archivo App.config del servicio debe actualizarse para reflejar este nuevo nombre de certificado. Puede crear uno utilizando el archivo Setup.bat si establece la variable `%SERVER_NAME%` en el nombre de host completo del equipo en el que se ejecutará el servicio. Tenga en cuenta que el archivo Setup. bat se debe ejecutar desde un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.  
  
4. Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente. No necesita hacerlo excepto cuando un emisor de confianza del cliente emite el certificado de servidor.  
  
5. En el archivo App.config situado en el equipo del servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.  
  
6. En el equipo del servicio, ejecute service.exe desde un símbolo del sistema.  
  
7. Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.  
  
9. En el equipo cliente, inicie Client.exe desde un símbolo del sistema.  
  
10. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
1. Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.  
