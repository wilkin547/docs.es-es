---
description: 'Más información acerca de: token personalizado'
title: Token personalizado
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: 500cc187db0280e508ef079ca370483c716ea2c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752436"
---
# <a name="custom-token"></a>Token personalizado

Este ejemplo muestra cómo agregar una implementación de token personalizada en una aplicación Windows Communication Foundation (WCF). El ejemplo utiliza `CreditCardToken` para pasar de manera segura información sobre las tarjetas de crédito del cliente al servicio. El token se pasa en el encabezado de mensaje WS-Security y se firma y cifra utilizando el elemento de enlace de seguridad simétrico junto con el cuerpo del mensaje y otros encabezados del mensaje. Esto es útil en casos donde los tokens integrados no son suficiente. Este ejemplo muestra cómo proporcionar un token de seguridad personalizado a un servicio en lugar de utilizar uno de los tokens integrados. El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

 En resumen, este ejemplo muestra lo siguiente:

- Cómo un cliente puede pasar un token de seguridad personalizado a un servicio.

- Cómo el servicio puede utilizar y validar un token de seguridad personalizado.

- Cómo el código de servicio WCF puede obtener la información sobre los tokens de seguridad recibidos, incluido el token de seguridad personalizado.

- Cómo el certificado X.509 del servidor se utiliza para proteger la clave simétrica utilizada para el cifrado y firma de mensajes.

## <a name="client-authentication-using-a-custom-security-token"></a>Autenticación del Cliente utilizando un token de seguridad personalizado

 El servicio expone un punto de conexión único que se crea mediante programación usando las clases `BindingHelper` y `EchoServiceHost`. El punto de conexión está compuesto por una dirección, un enlace y un contrato. El enlace se configura con un enlace personalizado utilizando `SymmetricSecurityBindingElement` y `HttpTransportBindingElement`. Este ejemplo establece `SymmetricSecurityBindingElement` para utilizar el certificado X.509 de un servicio para proteger la clave simétrica durante la transmisión y pasar un `CreditCardToken` personalizado en un encabezado de mensaje de WS-Security como un token de seguridad firmado y cifrado. El comportamiento especifica las credenciales del servicio que se van a utilizar para la autenticación del cliente además de la información sobre el certificado X.509 del servicio.

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

 Para utilizar un token de tarjeta de crédito en el mensaje, el ejemplo utiliza las credenciales del servicio personalizadas para proporcionar esta funcionalidad. La clase de credenciales de servicio se encuentra en la clase `CreditCardServiceCredentials` y se agrega a las colecciones de comportamientos del host de servicio en el método `EchoServiceHost.InitializeRuntime`.

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

 El extremo del cliente se configura de una manera similar al extremo de servicio. El cliente utiliza la misma clase `BindingHelper` para crear un enlace. El resto de la instalación se encuentra en la clase `Client`. El cliente también establece información que se va a contener en `CreditCardToken` e información sobre el certificado X.509 del servicio en el código de instalación agregando una instancia `CreditCardClientCredentials` con los datos apropiados a la colección de comportamientos de punto de conexión del cliente. El ejemplo utiliza el certificado X.509 con nombre sujeto establecido en `CN=localhost` como el certificado del servicio.

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

## <a name="custom-security-token-implementation"></a>Implementación de token de seguridad personalizada

 Para habilitar un token de seguridad personalizado en WCF, cree una representación de objeto del token de seguridad personalizado. El ejemplo tiene esta representación en la clase `CreditCardToken`. La representación de objeto es responsable de contener toda la información pertinente del token de seguridad y de proporcionar una lista de claves de seguridad contenida en el token de seguridad. En este caso, el token de seguridad de la tarjeta de crédito no contiene ninguna clave de seguridad.

 En la sección siguiente se describe lo que se debe hacer para permitir que un token personalizado se transmita a través de la conexión y lo consuma un punto de conexión de WCF.

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

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a>Obtener el token de la tarjeta de crédito personalizado en y desde el mensaje

 Los serializadores de tokens de seguridad en WCF son responsables de crear una representación de objeto de tokens de seguridad a partir del XML en el mensaje y de crear un formulario XML de los tokens de seguridad. También son responsables de otras funcionalidades, como leer y escribir identificadores de clave que señalan a token de seguridad, pero este ejemplo solo utiliza funcionalidad relacionada con token de seguridad. Para habilitar un token personalizado, debe implementar su propio serializador de tokens de seguridad. Para ello, en este ejemplo se utiliza la clase `CreditCardSecurityTokenSerializer`.

 En el servicio, el serializador personalizado lee la forma en XML del token personalizado y crea la representación de objeto del token personalizada a partir de ella.

 En el cliente, la clase `CreditCardSecurityTokenSerializer` escribe la información contenida en la representación de objeto del token de seguridad en el sistema de escritura de XML.

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

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a>Cómo se crean proveedores de tokens y clases de autenticador de tokens

 El cliente y las credenciales de servicio son responsables de proporcionar la instancia del administrador de tokens de seguridad. La instancia del administrador de tokens de seguridad se utiliza para obtener proveedores de tokens, autenticadores de tokens y serializadores de tokens.

 El proveedor de tokens crea una representación de objeto del token basada en la información contenida en las credenciales del cliente o del servicio. La representación de objeto de token se escribe a continuación en el mensaje utilizando el serializador de token (explicado en la sección anterior).

 El autenticador de tokens valida token que llegan en el mensaje. El serializador de token crea la representación de objeto del token de entrada. Esta representación de objeto se pasa a continuación al autenticador de tokens para la validación. Una vez validado correctamente el token, el autenticador de tokens devuelve una colección de objetos `IAuthorizationPolicy` que representan la información contenida en el token. Esta información se utiliza después durante el procesamiento de mensajes para realizar decisiones de autorización y proporcionar notificaciones para la aplicación. En este ejemplo, el autenticador de tokens de tarjeta de crédito utiliza `CreditCardTokenAuthorizationPolicy` para este propósito.

 El serializador de token es responsable de obtener la representación de objeto del token a y desde la conexión. Esto se explica en la sección anterior.

 En este ejemplo, utilizamos solo un proveedor de tokens en el cliente y un autenticador de tokens en el servicio, porque deseamos transmitir solo un token de tarjeta de crédito en la dirección cliente a servicio.

 La funcionalidad en el cliente se encuentra en las clases `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` y`CreditCardTokenProvider`.

 En el servicio, la funcionalidad reside en las clases `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` y `CreditCardTokenAuthorizationPolicy`.

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

## <a name="displaying-the-callers-information"></a>Mostrar la información de los llamadores

 Para mostrar la información del autor de la llamada, use `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` tal y como se muestra en el código muestra siguiente. `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contiene notificaciones de autorización asociadas con el autor de la llamada actual. La clase `CreditCardToken` proporciona las notificaciones en su colección `AuthorizationPolicies`.

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

 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes

 El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación hospedada en IIS que requiera seguridad basada en certificado de servidor. Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.

 A continuación, se proporciona una breve descripción de las diferentes secciones de los archivos por lotes de manera que se puedan modificar para ejecutarse con la configuración adecuada.

- Crear el certificado de servidor:

     Las líneas siguientes del archivo por lotes`Setup.bat` crean el certificado de servidor que se va a usar. La variable `%SERVER_NAME%`especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado en este archivo por lotes es el host local. Si cambia la variable `%SERVER_NAME%`, debe ir a través de los archivos Client.cs y Service.cs y reemplazar todas las instancias de host local con el nombre del servidor que utiliza en el script Setup.bat.

     El certificado está almacenado en Mi almacén (Personal) en la ubicación de almacén `LocalMachine`. El certificado está almacenado en el almacén LocalMachine para los servicios hospedados por IIS. En el caso de servicios autohospedados, debería modificar el archivo por lotes para almacenar el certificado de cliente en la ubicación de almacén CurrentUser reemplazando la cadena LocalMachine con CurrentUser.

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del servidor en el almacén de certificados de confianza del cliente:

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.

    ```bat
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Para permitir el acceso a la clave privada del certificado del servicio hospedado por IIS, la cuenta de usuario bajo la que se ejecuta el proceso hospedado por IIS debe tener los permisos adecuados para la clave privada. Esto se logra con los últimos pasos del script Setup.bat.

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
> El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.

#### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Abra una ventana del símbolo del sistema de Visual Studio 2012 con privilegios de administrador y ejecute Setup.bat desde la carpeta de instalación de ejemplo. De esta forma se instalan todos los certificados necesarios para ejecutar el ejemplo. Asegúrese de que la ruta de acceso incluye la carpeta donde se encuentra Makecert.exe.

> [!NOTE]
> Asegúrese de quitar los certificados ejecutando Cleanup.bat cuando termine con el ejemplo. Otros ejemplos de seguridad usan los mismos certificados.  
  
1. Inicie Client.exe desde el directorio \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
2. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computer"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Cree un directorio en el equipo del servicio para los binarios del servicio.  
  
2. Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio. No olvide copiar CreditCardFile.txt; de lo contrario el autenticador de la tarjeta de crédito no podrá validar la información de la tarjeta de crédito enviada por el cliente. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3. Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo. Puede crear uno con Setup.bat si cambia la variable `%SERVER_NAME%` por el nombre completo del equipo donde se hospeda el servicio. Tenga en cuenta que el archivo de Setup.bat se debe ejecutar en un Símbolo del sistema para desarrolladores para Visual Studio abierto con privilegios de administrador.  
  
4. Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople en el cliente. Solo debe hacerlo si el certificado del servidor no está emitido por un emisor de confianza.  
  
5. En el archivo EchoServiceHost.cs, cambie el valor del nombre del sujeto del certificado para especificar un nombre de equipo completo en lugar de localhost.  
  
6. Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
7. En el archivo Client.cs, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.  
  
8. En el archivo Client.cs, cambie el nombre del sujeto del certificado X.509 del servicio para que coincida con el nombre de equipo completo del host remoto en lugar de localhost.  
  
9. En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.  
  
10. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
1. Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.
