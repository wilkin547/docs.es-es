---
title: Autenticador de tokens
ms.date: 03/30/2017
ms.assetid: 84382f2c-f6b1-4c32-82fa-aebc8f6064db
ms.openlocfilehash: a493ea48d9d339c0bc1a4b191b084374ad5f2dc4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548597"
---
# <a name="token-authenticator"></a><span data-ttu-id="4fd31-102">Autenticador de tokens</span><span class="sxs-lookup"><span data-stu-id="4fd31-102">Token Authenticator</span></span>
<span data-ttu-id="4fd31-103">Este ejemplo muestra cómo implementar un autenticador de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-103">This sample demonstrates how to implement a custom token authenticator.</span></span> <span data-ttu-id="4fd31-104">Un autenticador de tokens en Windows Communication Foundation (WCF) se usa para validar el token utilizado con el mensaje, comprobar que es autocoherente y autenticar la identidad asociada con el token.</span><span class="sxs-lookup"><span data-stu-id="4fd31-104">A token authenticator in Windows Communication Foundation (WCF) is used for validating the token used with the message, verifying that it is self-consistent, and authenticating the identity associated with the token.</span></span>

 <span data-ttu-id="4fd31-105">Los autenticadores de tokens personalizados son útiles en diversos casos, como:</span><span class="sxs-lookup"><span data-stu-id="4fd31-105">Custom token authenticators are useful in a variety of cases, such as:</span></span>

- <span data-ttu-id="4fd31-106">Cuando desee reemplazar el mecanismo de autenticación predeterminado asociado a un token.</span><span class="sxs-lookup"><span data-stu-id="4fd31-106">When you want to override the default authentication mechanism associated with a token.</span></span>

- <span data-ttu-id="4fd31-107">Cuando está creando un token personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-107">When you are building a custom token.</span></span>

 <span data-ttu-id="4fd31-108">En este ejemplo se muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4fd31-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="4fd31-109">Cómo un cliente puede autenticar utilizando un par de nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="4fd31-109">How a client can authenticate using a username/password pair.</span></span>

- <span data-ttu-id="4fd31-110">Cómo el servidor puede validar las credenciales del cliente mediante un autenticador de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-110">How the server can validate the client credentials using a custom token authenticator.</span></span>

- <span data-ttu-id="4fd31-111">Cómo se vincula el código de servicio WCF con el autenticador de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-111">How the WCF service code ties in with the custom token authenticator.</span></span>

- <span data-ttu-id="4fd31-112">Cómo el servidor se puede autenticar utilizando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-112">How the server can be authenticated using the server's X.509 certificate.</span></span>

 <span data-ttu-id="4fd31-113">En este ejemplo también se muestra cómo se puede tener acceso a la identidad del llamador desde WCF después del proceso de autenticación de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-113">This sample also shows how the caller's identity is accessible from WCF after the custom token authentication process.</span></span>

 <span data-ttu-id="4fd31-114">El servicio expone un extremo único para comunicarse con el servicio, definido mediante el archivo de configuración App.config.</span><span class="sxs-lookup"><span data-stu-id="4fd31-114">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="4fd31-115">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="4fd31-115">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="4fd31-116">El enlace se configura con un `wsHttpBinding`estándar, con el conjunto de modo de seguridad en mensaje - el modo predeterminado de `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-116">The binding is configured with a standard `wsHttpBinding`, with the security mode set to message - the default mode of the `wsHttpBinding`.</span></span> <span data-ttu-id="4fd31-117">Este ejemplo establece el `wsHttpBinding` estándar para utilizar la autenticación mediante el nombre de usuario del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-117">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="4fd31-118">El servicio también configura el certificado del servicio utilizando comportamiento`serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-118">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="4fd31-119">El comportamiento `securityCredentials` le permite especificar un certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-119">The `securityCredentials` behavior allows you to specify a service certificate.</span></span> <span data-ttu-id="4fd31-120">Un cliente utiliza un certificado de servicio para autenticar el servicio y proporcionar protección al mensaje.</span><span class="sxs-lookup"><span data-stu-id="4fd31-120">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="4fd31-121">La configuración siguiente hace referencia al certificado del host local instalado durante la configuración del ejemplo tal y como se describe en las siguientes instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="4fd31-121">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>

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

 <span data-ttu-id="4fd31-122">La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="4fd31-122">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="4fd31-123">El enlace del cliente se configura con el `Mode` adecuado y `clientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-123">The client binding is configured with the appropriate `Mode` and `clientCredentialType`.</span></span>

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

 <span data-ttu-id="4fd31-124">La implementación del cliente establece el nombre de usuario y la contraseña que utilizar.</span><span class="sxs-lookup"><span data-stu-id="4fd31-124">The client implementation sets the user name and password to use.</span></span>

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a><span data-ttu-id="4fd31-125">autenticador de tokens personalizado</span><span class="sxs-lookup"><span data-stu-id="4fd31-125">Custom Token Authenticator</span></span>
 <span data-ttu-id="4fd31-126">Siga los siguientes pasos para crear un autenticador de tokens personalizado:</span><span class="sxs-lookup"><span data-stu-id="4fd31-126">Use the following steps to create a custom token authenticator:</span></span>

1. <span data-ttu-id="4fd31-127">Escriba un autenticador de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-127">Write a custom token authenticator.</span></span>

     <span data-ttu-id="4fd31-128">El ejemplo implementa un autenticador de tokens personalizado que valida que el nombre de usuario tiene un formato de correo electrónico válido.</span><span class="sxs-lookup"><span data-stu-id="4fd31-128">The sample implements a custom token authenticator that validates that the username has a valid email format.</span></span> <span data-ttu-id="4fd31-129">Deriva <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="4fd31-129">It derives the <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>.</span></span> <span data-ttu-id="4fd31-130">El método más importante en esta clase es <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="4fd31-130">The most important method in this class is <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>.</span></span> <span data-ttu-id="4fd31-131">En este método, el autenticador valida el formato del nombre de usuario y también que el nombre de host no es de un dominio no autorizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-131">In this method, the authenticator validates the format of the username and also that the host name is not from a rogue domain.</span></span> <span data-ttu-id="4fd31-132">Si se cumplen ambas condiciones, a continuación, devuelve una colección de solo lectura de instancias <xref:System.IdentityModel.Policy.IAuthorizationPolicy> que se utiliza a continuación para proporcionar indicaciones que representan la información almacenada dentro del token del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="4fd31-132">If both conditions are met, then it returns a read-only collection of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> instances that is then used to provide claims that represent the information stored inside the username token.</span></span>

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

2. <span data-ttu-id="4fd31-133">Proporcione una directiva de autorización que es devuelta por un autenticador de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-133">Provide an authorization policy that is returned by custom token authenticator.</span></span>

     <span data-ttu-id="4fd31-134">Este ejemplo proporciona su propia implementación de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> llamada `UnconditionalPolicy` que devuelve un conjunto de indicaciones e identidades que se pasaron a él en su constructor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-134">This sample provides its own implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> called `UnconditionalPolicy` that returns set of claims and identities that were passed to it in its constructor.</span></span>

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

3. <span data-ttu-id="4fd31-135">Escribir un administrador de tokens de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-135">Write a custom security token manager.</span></span>

     <span data-ttu-id="4fd31-136"><xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> para objetos <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concretos que se pasan en el método `CreateSecurityTokenAuthenticator`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-136">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> objects that are passed to it in the `CreateSecurityTokenAuthenticator` method.</span></span> <span data-ttu-id="4fd31-137">El administrador de tokens de seguridad también se utiliza para crear proveedores de tokens y serializadores de tokens, aunque en este ejemplo no se explica.</span><span class="sxs-lookup"><span data-stu-id="4fd31-137">The security token manager is also used to create token providers and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="4fd31-138">En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenAuthenticator` para devolver el autenticador de tokens de nombre de usuario personalizado cuando los requisitos de token pasados indican que se solicita el autenticador de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="4fd31-138">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenAuthenticator` method to return custom username token authenticator when the passed token requirements indicate that username authenticator is requested.</span></span>

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

4. <span data-ttu-id="4fd31-139">Escribir una credencial de servicio personalizada.</span><span class="sxs-lookup"><span data-stu-id="4fd31-139">Write a custom service credential.</span></span>

     <span data-ttu-id="4fd31-140">Se usa una clase de credenciales de servicio para representar las credenciales que se configuran para el servicio y crear el administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y serializadores de tokens.</span><span class="sxs-lookup"><span data-stu-id="4fd31-140">The service credentials class is used to represent the credentials that are configured for the service and creates a security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>

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

5. <span data-ttu-id="4fd31-141">Configurar el servicio para utilizar la credencial de servicio personalizada.</span><span class="sxs-lookup"><span data-stu-id="4fd31-141">Configure the service to use the custom service credential.</span></span>

     <span data-ttu-id="4fd31-142">Para que el servicio utilice la credencial de servicio personalizada, eliminamos la clase de credencial de servicio predeterminada después de capturar el certificado del servicio que ya está preconfigurado en la credencial del servicio predeterminada y configuramos la nueva instancia de credencial de servicio para utilizar los certificados del servicio preconfigurados y agregar esta nueva instancia de credencial de servicio a los comportamientos del servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-142">In order for the service to use the custom service credential, we delete the default service credential class after capturing the service certificate that is already preconfigured in the default service credential, and configure the new service credential instance to use the preconfigured service certificates and add this new service credential instance to service behaviors.</span></span>

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 <span data-ttu-id="4fd31-143">Para mostrar la información del autor de la llamada, puede usar <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-143">To display the caller's information, you can use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code.</span></span> <span data-ttu-id="4fd31-144"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene información de las notificaciones sobre el llamador actual.</span><span class="sxs-lookup"><span data-stu-id="4fd31-144">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 <span data-ttu-id="4fd31-145">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-145">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4fd31-146">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-146">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="4fd31-147">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="4fd31-147">Setup Batch File</span></span>
 <span data-ttu-id="4fd31-148">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-148">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate based security.</span></span> <span data-ttu-id="4fd31-149">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="4fd31-149">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="4fd31-150">A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="4fd31-150">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration.</span></span>

- <span data-ttu-id="4fd31-151">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-151">Creating the server certificate.</span></span>

     <span data-ttu-id="4fd31-152">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4fd31-152">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="4fd31-153">La variable `%SERVER_NAME%`especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-153">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="4fd31-154">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-154">Change this variable to specify your own server name.</span></span> <span data-ttu-id="4fd31-155">El valor predeterminado en este archivo por lotes es el host local.</span><span class="sxs-lookup"><span data-stu-id="4fd31-155">The default in this batch file is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="4fd31-156">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-156">Installing the server certificate into client's trusted certificate store.</span></span>

     <span data-ttu-id="4fd31-157">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-157">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="4fd31-158">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="4fd31-158">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="4fd31-159">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-159">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="4fd31-160">El archivo por lotes de instalación está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="4fd31-160">The setup batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="4fd31-161">Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="4fd31-161">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="4fd31-162">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="4fd31-162">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="4fd31-163">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fd31-163">To set up and build the sample</span></span>

1. <span data-ttu-id="4fd31-164">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4fd31-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="4fd31-165">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4fd31-165">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="4fd31-166">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="4fd31-166">To run the sample on the same computer</span></span>

1. <span data-ttu-id="4fd31-167">Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="4fd31-167">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="4fd31-168">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4fd31-168">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fd31-169">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="4fd31-169">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="4fd31-170">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="4fd31-170">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="4fd31-171">Inicie service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="4fd31-171">Launch service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="4fd31-172">Inicie client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="4fd31-172">Launch client.exe from \client\bin.</span></span> <span data-ttu-id="4fd31-173">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-173">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="4fd31-174">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="4fd31-174">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="4fd31-175">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="4fd31-175">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="4fd31-176">Cree un directorio en el equipo del servicio para los binarios del servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-176">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="4fd31-177">Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-177">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="4fd31-178">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-178">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="4fd31-179">Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="4fd31-179">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="4fd31-180">El archivo App.config del servicio debe actualizarse para reflejar este nuevo nombre de certificado.</span><span class="sxs-lookup"><span data-stu-id="4fd31-180">The service App.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="4fd31-181">Puede crear uno utilizando el archivo Setup.bat si establece la variable `%SERVER_NAME%` en el nombre de host completo del equipo en el que se ejecutará el servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-181">You can create one by using the Setup.bat if you set the `%SERVER_NAME%` variable to fully-qualified host name of the computer on which the service will run.</span></span> <span data-ttu-id="4fd31-182">Tenga en cuenta que el archivo de setup.bat se debe ejecutar desde un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="4fd31-182">Note that the setup.bat file must be run from a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>  
  
4. <span data-ttu-id="4fd31-183">Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-183">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="4fd31-184">No necesita hacerlo excepto cuando un emisor de confianza del cliente emite el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="4fd31-184">You do not need to do this except when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="4fd31-185">En el archivo App.config situado en el equipo del servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="4fd31-185">In the App.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="4fd31-186">En el equipo del servicio, ejecute service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4fd31-186">On the service computer, run service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="4fd31-187">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="4fd31-187">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="4fd31-188">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd31-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="4fd31-189">En el equipo cliente, inicie Client.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="4fd31-189">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
10. <span data-ttu-id="4fd31-190">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="4fd31-190">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="4fd31-191">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fd31-191">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="4fd31-192">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4fd31-192">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>
