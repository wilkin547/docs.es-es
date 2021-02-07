---
description: 'Más información acerca de: proveedor de tokens SAML'
title: Proveedor de tokens SAML
ms.date: 03/30/2017
ms.assetid: eb16e5e2-4c8d-4f61-a479-9c965fcec80c
ms.openlocfilehash: f65d34732c14bc1d3a442b9aacda1621995c975e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703697"
---
# <a name="saml-token-provider"></a>Proveedor de tokens SAML

Este ejemplo muestra cómo implementar un proveedor de tokens de SAML de cliente personalizado. Un proveedor de tokens en Windows Communication Foundation (WCF) se usa para proporcionar credenciales a la infraestructura de seguridad. En general, el proveedor de tokens examina el destino y emite las credenciales adecuadas de manera que la infraestructura de seguridad pueda proteger el mensaje. WCF se suministra con el proveedor de tokens del administrador de credenciales predeterminado. WCF también se suministra con un proveedor de tokens de CardSpace. Los proveedores de tokens personalizados son útiles en los casos siguientes:

- Si tiene un almacén de credenciales con el que estos proveedores de tokens no pueden funcionar.

- Si desea proporcionar su propio mecanismo personalizado para transformar las credenciales desde el punto en el que el usuario proporciona detalles cuando el marco de trabajo de cliente de WCF usa las credenciales.

- Si está creando un token personalizado.

 En este ejemplo se muestra cómo crear un proveedor de tokens personalizado que permite el uso de un token SAML obtenido desde fuera de la plataforma de cliente de WCF.

 En resumen, este ejemplo muestra lo siguiente:

- Cómo se puede configurar un cliente con un proveedor de tokens personalizado.

- Cómo un token de SAML se puede pasar a las credenciales del cliente personalizadas.

- Cómo se proporciona el token SAML al marco de cliente de WCF.

- Cómo el cliente autentica el servidor usando el certificado X.509 del servidor.

 El servicio expone dos puntos de conexión para comunicarse con el servicio, definidos mediante el archivo de configuración App.config. Cada punto de conexión consta de una dirección, un enlace y un contrato. El enlace se configura con un `wsFederationHttpBinding` estándar, que usa la seguridad de mensaje. Un punto de conexión espera que el cliente autentique con un token de SAML que utiliza una clave de prueba simétrica mientras el otro espera que el cliente autentique con un token de SAML que utiliza una clave de prueba asimétrica. El servicio también configura el certificado del servicio utilizando comportamiento`serviceCredentials`. El comportamiento `serviceCredentials` le permite configurar un certificado del servicio. Un cliente utiliza un certificado de servicio para autenticar el servicio y proporcionar protección al mensaje. La configuración siguiente hace referencia al certificado del host local instalado durante la configuración del ejemplo tal y como se describe en las instrucciones de configuración al final de este tema. El comportamiento `serviceCredentials` también le permite configurar certificados en los que se confia para firmar los tokens de SAML. La configuración siguiente hace referencia al certificado 'Alice' instalado durante el ejemplo.

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

 En los pasos siguientes se muestra cómo desarrollar un proveedor de tokens SAML personalizado e integrarlo con WCF: marco de seguridad:

1. Escriba un proveedor de tokens personalizado SAML.

     El ejemplo implementa un proveedor de tokens de SAML personalizado que devuelve un token de seguridad basado en una aserción de SAML que se proporciona en el momento de la construcción.

     Para realizar esta tarea, el proveedor de tokens personalizado se deriva de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>. Este método crea y devuelve un nuevo `SecurityToken`.

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

2. Escribir el administrador de tokens de seguridad personalizado.

     La clase <xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear <xref:System.IdentityModel.Selectors.SecurityTokenProvider> para el <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concreto que se pasa en el método `CreateSecurityTokenProvider`. Un administrador de tokens de seguridad también se utiliza para crear autenticadores de tokens y serializadores de tokens, aunque en este ejemplo no se explica. En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenProvider` para devolver el proveedor de tokens personalizado SAML cuando los requisitos de tokens pasados indican que se solicita el token SAML. Si la clase (vea el paso 3) de credenciales del cliente no ha especificado una aserción, el administrador de tokens de seguridad crea una instancia adecuada.

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

3. Escribir una credencial de cliente personalizada.

     Se usa una clase de credenciales de cliente para representar las credenciales que se configuran para el proxy de cliente y crear un administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y un serializador de tokens.

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

4. Configure el cliente para utilizar la credencial del cliente personalizada.

     Para que el cliente pueda utilizar la credencial de cliente personalizada, el ejemplo elimina la clase de credencial de cliente predeterminada y proporciona la nueva.

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

 En el servicio, las notificaciones asociadas al llamador se muestran. Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de cliente para cerrar el cliente.

## <a name="setup-batch-file"></a>Instalar el archivo por lotes

 El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con el certificado pertinente para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado de servidor. Este archivo por lotes debe modificarse para que funcione en varios equipos o en un escenario sin hospedaje.

 A continuación, se proporciona una breve descripción de las diferentes secciones de los archivos por lotes de manera que se puedan modificar para ejecutarse con la configuración adecuada.

- Crear el certificado de servidor:

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar. La variable `%SERVER_NAME%`especifica el nombre del servidor. Cambie esta variable para especificar su propio nombre de servidor. El valor predeterminado en este archivo por lotes es el host local.

     El certificado se almacena en el almacén My (Personal), en la ubicación de almacenamiento LocalMachine.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del servidor en el almacén de certificados de confianza de cliente:

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado de cliente con el certificado de servidor.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople
    ```

- Crear el certificado de emisor.

     Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de emisor que se va a usar. La variable `%USER_NAME%` especifica el nombre del emisor. Cambie esta variable para especificar el nombre del emisor. El valor predeterminado en este archivo por lotes es Alice.

     El certificado está almacenado en My store en la ubicación del almacén CurrentUser.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- Instalar el certificado del emisor en el almacén de certificados de confianza del servidor.

     Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente. Este paso es necesario porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe. Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado del servidor con el certificado de emisor.

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a>Para configurar y compilar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

> [!NOTE]
> Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.

#### <a name="to-run-the-sample-on-the-same-computer"></a>Para ejecutar el ejemplo en el mismo equipo

1. Ejecute Setup.bat desde la carpeta de instalación del ejemplo en un símbolo del sistema de Visual Studio 2012 y ejecute con privilegios de administrador. De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.

    > [!NOTE]
    > El archivo por lotes Setup.bat está diseñado para ejecutarse desde un símbolo del sistema de Visual Studio 2012. La variable de entorno PATH establecida en el símbolo del sistema de Visual Studio 2012 apunta al directorio que contiene los archivos ejecutables requeridos por el script Setup.bat.  
  
2. Inicie Service.exe desde \service\bin.  
  
3. Inicie Client.exe desde \client\bin. La actividad del cliente se muestra en la aplicación de consola del cliente.  
  
4. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1. Cree un directorio en el equipo del servicio para los binarios del servicio.  
  
2. Copie los archivos de programa del servicio en el directorio del servicio en el equipo de servicio. Copie también los archivos Setup.bat y Cleanup.bat en el equipo del servicio.  
  
3. Debe tener un certificado de servidor con el nombre del sujeto que contiene el nombre de dominio completo del equipo. El archivo Service.exe.config debe actualizarse para reflejar este nuevo nombre de certificado. Puede crear el certificado de servidor modificando el archivo por lotes Setup.bat. Tenga en cuenta que el archivo de setup.bat se debe ejecutar en una ventana Símbolo del sistema para desarrolladores para Visual Studio abierta con privilegios de administrador. Debe establecer la variable `%SERVER_NAME%` en el nombre de host completo del equipo que se utiliza para hospedar el servicio.  
  
4. Copie el certificado de servidor en el almacén CurrentUser-TrustedPeople del cliente. Este paso no es necesario cuando el certificado de servidor procede de un emisor de confianza para el cliente.  
  
5. En el archivo Service.exe.config situado en el equipo del servicio, cambie el valor de la dirección base para especificar un nombre de equipo completo en lugar del host local.  
  
6. En el equipo del servicio, ejecute Service.exe desde un símbolo del sistema.  
  
7. Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
8. En el archivo Client.exe.config del equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.  
  
9. En el equipo cliente, inicie `Client.exe` desde una ventana de símbolo del sistema.  
  
10. Si el cliente y el servicio no pueden comunicarse, vea [sugerencias para la solución de problemas de ejemplos de WCF](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Para realizar una limpieza después de ejecutar el ejemplo  
  
1. Ejecute Cleanup.bat en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.
