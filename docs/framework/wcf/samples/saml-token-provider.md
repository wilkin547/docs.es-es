---
title: Proveedor de tokens SAML
ms.date: 03/30/2017
ms.assetid: eb16e5e2-4c8d-4f61-a479-9c965fcec80c
ms.openlocfilehash: 97c3c89a94882000c529bae77f1a4d707b242d7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262663"
---
# <a name="saml-token-provider"></a><span data-ttu-id="c5668-102">Proveedor de tokens SAML</span><span class="sxs-lookup"><span data-stu-id="c5668-102">SAML Token Provider</span></span>

<span data-ttu-id="c5668-103">Este ejemplo muestra cómo implementar un proveedor de tokens de SAML de cliente personalizado.</span><span class="sxs-lookup"><span data-stu-id="c5668-103">This sample demonstrates how to implement a custom client SAML token provider.</span></span> <span data-ttu-id="c5668-104">Un proveedor de tokens en Windows Communication Foundation (WCF) se usa para proporcionar credenciales a la infraestructura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c5668-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="c5668-105">En general, el proveedor de tokens examina el destino y emite las credenciales adecuadas de manera que la infraestructura de seguridad pueda proteger el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5668-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="c5668-106">WCF se suministra con el proveedor de tokens del administrador de credenciales predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c5668-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="c5668-107">WCF también se suministra con un proveedor de tokens de CardSpace.</span><span class="sxs-lookup"><span data-stu-id="c5668-107">WCF also ships with a CardSpace token provider.</span></span> <span data-ttu-id="c5668-108">Los proveedores de tokens personalizados son útiles en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5668-108">Custom token providers are useful in the following cases:</span></span>

- <span data-ttu-id="c5668-109">Si tiene un almacén de credenciales con el que estos proveedores de tokens no pueden funcionar.</span><span class="sxs-lookup"><span data-stu-id="c5668-109">If you have a credential store that these token providers cannot operate with.</span></span>

- <span data-ttu-id="c5668-110">Si desea proporcionar su propio mecanismo personalizado para transformar las credenciales desde el punto en el que el usuario proporciona detalles cuando el marco de trabajo de cliente de WCF usa las credenciales.</span><span class="sxs-lookup"><span data-stu-id="c5668-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>

- <span data-ttu-id="c5668-111">Si está creando un token personalizado.</span><span class="sxs-lookup"><span data-stu-id="c5668-111">If you are building a custom token.</span></span>

 <span data-ttu-id="c5668-112">En este ejemplo se muestra cómo crear un proveedor de tokens personalizado que permite el uso de un token SAML obtenido desde fuera de la plataforma de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="c5668-112">This sample shows how to build a custom token provider that allows a SAML token obtained from outside of the WCF client framework to be used.</span></span>

 <span data-ttu-id="c5668-113">En resumen, este ejemplo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5668-113">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="c5668-114">Cómo se puede configurar un cliente con un proveedor de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="c5668-114">How a client can be configured with a custom token provider.</span></span>

- <span data-ttu-id="c5668-115">Cómo un token de SAML se puede pasar a las credenciales del cliente personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5668-115">How a SAML token can be passed to the custom client credentials.</span></span>

- <span data-ttu-id="c5668-116">Cómo se proporciona el token SAML al marco de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="c5668-116">How the SAML token is provided to the WCF client framework.</span></span>

- <span data-ttu-id="c5668-117">Cómo el cliente autentica el servidor usando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="c5668-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>

 <span data-ttu-id="c5668-118">El servicio expone dos puntos de conexión para comunicarse con el servicio, definidos mediante el archivo de configuración App.config. Cada punto de conexión consta de una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="c5668-118">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="c5668-119">El enlace se configura con un `wsFederationHttpBinding` estándar, que usa la seguridad de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5668-119">The binding is configured with a standard `wsFederationHttpBinding`, which uses Message security.</span></span> <span data-ttu-id="c5668-120">Un punto de conexión espera que el cliente autentique con un token de SAML que utiliza una clave de prueba simétrica mientras el otro espera que el cliente autentique con un token de SAML que utiliza una clave de prueba asimétrica.</span><span class="sxs-lookup"><span data-stu-id="c5668-120">One endpoint expects the client to authenticate with a SAML token that uses a symmetric proof key while the other expects the client to authenticate with a SAML token that uses an asymmetric proof key.</span></span> <span data-ttu-id="c5668-121">El servicio también configura el certificado del servicio utilizando comportamiento`serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="c5668-121">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="c5668-122">El comportamiento `serviceCredentials` le permite configurar un certificado del servicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-122">The `serviceCredentials` behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="c5668-123">Un cliente utiliza un certificado de servicio para autenticar el servicio y proporcionar protección al mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5668-123">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="c5668-124">La configuración siguiente hace referencia al certificado del host local instalado durante la configuración del ejemplo tal y como se describe en las instrucciones de configuración al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="c5668-124">The following configuration references the "localhost" certificate installed during the sample setup as described in the setup instructions at the end of this topic.</span></span> <span data-ttu-id="c5668-125">El comportamiento `serviceCredentials` también le permite configurar certificados en los que se confia para firmar los tokens de SAML.</span><span class="sxs-lookup"><span data-stu-id="c5668-125">The `serviceCredentials` behavior also allows you to configure certificates that are trusted to sign SAML tokens.</span></span> <span data-ttu-id="c5668-126">La configuración siguiente hace referencia al certificado 'Alice' instalado durante el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5668-126">The following configuration references the 'Alice' certificate installed during the sample.</span></span>

```xml
<system.serviceModel>
 <services>
  <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
   <host>
    <baseAddresses>
     <!-- configure base address provided by host -->
     <add
  baseAddress="http://localhost:8000/servicemodelsamples/service/" />
    </baseAddresses>
   </host>
   <!-- use base address provided by host -->
   <!-- Endpoint that expect SAML tokens with Symmetric proof keys -->
   <endpoint address="calc/symm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
   <!-- Endpoint that expect SAML tokens with Asymmetric proof keys -->
   <endpoint address="calc/asymm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding2"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
 </services>

 <bindings>
  <wsFederationHttpBinding>
   <!-- Binding that expect SAML tokens with Symmetric proof keys -->
   <binding name="Binding1">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="SymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
   <!-- Binding that expect SAML tokens with Asymmetric proof keys -->
   <binding name="Binding2">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="AsymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
  </wsFederationHttpBinding>
 </bindings>

 <behaviors>
  <serviceBehaviors>
   <behavior name="CalculatorServiceBehavior">
    <!--
    The serviceCredentials behavior allows one to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
    <serviceCredentials>
     <!-- Set allowUntrustedRsaIssuers to true to allow self-signed, asymmetric key based SAML tokens -->
     <issuedTokenAuthentication allowUntrustedRsaIssuers ="true" >
      <!-- Add Alice to the list of certs trusted to issue SAML tokens -->
      <knownCertificates>
       <add storeLocation="LocalMachine"
            storeName="TrustedPeople"
            x509FindType="FindBySubjectName"
            findValue="Alice"/>
      </knownCertificates>
     </issuedTokenAuthentication>
     <serviceCertificate storeLocation="LocalMachine"
                         storeName="My"
                         x509FindType="FindBySubjectName"
                         findValue="localhost"  />
    </serviceCredentials>
   </behavior>
  </serviceBehaviors>
 </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="c5668-127">En los pasos siguientes se muestra cómo desarrollar un proveedor de tokens SAML personalizado e integrarlo con WCF: marco de seguridad:</span><span class="sxs-lookup"><span data-stu-id="c5668-127">The following steps show how to develop a custom SAML token provider and integrate it with WCF: security framework:</span></span>

1. <span data-ttu-id="c5668-128">Escriba un proveedor de tokens personalizado SAML.</span><span class="sxs-lookup"><span data-stu-id="c5668-128">Write a custom SAML token provider.</span></span>

     <span data-ttu-id="c5668-129">El ejemplo implementa un proveedor de tokens de SAML personalizado que devuelve un token de seguridad basado en una aserción de SAML que se proporciona en el momento de la construcción.</span><span class="sxs-lookup"><span data-stu-id="c5668-129">The sample implements a custom SAML token provider that returns a security token based on a SAML assertion that is provided at construction time.</span></span>

     <span data-ttu-id="c5668-130">Para realizar esta tarea, el proveedor de tokens personalizado se deriva de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5668-130">To perform this task, the custom token provider is derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="c5668-131">Este método crea y devuelve un nuevo `SecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="c5668-131">This method creates and returns a new `SecurityToken`.</span></span>

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
     // Create a SamlSecurityToken from the provided assertion
     SamlSecurityToken samlToken = new SamlSecurityToken(assertion);

     // Create a SecurityTokenSerializer that will be used to
     // serialize the SamlSecurityToken
     WSSecurityTokenSerializer ser = new WSSecurityTokenSerializer();
     // Create a memory stream to write the serialized token into
     // Use an initial size of 64Kb
     MemoryStream s = new MemoryStream(UInt16.MaxValue);

     // Create an XmlWriter over the stream
     XmlWriter xw = XmlWriter.Create(s);

     // Write the SamlSecurityToken into the stream
     ser.WriteToken(xw, samlToken);

     // Seek back to the beginning of the stream
     s.Seek(0, SeekOrigin.Begin);

     // Load the serialized token into a DOM
     XmlDocument dom = new XmlDocument();
     dom.Load(s);

     // Create a KeyIdentifierClause for the SamlSecurityToken
     SamlAssertionKeyIdentifierClause samlKeyIdentifierClause = samlToken.CreateKeyIdentifierClause<SamlAssertionKeyIdentifierClause>();

    // Return a GenericXmlToken from the XML for the
    // SamlSecurityToken, the proof token, the valid from and valid
    // until times from the assertion and the key identifier clause
    // created above
    return new GenericXmlSecurityToken(dom.DocumentElement, proofToken, assertion.Conditions.NotBefore, assertion.Conditions.NotOnOrAfter, samlKeyIdentifierClause, samlKeyIdentifierClause, null);
    }
    ```

2. <span data-ttu-id="c5668-132">Escribir el administrador de tokens de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="c5668-132">Write custom security token manager.</span></span>

     <span data-ttu-id="c5668-133">La clase <xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear <xref:System.IdentityModel.Selectors.SecurityTokenProvider> para el <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concreto que se pasa en el método `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="c5668-133">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> class is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="c5668-134">Un administrador de tokens de seguridad también se utiliza para crear autenticadores de tokens y serializadores de tokens, aunque en este ejemplo no se explica.</span><span class="sxs-lookup"><span data-stu-id="c5668-134">A security token manager is also used to create token authenticators and token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="c5668-135">En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenProvider` para devolver el proveedor de tokens personalizado SAML cuando los requisitos de tokens pasados indican que se solicita el token SAML.</span><span class="sxs-lookup"><span data-stu-id="c5668-135">In this sample the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom SAML token provider when the passed token requirements indicate that the SAML token is requested.</span></span> <span data-ttu-id="c5668-136">Si la clase (vea el paso 3) de credenciales del cliente no ha especificado una aserción, el administrador de tokens de seguridad crea una instancia adecuada.</span><span class="sxs-lookup"><span data-stu-id="c5668-136">If the client credentials class (see step 3) has not specified an assertion, the security token manager creates an appropriate instance.</span></span>

    ```csharp
    public class SamlSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
     SamlClientCredentials samlClientCredentials;

     public SamlSecurityTokenManager ( SamlClientCredentials samlClientCredentials)
      : base(samlClientCredentials)
     {
      // Store the creating client credentials
      this.samlClientCredentials = samlClientCredentials;
     }

     public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )
     {
      // If token requirement matches SAML token return the
      // custom SAML token provider
      if (tokenRequirement.TokenType == SecurityTokenTypes.Saml ||
          tokenRequirement.TokenType == "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1")
      {
       // Retrieve the SAML assertion and proof token from the
       // client credentials
       SamlAssertion assertion = this.samlClientCredentials.Assertion;
       SecurityToken prooftoken = this.samlClientCredentials.ProofToken;

       // If either the assertion of proof token is null...
       if (assertion == null || prooftoken == null)
       {
        // ...get the SecurityBindingElement and then the
        // specified algorithm suite
        SecurityBindingElement sbe = null;
        SecurityAlgorithmSuite sas = null;

        if ( tokenRequirement.TryGetProperty<SecurityBindingElement> ( "http://schemas.microsoft.com/ws/2006/05/servicemodel/securitytokenrequirement/SecurityBindingElement", out sbe))
        {
         sas = sbe.DefaultAlgorithmSuite;
        }

        // If the token requirement is for a SymmetricKey based token..
        if (tokenRequirement.KeyType == SecurityKeyType.SymmetricKey)
        {
         // Create a symmetric proof token
         prooftoken = SamlUtilities.CreateSymmetricProofToken ( tokenRequirement.KeySize );
         // and a corresponding assertion based on the claims specified in the client credentials
         assertion = SamlUtilities.CreateSymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, new X509SecurityToken ( samlClientCredentials.ClientCertificate.Certificate ), new X509SecurityToken ( samlClientCredentials.ServiceCertificate.DefaultCertificate ), (BinarySecretSecurityToken)prooftoken, sas);
        }
        // otherwise...
        else
        {
         // Create an asymmetric proof token
         prooftoken = SamlUtilities.CreateAsymmetricProofToken();
         // and a corresponding assertion based on the claims
         // specified in the client credentials
         assertion = SamlUtilities.CreateAsymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, prooftoken, sas );
        }
       }

       // Create a SamlSecurityTokenProvider based on the assertion and proof token
       return new SamlSecurityTokenProvider(assertion, prooftoken);
      }
      // otherwise use base implementation
      else
      {
       return base.CreateSecurityTokenProvider(tokenRequirement);
      }
    }
    ```

3. <span data-ttu-id="c5668-137">Escribir una credencial de cliente personalizada.</span><span class="sxs-lookup"><span data-stu-id="c5668-137">Write a custom client credential.</span></span>

     <span data-ttu-id="c5668-138">Se usa una clase de credenciales de cliente para representar las credenciales que se configuran para el proxy de cliente y crear un administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y un serializador de tokens.</span><span class="sxs-lookup"><span data-stu-id="c5668-138">Client credentials class is used to represent the credentials that are configured for the client proxy and creates a security token manager that is used to obtain token authenticators, token providers and token serializer.</span></span>

    ```csharp
    public class SamlClientCredentials : ClientCredentials
    {
     ClaimSet claims;
     SamlAssertion assertion;
     SecurityToken proofToken;

     public SamlClientCredentials() : base()
     {
      // Set SupportInteractive to false to suppress Cardspace UI
      base.SupportInteractive = false;
     }

     protected SamlClientCredentials(SamlClientCredentials other) : base ( other )
     {
      // Just do reference copy given sample nature
      this.assertion = other.assertion;
      this.claims = other.claims;
      this.proofToken = other.proofToken;
     }

     public SamlAssertion Assertion { get { return assertion; } set { assertion = value; } }

     public SecurityToken ProofToken { get { return proofToken; } set { proofToken = value; } }
     public ClaimSet Claims { get { return claims; } set { claims = value; } }

     protected override ClientCredentials CloneCore()
     {
      return new SamlClientCredentials(this);
     }

     public override SecurityTokenManager CreateSecurityTokenManager()
     {
      // return custom security token manager
      return new SamlSecurityTokenManager(this);
     }
    }
    ```

4. <span data-ttu-id="c5668-139">Configure el cliente para utilizar la credencial del cliente personalizada.</span><span class="sxs-lookup"><span data-stu-id="c5668-139">Configure the client to use the custom client credential.</span></span>

     <span data-ttu-id="c5668-140">Para que el cliente pueda utilizar la credencial de cliente personalizada, el ejemplo elimina la clase de credencial de cliente predeterminada y proporciona la nueva.</span><span class="sxs-lookup"><span data-stu-id="c5668-140">The sample deletes the default client credential class and supplies the new client credential class so the client can use the custom client credential.</span></span>

    ```csharp
    // Create new credentials class
    SamlClientCredentials samlCC = new SamlClientCredentials();

    // Set the client certificate. This is the cert that will be used to sign the SAML token in the symmetric proof key case
    samlCC.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "Alice");

    // Set the service certificate. This is the cert that will be used to encrypt the proof key in the symmetric proof key case
    samlCC.ServiceCertificate.SetDefaultCertificate(StoreLocation.CurrentUser, StoreName.TrustedPeople, X509FindType.FindBySubjectName, "localhost");

    // Create some claims to put in the SAML assertion
    IList<Claim> claims = new List<Claim>();
    claims.Add(Claim.CreateNameClaim(samlCC.ClientCertificate.Certificate.Subject));
    ClaimSet claimset = new DefaultClaimSet(claims);
    samlCC.Claims = claimset;

    // set new credentials
    client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
    client.ChannelFactory.Endpoint.Behaviors.Add(samlCC);
    ```

 <span data-ttu-id="c5668-141">En el servicio, las notificaciones asociadas al llamador se muestran.</span><span class="sxs-lookup"><span data-stu-id="c5668-141">On the service, the claims associated with the caller are displayed.</span></span> <span data-ttu-id="c5668-142">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-142">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c5668-143">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-143">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="c5668-144">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="c5668-144">Setup Batch File</span></span>

 <span data-ttu-id="c5668-145">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con el certificado pertinente para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="c5668-145">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="c5668-146">Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.</span><span class="sxs-lookup"><span data-stu-id="c5668-146">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="c5668-147">A continuación, se proporciona una breve descripción de las diferentes secciones de los archivos por lotes de manera que se puedan modificar para ejecutarse con la configuración adecuada.</span><span class="sxs-lookup"><span data-stu-id="c5668-147">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="c5668-148">Crear el certificado de servidor:</span><span class="sxs-lookup"><span data-stu-id="c5668-148">Creating the server certificate:</span></span>

     <span data-ttu-id="c5668-149">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c5668-149">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="c5668-150">La variable `%SERVER_NAME%`especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="c5668-150">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="c5668-151">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="c5668-151">Change this variable to specify your own server name.</span></span> <span data-ttu-id="c5668-152">El valor predeterminado en este archivo por lotes es el host local.</span><span class="sxs-lookup"><span data-stu-id="c5668-152">The default value in this batch file is localhost.</span></span>

     <span data-ttu-id="c5668-153">El certificado se almacena en el almacén My (Personal), en la ubicación de almacenamiento LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="c5668-153">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="c5668-154">Instalar el certificado del servidor en el almacén de certificados de confianza de cliente:</span><span class="sxs-lookup"><span data-stu-id="c5668-154">Installing the server certificate into the client's trusted certificate store:</span></span>

     <span data-ttu-id="c5668-155">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-155">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c5668-156">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="c5668-156">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c5668-157">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="c5668-157">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="c5668-158">Crear el certificado de emisor.</span><span class="sxs-lookup"><span data-stu-id="c5668-158">Creating the issuer certificate.</span></span>

     <span data-ttu-id="c5668-159">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de emisor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c5668-159">The following lines from the Setup.bat batch file create the issuer certificate to be used.</span></span> <span data-ttu-id="c5668-160">La variable `%USER_NAME%` especifica el nombre del emisor.</span><span class="sxs-lookup"><span data-stu-id="c5668-160">The `%USER_NAME%` variable specifies the issuer name.</span></span> <span data-ttu-id="c5668-161">Cambie esta variable para especificar el nombre del emisor.</span><span class="sxs-lookup"><span data-stu-id="c5668-161">Change this variable to specify your own issuer name.</span></span> <span data-ttu-id="c5668-162">El valor predeterminado en este archivo por lotes es Alice.</span><span class="sxs-lookup"><span data-stu-id="c5668-162">The default value in this batch file is Alice.</span></span>

     <span data-ttu-id="c5668-163">El certificado está almacenado en My store en la ubicación del almacén CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="c5668-163">The certificate is stored in My store under the CurrentUser store location.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="c5668-164">Instalar el certificado del emisor en el almacén de certificados de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="c5668-164">Installing the issuer certificate into the server's trusted certificate store.</span></span>

     <span data-ttu-id="c5668-165">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-165">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="c5668-166">Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="c5668-166">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="c5668-167">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado del servidor con el certificado de emisor.</span><span class="sxs-lookup"><span data-stu-id="c5668-167">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the server certificate store with the issuer certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="c5668-168">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5668-168">To set up and build the sample</span></span>

1. <span data-ttu-id="c5668-169">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5668-169">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c5668-170">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c5668-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c5668-171">Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-171">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="c5668-172">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="c5668-172">To run the sample on the same computer</span></span>

1. <span data-ttu-id="c5668-173">Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 y ejecute con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c5668-173">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="c5668-174">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5668-174">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c5668-175">El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="c5668-175">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="c5668-176">La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="c5668-176">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="c5668-177">Inicie Service.exe desde \service\bin.</span><span class="sxs-lookup"><span data-stu-id="c5668-177">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="c5668-178">Inicie Client.exe desde \client\bin.</span><span class="sxs-lookup"><span data-stu-id="c5668-178">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="c5668-179">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-179">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="c5668-180">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c5668-180">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="c5668-181">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="c5668-181">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="c5668-182">Cree un directorio en el equipo del servicio para los binarios del servicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-182">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="c5668-183">Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-183">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="c5668-184">Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-184">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="c5668-185">Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="c5668-185">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="c5668-186">El archivo Service.exe.config debe actualizarse para reflejar este nuevo nombre de certificado.</span><span class="sxs-lookup"><span data-stu-id="c5668-186">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="c5668-187">Puede crear el certificado de servidor modificando el archivo por lotes Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="c5668-187">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="c5668-188">Tenga en cuenta que el archivo de setup.bat se debe ejecutar en una ventana Símbolo del sistema para desarrolladores para Visual Studio abierta con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="c5668-188">Note that the setup.bat file must be run in a Developer Command Prompt for Visual Studio window opened with administrator privileges.</span></span> <span data-ttu-id="c5668-189">Debe establecer la variable `%SERVER_NAME%` en el nombre de host completo del equipo que se utiliza para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-189">You must set the `%SERVER_NAME%` variable to the fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4. <span data-ttu-id="c5668-190">Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-190">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="c5668-191">Este paso no es necesario cuando el certificado de servidor procede de un emisor de confianza para el cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-191">This step is not necessary when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="c5668-192">En el archivo Service.exe.config situado en el equipo del servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.</span><span class="sxs-lookup"><span data-stu-id="c5668-192">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="c5668-193">En el equipo del servicio, ejecute Service.exe desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5668-193">On the service computer, run Service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="c5668-194">Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="c5668-194">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="c5668-195">En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="c5668-195">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="c5668-196">En el equipo cliente, inicie `Client.exe` desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5668-196">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="c5668-197">Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="c5668-197">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="c5668-198">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5668-198">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="c5668-199">Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5668-199">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>
