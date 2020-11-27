---
title: Tokens auxiliares
ms.date: 03/30/2017
ms.assetid: 65a8905d-92cc-4ab0-b6ed-1f710e40784e
ms.openlocfilehash: d7e2a824060f4be05e0b0e9d1765fcf271eacbd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293668"
---
# <a name="supporting-tokens"></a><span data-ttu-id="ac317-102">Tokens auxiliares</span><span class="sxs-lookup"><span data-stu-id="ac317-102">Supporting Tokens</span></span>

<span data-ttu-id="ac317-103">El ejemplo de los tokens auxiliares muestra cómo agregar tokens adicionales a un mensaje que utiliza WS-Security.</span><span class="sxs-lookup"><span data-stu-id="ac317-103">The Supporting Tokens sample demonstrates how to add additional tokens to a message that uses WS-Security.</span></span> <span data-ttu-id="ac317-104">El ejemplo agrega un token de seguridad binario de X.509 además de un token de seguridad del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="ac317-104">The example adds an X.509 binary security token in addition to a username security token.</span></span> <span data-ttu-id="ac317-105">El token se pasa en un encabezado de mensaje de WS-Security desde el cliente al servicio y parte del mensaje se firma con una clave privada asociada con el token de seguridad de X.509 para demostrar la posesión del certificado X.509 al receptor.</span><span class="sxs-lookup"><span data-stu-id="ac317-105">The token is passed in a WS-Security message header from the client to the service and part of the message is signed with the private key associated with the X.509 security token to prove the possession of the X.509 certificate to the receiver.</span></span> <span data-ttu-id="ac317-106">Esto es útil cuando es un requisito tener varias solicitudes asociadas con un mensaje para autenticar o autorizar el remitente.</span><span class="sxs-lookup"><span data-stu-id="ac317-106">This is useful in the case when there is a requirement to have multiple claims associated with a message to authenticate or authorize the sender.</span></span> <span data-ttu-id="ac317-107">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="ac317-107">The service implements a contract that defines a request-reply communication pattern.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="ac317-108">Muestra</span><span class="sxs-lookup"><span data-stu-id="ac317-108">Demonstrates</span></span>

 <span data-ttu-id="ac317-109">El ejemplo explica:</span><span class="sxs-lookup"><span data-stu-id="ac317-109">The sample demonstrates:</span></span>

- <span data-ttu-id="ac317-110">Cómo un cliente puede pasar los tokens de seguridad adicionales a un servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-110">How a client can pass additional security tokens to a service.</span></span>

- <span data-ttu-id="ac317-111">Cómo el servidor puede tener acceso a las notificaciones asociadas a tokens de seguridad adicionales.</span><span class="sxs-lookup"><span data-stu-id="ac317-111">How the server can access claims associated with additional security tokens.</span></span>

- <span data-ttu-id="ac317-112">Cómo el certificado X.509 del servidor se utiliza para proteger la clave simétrica utilizada para el cifrado y firma de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ac317-112">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

> [!NOTE]
> <span data-ttu-id="ac317-113">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ac317-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

## <a name="client-authenticates-with-username-token-and-supporting-x509-security-token"></a><span data-ttu-id="ac317-114">El cliente se autentica con el token del nombre de usuario y el token de seguridad X.509 compatible</span><span class="sxs-lookup"><span data-stu-id="ac317-114">Client Authenticates with Username Token and Supporting X.509 Security Token</span></span>

 <span data-ttu-id="ac317-115">El servicio expone un punto de conexión único para comunicarse que se crea mediante programación usando las clases `BindingHelper` y `EchoServiceHost`.</span><span class="sxs-lookup"><span data-stu-id="ac317-115">The service exposes a single endpoint for communicating that is programmatically created using the `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="ac317-116">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="ac317-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="ac317-117">El enlace se configura con un enlace personalizado utilizando `SymmetricSecurityBindingElement` y `HttpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="ac317-117">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="ac317-118">Este ejemplo establece `SymmetricSecurityBindingElement` para utilizar un certificado X.509 de servicio para proteger la clave simétrica durante la transmisión y pasar `UserNameToken` junto con el `X509SecurityToken` compatible en un encabezado de mensaje de WS-Security.</span><span class="sxs-lookup"><span data-stu-id="ac317-118">This sample sets the `SymmetricSecurityBindingElement` to use a service X.509 certificate to protect the symmetric key during transmission and to pass a `UserNameToken` along with the supporting `X509SecurityToken` in a WS-Security message header.</span></span> <span data-ttu-id="ac317-119">La clave simétrica se utiliza para cifrar el cuerpo del mensaje y el token de seguridad del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="ac317-119">The symmetric key is used to encrypt the message body and the username security token.</span></span> <span data-ttu-id="ac317-120">El token auxiliar se pasa como un token de seguridad binario adicional en el encabezado de mensaje de WS-Security.</span><span class="sxs-lookup"><span data-stu-id="ac317-120">The supporting token is passed as an additional binary security token in the WS-Security message header.</span></span> <span data-ttu-id="ac317-121">La autenticidad del token auxiliar se demuestra firmando parte del mensaje con la clave privada asociada con el token de seguridad X.509 compatible.</span><span class="sxs-lookup"><span data-stu-id="ac317-121">The authenticity of the supporting token is proved by signing part of the message with the private key associated with the supporting X.509 security token.</span></span>

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

 <span data-ttu-id="ac317-122">El comportamiento especifica las credenciales del servicio que se van a utilizar para la autenticación del cliente además de la información sobre el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-122">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span> <span data-ttu-id="ac317-123">El ejemplo utiliza `CN=localhost` como un nombre de asunto en el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-123">The sample uses `CN=localhost` as a subject name in the service X.509 certificate.</span></span>

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

 <span data-ttu-id="ac317-124">Código del servicio:</span><span class="sxs-lookup"><span data-stu-id="ac317-124">Service code:</span></span>

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

 <span data-ttu-id="ac317-125">El extremo del cliente se configura de una manera similar al extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-125">The client endpoint is configured in a similar way to the service endpoint.</span></span> <span data-ttu-id="ac317-126">El cliente utiliza la misma clase `BindingHelper` para crear un enlace.</span><span class="sxs-lookup"><span data-stu-id="ac317-126">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="ac317-127">El resto de la instalación se encuentra en la clase `Client`.</span><span class="sxs-lookup"><span data-stu-id="ac317-127">The rest of the setup is located in `Client` class.</span></span> <span data-ttu-id="ac317-128">El cliente establece información sobre el token de seguridad del nombre de usuario, el token de seguridad X.509 compatible y la información sobre el certificado X.509 de servicio en el código de configuración en la colección de comportamientos del extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-128">The client sets information about the user name security token, the supporting X.509 security token and information about the service X.509 certificate in the setup code to the client endpoint behaviors collection.</span></span>

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

## <a name="displaying-callers-information"></a><span data-ttu-id="ac317-129">Visualización de la información de los autores de la llamada</span><span class="sxs-lookup"><span data-stu-id="ac317-129">Displaying Callers' Information</span></span>

 <span data-ttu-id="ac317-130">Para mostrar la información del autor de la llamada, puede usar `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ac317-130">To display the caller's information, you can use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following code.</span></span> <span data-ttu-id="ac317-131">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contiene notificaciones de autorización asociadas con el autor de la llamada actual.</span><span class="sxs-lookup"><span data-stu-id="ac317-131">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="ac317-132">Windows Communication Foundation (WCF) suministra automáticamente esas notificaciones para cada token recibido en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ac317-132">Those claims are supplied automatically by Windows Communication Foundation (WCF) for every token received in the message.</span></span>

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

## <a name="running-the-sample"></a><span data-ttu-id="ac317-133">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac317-133">Running the Sample</span></span>

 <span data-ttu-id="ac317-134">Al ejecutar el ejemplo, el cliente le pide primero que proporcione el nombre de usuario y la contraseña para el token del nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="ac317-134">When you run the sample, the client first prompts you to provide user name and password for the user name token.</span></span> <span data-ttu-id="ac317-135">Asegúrese de proporcionar los valores correctos para la cuenta del sistema, porque WCF en el servicio asigna los valores proporcionados en el token de nombre de usuario a la identidad proporcionada por el sistema.</span><span class="sxs-lookup"><span data-stu-id="ac317-135">Be sure to provide correct values for your system account, because WCF on the service maps the values supplied in the user name token into the identity provided by the system.</span></span> <span data-ttu-id="ac317-136">Después de esto, el cliente muestra la respuesta del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-136">After that, the client displays the response from the service.</span></span> <span data-ttu-id="ac317-137">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-137">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="ac317-138">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="ac317-138">Setup Batch File</span></span>

 <span data-ttu-id="ac317-139">El archivo por lotes Setup.bat incluido con este ejemplo le permite configurar el servidor con certificados pertinentes para ejecutar la aplicación hospedada por Internet Information Services (IIS) que necesita la seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-139">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run Internet Information Services (IIS) hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="ac317-140">Este archivo por lotes debe modificarse para que funcione a través de los equipos o en un caso no hospedado.</span><span class="sxs-lookup"><span data-stu-id="ac317-140">This batch file must be modified to work across machines or to work in a non-hosted case.</span></span>

 <span data-ttu-id="ac317-141">A continuación se proporciona una descripción breve de las diferentes secciones de los archivos por lotes con objeto de que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="ac317-141">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration.</span></span>

### <a name="creating-the-client-certificate"></a><span data-ttu-id="ac317-142">Crear el certificado del cliente</span><span class="sxs-lookup"><span data-stu-id="ac317-142">Creating the Client Certificate</span></span>

 <span data-ttu-id="ac317-143">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de cliente que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ac317-143">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="ac317-144">La variable `%CLIENT_NAME%` especifica el asunto del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-144">The `%CLIENT_NAME%` variable specifies the subject of the client certificate.</span></span> <span data-ttu-id="ac317-145">Este ejemplo utiliza "client.com" como el nombre del asunto.</span><span class="sxs-lookup"><span data-stu-id="ac317-145">This sample uses "client.com" as the subject name.</span></span>

 <span data-ttu-id="ac317-146">El certificado está almacenado en Mi almacén (Personal) en la ubicación de almacén `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="ac317-146">The certificate is stored in My (Personal) store under the `CurrentUser` store location.</span></span>

```console
echo ************
echo making client cert
echo ************
makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
```

### <a name="installing-the-client-certificate-into-the-servers-trusted-store"></a><span data-ttu-id="ac317-147">Instalar el certificado del cliente en el almacén de confianza del servidor</span><span class="sxs-lookup"><span data-stu-id="ac317-147">Installing the Client Certificate into the Server's Trusted Store</span></span>

 <span data-ttu-id="ac317-148">La línea siguiente del archivo por lotes Setup.bat copia el certificado de cliente en el almacén de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-148">The following line in the Setup.bat batch file copies the client certificate into the server’s trusted people store.</span></span> <span data-ttu-id="ac317-149">Este paso es necesario porque el sistema del servidor no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="ac317-149">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the server’s system.</span></span> <span data-ttu-id="ac317-150">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-150">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

```console
echo ************
echo copying client cert to server's CurrentUserstore
echo ************
certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
```

### <a name="creating-the-server-certificate"></a><span data-ttu-id="ac317-151">Crear el certificado de servidor</span><span class="sxs-lookup"><span data-stu-id="ac317-151">Creating the Server Certificate</span></span>

 <span data-ttu-id="ac317-152">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ac317-152">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="ac317-153">La variable `%SERVER_NAME%`especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-153">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="ac317-154">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-154">Change this variable to specify your own server name.</span></span> <span data-ttu-id="ac317-155">El valor predeterminado en este archivo por lotes es el host local.</span><span class="sxs-lookup"><span data-stu-id="ac317-155">The default in this batch file is localhost.</span></span>

 <span data-ttu-id="ac317-156">El certificado se almacena en el almacén My (Personal), en la ubicación de almacenamiento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ac317-156">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span> <span data-ttu-id="ac317-157">El certificado está almacenado en el almacén LocalMachine para los servicios hospedados por IIS.</span><span class="sxs-lookup"><span data-stu-id="ac317-157">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="ac317-158">En el caso de servicios autohospedados, debería modificar el archivo por lotes para almacenar el certificado de servidor en la ubicación de almacén CurrentUser reemplazando la cadena LocalMachine con CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="ac317-158">For self-hosted services, you should modify the batch file to store the server certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

```console
echo ************
echo Server cert setup starting
echo %SERVER_NAME%
echo ************
echo making server cert
echo ************
makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
```

### <a name="installing-server-certificate-into-clients-trusted-certificate-store"></a><span data-ttu-id="ac317-159">Instalar el certificado del servidor en un almacén de certificados de confianza del cliente</span><span class="sxs-lookup"><span data-stu-id="ac317-159">Installing Server Certificate into Client's Trusted Certificate Store</span></span>

 <span data-ttu-id="ac317-160">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-160">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="ac317-161">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="ac317-161">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="ac317-162">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-162">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

```console
echo ************
echo copying server cert to client's TrustedPeople store
echo ************certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
```

### <a name="enabling-access-to-the-certificates-private-key"></a><span data-ttu-id="ac317-163">Cómo permitir el acceso a la clave privada del certificado</span><span class="sxs-lookup"><span data-stu-id="ac317-163">Enabling Access to the Certificate's Private Key</span></span>

 <span data-ttu-id="ac317-164">Para permitir el acceso a la clave privada del certificado del servicio hospedado por IIS, la cuenta de usuario bajo la que se ejecuta el proceso hospedado por IIS debe tener los permisos adecuados para la clave privada.</span><span class="sxs-lookup"><span data-stu-id="ac317-164">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="ac317-165">Esto se logra con los últimos pasos del script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="ac317-165">This is accomplished by last steps in the Setup.bat script.</span></span>

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

##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac317-166">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac317-166">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="ac317-167">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac317-167">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="ac317-168">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ac317-168">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="ac317-169">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ac317-169">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>

##### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="ac317-170">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="ac317-170">To run the sample on the same machine</span></span>

1. <span data-ttu-id="ac317-171">Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 y ejecute con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="ac317-171">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="ac317-172">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ac317-172">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac317-173">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="ac317-173">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="ac317-174">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="ac317-174">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="ac317-175">Asegúrese de quitar los certificados ejecutando Cleanup.bat cuando termine con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ac317-175">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="ac317-176">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="ac317-176">Other security samples use the same certificates.</span></span>  
  
2. <span data-ttu-id="ac317-177">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="ac317-177">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="ac317-178">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-178">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="ac317-179">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="ac317-179">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
##### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="ac317-180">Para ejecutar el ejemplo en los equipos</span><span class="sxs-lookup"><span data-stu-id="ac317-180">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="ac317-181">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-181">Create a directory on the service machine.</span></span> <span data-ttu-id="ac317-182">Cree una aplicación virtual denominada "servicemodelsamples" para este directorio utilizando la herramienta de administración de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="ac317-182">Create a virtual application named servicemodelsamples for this directory using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="ac317-183">Copie los archivos de programa de servicio del directorio \inetpub\wwwroot\servicemodelsamples al directorio virtual del equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-183">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service machine.</span></span> <span data-ttu-id="ac317-184">Asegúrese de que copia los archivos en el subdirectorio \bin.</span><span class="sxs-lookup"><span data-stu-id="ac317-184">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="ac317-185">Copie también los archivos Setup.bat, Cleanup.bat e ImportClientCert.bat en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-185">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service machine.</span></span>  
  
3. <span data-ttu-id="ac317-186">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-186">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="ac317-187">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-187">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="ac317-188">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-188">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="ac317-189">En el servidor, ejecute `setup.bat service` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="ac317-189">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="ac317-190">Al ejecutar `setup.bat` con el `service` argumento se crea un certificado de servicio con el nombre de dominio completo del equipo y se exporta el certificado del servicio a un archivo denominado Service. cer.</span><span class="sxs-lookup"><span data-stu-id="ac317-190">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="ac317-191">Edite Web.config para reflejar el nuevo nombre del certificado (en el `findValue` atributo en [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="ac317-191">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the machine.</span></span>  
  
7. <span data-ttu-id="ac317-192">Copie el archivo Service.cer del directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="ac317-192">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="ac317-193">En el cliente, ejecute `setup.bat client` en un símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="ac317-193">On the client, run `setup.bat client` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="ac317-194">Al ejecutar `setup.bat`con el argumento `client`, se crea un certificado de cliente denominado client.com y se exporta el certificado de cliente a un archivo denominado Client.cer.</span><span class="sxs-lookup"><span data-stu-id="ac317-194">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="ac317-195">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="ac317-195">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="ac317-196">Para hacerlo, reemplace el host local con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-196">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="ac317-197">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ac317-197">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="ac317-198">En el cliente, ejecute ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="ac317-198">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="ac317-199">Así se importa el certificado del servicio del archivo Service.cer en el almacén CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="ac317-199">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="ac317-200">En el servidor, ejecute ImportClientCert.bat. Esto importa el certificado de cliente del archivo Client.cer en el almacén LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="ac317-200">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="ac317-201">En el equipo cliente, inicie Client.exe desde la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ac317-201">On the client machine, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="ac317-202">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="ac317-202">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
##### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="ac317-203">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac317-203">To clean up after the sample</span></span>  
  
- <span data-ttu-id="ac317-204">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ac317-204">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac317-205">Este script no quita los certificados del servicio en un cliente cuando se ejecuta este ejemplo en los equipos.</span><span class="sxs-lookup"><span data-stu-id="ac317-205">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="ac317-206">Si ha ejecutado ejemplos de WCF que usan certificados entre equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="ac317-206">If you have run WCF samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="ac317-207">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="ac317-207">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
