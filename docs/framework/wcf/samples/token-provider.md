---
description: 'Más información acerca de: proveedor de tokens'
title: Proveedor de tokens
ms.date: 03/30/2017
ms.assetid: 947986cf-9946-4987-84e5-a14678d96edb
ms.openlocfilehash: 145d85eb0e0d8622c7cfb90ef4a6e24ccb7b9226
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668570"
---
# <a name="token-provider"></a><span data-ttu-id="aca59-103">Proveedor de tokens</span><span class="sxs-lookup"><span data-stu-id="aca59-103">Token Provider</span></span>

<span data-ttu-id="aca59-104">Este ejemplo muestra cómo implementar un proveedor de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca59-104">This sample demonstrates how to implement a custom token provider.</span></span> <span data-ttu-id="aca59-105">Un proveedor de tokens en Windows Communication Foundation (WCF) se usa para proporcionar credenciales a la infraestructura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aca59-105">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="aca59-106">En general, el proveedor de tokens examina el destino y emite las credenciales adecuadas de manera que la infraestructura de seguridad pueda proteger el mensaje.</span><span class="sxs-lookup"><span data-stu-id="aca59-106">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="aca59-107">WCF se suministra con el proveedor de tokens del administrador de credenciales predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aca59-107">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="aca59-108">WCF también se suministra con un proveedor de tokens de CardSpace.</span><span class="sxs-lookup"><span data-stu-id="aca59-108">WCF also ships with a CardSpace token provider.</span></span> <span data-ttu-id="aca59-109">Los proveedores de tokens personalizados son útiles en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aca59-109">Custom token providers are useful in the following cases:</span></span>

- <span data-ttu-id="aca59-110">Si tiene un almacén de credenciales con el que estos proveedores de tokens no pueden funcionar.</span><span class="sxs-lookup"><span data-stu-id="aca59-110">If you have a credential store that these token providers cannot operate with.</span></span>

- <span data-ttu-id="aca59-111">Si desea proporcionar su propio mecanismo personalizado para transformar las credenciales desde el punto en el que el usuario proporciona detalles cuando el marco de trabajo de cliente de WCF usa las credenciales.</span><span class="sxs-lookup"><span data-stu-id="aca59-111">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>

- <span data-ttu-id="aca59-112">Si está creando un token personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca59-112">If you are building a custom token.</span></span>

 <span data-ttu-id="aca59-113">Este ejemplo muestra cómo crear un proveedor de tokens personalizado que transforma la entrada del usuario a un formato diferente.</span><span class="sxs-lookup"><span data-stu-id="aca59-113">This sample shows how to build a custom token provider that transforms the input from the user into a different format.</span></span>

 <span data-ttu-id="aca59-114">En resumen, este ejemplo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aca59-114">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="aca59-115">Cómo un cliente puede autenticar utilizando un par de nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="aca59-115">How a client can authenticate using a username/password pair.</span></span>

- <span data-ttu-id="aca59-116">Cómo se puede configurar un cliente con un proveedor de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca59-116">How a client can be configured with a custom token provider.</span></span>

- <span data-ttu-id="aca59-117">Cómo el servidor puede validar las credenciales del cliente utilizando una contraseña con un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizado que valida que el nombre de usuario y la contraseña coinciden.</span><span class="sxs-lookup"><span data-stu-id="aca59-117">How the server can validate the client credentials using a password with a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> that validates that the username and password match.</span></span>

- <span data-ttu-id="aca59-118">Cómo el cliente autentica el servidor usando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-118">How the server is authenticated by the client using the server's X.509 certificate.</span></span>

 <span data-ttu-id="aca59-119">Este ejemplo también muestra cómo la identidad del llamador es accesible después del proceso de autenticación del token personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca59-119">This sample also shows how the caller's identity is accessible after the custom token authentication process.</span></span>

 <span data-ttu-id="aca59-120">El servicio expone un extremo único para comunicarse con el servicio, definido mediante el archivo de configuración App.config.</span><span class="sxs-lookup"><span data-stu-id="aca59-120">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="aca59-121">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="aca59-121">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="aca59-122">El enlace se configura con un `wsHttpBinding` estándar, que usa la seguridad de mensaje de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aca59-122">The binding is configured with a standard `wsHttpBinding`, which uses message security by default.</span></span> <span data-ttu-id="aca59-123">Este ejemplo establece el `wsHttpBinding` estándar para utilizar la autenticación mediante el nombre de usuario del cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-123">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="aca59-124">El servicio también configura el certificado del servicio utilizando el comportamiento serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="aca59-124">The service also configures the service certificate using the serviceCredentials behavior.</span></span> <span data-ttu-id="aca59-125">El comportamiento serviceCredentials le permite configurar un certificado de servicio.</span><span class="sxs-lookup"><span data-stu-id="aca59-125">The serviceCredentials behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="aca59-126">Un cliente utiliza un certificado de servicio para autenticar el servicio y proporcionar protección al mensaje.</span><span class="sxs-lookup"><span data-stu-id="aca59-126">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="aca59-127">La configuración siguiente hace referencia al certificado del host local instalado durante la configuración del ejemplo tal y como se describe en las siguientes instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="aca59-127">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service"/>
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
        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
```

 <span data-ttu-id="aca59-128">La configuración de punto de conexión de cliente está compuesta por un nombre de configuración, una dirección absoluta para el punto de conexión de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="aca59-128">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="aca59-129">El enlace del cliente se configura con el adecuado `Mode` y `clientCredentialType`del mensaje.</span><span class="sxs-lookup"><span data-stu-id="aca59-129">The client binding is configured with the appropriate `Mode` and message `clientCredentialType`.</span></span>

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

 <span data-ttu-id="aca59-130">En los pasos siguientes se muestra cómo desarrollar un proveedor de tokens personalizado e integrarlo con el marco de seguridad de WCF:</span><span class="sxs-lookup"><span data-stu-id="aca59-130">The following steps show how to develop a custom token provider and integrate it with the WCF security framework:</span></span>

1. <span data-ttu-id="aca59-131">Escriba un proveedor de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca59-131">Write a custom token provider.</span></span>

     <span data-ttu-id="aca59-132">El ejemplo implementa un proveedor de tokens personalizado que obtiene el nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="aca59-132">The sample implements a custom token provider that obtains the username and password.</span></span> <span data-ttu-id="aca59-133">La contraseña debe coincidir con este nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="aca59-133">The password must match this username.</span></span> <span data-ttu-id="aca59-134">Este proveedor de tokens personalizado solo tiene propósitos de muestra y no se recomienda para una implementación real.</span><span class="sxs-lookup"><span data-stu-id="aca59-134">This custom token provider is for demonstration purposes only and is not recommended for real world deployment.</span></span>

     <span data-ttu-id="aca59-135">Para realizar esta tarea, el proveedor de tokens personalizado deriva la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>.</span><span class="sxs-lookup"><span data-stu-id="aca59-135">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="aca59-136">Este método crea y devuelve un nuevo `UserNameSecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="aca59-136">This method creates and returns a new `UserNameSecurityToken`.</span></span>

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
        // obtain username and password from the user using console window
        string username = GetUserName();
        string password = GetPassword();
        Console.WriteLine("username: {0}", username);

        // return new UserNameSecurityToken containing information obtained from user
        return new UserNameSecurityToken(username, password);
    }
    ```

2. <span data-ttu-id="aca59-137">Escribir el administrador de tokens de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="aca59-137">Write custom security token manager.</span></span>

     <span data-ttu-id="aca59-138"><xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear <xref:System.IdentityModel.Selectors.SecurityTokenProvider> para el <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concreto que se pasa en el método `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="aca59-138">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="aca59-139">El administrador de tokens de seguridad también se utiliza para crear autenticadores de tokens y serializadores de tokens, aunque en este ejemplo no se explica.</span><span class="sxs-lookup"><span data-stu-id="aca59-139">Security token manager is also used to create token authenticators and a token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="aca59-140">En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenProvider` para devolver el proveedor de tokens de nombre de usuario personalizado cuando los requisitos de tokens pasados indican que se solicita un proveedor de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="aca59-140">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return custom username token provider when the passed token requirements indicate that username provider is requested.</span></span>

    ```csharp
    public class MyUserNameSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        MyUserNameClientCredentials myUserNameClientCredentials;

        public MyUserNameSecurityTokenManager(MyUserNameClientCredentials myUserNameClientCredentials)
            : base(myUserNameClientCredentials)
        {
            this.myUserNameClientCredentials = myUserNameClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // if token requirement matches username token return custom username token provider
            // otherwise use base implementation
            if (tokenRequirement.TokenType == SecurityTokenTypes.UserName)
            {
                return new MyUserNameTokenProvider();
            }
            else
            {
                return base.CreateSecurityTokenProvider(tokenRequirement);
            }
        }
    }
    ```

3. <span data-ttu-id="aca59-141">Escribir una credencial de cliente personalizada.</span><span class="sxs-lookup"><span data-stu-id="aca59-141">Write a custom client credential.</span></span>

     <span data-ttu-id="aca59-142">Se usa una clase de credenciales de cliente para representar las credenciales que se configuran para el proxy de cliente y crear el administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y un serializador de tokens.</span><span class="sxs-lookup"><span data-stu-id="aca59-142">Client credentials class is used to represent the credentials that are configured for the client proxy and creates security token manager that is used to obtain token authenticators, token providers and a token serializer.</span></span>

    ```csharp
    public class MyUserNameClientCredentials : ClientCredentials
    {
        public MyUserNameClientCredentials()
            : base()
        {
        }

        protected override ClientCredentials CloneCore()
        {
            return new MyUserNameClientCredentials();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            // return custom security token manager
            return new MyUserNameSecurityTokenManager(this);
        }
    }
    ```

4. <span data-ttu-id="aca59-143">Configure el cliente para utilizar la credencial del cliente personalizada.</span><span class="sxs-lookup"><span data-stu-id="aca59-143">Configure the client to use the custom client credential.</span></span>

     <span data-ttu-id="aca59-144">Para que el cliente utilice la credencial de cliente personalizada, el ejemplo elimina la clase de credencial de cliente predeterminada y proporciona la nueva.</span><span class="sxs-lookup"><span data-stu-id="aca59-144">In order for the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>

    ```csharp
    static void Main()
    {
        // ...
           // Create a client with given client endpoint configuration
          CalculatorClient client = new CalculatorClient();

          // set new credentials
           client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
         client.ChannelFactory.Endpoint.Behaviors.Add(new MyUserNameClientCredentials());
       // ...
    }
    ```

 <span data-ttu-id="aca59-145">En el servicio, para mostrar la información del llamador, utilice como se muestra <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="aca59-145">On the service, to display the caller's information, use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code example.</span></span> <span data-ttu-id="aca59-146"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contiene información de las notificaciones sobre el llamador actual.</span><span class="sxs-lookup"><span data-stu-id="aca59-146">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
        ServiceSecurityContext.Current.PrimaryIdentity.Name);
}
```

 <span data-ttu-id="aca59-147">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="aca59-148">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-148">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="aca59-149">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="aca59-149">Setup Batch File</span></span>

 <span data-ttu-id="aca59-150">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con el certificado pertinente para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-150">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="aca59-151">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="aca59-151">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="aca59-152">A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar para su ejecución en la configuración adecuada:</span><span class="sxs-lookup"><span data-stu-id="aca59-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="aca59-153">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-153">Creating the server certificate.</span></span>

     <span data-ttu-id="aca59-154">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="aca59-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="aca59-155">La variable `%SERVER_NAME%`especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-155">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="aca59-156">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="aca59-157">El valor predeterminado en este archivo por lotes es el host local.</span><span class="sxs-lookup"><span data-stu-id="aca59-157">The default value in this batch file is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="aca59-158">Instalar el certificado del servidor en el almacén de certificados de confianza de cliente:</span><span class="sxs-lookup"><span data-stu-id="aca59-158">Installing the server certificate into the client's trusted certificate store:</span></span>

     <span data-ttu-id="aca59-159">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="aca59-160">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="aca59-160">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="aca59-161">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

> [!NOTE]
> <span data-ttu-id="aca59-162">El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="aca59-162">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="aca59-163">Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="aca59-163">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="aca59-164">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="aca59-164">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="aca59-165">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="aca59-165">To set up and build the sample</span></span>

1. <span data-ttu-id="aca59-166">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aca59-166">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="aca59-167">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aca59-167">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="aca59-168">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="aca59-168">To run the sample on the same computer</span></span>

1. <span data-ttu-id="aca59-169">Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="aca59-169">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="aca59-170">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aca59-170">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aca59-171">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="aca59-171">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="aca59-172">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="aca59-172">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="aca59-173">Inicie service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="aca59-173">Launch service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="aca59-174">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="aca59-174">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="aca59-175">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-175">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="aca59-176">Cuando se pida el nombre de usuario, escriba un nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="aca59-176">At the username prompt, type a user name.</span></span>  
  
5. <span data-ttu-id="aca59-177">Cuando se pida la contraseña, utilice la misma cadena que escribió cuando se solicitó el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="aca59-177">At the password prompt, use the same string that was typed for the username prompt.</span></span>  
  
6. <span data-ttu-id="aca59-178">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="aca59-178">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="aca59-179">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="aca59-179">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="aca59-180">Cree un directorio en el equipo del servicio para los binarios del servicio.</span><span class="sxs-lookup"><span data-stu-id="aca59-180">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="aca59-181">Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="aca59-181">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="aca59-182">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="aca59-182">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="aca59-183">Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="aca59-183">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="aca59-184">El archivo Service.exe.config debe actualizarse para reflejar este nuevo nombre de certificado.</span><span class="sxs-lookup"><span data-stu-id="aca59-184">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="aca59-185">Puede crear el certificado de servidor modificando el archivo por lotes Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="aca59-185">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="aca59-186">Tenga en cuenta que el archivo de setup.bat se debe ejecutar desde un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="aca59-186">Note that the setup.bat file must be run from a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="aca59-187">Debe establecer la variable `%SERVER_NAME%` en el nombre de host completo del equipo que se utiliza para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="aca59-187">You must set `%SERVER_NAME%` variable to fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4. <span data-ttu-id="aca59-188">Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-188">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="aca59-189">No es necesario cuando un emisor de confianza para el cliente ha emitido el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="aca59-189">You do not need to do this when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="aca59-190">En el archivo Service.exe.config situado en el equipo del servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="aca59-190">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="aca59-191">En el equipo del servicio, ejecute service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="aca59-191">On the service computer, run service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="aca59-192">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="aca59-192">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="aca59-193">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="aca59-193">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="aca59-194">En el equipo cliente, inicie `Client.exe` desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="aca59-194">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="aca59-195">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="aca59-195">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="aca59-196">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="aca59-196">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="aca59-197">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="aca59-197">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>
