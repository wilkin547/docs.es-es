---
title: Token personalizado
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: 1a8c312248b0c15bb2e366a3d9925014556b6dd8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553166"
---
# <a name="custom-token"></a><span data-ttu-id="fd999-102">Token personalizado</span><span class="sxs-lookup"><span data-stu-id="fd999-102">Custom Token</span></span>

<span data-ttu-id="fd999-103">Este ejemplo muestra cómo agregar una implementación de token personalizada en una aplicación Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="fd999-103">This sample demonstrates how to add a custom token implementation into a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="fd999-104">El ejemplo utiliza `CreditCardToken` para pasar de manera segura información sobre las tarjetas de crédito del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-104">The example uses a `CreditCardToken` to securely pass information about client credit cards to the service.</span></span> <span data-ttu-id="fd999-105">El token se pasa en el encabezado de mensaje WS-Security y se firma y cifra utilizando el elemento de enlace de seguridad simétrico junto con el cuerpo del mensaje y otros encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fd999-105">The token is passed in the WS-Security message header and is signed and encrypted using the symmetric security binding element along with message body and other message headers.</span></span> <span data-ttu-id="fd999-106">Esto es útil en casos donde los tokens integrados no son suficiente.</span><span class="sxs-lookup"><span data-stu-id="fd999-106">This is useful in cases where the built-in tokens are not sufficient.</span></span> <span data-ttu-id="fd999-107">Este ejemplo muestra cómo proporcionar un token de seguridad personalizado a un servicio en lugar de utilizar uno de los tokens integrados.</span><span class="sxs-lookup"><span data-stu-id="fd999-107">This sample demonstrates how to provide a custom security token to a service instead of using one of the built-in tokens.</span></span> <span data-ttu-id="fd999-108">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="fd999-108">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
> <span data-ttu-id="fd999-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="fd999-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="fd999-110">En resumen, este ejemplo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd999-110">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="fd999-111">Cómo un cliente puede pasar un token de seguridad personalizado a un servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-111">How a client can pass a custom security token to a service.</span></span>

- <span data-ttu-id="fd999-112">Cómo el servicio puede utilizar y validar un token de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="fd999-112">How the service can consume and validate a custom security token.</span></span>

- <span data-ttu-id="fd999-113">Cómo el código de servicio WCF puede obtener la información sobre los tokens de seguridad recibidos, incluido el token de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="fd999-113">How the WCF service code can obtain the information about received security tokens including the custom security token.</span></span>

- <span data-ttu-id="fd999-114">Cómo el certificado X.509 del servidor se utiliza para proteger la clave simétrica utilizada para el cifrado y firma de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fd999-114">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

## <a name="client-authentication-using-a-custom-security-token"></a><span data-ttu-id="fd999-115">Autenticación del Cliente utilizando un token de seguridad personalizado</span><span class="sxs-lookup"><span data-stu-id="fd999-115">Client Authentication Using a Custom Security Token</span></span>

 <span data-ttu-id="fd999-116">El servicio expone un punto de conexión único que se crea mediante programación usando las clases `BindingHelper` y `EchoServiceHost`.</span><span class="sxs-lookup"><span data-stu-id="fd999-116">The service exposes a single endpoint that is programmatically created using `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="fd999-117">El punto de conexión está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="fd999-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="fd999-118">El enlace se configura con un enlace personalizado utilizando `SymmetricSecurityBindingElement` y `HttpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="fd999-118">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="fd999-119">Este ejemplo establece `SymmetricSecurityBindingElement` para utilizar el certificado X.509 de un servicio para proteger la clave simétrica durante la transmisión y pasar un `CreditCardToken` personalizado en un encabezado de mensaje de WS-Security como un token de seguridad firmado y cifrado.</span><span class="sxs-lookup"><span data-stu-id="fd999-119">This sample sets the `SymmetricSecurityBindingElement` to use a service's X.509 certificate to protect the symmetric key during transmission and to pass a custom `CreditCardToken` in a WS-Security message header as a signed and encrypted security token.</span></span> <span data-ttu-id="fd999-120">El comportamiento especifica las credenciales del servicio que se van a utilizar para la autenticación del cliente además de la información sobre el certificado X.509 del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-120">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span>

```csharp
public static class BindingHelper
{
    public static Binding CreateCreditCardBinding()
    {
        var httpTransport = new HttpTransportBindingElement();

        // The message security binding element will be configured to require a credit card.
        // The token that is encrypted with the service's certificate.
        var messageSecurity = new SymmetricSecurityBindingElement();
        messageSecurity.EndpointSupportingTokenParameters.SignedEncrypted.Add(new CreditCardTokenParameters());
        X509SecurityTokenParameters x509ProtectionParameters = new X509SecurityTokenParameters();
        x509ProtectionParameters.InclusionMode = SecurityTokenInclusionMode.Never;
        messageSecurity.ProtectionTokenParameters = x509ProtectionParameters;
        return new CustomBinding(messageSecurity, httpTransport);
    }
}
```

 <span data-ttu-id="fd999-121">Para utilizar un token de tarjeta de crédito en el mensaje, el ejemplo utiliza las credenciales del servicio personalizadas para proporcionar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="fd999-121">To consume a credit card token in the message, the sample uses custom service credentials to provide this functionality.</span></span> <span data-ttu-id="fd999-122">La clase de credenciales de servicio se encuentra en la clase `CreditCardServiceCredentials` y se agrega a las colecciones de comportamientos del host de servicio en el método `EchoServiceHost.InitializeRuntime`.</span><span class="sxs-lookup"><span data-stu-id="fd999-122">The service credentials class is located in the `CreditCardServiceCredentials` class and is added to the behaviors collections of the service host in the `EchoServiceHost.InitializeRuntime` method.</span></span>

```csharp
class EchoServiceHost : ServiceHost
{
    string creditCardFile;

    public EchoServiceHost(parameters Uri[] addresses)
        : base(typeof(EchoService), addresses)
    {
        creditCardFile = ConfigurationManager.AppSettings["creditCardFile"];
        if (string.IsNullOrEmpty(creditCardFile))
        {
            throw new ConfigurationErrorsException("creditCardFile not specified in service config");
        }

        creditCardFile = String.Format("{0}\\{1}", System.Web.Hosting.HostingEnvironment.ApplicationPhysicalPath, creditCardFile);
    }

    override protected void InitializeRuntime()
    {
        // Create a credit card service credentials and add it to the behaviors.
        CreditCardServiceCredentials serviceCredentials = new CreditCardServiceCredentials(this.creditCardFile);
        serviceCredentials.ServiceCertificate.SetCertificate("CN=localhost", StoreLocation.LocalMachine, StoreName.My);
        this.Description.Behaviors.Remove((typeof(ServiceCredentials)));
        this.Description.Behaviors.Add(serviceCredentials);

        // Register a credit card binding for the endpoint.
        Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
        this.AddServiceEndpoint(typeof(IEchoService), creditCardBinding, string.Empty);

        base.InitializeRuntime();
    }
}
```

 <span data-ttu-id="fd999-123">El extremo del cliente se configura de una manera similar al extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-123">The client endpoint is configured in a similar manner as the service endpoint.</span></span> <span data-ttu-id="fd999-124">El cliente utiliza la misma clase `BindingHelper` para crear un enlace.</span><span class="sxs-lookup"><span data-stu-id="fd999-124">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="fd999-125">El resto de la instalación se encuentra en la clase `Client`.</span><span class="sxs-lookup"><span data-stu-id="fd999-125">The rest of the setup is located in the `Client` class.</span></span> <span data-ttu-id="fd999-126">El cliente también establece información que se va a contener en `CreditCardToken` e información sobre el certificado X.509 del servicio en el código de instalación agregando una instancia `CreditCardClientCredentials` con los datos apropiados a la colección de comportamientos de punto de conexión del cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-126">The client also sets information to be contained in the `CreditCardToken` and information about the service X.509 certificate in the setup code by adding a `CreditCardClientCredentials` instance with the proper data to the client endpoint behaviors collection.</span></span> <span data-ttu-id="fd999-127">El ejemplo utiliza el certificado X.509 con nombre sujeto establecido en `CN=localhost` como el certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-127">The sample uses X.509 certificate with subject name set to `CN=localhost` as the service certificate.</span></span>

```csharp
Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
var serviceAddress = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");

// Create a client with given client endpoint configuration.
channelFactory = new ChannelFactory<IEchoService>(creditCardBinding, serviceAddress);

// Configure the credit card credentials on the channel factory.
var credentials =
      new CreditCardClientCredentials(
      new CreditCardInfo(creditCardNumber, issuer, expirationTime));
// Configure the service certificate on the credentials.
credentials.ServiceCertificate.SetDefaultCertificate(
      "CN=localhost", StoreLocation.LocalMachine, StoreName.My);

// Replace ClientCredentials with CreditCardClientCredentials.
channelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
channelFactory.Endpoint.Behaviors.Add(credentials);

client = channelFactory.CreateChannel();

Console.WriteLine($"Echo service returned: {client.Echo()}");

((IChannel)client).Close();
channelFactory.Close();
```

## <a name="custom-security-token-implementation"></a><span data-ttu-id="fd999-128">Implementación de token de seguridad personalizada</span><span class="sxs-lookup"><span data-stu-id="fd999-128">Custom Security Token Implementation</span></span>

 <span data-ttu-id="fd999-129">Para habilitar un token de seguridad personalizado en WCF, cree una representación de objeto del token de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="fd999-129">To enable a custom security token in WCF, create an object representation of the custom security token.</span></span> <span data-ttu-id="fd999-130">El ejemplo tiene esta representación en la clase `CreditCardToken`.</span><span class="sxs-lookup"><span data-stu-id="fd999-130">The sample has this representation in the `CreditCardToken` class.</span></span> <span data-ttu-id="fd999-131">La representación de objeto es responsable de contener toda la información pertinente del token de seguridad y de proporcionar una lista de claves de seguridad contenida en el token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd999-131">The object representation is responsible for holding all relevant security token information and to provide a list of security keys contained in the security token.</span></span> <span data-ttu-id="fd999-132">En este caso, el token de seguridad de la tarjeta de crédito no contiene ninguna clave de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd999-132">In this case, the credit card security token does not contain any security key.</span></span>

 <span data-ttu-id="fd999-133">En la sección siguiente se describe lo que se debe hacer para permitir que un token personalizado se transmita a través de la conexión y lo consuma un punto de conexión de WCF.</span><span class="sxs-lookup"><span data-stu-id="fd999-133">The next section describes what must be done to enable a custom token to be transmitted over the wire and consumed by a WCF endpoint.</span></span>

```csharp
class CreditCardToken : SecurityToken
{
    CreditCardInfo cardInfo;
    DateTime effectiveTime = DateTime.UtcNow;
    string id;
    ReadOnlyCollection<SecurityKey> securityKeys;

    public CreditCardToken(CreditCardInfo cardInfo) : this(cardInfo, Guid.NewGuid().ToString()) { }

    public CreditCardToken(CreditCardInfo cardInfo, string id)
    {
        if (cardInfo == null)
            throw new ArgumentNullException(nameof(cardInfo));

        if (id == null)
            throw new ArgumentNullException(nameof(id));

        this.cardInfo = cardInfo;
        this.id = id;

        // The credit card token is not capable of any cryptography.
        this.securityKeys = new ReadOnlyCollection<SecurityKey>(new List<SecurityKey>());
    }

    public CreditCardInfo CardInfo { get { return this.cardInfo; } }

    public override ReadOnlyCollection<SecurityKey> SecurityKeys { get { return this.securityKeys; } }

    public override DateTime ValidFrom { get { return this.effectiveTime; } }
    public override DateTime ValidTo { get { return this.cardInfo.ExpirationDate; } }
    public override string Id { get { return this.id; } }
}
```

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a><span data-ttu-id="fd999-134">Obtener el token de la tarjeta de crédito personalizado en y desde el mensaje</span><span class="sxs-lookup"><span data-stu-id="fd999-134">Getting the Custom Credit Card Token to and from the Message</span></span>

 <span data-ttu-id="fd999-135">Los serializadores de tokens de seguridad en WCF son responsables de crear una representación de objeto de tokens de seguridad a partir del XML en el mensaje y de crear un formulario XML de los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd999-135">Security token serializers in WCF are responsible for creating an object representation of security tokens from the XML in the message and creating a XML form of the security tokens.</span></span> <span data-ttu-id="fd999-136">También son responsables de otras funcionalidades, como leer y escribir identificadores de clave que señalan a token de seguridad, pero este ejemplo solo utiliza funcionalidad relacionada con token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd999-136">They are also responsible for other functionality such as reading and writing key identifiers pointing to security tokens, but this example uses only security token-related functionality.</span></span> <span data-ttu-id="fd999-137">Para habilitar un token personalizado, debe implementar su propio serializador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd999-137">To enable a custom token you must implement your own security token serializer.</span></span> <span data-ttu-id="fd999-138">Para ello, en este ejemplo se utiliza la clase `CreditCardSecurityTokenSerializer`.</span><span class="sxs-lookup"><span data-stu-id="fd999-138">This sample uses the `CreditCardSecurityTokenSerializer` class for this purpose.</span></span>

 <span data-ttu-id="fd999-139">En el servicio, el serializador personalizado lee la forma en XML del token personalizado y crea la representación de objeto del token personalizada a partir de ella.</span><span class="sxs-lookup"><span data-stu-id="fd999-139">On the service, the custom serializer reads the XML form of the custom token and creates the custom token object representation from it.</span></span>

 <span data-ttu-id="fd999-140">En el cliente, la clase `CreditCardSecurityTokenSerializer` escribe la información contenida en la representación de objeto del token de seguridad en el sistema de escritura de XML.</span><span class="sxs-lookup"><span data-stu-id="fd999-140">On the client, the `CreditCardSecurityTokenSerializer` class writes the information contained in the security token object representation into the XML writer.</span></span>

```csharp
public class CreditCardSecurityTokenSerializer : WSSecurityTokenSerializer
{
    public CreditCardSecurityTokenSerializer(SecurityTokenVersion version) : base() { }

    protected override bool CanReadTokenCore(XmlReader reader)
    {
        XmlDictionaryReader localReader = XmlDictionaryReader.CreateDictionaryReader(reader);

        if (reader == null)
            throw new ArgumentNullException(nameof(reader));

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
            return true;

        return base.CanReadTokenCore(reader);
    }

    protected override SecurityToken ReadTokenCore(XmlReader reader, SecurityTokenResolver tokenResolver)
    {
        if (reader == null)
            throw new ArgumentNullException(nameof(reader));

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
        {
            string id = reader.GetAttribute(Constants.Id, Constants.WsUtilityNamespace);

            reader.ReadStartElement();

            // Read the credit card number.
            string creditCardNumber = reader.ReadElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace);

            // Read the expiration date.
            string expirationTimeString = reader.ReadElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace);
            DateTime expirationTime = XmlConvert.ToDateTime(expirationTimeString, XmlDateTimeSerializationMode.Utc);

            // Read the issuer of the credit card.
            string creditCardIssuer = reader.ReadElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace);
            reader.ReadEndElement();

            var cardInfo = new CreditCardInfo(creditCardNumber, creditCardIssuer, expirationTime);

            return new CreditCardToken(cardInfo, id);
        }
        else
        {
            return WSSecurityTokenSerializer.DefaultInstance.ReadToken(reader, tokenResolver);
        }
    }

    protected override bool CanWriteTokenCore(SecurityToken token)
    {
        if (token is CreditCardToken)
            return true;
        return base.CanWriteTokenCore(token);
    }

    protected override void WriteTokenCore(XmlWriter writer, SecurityToken token)
    {
        if (writer == null)
            throw new ArgumentNullException(nameof(writer));
        if (token == null)
            throw new ArgumentNullException(nameof(token));

        CreditCardToken c = token as CreditCardToken;
        if (c != null)
        {
            writer.WriteStartElement(Constants.CreditCardTokenPrefix, Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace);
            writer.WriteAttributeString(Constants.WsUtilityPrefix, Constants.Id, Constants.WsUtilityNamespace, token.Id);
            writer.WriteElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardNumber);
            writer.WriteElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace, XmlConvert.ToString(c.CardInfo.ExpirationDate, XmlDateTimeSerializationMode.Utc));
            writer.WriteElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardIssuer);
            writer.WriteEndElement();
            writer.Flush();
        }
        else
        {
            base.WriteTokenCore(writer, token);
        }
    }
}
```

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a><span data-ttu-id="fd999-141">Cómo se crean proveedores de tokens y clases de autenticador de tokens</span><span class="sxs-lookup"><span data-stu-id="fd999-141">How Token Provider and Token Authenticator Classes are Created</span></span>

 <span data-ttu-id="fd999-142">El cliente y las credenciales de servicio son responsables de proporcionar la instancia del administrador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fd999-142">Client and service credentials are responsible for providing the security token manager instance.</span></span> <span data-ttu-id="fd999-143">La instancia del administrador de tokens de seguridad se utiliza para obtener proveedores de tokens, autenticadores de tokens y serializadores de tokens.</span><span class="sxs-lookup"><span data-stu-id="fd999-143">The security token manager instance is used to get token providers, token authenticators and token serializers.</span></span>

 <span data-ttu-id="fd999-144">El proveedor de tokens crea una representación de objeto del token basada en la información contenida en las credenciales del cliente o del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-144">The token provider creates an object representation of the token based on the information contained in the client or service credentials.</span></span> <span data-ttu-id="fd999-145">La representación de objeto de token se escribe a continuación en el mensaje utilizando el serializador de token (explicado en la sección anterior).</span><span class="sxs-lookup"><span data-stu-id="fd999-145">The token object representation is then written to the message using the token serializer (discussed in the previous section).</span></span>

 <span data-ttu-id="fd999-146">El autenticador de tokens valida token que llegan en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fd999-146">The token authenticator validates tokens that arrive in the message.</span></span> <span data-ttu-id="fd999-147">El serializador de token crea la representación de objeto del token de entrada.</span><span class="sxs-lookup"><span data-stu-id="fd999-147">The incoming token object representation is created by the token serializer.</span></span> <span data-ttu-id="fd999-148">Esta representación de objeto se pasa a continuación al autenticador de tokens para la validación.</span><span class="sxs-lookup"><span data-stu-id="fd999-148">This object representation is then passed to the token authenticator for validation.</span></span> <span data-ttu-id="fd999-149">Una vez validado correctamente el token, el autenticador de tokens devuelve una colección de objetos `IAuthorizationPolicy` que representan la información contenida en el token.</span><span class="sxs-lookup"><span data-stu-id="fd999-149">After the token is successfully validated, the token authenticator returns a collection of `IAuthorizationPolicy` objects that represent the information contained in the token.</span></span> <span data-ttu-id="fd999-150">Esta información se utiliza después durante el procesamiento de mensajes para realizar decisiones de autorización y proporcionar notificaciones para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd999-150">This information is used later during the message processing to perform authorization decisions and to provide claims for the application.</span></span> <span data-ttu-id="fd999-151">En este ejemplo, el autenticador de tokens de tarjeta de crédito utiliza `CreditCardTokenAuthorizationPolicy` para este propósito.</span><span class="sxs-lookup"><span data-stu-id="fd999-151">In this example, the credit card token authenticator uses `CreditCardTokenAuthorizationPolicy` for this purpose.</span></span>

 <span data-ttu-id="fd999-152">El serializador de token es responsable de obtener la representación de objeto del token a y desde la conexión.</span><span class="sxs-lookup"><span data-stu-id="fd999-152">The token serializer is responsible for getting the object representation of the token to and from the wire.</span></span> <span data-ttu-id="fd999-153">Esto se explica en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="fd999-153">This is discussed in the previous section.</span></span>

 <span data-ttu-id="fd999-154">En este ejemplo, utilizamos solo un proveedor de tokens en el cliente y un autenticador de tokens en el servicio, porque deseamos transmitir solo un token de tarjeta de crédito en la dirección cliente a servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-154">In this sample, we use a token provider only on the client and a token authenticator only on the service, because we want to transmit a credit card token only in the client-to-service direction.</span></span>

 <span data-ttu-id="fd999-155">La funcionalidad en el cliente se encuentra en las clases `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` y`CreditCardTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="fd999-155">The functionality on the client is located in the `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` and `CreditCardTokenProvider` classes.</span></span>

 <span data-ttu-id="fd999-156">En el servicio, la funcionalidad reside en las clases `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` y `CreditCardTokenAuthorizationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="fd999-156">On the service, the functionality resides in the `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` and `CreditCardTokenAuthorizationPolicy` classes.</span></span>

```csharp
    public class CreditCardClientCredentials : ClientCredentials
    {
        CreditCardInfo creditCardInfo;

        public CreditCardClientCredentials(CreditCardInfo creditCardInfo)
            : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException(nameof(creditCardInfo));

            this.creditCardInfo = creditCardInfo;
        }

        public CreditCardInfo CreditCardInfo
        {
            get { return this.creditCardInfo; }
        }

        protected override ClientCredentials CloneCore()
        {
            return new CreditCardClientCredentials(this.creditCardInfo);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardClientCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardClientCredentialsSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        CreditCardClientCredentials creditCardClientCredentials;

        public CreditCardClientCredentialsSecurityTokenManager(CreditCardClientCredentials creditCardClientCredentials)
            : base (creditCardClientCredentials)
        {
            this.creditCardClientCredentials = creditCardClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // Handle this token for Custom.
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
                return new CreditCardTokenProvider(this.creditCardClientCredentials.CreditCardInfo);
            // Return server cert.
            else if (tokenRequirement is InitiatorServiceModelSecurityTokenRequirement)
            {
                if (tokenRequirement.TokenType == SecurityTokenTypes.X509Certificate)
                {
                    return new X509SecurityTokenProvider(creditCardClientCredentials.ServiceCertificate.DefaultCertificate);
                }
            }

            return base.CreateSecurityTokenProvider(tokenRequirement);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {

            return new CreditCardSecurityTokenSerializer(version);
        }

    }

    class CreditCardTokenProvider : SecurityTokenProvider
    {
        CreditCardInfo creditCardInfo;

        public CreditCardTokenProvider(CreditCardInfo creditCardInfo) : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException(nameof(creditCardInfo));

            this.creditCardInfo = creditCardInfo;
        }

        protected override SecurityToken GetTokenCore(TimeSpan timeout)
        {
            SecurityToken result = new CreditCardToken(this.creditCardInfo);
            return result;
        }
    }

    public class CreditCardServiceCredentials : ServiceCredentials
    {
        string creditCardFile;

        public CreditCardServiceCredentials(string creditCardFile)
            : base()
        {
            if (creditCardFile == null)
                throw new ArgumentNullException(nameof(creditCardFile));

            this.creditCardFile = creditCardFile;
        }

        public string CreditCardDataFile
        {
            get { return this.creditCardFile; }
        }

        protected override ServiceCredentials CloneCore()
        {
            return new CreditCardServiceCredentials(this.creditCardFile);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardServiceCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardServiceCredentialsSecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        CreditCardServiceCredentials creditCardServiceCredentials;

        public CreditCardServiceCredentialsSecurityTokenManager(CreditCardServiceCredentials creditCardServiceCredentials)
            : base(creditCardServiceCredentials)
        {
            this.creditCardServiceCredentials = creditCardServiceCredentials;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
            {
                outOfBandTokenResolver = null;
                return new CreditCardTokenAuthenticator(creditCardServiceCredentials.CreditCardDataFile);
            }

            return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {
            return new CreditCardSecurityTokenSerializer(version);
        }
    }

    class CreditCardTokenAuthenticator : SecurityTokenAuthenticator
    {
        string creditCardsFile;
        public CreditCardTokenAuthenticator(string creditCardsFile)
        {
            this.creditCardsFile = creditCardsFile;
        }

        protected override bool CanValidateTokenCore(SecurityToken token)
        {
            return (token is CreditCardToken);
        }

        protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateTokenCore(SecurityToken token)
        {
            CreditCardToken creditCardToken = token as CreditCardToken;

            if (creditCardToken.CardInfo.ExpirationDate < DateTime.UtcNow)
                throw new SecurityTokenValidationException("The credit card has expired.");
            if (!IsCardNumberAndExpirationValid(creditCardToken.CardInfo))
                throw new SecurityTokenValidationException("Unknown or invalid credit card.");

            // the credit card token has only 1 claim - the card number. The issuer for the claim is the
            // credit card issuer

            var cardIssuerClaimSet = new DefaultClaimSet(new Claim(ClaimTypes.Name, creditCardToken.CardInfo.CardIssuer, Rights.PossessProperty));
            var cardClaimSet = new DefaultClaimSet(cardIssuerClaimSet, new Claim(Constants.CreditCardNumberClaim, creditCardToken.CardInfo.CardNumber, Rights.PossessProperty));
            var policies = new List<IAuthorizationPolicy>(1);
            policies.Add(new CreditCardTokenAuthorizationPolicy(cardClaimSet));
            return policies.AsReadOnly();
        }

        /// <summary>
        /// Helper method to check if a given credit card entry is present in the User DB
        /// </summary>
        private bool IsCardNumberAndExpirationValid(CreditCardInfo cardInfo)
        {
            try
            {
                using (var myStreamReader = new StreamReader(this.creditCardsFile))
                {
                    string line = "";
                    while ((line = myStreamReader.ReadLine()) != null)
                    {
                        string[] splitEntry = line.Split('#');
                        if (splitEntry[0] == cardInfo.CardNumber)
                        {
                            string expirationDateString = splitEntry[1].Trim();
                            DateTime expirationDateOnFile = DateTime.Parse(expirationDateString, System.Globalization.DateTimeFormatInfo.InvariantInfo, System.Globalization.DateTimeStyles.AdjustToUniversal);
                            if (cardInfo.ExpirationDate == expirationDateOnFile)
                            {
                                string issuer = splitEntry[2];
                                return issuer.Equals(cardInfo.CardIssuer, StringComparison.InvariantCultureIgnoreCase);
                            }
                            else
                            {
                                return false;
                            }
                        }
                    }
                    return false;
                }
            }
            catch (Exception e)
            {
                throw new Exception("BookStoreService: Error while retrieving credit card information from User DB " + e.ToString());
            }
        }
    }

    public class CreditCardTokenAuthorizationPolicy : IAuthorizationPolicy
    {
        string id;
        ClaimSet issuer;
        IEnumerable<ClaimSet> issuedClaimSets;

        public CreditCardTokenAuthorizationPolicy(ClaimSet issuedClaims)
        {
            if (issuedClaims == null)
                throw new ArgumentNullException(nameof(issuedClaims));
            this.issuer = issuedClaims.Issuer;
            this.issuedClaimSets = new ClaimSet[] { issuedClaims };
            this.id = Guid.NewGuid().ToString();
        }

        public ClaimSet Issuer { get { return this.issuer; } }

        public string Id { get { return this.id; } }

        public bool Evaluate(EvaluationContext context, ref object state)
        {
            foreach (ClaimSet issuance in this.issuedClaimSets)
            {
                context.AddClaimSet(this, issuance);
            }

            return true;
        }
    }
```

## <a name="displaying-the-callers-information"></a><span data-ttu-id="fd999-157">Mostrar la información de los llamadores</span><span class="sxs-lookup"><span data-stu-id="fd999-157">Displaying the Callers' Information</span></span>

 <span data-ttu-id="fd999-158">Para mostrar la información del autor de la llamada, use `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` tal y como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="fd999-158">To display the caller's information, use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following sample code.</span></span> <span data-ttu-id="fd999-159">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contiene notificaciones de autorización asociadas con el autor de la llamada actual.</span><span class="sxs-lookup"><span data-stu-id="fd999-159">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="fd999-160">La clase `CreditCardToken` proporciona las notificaciones en su colección `AuthorizationPolicies`.</span><span class="sxs-lookup"><span data-stu-id="fd999-160">The claims are supplied by the `CreditCardToken` class in its `AuthorizationPolicies` collection.</span></span>

```csharp
bool TryGetStringClaimValue(ClaimSet claimSet, string claimType, out string claimValue)
{
    claimValue = null;
    IEnumerable<Claim> matchingClaims = claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
        return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    enumerator.MoveNext();
    claimValue = (enumerator.Current.Resource == null) ? null :
        enumerator.Current.Resource.ToString();
    return true;
}

string GetCallerCreditCardNumber()
{
     foreach (ClaimSet claimSet in
         ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)
     {
         string creditCardNumber = null;
         if (TryGetStringClaimValue(claimSet,
             Constants.CreditCardNumberClaim, out creditCardNumber))
             {
                 string issuer;
                 if (!TryGetStringClaimValue(claimSet.Issuer,
                        ClaimTypes.Name, out issuer))
                 {
                     issuer = "Unknown";
                 }
                 return $"Credit card '{creditCardNumber}' issued by '{issuer}'";
        }
    }
    return "Credit card is not known";
}
```

 <span data-ttu-id="fd999-161">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="fd999-162">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-162">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="fd999-163">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="fd999-163">Setup Batch File</span></span>

 <span data-ttu-id="fd999-164">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación hospedada en IIS que requiera seguridad basada en certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="fd999-164">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run the IIS-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="fd999-165">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="fd999-165">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="fd999-166">A continuación, se proporciona una breve descripción de las diferentes secciones de los archivos por lotes de manera que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="fd999-166">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="fd999-167">Crear el certificado de servidor:</span><span class="sxs-lookup"><span data-stu-id="fd999-167">Creating the server certificate:</span></span>

     <span data-ttu-id="fd999-168">Las líneas siguientes del archivo por lotes`Setup.bat` crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="fd999-168">The following lines from the `Setup.bat` batch file create the server certificate to be used.</span></span> <span data-ttu-id="fd999-169">La variable `%SERVER_NAME%`especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="fd999-169">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="fd999-170">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="fd999-170">Change this variable to specify your own server name.</span></span> <span data-ttu-id="fd999-171">El valor predeterminado en este archivo por lotes es el host local.</span><span class="sxs-lookup"><span data-stu-id="fd999-171">The default in this batch file is localhost.</span></span> <span data-ttu-id="fd999-172">Si cambia la variable `%SERVER_NAME%`, debe ir a través de los archivos Client.cs y Service.cs y reemplazar todas las instancias de host local con el nombre del servidor que utiliza en el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="fd999-172">If you change the `%SERVER_NAME%` variable, you must go through the Client.cs and Service.cs files and replace all instances of localhost with the server name that you use in the Setup.bat script.</span></span>

     <span data-ttu-id="fd999-173">El certificado está almacenado en Mi almacén (Personal) en la ubicación de almacén `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="fd999-173">The certificate is stored in My (Personal) store under the `LocalMachine` store location.</span></span> <span data-ttu-id="fd999-174">El certificado está almacenado en el almacén LocalMachine para los servicios hospedados por IIS.</span><span class="sxs-lookup"><span data-stu-id="fd999-174">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="fd999-175">En el caso de servicios autohospedados, debería modificar el archivo por lotes para almacenar el certificado de cliente en la ubicación de almacén CurrentUser reemplazando la cadena LocalMachine con CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="fd999-175">For self-hosted services, you should modify the batch file to store the client certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="fd999-176">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente:</span><span class="sxs-lookup"><span data-stu-id="fd999-176">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="fd999-177">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="fd999-178">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="fd999-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="fd999-179">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="fd999-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```bat
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="fd999-180">Para permitir el acceso a la clave privada del certificado del servicio hospedado por IIS, la cuenta de usuario bajo la que se ejecuta el proceso hospedado por IIS debe tener los permisos adecuados para la clave privada.</span><span class="sxs-lookup"><span data-stu-id="fd999-180">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="fd999-181">Esto se logra con los últimos pasos del script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="fd999-181">This is accomplished by last steps in the Setup.bat script.</span></span>

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
> <span data-ttu-id="fd999-182">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="fd999-182">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="fd999-183">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="fd999-183">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="fd999-184">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd999-184">To set up and build the sample</span></span>

1. <span data-ttu-id="fd999-185">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fd999-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="fd999-186">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="fd999-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="fd999-187">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="fd999-187">To run the sample on the same computer</span></span>

1. <span data-ttu-id="fd999-188">Abra una ventana del símbolo del sistema de Visual Studio 2012 con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd999-188">Open a Visual Studio 2012 Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="fd999-189">De esta forma se instalan todos los certificados necesarios para ejecutar el ejemplo. Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentra Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="fd999-189">This installs all the certificates required for running the sample.Make sure that the path includes the folder where Makecert.exe is located.</span></span>

> [!NOTE]
> <span data-ttu-id="fd999-190">Asegúrese de quitar los certificados ejecutando Cleanup.bat cuando termine con el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd999-190">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="fd999-191">Otros ejemplos de seguridad usan los mismos certificados.</span><span class="sxs-lookup"><span data-stu-id="fd999-191">Other security samples use the same certificates.</span></span>  
  
1. <span data-ttu-id="fd999-192">Inicie Client.exe desde el directorio \client\bin.</span><span class="sxs-lookup"><span data-stu-id="fd999-192">Launch Client.exe from client\bin directory.</span></span> <span data-ttu-id="fd999-193">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-193">Client activity is displayed on the client console application.</span></span>  
  
2. <span data-ttu-id="fd999-194">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="fd999-194">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computer"></a><span data-ttu-id="fd999-195">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="fd999-195">To run the sample across computer</span></span>  
  
1. <span data-ttu-id="fd999-196">Cree un directorio en el equipo del servicio para los binarios del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-196">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="fd999-197">Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-197">Copy the service program files into the service directory on the service computer.</span></span> <span data-ttu-id="fd999-198">No olvide copiar CreditCardFile.txt; de lo contrario el autenticador de la tarjeta de crédito no podrá validar la información de la tarjeta de crédito enviada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-198">Do not forget to copy CreditCardFile.txt; otherwise the credit card authenticator cannot validate credit card information sent from the client.</span></span> <span data-ttu-id="fd999-199">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-199">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="fd999-200">Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="fd999-200">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="fd999-201">Puede crear uno con Setup.bat si cambia la variable `%SERVER_NAME%` por el nombre completo del equipo donde se hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-201">You can create one using the Setup.bat if you change the `%SERVER_NAME%` variable to fully-qualified name of the computer where the service is hosted.</span></span> <span data-ttu-id="fd999-202">Tenga en cuenta que el archivo de Setup.bat se debe ejecutar en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="fd999-202">Note that the Setup.bat file must be run in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>  
  
4. <span data-ttu-id="fd999-203">Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople en el cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-203">Copy the server certificate into the CurrentUser-TrustedPeople store on the client.</span></span> <span data-ttu-id="fd999-204">Solo debe hacerlo si el certificado del servidor no está emitido por un emisor de confianza.</span><span class="sxs-lookup"><span data-stu-id="fd999-204">You must do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5. <span data-ttu-id="fd999-205">En el archivo EchoServiceHost.cs, cambie el valor del nombre del sujeto del certificado para especificar un nombre de equipo completo en lugar de localhost.</span><span class="sxs-lookup"><span data-stu-id="fd999-205">In the EchoServiceHost.cs file, change the value of the certificate subject name to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="fd999-206">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="fd999-206">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
7. <span data-ttu-id="fd999-207">En el archivo Client.cs, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="fd999-207">In the Client.cs file, change the address value of the endpoint to match the new address of your service.</span></span>  
  
8. <span data-ttu-id="fd999-208">En el archivo Client.cs, cambie el nombre del sujeto del certificado X.509 del servicio para que coincida con el nombre de equipo completo del host remoto en lugar de localhost.</span><span class="sxs-lookup"><span data-stu-id="fd999-208">In the Client.cs file change the subject name of the service X.509 certificate to match the fully-qualified computer name of the remote host instead of localhost.</span></span>  
  
9. <span data-ttu-id="fd999-209">En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="fd999-209">On the client computer, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="fd999-210">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="fd999-210">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="fd999-211">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd999-211">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="fd999-212">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd999-212">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>
