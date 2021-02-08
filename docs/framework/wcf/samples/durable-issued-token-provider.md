---
description: 'Más información sobre: proveedor de tokens emitidos durable'
title: Proveedor de token emitido duradero
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: dfde4efa961704659d9d1de6010b16616467a779
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793277"
---
# <a name="durable-issued-token-provider"></a><span data-ttu-id="87290-103">Proveedor de token emitido duradero</span><span class="sxs-lookup"><span data-stu-id="87290-103">Durable Issued Token Provider</span></span>

<span data-ttu-id="87290-104">Este ejemplo muestra cómo implementar un proveedor personalizado de tokens emitidos por el cliente.</span><span class="sxs-lookup"><span data-stu-id="87290-104">This sample demonstrates how to implement a custom client issued token provider.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="87290-105">Debate</span><span class="sxs-lookup"><span data-stu-id="87290-105">Discussion</span></span>  

 <span data-ttu-id="87290-106">Un proveedor de tokens en Windows Communication Foundation (WCF) se usa para proporcionar credenciales a la infraestructura de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87290-106">A token provider in Windows Communication Foundation (WCF) is used to supply credentials to the security infrastructure.</span></span> <span data-ttu-id="87290-107">En general, el proveedor de tokens examina el destino y emite las credenciales adecuadas de manera que la infraestructura de seguridad pueda proteger el mensaje.</span><span class="sxs-lookup"><span data-stu-id="87290-107">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="87290-108">WCF se suministra con un proveedor de tokens de CardSpace.</span><span class="sxs-lookup"><span data-stu-id="87290-108">WCF ships with a CardSpace token provider.</span></span> <span data-ttu-id="87290-109">Los proveedores de tokens personalizados son útiles en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="87290-109">Custom token providers are useful in the following cases:</span></span>  
  
- <span data-ttu-id="87290-110">Si tiene un almacén de credenciales con el que el proveedor de tokens integrado no puede funcionar.</span><span class="sxs-lookup"><span data-stu-id="87290-110">If you have a credential store that the built-in token provider cannot operate with.</span></span>  
  
- <span data-ttu-id="87290-111">Si desea proporcionar su propio mecanismo personalizado para transformar las credenciales desde el punto en el que el usuario proporciona detalles cuando el cliente de WCF usa las credenciales.</span><span class="sxs-lookup"><span data-stu-id="87290-111">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client uses the credentials.</span></span>  
  
- <span data-ttu-id="87290-112">Si está creando un token personalizado.</span><span class="sxs-lookup"><span data-stu-id="87290-112">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="87290-113">Este ejemplo muestra cómo crear un proveedor de tokens personalizado que almacena en memoria caché los tokens emitidos por un servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="87290-113">This sample shows how to build a custom token provider that caches tokens issued by a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="87290-114">En resumen, este ejemplo muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87290-114">To summarize, this sample demonstrates the following:</span></span>  
  
- <span data-ttu-id="87290-115">Cómo se puede configurar un cliente con un proveedor de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="87290-115">How a client can be configured with a custom token provider.</span></span>  
  
- <span data-ttu-id="87290-116">Cómo se pueden almacenar en caché y proporcionar los tokens emitidos al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="87290-116">How issued tokens can be cached and provided to the WCF client.</span></span>  
  
- <span data-ttu-id="87290-117">Cómo el cliente autentica el servidor usando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="87290-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="87290-118">Este ejemplo está compuesto de un programa de consola de cliente (Client.exe), un programa de consola de servicio de token de seguridad (Securitytokenservice.exe) y un programa de consola de servicio (Service.exe).</span><span class="sxs-lookup"><span data-stu-id="87290-118">This sample consists of a client console program (Client.exe), a security token service console program (Securitytokenservice.exe) and a service console program (Service.exe).</span></span> <span data-ttu-id="87290-119">El servicio implementa un contrato que define un modelo de comunicación de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="87290-119">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="87290-120">La interfaz `ICalculator`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato.</span><span class="sxs-lookup"><span data-stu-id="87290-120">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="87290-121">El cliente obtiene un token de seguridad del servicio de token de seguridad (STS) y realiza las solicitudes sincrónicas al servicio para una operación matemática determinada y el servicio responde con el resultado.</span><span class="sxs-lookup"><span data-stu-id="87290-121">The client gets a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation and the service replies with the result.</span></span> <span data-ttu-id="87290-122">La actividad del cliente es visible en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="87290-122">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87290-123">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="87290-123">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="87290-124">Este ejemplo expone el contrato de ICalculator mediante [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="87290-124">This sample exposes the ICalculator contract using the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="87290-125">La configuración de este enlace en el cliente se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="87290-125">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuer address="http://localhost:8000/sts/windows"
                  binding="wsHttpBinding" />
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="87290-126">En el elemento `security` de `wsFederationHttpBinding`, el valor `mode` configura qué modo de seguridad debería utilizarse.</span><span class="sxs-lookup"><span data-stu-id="87290-126">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="87290-127">En este ejemplo, se utiliza la seguridad de los mensajes, que es por lo que se especifica el elemento `message` de `wsFederationHttpBinding` dentro del elemento `security` de `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="87290-127">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="87290-128">El elemento `issuer` de `wsFederationHttpBinding` que se encuentra dentro del elemento `message` de `wsFederationHttpBinding` especifica la dirección y el enlace para el Servicio de token de seguridad que emite un token de seguridad para el cliente, de manera que el cliente pueda autenticarlo con el servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="87290-128">The `issuer` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and binding for the Security Token Service that issues a security token to the client so that the client can authenticate to the Calculator service.</span></span>  
  
 <span data-ttu-id="87290-129">La configuración de este enlace en el servicio se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="87290-129">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuerMetadata address="http://localhost:8000/sts/mex">
            <identity>
              <certificateReference storeLocation="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType="FindBySubjectDistinguishedName"
                                    findValue="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="87290-130">En el elemento `security` de `wsFederationHttpBinding`, el valor `mode` configura qué modo de seguridad debería utilizarse.</span><span class="sxs-lookup"><span data-stu-id="87290-130">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="87290-131">En este ejemplo, se utiliza la seguridad de los mensajes, que es por lo que se especifica el elemento `message` de `wsFederationHttpBinding` dentro del elemento `security` de `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="87290-131">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="87290-132">El elemento `issuerMetadata` de `wsFederationHttpBinding` dentro del elemento `message` de `wsFederationHttpBinding` especifica la dirección e identidad de un punto de conexión que se puede utilizar para recuperar los metadatos para el Servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87290-132">The `issuerMetadata` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and identity for an endpoint that can be used to retrieve metadata for the Security Token Service.</span></span>  
  
 <span data-ttu-id="87290-133">El comportamiento para el servicio se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="87290-133">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behavior name="ServiceBehavior">
  <serviceDebug includeExceptionDetailInFaults="true" />
  <serviceMetadata httpGetEnabled="true" />
  <serviceCredentials>
    <issuedTokenAuthentication>
      <knownCertificates>
        <add storeLocation="LocalMachine"
              storeName="TrustedPeople"
              x509FindType="FindBySubjectDistinguishedName"
              findValue="CN=STS" />
      </knownCertificates>
    </issuedTokenAuthentication>
    <serviceCertificate storeLocation="LocalMachine"
                        storeName="My"
                        x509FindType="FindBySubjectDistinguishedName"
                        findValue="CN=localhost" />
  </serviceCredentials>
</behavior>  
```  
  
 <span data-ttu-id="87290-134">El elemento `issuedTokenAuthentication` dentro del elemento `serviceCredentials` permite al servicio especificar las restricciones en los tokens y permite a los clientes presentarse durante la autenticación.</span><span class="sxs-lookup"><span data-stu-id="87290-134">The `issuedTokenAuthentication` element inside the `serviceCredentials` element allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="87290-135">Esta configuración especifica que el servicio acepta los tokens firmados por un certificado cuyo nombre de asunto sea CN=STS.</span><span class="sxs-lookup"><span data-stu-id="87290-135">This configuration specifies that tokens signed by a certificate whose Subject Name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="87290-136">El Servicio de token de seguridad expone un solo punto de conexión con el wsHttpBinding estándar.</span><span class="sxs-lookup"><span data-stu-id="87290-136">The Security Token Service exposes a single endpoint using the standard wsHttpBinding.</span></span> <span data-ttu-id="87290-137">El Servicio de token de seguridad responde a las solicitudes de tokens de los clientes y, siempre que el cliente se autentique utilizando una cuenta de Windows, emite un token que contiene el nombre de usuario del cliente como una notificación en el token emitido.</span><span class="sxs-lookup"><span data-stu-id="87290-137">The Security Token Service responds to request from clients for tokens and, provided the client authenticates using a Windows account, issues a token that contains the client's user name as a claim in the issued token.</span></span> <span data-ttu-id="87290-138">Como parte de la creación del token, el servicio de token de seguridad firma el token usando la clave privada asociada con el certificado de CN=STS.</span><span class="sxs-lookup"><span data-stu-id="87290-138">As part of creating the token, the Security Token Service signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="87290-139">Además, crea una clave simétrica y la cifra utilizando la clave pública asociada con el certificado de CN=localhost.</span><span class="sxs-lookup"><span data-stu-id="87290-139">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="87290-140">Para devolver el token al cliente, el servicio de token de seguridad devuelve también la clave simétrica.</span><span class="sxs-lookup"><span data-stu-id="87290-140">In returning the token to the client, the Security Token Service also returns the symmetric key.</span></span> <span data-ttu-id="87290-141">El cliente presenta el token emitido al servicio de la calculadora y demuestra que conoce la clave simétrica firmando el mensaje con esa clave.</span><span class="sxs-lookup"><span data-stu-id="87290-141">The client presents the issued token to the Calculator service, and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
## <a name="custom-client-credentials-and-token-provider"></a><span data-ttu-id="87290-142">Credenciales de cliente personalizadas y proveedor de tokens</span><span class="sxs-lookup"><span data-stu-id="87290-142">Custom Client Credentials and Token Provider</span></span>  

 <span data-ttu-id="87290-143">En los pasos siguientes se muestra cómo desarrollar un proveedor de tokens personalizado que almacena en memoria caché los tokens emitidos y los integra con WCF: Security.</span><span class="sxs-lookup"><span data-stu-id="87290-143">The following steps show how to develop a custom token provider that caches issued tokens and integrate it with WCF: security.</span></span>  
  
### <a name="to-develop-a-custom-token-provider"></a><span data-ttu-id="87290-144">Para desarrollar un proveedor de tokens personalizado</span><span class="sxs-lookup"><span data-stu-id="87290-144">To develop a custom token provider</span></span>  
  
1. <span data-ttu-id="87290-145">Escriba un proveedor de tokens personalizado.</span><span class="sxs-lookup"><span data-stu-id="87290-145">Write a custom token provider.</span></span>  
  
     <span data-ttu-id="87290-146">El ejemplo implementa un proveedor de tokens personalizado que devuelve un token de seguridad recuperado de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="87290-146">The sample implements a custom token provider that returns a security token retrieved from a cache.</span></span>  
  
     <span data-ttu-id="87290-147">Para realizar esta tarea, el proveedor de tokens personalizado deriva la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider> e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="87290-147">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="87290-148">Este método intenta recibir un token de la memoria caché o si un token no se puede encontrar en la caché, se recupera un token del proveedor subyacente y, a continuación, lo almacena en la caché.</span><span class="sxs-lookup"><span data-stu-id="87290-148">This method tries to get a token from the cache, or if a token cannot be found in the cache, retrieves a token from the underlying provider and then caches that token.</span></span> <span data-ttu-id="87290-149">En ambos casos, el método devuelve un `SecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="87290-149">In both cases the method returns a `SecurityToken`.</span></span>  
  
    ```csharp  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
      GenericXmlSecurityToken token;  
      if (!this.cache.TryGetToken(target, issuer, out token))  
      {  
        token = (GenericXmlSecurityToken) this.innerTokenProvider.GetToken(timeout);  
        this.cache.AddToken(token, target, issuer);  
      }  
      return token;  
    }  
    ```  
  
2. <span data-ttu-id="87290-150">Escribir el administrador de tokens de seguridad personalizado.</span><span class="sxs-lookup"><span data-stu-id="87290-150">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="87290-151">El <xref:System.IdentityModel.Selectors.SecurityTokenManager> se utiliza para crear un <xref:System.IdentityModel.Selectors.SecurityTokenProvider> para el <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> concreto que se pasa en el método `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="87290-151">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for a specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in the `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="87290-152">Un administrador de tokens de seguridad también se utiliza para crear autenticadores y serializadores de tokens, aunque en este ejemplo no se explica.</span><span class="sxs-lookup"><span data-stu-id="87290-152">Security token manager is also used to create token authenticators and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="87290-153">En este ejemplo, el administrador de tokens de seguridad personalizado hereda de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> e invalida el método `CreateSecurityTokenProvider` para devolver el proveedor de tokens personalizado cuando los requisitos de tokens pasados indican que se solicita un token emitido.</span><span class="sxs-lookup"><span data-stu-id="87290-153">In this sample, the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom token provider when the passed token requirements indicate that an issued token is requested.</span></span>  
  
    ```csharp
    class DurableIssuedTokenClientCredentialsTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentialsTokenManager ( DurableIssuedTokenClientCredentials creds ): base(creds)  
      {  
        this.cache = creds.IssuedTokenCache;  
      }  
  
      public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
      {  
        if (IsIssuedSecurityTokenRequirement(tokenRequirement))  
        {  
          return new DurableIssuedSecurityTokenProvider ((IssuedSecurityTokenProvider)base.CreateSecurityTokenProvider( tokenRequirement), this.cache);  
        }  
        else
        {  
          return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
      }  
    }  
    ```  
  
3. <span data-ttu-id="87290-154">Escribir una credencial de cliente personalizada.</span><span class="sxs-lookup"><span data-stu-id="87290-154">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="87290-155">Se usa una clase de credenciales de cliente para representar las credenciales que se configuran para el proxy de cliente y crea el administrador de tokens de seguridad que se utiliza para obtener autenticadores, proveedores y serializadores de tokens.</span><span class="sxs-lookup"><span data-stu-id="87290-155">A client credentials class is used to represent the credentials that are configured for the client proxy and creates the security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>  
  
    ```csharp
    public class DurableIssuedTokenClientCredentials : ClientCredentials  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentials() : base()  
      {  
      }  
  
      DurableIssuedTokenClientCredentials ( DurableIssuedTokenClientCredentials other) : base(other)  
      {  
        this.cache = other.cache;  
      }  
  
      public IssuedTokenCache IssuedTokenCache  
      {  
        get  
        {  
          return this.cache;  
        }  
        set  
        {  
          this.cache = value;  
        }  
      }  
  
      protected override ClientCredentials CloneCore()  
      {  
        return new DurableIssuedTokenClientCredentials(this);  
      }  
  
      public override SecurityTokenManager CreateSecurityTokenManager()  
      {  
        return new DurableIssuedTokenClientCredentialsTokenManager ((DurableIssuedTokenClientCredentials)this.Clone());  
      }  
    }  
    ```  
  
4. <span data-ttu-id="87290-156">Implementar la caché del token.</span><span class="sxs-lookup"><span data-stu-id="87290-156">Implement the token cache.</span></span> <span data-ttu-id="87290-157">La implementación del ejemplo utiliza una clase base abstracta a través de la cual los consumidores de una caché de token determinada interactúan con la caché.</span><span class="sxs-lookup"><span data-stu-id="87290-157">The sample implementation uses an abstract base class through which consumers of a given token cache interact with the cache.</span></span>  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     <span data-ttu-id="87290-158">Para que el cliente utilice la credencial de cliente personalizada, el ejemplo elimina la clase de credencial de cliente predeterminada y proporciona la nueva.</span><span class="sxs-lookup"><span data-stu-id="87290-158">For the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a><span data-ttu-id="87290-159">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="87290-159">Running the sample</span></span>  

 <span data-ttu-id="87290-160">Consulte las instrucciones siguientes para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="87290-160">See the following instructions to run the sample.</span></span> <span data-ttu-id="87290-161">Al ejecutar el ejemplo, la solicitud para el token de seguridad se muestra en la ventana de la consola del servicio de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="87290-161">When you run the sample, the request for the security token is shown in the Security Token Service console window.</span></span> <span data-ttu-id="87290-162">Las solicitudes y respuestas de la operación se muestran en las ventanas de la consola del cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="87290-162">The operation requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="87290-163">Presione ENTRAR en cualquiera de las ventanas de la consola para cerrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="87290-163">Press ENTER in any of the console windows to shut down the application.</span></span>  
  
## <a name="the-setupcmd-batch-file"></a><span data-ttu-id="87290-164">Archivo por lotes Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="87290-164">The Setup.cmd Batch File</span></span>  

 <span data-ttu-id="87290-165">El archivo por lotes de Setup.cmd incluido con este ejemplo le permite configurar el servidor y servicio de token de seguridad con certificados pertinentes para ejecutar una aplicación autohospedada.</span><span class="sxs-lookup"><span data-stu-id="87290-165">The Setup.cmd batch file included with this sample allows you to configure the server and security token service with relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="87290-166">El archivo por lotes crea dos certificados en el almacén de certificados CurrentUser/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="87290-166">The batch file creates two certificates both in the CurrentUser/TrustedPeople certificate store.</span></span> <span data-ttu-id="87290-167">El primer certificado tiene un nombre de asunto CN=STS que utiliza el servicio de token de seguridad para firmar los tokens de seguridad que emite el cliente.</span><span class="sxs-lookup"><span data-stu-id="87290-167">The first certificate has a subject name of CN=STS and is used by the Security Token Service to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="87290-168">El segundo certificado tiene un nombre de asunto de CN=localhost que usa el servicio de token de seguridad para cifrar un secreto para que el servicio lo pueda descifrar.</span><span class="sxs-lookup"><span data-stu-id="87290-168">The second certificate has a subject name of CN=localhost and is used by the Security Token Service to encrypt a secret so that the service can decrypt it.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="87290-169">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="87290-169">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="87290-170">Ejecute el archivo Setup.cmd para crear los certificados necesarios.</span><span class="sxs-lookup"><span data-stu-id="87290-170">Run the Setup.cmd file to create the required certificates.</span></span>  
  
2. <span data-ttu-id="87290-171">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87290-171">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span> <span data-ttu-id="87290-172">Asegúrese de que todos los proyectos en la solución están compilados (compartido, RSTRSTR, servicio, SecurityTokenService y cliente).</span><span class="sxs-lookup"><span data-stu-id="87290-172">Ensure that all the projects in the solution are built (Shared, RSTRSTR, Service, SecurityTokenService, and Client).</span></span>  
  
3. <span data-ttu-id="87290-173">Asegúrese de que tanto el archivo Service.exe como el archivo SecurityTokenService.exe se ejecutan con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="87290-173">Ensure that Service.exe and SecurityTokenService.exe are both running with administrator privileges.</span></span>  
  
4. <span data-ttu-id="87290-174">Ejecute Client.exe.</span><span class="sxs-lookup"><span data-stu-id="87290-174">Run Client.exe.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="87290-175">Para realizar una limpieza después de ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="87290-175">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="87290-176">Ejecute Cleanup.cmd en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="87290-176">Run Cleanup.cmd in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="87290-177">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="87290-177">The samples may already be installed on your machine.</span></span> <span data-ttu-id="87290-178">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="87290-178">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="87290-179">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="87290-179">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="87290-180">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="87290-180">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
